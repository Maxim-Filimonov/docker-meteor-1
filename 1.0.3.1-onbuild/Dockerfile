FROM danieldent/meteor:1.0.3.1
ONBUILD COPY . /opt/src
ONBUILD WORKDIR /opt/src
ONBUILD RUN meteor build .. --directory \
    && cd ../bundle/programs/server \
    && npm install \
    && rm -rf /opt/src
ONBUILD WORKDIR /opt/bundle
ONBUILD USER nobody
ONBUILD ENV PORT 3000
CMD ["/usr/local/bin/node", "main.js"]