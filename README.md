# ivoatex
Docker container to build [IvoaTex](http://www.ivoa.net/documents/Notes/IVOATex/index.html) documents.

Based on [metagrid/notroot-debian](/u/metagrid/notroot-debian).

To run the container :

    docker run -it \
        -e "useruid=$(id -u)" \
        -v "${document}:/var/local/texdata" \
        ivoa/ivoatex

To build the document :

    pushd /var/local/texdata

        make clean
        make biblio
        make

