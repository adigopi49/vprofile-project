FROM tomcat:9-jre11
LABEL "Project"="Vprofile"
LABEL "Author"="Gopi"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY /var/lib/jenkins/workspace/social-website/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
