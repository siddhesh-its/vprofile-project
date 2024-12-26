FROM maven:3.9.9-eclipse-temurin-21-jammy AS MAVEN_IMAGE
RUN git clone https://github.com/siddhesh-its/vprofile-project.git
RUN cd vprofile-project && git checkout containers && mvn install

FROM tomcat:10-jdk21 AS SERVICE_IMAGE
LABEL "AUTHOR"="SIDDHESH"
LABEL "PROJECT"="VPROFILE_app"
RUN rm -rf /urs/local/tomcat/webapps/*
COPY --from=MAVEN_IMAGE vprofile-project/target/vprofile-v2.war /urs/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD [ "catalina.sh", "run" ]