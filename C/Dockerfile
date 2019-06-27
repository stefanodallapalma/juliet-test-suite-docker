FROM alpine:latest
USER root

RUN apk add --update \
    gcc \
    make \  
    python3\
    unzip \
    wget

RUN mkdir -p /juliet/ \
    && mkdir -p /juliet/c/

WORKDIR /juliet/c/

# Download Juliet Test Suite for C
RUN wget https://samate.nist.gov/SARD/testsuites/juliet/Juliet_Test_Suite_v1.3_for_C_Cpp.zip \
    && unzip Juliet_Test_Suite_v1.3_for_C_Cpp.zip -d . 

RUN make C