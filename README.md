docker-s3-volume
==============

Creates a Docker container that is restored and backed up to a directory on s3. You could use this to run short lived processes that work with and persist data to and from S3.

Usage:

```
docker run -it --rm \
  -e ACCESS_KEY=... -e SECRET_KEY=... whatupdave/s3-volume s3://<BUCKET>/<PATH>
```

This pulls down the contents of a directory on S3. If the container is stopped or sent a `USR1` signal, it will backup the modified local contents to S3.