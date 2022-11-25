# Google Cloud Storage

[Google Cloud Storage](https://cloud.google.com/storage) (GCS) is an object storage service provided by Google Cloud. You can use it to store a hierarchical tree of files. The documentation on [*Hosting a Static Website*](https://cloud.google.com/storage/docs/hosting-static-website) describes "how to configure a Cloud Storage bucket to host a static website"; it is a quick introduction to the core concepts. When you're ready for more details, you can read all about GCS [APIs](https://cloud.google.com/storage/docs/apis).

## `gsutil`

When you need to build GCS into your automation, you can leverage [`gsutil`](https://cloud.google.com/storage/docs/gsutil): "a Python application that lets you access Cloud Storage from the command line".

The list below highlights some important `gsutil` commands you may utilize:
 
* [`rsync`](https://cloud.google.com/storage/docs/gsutil/commands/rsync): Synchronize content of two buckets/directories
* [`rm`](https://cloud.google.com/storage/docs/gsutil/commands/rm): Remove objects

## JSON API

GCS also offers a [JSON API](https://cloud.google.com/storage/docs/json_api/v1) which is more appropriate for integration into you source code.

The list below highlights some import documentation of the JSON API:

* [*Using the Cloud Storage JSON API*](https://cloud.google.com/storage/docs/json_api/v1/how-tos)
* [API Reference: Buckets](https://cloud.google.com/storage/docs/json_api/v1#buckets)
* [*Authorize Requests*](https://cloud.google.com/storage/docs/json_api/v1/how-tos/authorizing)
* [Objects:get](https://cloud.google.com/storage/docs/json_api/v1/objects/get)
