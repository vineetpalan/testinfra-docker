# testinfra-docker

testinfra-docker is a alpine based docker image, that has testinfra along with paramiko and requests modules.


## Building

```bash
docker build -t vineetpalan/testinfra-docker .
```

## Running an interactive test

```bash
docker run --rm -it vineetpalan/testinfra-docker
```

## Testing testinfra project

```bash
docker run --rm -t \
-v /path/to/your-testinfra-project:/project \
vineetpalan/testinfra-docker pytest test_file_name
```
* `Eg.
docker run --rm -t -v $PWD/test:/test -w /test vineetpalan/testinfra-docker pytest test.py
`

## Use it with CI/CD like Gitlab

```bash

test:
  image: vineetpalan/testinfra-docker
  stage: test
  only:
    - master
  script:
    - sh run_tests.sh

```
