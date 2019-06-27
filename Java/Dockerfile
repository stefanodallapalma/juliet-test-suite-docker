FROM stefadp/jbmc:latest

RUN apk add --update \ 
    apache-ant \
    openjdk8 \
    python3 \
    unzip \
    wget     

ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
ENV PATH="$JAVA_HOME/bin:${PATH}" 

RUN mkdir -p /juliet/ \
    && mkdir -p /juliet/java/

WORKDIR /juliet/java/

# Download Juliet Test Suite for Java
RUN wget https://samate.nist.gov/SARD/testsuites/juliet/Juliet_Test_Suite_v1.3_for_Java.zip \
    && unzip Juliet_Test_Suite_v1.3_for_Java.zip -d . \
    && cd Java \
    #&& sed -i 's/src\\\\testcases/src\/\/testcases/g' run_analysis_example_tool.py \
    && ant 