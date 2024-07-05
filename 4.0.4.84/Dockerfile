FROM openjdk:21-jdk-slim-buster

RUN rm -rf /var/lib/apt/lists/*
RUN apt-get update 
RUN apt-get install -y --no-install-recommends \
        curl \
		ruby \
		unzip \
		libfreetype6 \
		fontconfig \
	&& rm -rf /var/lib/apt/lists/*

# Installing SenchaCmd
RUN curl --silent http://cdn.sencha.com/cmd/4.0.4.84/SenchaCmd-4.0.4.84-linux-x64.run.zip -o /tmp/sencha.zip 
RUN unzip /tmp/sencha.zip -d /tmp  
RUN unlink /tmp/sencha.zip  
RUN chmod o+x /tmp/SenchaCmd-4.0.4.84-linux-x64.run  
RUN echo -e '\n\n\n\n\n\ny\n/opt\n\n' | /tmp/SenchaCmd-4.0.4.84-linux-x64.run 
RUN  unlink /tmp/SenchaCmd-4.0.4.84-linux-x64.run

WORKDIR /app

ENV PATH="/opt/Sencha/Cmd/4.0.4.84:${PATH}"

ENTRYPOINT ["sencha"]
