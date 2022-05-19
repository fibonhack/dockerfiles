FROM ubuntu:20.04

# Install dependencies
RUN apt update
RUN apt-get update
RUN apt-get install -y cmake 
RUN apt-get install -y \ 
    build-essential \
    ccache \
    libbsd-dev \
    libcln-dev \
    libedit-dev \
    libgmp-dev \
    libtinfo-dev \
    flex \
    libfl-dev \
    flexc++ \
    python3 \ 
    python3-pip \
    git \
    wget \
    curl \
    default-jre

RUN python3 -m pip install --no-cache-dir pexpect setuptools toml
RUN python3 -m pip install --no-cache-dir -q --upgrade pip
RUN python3 -m pip install --no-cache-dir pytest scikit-build
RUN python3 -m pip install --no-cache-dir Cython
RUN python3 -m pip install --no-cache-dir ipython

# Build it
RUN git clone https://github.com/cvc5/cvc5.git 
RUN cd cvc5 && \
    ./configure.sh production --auto-download --python-bindings && \
    cd build && \
    make -j$(nproc) && \
    make install
RUN git clone https://github.com/cvc5/cvc5_pythonic_api.git
RUN cp -r cvc5_pythonic_api/cvc5_pythonic_api /usr/local/lib/python3.8/dist-packages/

CMD ["sleep", "infinity"]