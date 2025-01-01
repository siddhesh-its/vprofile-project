FROM maven:3.9.9-eclipse-temurin-21-jammy AS maven_images
RUN git clone https://github.com/hkhcoder/vprofile-project.git
#RUN git clone https://github.com/siddhesh-its/vprofile-project.git
RUN cd vprofile-project && git checkout containers && mvn install

FROM tomcat:10-jdk21
LABEL "AUTHOR"="SIDDHESH"
LABEL "PROJECT"="VPROFILE_app"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=maven_images vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]


# Stage 1: Build the application using Maven
# FROM maven:3.9.9-eclipse-temurin-21-jammy AS maven_build

# # Clone the project and build
# RUN git clone https://github.com/siddhesh-its/vprofile-project.git && cd vprofile-project && git checkout containers
# RUN mvn clean install -DskipTests

# # Stage 2: Deploy the WAR file to Tomcat
# FROM tomcat:10-jdk21
# LABEL "AUTHOR"="SIDDHESH"
# LABEL "PROJECT"="VPROFILE_app"

# # Clean existing webapps and copy the built WAR file
# RUN rm -rf /usr/local/tomcat/webapps/*
# COPY --from=maven_build vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# # Expose port 8080 and run Tomcat
# EXPOSE 8080
# CMD ["catalina.sh", "run"]



