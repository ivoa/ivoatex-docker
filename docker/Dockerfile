#
# <meta:header>
#   <meta:licence>
#     Copyright (c) 2015, ROE (http://www.roe.ac.uk/)
#
#     This information is free software: you can redistribute it and/or modify
#     it under the terms of the GNU General Public License as published by
#     the Free Software Foundation, either version 3 of the License, or
#     (at your option) any later version.
#
#     This information is distributed in the hope that it will be useful,
#     but WITHOUT ANY WARRANTY; without even the implied warranty of
#     MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#     GNU General Public License for more details.
#
#     You should have received a copy of the GNU General Public License
#     along with this program.  If not, see <http://www.gnu.org/licenses/>.
#   </meta:licence>
# </meta:header>
#

#
# Docker container to run the IvoaTex build environment.

ARG osversion

FROM ${osversion}
MAINTAINER Dave Morris <docker-admin@metagrid.co.uk>

ARG builddate
ARG buildtime

LABEL maintainer="Dave Morris <docker-admin@metagrid.co.uk>"
LABEL builddate="${builddate}"
LABEL buildtime="${buildtime}"
LABEL gitrepo="https://github.com/ivoa/ivoa"

#
# Disable interactive install.
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y \
        texlive-latex-extra \
        texlive-bibtex-extra \
        build-essential \
        librsvg2-bin \
        imagemagick \
        ghostscript \
        xsltproc \
        cm-super \
        zip

#
# Label working directory as a data volume.
VOLUME  /document
WORKDIR /document


