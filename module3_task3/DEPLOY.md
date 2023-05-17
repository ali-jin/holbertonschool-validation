# Manual deployment

## Preparing a Release

To deploy a new version of the application, run this:

```bash
git tag 1.0.0
git push origin 1.0.0
```

## Deploying a Release

An archive is a single file that contains a collection of other files and/or directories.
Our Archive is named `awesome-api.zip`
To unarchive it, run the command unzip files.zip

```bash
unzip awesome-api.zip
```

### What are the commands to start and stop the application?

To start the application, run the command make build
To stop the application, run the command make stop

### How to customize where the application logs are written?

Run the command make run

### How to “quickly” verify that the application is running (healthcheck)?

`curl http://localhost:9999/health`
