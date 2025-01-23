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
FROM docker.io/library/debian:12.9

ARG builddate
ARG buildtime

MAINTAINER Dave Morris <docker-admin@metagrid.co.uk>

LABEL maintainer "Dave Morris <docker-admin@metagrid.co.uk>"
LABEL buildtag   "${buildtag}"
LABEL buildtime  "${buildtime}"
LABEL vendor     "UK SKA Regional Centre (UKSRC)"
LABEL version    "${buildtag}"
LABEL license    "GPL-3.0-or-later"
LABEL org.opencontainers.image.created  "${buildtime}"
LABEL org.opencontainers.image.vendor   "UK SKA Regional Centre (UKSRC)"
LABEL org.opencontainers.image.version  "${buildtag}"
LABEL org.opencontainers.image.licenses "GPL-3.0-or-later"
LABEL org.opencontainers.image.source   "https://github.com/ivoa/ivoatex-docker"
LABEL org.opencontainers.image.authors  "https://github.com/Zarquan"

#
# Disable interactive install.
ENV DEBIAN_FRONTEND noninteractive

#
# Install LaTex tools.
RUN apt-get update && apt-get -yq install \
    build-essential \
    cm-super \
    ghostscript \
    git \
    latexmk \
    librsvg2-bin \
    librsvg2-bin \
    nano \
    pdftk \
    python-is-python3 \
    texlive-latex-extra \
    texlive-bibtex-extra \
    vim \
    xsltproc \
    zip

#
# Label working directory as a data volume.
VOLUME  /document
WORKDIR /document


