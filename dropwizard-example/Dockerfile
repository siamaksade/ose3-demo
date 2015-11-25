FROM java:8-jre


COPY target/dropwizard-example-0.9.1.jar /opt/dropwizard/
COPY example.yml /opt/dropwizard/
COPY example.keystore /opt/dropwizard/
RUN java -jar /opt/dropwizard/dropwizard-example-0.9.1.jar db migrate /opt/dropwizard/example.yml
RUN mv ./target /opt/dropwizard

EXPOSE 8080
EXPOSE 8443
EXPOSE 8081
EXPOSE 8444

WORKDIR /opt/dropwizard
CMD ["java", "-jar", "/opt/dropwizard/dropwizard-example-0.9.1.jar", "server", "/opt/dropwizard/example.yml"]