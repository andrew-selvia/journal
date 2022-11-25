# Parameterize a Dockerfile

In order to honor the [Don't Repeat Yourself (DRY) principle](https://en.wikipedia.org/wiki/Don't_repeat_yourself) within a Dockerfile, you should understand the use cases for `ARG`, `ENV`, and `env_file`s. Here are some high-level principles to follow:

* `ARG`: build-time parameter
* `ENV`: run-time parameter
* `env_file`: a set of run-time parameters not hard-coded in the Dockerfile

## Build-time Parameters

If you need to parameterize your build (i.e. supplying the base image as a parameter, using different compiler flags in development & production, etc.), you should leverage `ARG`s. In your Dockerfile, you can declare an `ARG` (with an optional default value); then, if you need to access its value at runtime, you can store it in an `ENV`. For example:

```dockerfile
ARG arg=default
ENV env=$arg
```

When you build your image, you can supply values for the declared `ARG`s via the `--build-arg` flag:

```shell script
docker build --build-arg arg=custom .
```

## Run-time Parameters

If you just need to parameterize your image at runtime, you can leverage `ENV` or an `env_file` if you have many parameters to inject.

## References

For more detailed explanation of these techniques, refer to these articles:

* [*Setting Default Docker Environment Variables During Image Build*](https://vsupalov.com/docker-build-time-env-values/): A short introduction to using `ARG` for build parameterization
* [*Docker ARG vs. ENV*](https://vsupalov.com/docker-arg-vs-env/): A detailed comparison of `ARG` & `ENV` mechanics
* [*Docker ARG, ENV and .env - A Complete Guide*](https://vsupalov.com/docker-arg-env-variable-guide/): A truly *complete* guide to the use cases for each type of parameterization
* [*Pass Docker Environment Variables During the Image Build*](https://vsupalov.com/docker-build-pass-environment-variables/): Additional documentation about build parameterization strategies, including this important warning:

    > Remember to be cautious when considering ARG and ENV for secrets, as they are [not safe](https://vsupalov.com/build-docker-image-clone-private-repo-ssh-key/).
