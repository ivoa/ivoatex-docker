# ivoatex
Docker container to build [IvoaTex](http://www.ivoa.net/documents/Notes/IVOATex/index.html) documents.

To run the container :

    docker run -it \
        -e "useruid=$(id -u)" \
        -v "$(pwd):/var/local/texdata" \
        ivoa/ivoatex

To build the document :

    pushd /var/local/texdata

        make clean
        make biblio
        make

