# ivoatex
Docker container to build [IvoaTex](http://www.ivoa.net/documents/Notes/IVOATex/index.html) documents.

Run the container in the target document directory:

    docker run \
        --rm  \
        --tty \
        --interactive \
        --user "$(id -u):$(id -g)" \
        --volume "$(pwd):/texdata" \
        ivoa/ivoatex:1.2

Run make inside the container to build the document:

    make clean
    make biblio
    make

