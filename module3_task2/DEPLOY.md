# Manual deployment

## What is in the archive and how to unarchive it?

An archive is a single file that contains a collection of other files and/or directories.
To unarchive it, run the command unzip files.zip

## What are the commands to start and stop the application?

To start the application, run the command make build
To stop the application, run the command make stop

## How to customize where the application logs are written?

Run the command make run

## How to “quickly” verify that the application is running (healthcheck)?

`curl http://localhost:9999/health`
