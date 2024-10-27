FROM nginx:latest
LABEL maintainer="Caglar Gokcen @caglargokcen"
ENV USER="MVP"
ARG VERSION
RUN apt update && apt install -y curl htop wget
WORKDIR /temporary
ADD https://www.python.org/ftp/python/3.9.9/Python-3.9.9.tgz .
WORKDIR /usr/share/nginx/html
COPY web/${VERSION} .
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 CMD curl -f http://localhost/ || exit 1
CMD [ "./script.sh" ]