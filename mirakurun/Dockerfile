FROM chinachu/mirakurun

RUN apt update
RUN apt install -y git autoconf make cmake

WORKDIR /usr/local/src/
RUN git clone https://github.com/stz2012/libarib25.git
WORKDIR /usr/local/src/libarib25
RUN cmake - DLDCONFIG_EXECUTABLE=IGNORE ./ && \
    make && \
    make install

WORKDIR /usr/local/src/
RUN git clone https://github.com/stz2012/recpt1.git
WORKDIR /usr/local/src/recpt1/recpt1

RUN ./autogen.sh
RUN ./configure --enable-b25
RUN make
RUN make install
WORKDIR /app
