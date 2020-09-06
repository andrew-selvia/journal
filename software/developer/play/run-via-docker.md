# Run via Docker

You may find [this shell script](https://github.com/wsargent/play-jdk13-alpine-slim/blob/master/run-docker) helpful when attempting to run a Play app via Docker.

Additionally, [this guide](https://guilhebl.github.io/scala/backend/docker/play/2017/08/23/scala-play-docker-sbt-native-packager-example) includes some critical details about how to:

* Generate a secret key for use in production
* Generate a Docker image via SBT
* Run the Play app via Docker
* Pass the application secret to Play via `docker run`
* Configure the JVM via SBT 
* Configure the app

One particularly critical piece of information you can glean from that article is how to handle the pid file used by Play in production within `build.sbt`:

```sbt
javaOptions in Universal ++= Seq(
  // Since play uses separate pidfile we have to provide it with a proper path name of the pid file must be play.pid
  s"-Dpidfile.path=/opt/docker/${packageName.value}/run/play.pid"
)
```