# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.137.0/containers/go/.devcontainer/base.Dockerfile
ARG VARIANT="1"
FROM mcr.microsoft.com/vscode/devcontainers/go:0-${VARIANT}
ENV GOPROXY=http://goproxy.sas.com:3000
ENV GONOSUMDB=*.sas.com

# [Optional] Install a version of Node.js using nvm for front end dev
ARG INSTALL_NODE="true"
ARG NODE_VERSION="lts/*"
RUN if [ "${INSTALL_NODE}" = "true" ]; then su vscode -c "source /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends file tree vim

# [Optional] Uncomment this section to add vim settings to .vimrc
RUN echo "set ai"                 > /home/vscode/.vimrc \
    && echo "set sw=2"           >> /home/vscode/.vimrc \
    && echo "set et"             >> /home/vscode/.vimrc \
    && echo "syntax on"          >> /home/vscode/.vimrc \
    && echo "colorscheme murphy" >> /home/vscode/.vimrc 

# [Optional] Uncomment the next line to use go get to install anything else you need
# RUN go get -x <your-dependency-or-tool>

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1
