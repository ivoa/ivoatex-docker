# ivoatex
Docker container to build [IvoaTex](http://www.ivoa.net/documents/Notes/IVOATex/index.html) documents.

We recommend you use [Podman](https://podman.io/) to run IvoaTex as a [rootless-container](https://github.com/containers/podman#rootless).
The advantage is that the user inside the container is automatically mapped to your `uid` on the host, avoiding problems with file ownership.

Using Podman to build a document in the current directory:

    DOC_PATH=$(pwd)

    podman run \
        --rm \
        --tty \
        --interactive \
        --volume "${DOC_PATH:?}:/document:rw,Z" \
        ivoa/ivoatex:latest

Once inside the container, run the following commands to build the document:

    make clean
    make biblio
    make forcetex


To do the same with Docker you need to specify the user `uid` and `gid` so that the resulting documents are owned by your account rather than by root.

    docker run \
        --rm  \
        --tty \
        --interactive \
        --user "$(id -u):$(id -g)" \
        --volume "${DOC_PATH:?}:/document:rw,Z" \
        ivoa/ivoatex:latest

