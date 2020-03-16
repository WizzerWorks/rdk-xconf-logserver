# Alticast Log Server

The Alticast logserver is a simple file server written in the Go Language.
It may be used to upload files to the server and stored to the local file
system. Uploaded files may also be downloaded via the Web UI or a REST API.

## Build Instructions

### Dependencies

1. Ubuntu 18.04 LTS 64-bit platform
2. Git
3. Go Language tools

### Detail

To build the logserver for the Linux Ubuntu 18.04 LTS 64-bit platform,
follow these instructions:

1. Download the source code from the Github repository.
2. Set the GOPATH to the downloaded source code directory:

        ```
        $ cd <project>
        $ export GOPATH=`pwd`
        ```

3. Install the Go gin package:

        ```
        $ go get -u github.com/gin-gonic/gin
        ```

4. Install the Go viper package:

        ```
        $ go get -u github.com/spf13/viper
        ```

5. Build the source:

        ```
        $ cd src
        $ go build -o logserver
        ```

The executable, *logserver*, will be created.

## Run the Executable

To run the logserver, simply

```
$ cd <project>
$ ./logserver &
```

### Smoke Test

To validate that the server is running correctly, use curl:

```
$ curl -X GET http://localhost:8080/ping
```

The JSON message **{"message":"pong"}** will be returned upon success.

## Configuration

The Alticast logserver uses a ***config.yml*** file to configure its behavior.
The configuration file may be located in either the */etc/logserver* or
*$HOME/.logserver* directory.