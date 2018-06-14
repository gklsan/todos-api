FROM ruby:2.5

ENV HOME /home/app

EXPOSE 3000

RUN useradd -m -s /bin/bash app

#RUN apt-get update && apt-get install -y ca-certificates build-essential postgresql-client-9.6
RUN apt-get update && apt-get install -y less nano wget telnet nodejs

ENV GEM_HOME /usr/local/bundle
ENV PATH $GEM_HOME/bin:$PATH
RUN gem install bundler \
	&& bundle config --global path "$GEM_HOME" \
	&& bundle config --global bin "$GEM_HOME/bin"

#RUN useradd -m -s /bin/bash app
WORKDIR /opt/todos-api

ADD docker/start.sh /usr/local/sbin/start
RUN chmod 755 /usr/local/sbin/start

CMD ["/usr/local/sbin/start"]
#CMD ["/bin/bash"]


RUN echo "Docker builded..................."