# Quickstart

<!-- GETTING STARTED -->
## Prerequisites

1. **A computer that's on the public internet to run it on.**  While crunching through video and serving it to viewers can be intensive from the computing side, you can get away with pretty meager resources on a simple setup.  If you don't already have a server to run it on you can get a [Linode](https://www.linode.com/products/nanodes/) instance for $5/mo that runs it fine.  If you worry that you'll be maxing out the bandwidth or transfer limits allotted to you, then utilize [S3 Storage](/docs/s3) very cheaply (or even free for a certain amount) to serve the files instead.

1. [`ffmpeg`](https://ffmpeg.org/download.html) needs to be available on your machine (unless you're using a Docker image, it'll be installed for you in that case.)


There are two quick ways to get up and running, depending on your preference.  One is to simply download the service and run it, and the other is through Docker, if Docker is your thing.

## Options

You can choose between downloading a zip file of Owncast, or using Docker.

### Download and run a release

1. Install [`ffmpeg`](https://ffmpeg.org/download.html) if you haven't.
1. Make a directory to run the service from, and download a release from https://github.com/gabek/owncast/releases into that directory.
1. Unzip the release's archive for linux or macOS: `unzip owncast-linux-x.x.x.zip`.
1. [Edit `config.yaml` as detailed below](#configure).  Specifically your stream key and `ffmpeg` location.
1. Run `./owncast` to start the service.


### Use a Docker image

1. Find the recent version on Docker [by visiting Dockerhub](https://hub.docker.com/repository/registry-1.docker.io/gabekangas/owncast/tags?page=1).
1. `docker pull gabekangas/owncast:x.x.x` replacing x.x.x with the tag
1. Run `docker run -p 8080:8080 -p 1935:1935 -it gabekangas/owncast:x.x.x` to start the service.


---

## Configure

1. Edit `config.yaml` and change the path of ffmpeg to where your copy is.
1. In this default configuration there will be a single video quality available, simply whatever is being sent to the server is being distributed to the viewers.  The video is also going to be distributed from the server running the service in this case.
1. Continue to edit the config file and customize with your own details, links and info.  See [More Configuration](/docs/configuration/) to find additional ways to configure video quality.

## Test
1. Point your broadcasting software at your new server using `rtmp://yourserver/live` and the stream key you set above and start your stream.
1. Access your server in your web browser by visiting `http://yourserver:8080`.


### That's it!
