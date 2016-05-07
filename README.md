# ivoatex
Docker container to build [IvoaTex](http://www.ivoa.net/documents/Notes/IVOATex/index.html) documents.

Run the container in the target document directory:

    docker run -it --rm \
        -e "useruid=$(id -u)" \
        -v "$(pwd):/var/local/texdata" \
        ivoa/ivoatex

Run make inside the container to build the document:

    pushd /var/local/texdata

        make clean
        make biblio
        make

