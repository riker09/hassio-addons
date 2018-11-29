ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8
RUN apk add --no-cache \
    clang \
    g++ \
    gcc-gnat \
    jq \
    libffi-dev \
    libgc++ \
    libgcc \
    make \
    mosquitto \
    mosquitto-clients \
    mosquitto-dev \
    mosquitto-libs \
    openssl-dev \
    py2-pip \
    python2-dev
    
RUN pip install pyaes
RUN pip install pycrypto
RUN apk add --no-cache \
        py-pip \
	python \
	python-dev \
	python3 \
	python3-dev\
 && pip install -U pip \
 && pip3 install -U pip \
 && pip install -U virtualenv

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ] 
