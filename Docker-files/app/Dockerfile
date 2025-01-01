FROM maven:3.9.9-eclipse-temurin-21-jammy AS maven_images
RUN git clone https://github.com/siddhesh-its/vprofile-project.git
RUN cd vprofile-project && git checkout containers && mvn install

FROM tomcat:10-jdk21
LABEL "AUTHOR"="SIDDHESH"
LABEL "PROJECT"="VPROFILE_app"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=maven_images vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]