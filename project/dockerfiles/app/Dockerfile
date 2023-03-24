# Create openjdk-8 image to download artifact
FROM openjdk-8 AS BUILDER

RUN apt update && apt install maven -y 
RUN git clone -b https://github.com/devopshydclub/vprofile-project.git
RUN cp vprofile-project && mvn install

# Create tomcat image to download artifact
FROM tomcat:8.5.87-jre11

RUN rm -rf /usr/local/tomcat/webapps/*

# Copy artifact from openjdk to tomcat container
COPY --from=BUILDER vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
# from hub docker tomcat - Run the default Tomcat server
CMD ["catalina.sh", "run"]
