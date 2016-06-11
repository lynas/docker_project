#[Using Docker ubuntu latest]
FROM ubuntu:latest
MAINTAINER szlynas@gmail.com



#[ installing necessary software]
RUN apt-get update
RUN apt-get install -y wget software-properties-common vim zsh git curl unzip ruby-full
RUN apt-get install -y rubygems
RUN gem install rhc




#[Setting up working directory]
WORKDIR /root




#[Setup JAVA]
RUN wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u65-b17/jdk-8u65-linux-x64.tar.gz
RUN tar -xvf jdk-8u65-linux-x64.tar.gz
RUN update-alternatives --install /usr/bin/java java /root/jdk1.8.0_65/bin/java 100
RUN update-alternatives --install /usr/bin/javac javac /root/jdk1.8.0_65/bin/javac 100
RUN update-alternatives --install /usr/bin/javaws javaws /root/jdk1.8.0_65/bin/javaws 100
RUN java -version
RUN rm jdk-8u65-linux-x64.tar.gz




#[Setup Maven]
RUN wget http://www.eu.apache.org/dist/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
RUN tar -xvf apache-maven-3.3.9-bin.tar.gz
env PATH /root/apache-maven-3.3.9/bin:$PATH
RUN mvn -v
RUN rm apache-maven-3.3.9-bin.tar.gz




#[Setup Ant]
RUN wget http://www-us.apache.org/dist//ant/binaries/apache-ant-1.9.7-bin.tar.gz
RUN tar -xvf apache-ant-1.9.7-bin.tar.gz
env PATH /root/apache-ant-1.9.7/bin:$PATH
RUN rm apache-ant-1.9.7-bin.tar.gz



#[Setup gradle]
RUN wget https://downloads.gradle.org/distributions/gradle-2.13-bin.zip
RUN unzip gradle-2.13-bin.zip
env PATH /root/gradle-2.13/bin:$PATH
RUN rm gradle-2.13-bin.zip








#[Installing Oh-My-Zsh]

RUN curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh > install.sh

RUN bash install.sh




