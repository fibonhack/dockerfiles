# CVC5

> https://hub.docker.com/repository/docker/fibonhack/cvc5

### What

It is a super duper faster z3
* https://github.com/cvc5/cvc5

Converting z3 scripts to cvc5 is easy with the pythonic api;
```
- import z3
+ import cvc5_pythonic_api as z3
```

### How to run a prebuilt image

`docker run --name cvc5 --rm -v $(pwd)/:/ctf/work -d fibonhack/cvc5:latest`

