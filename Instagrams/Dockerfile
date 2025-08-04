# # Use official Tomcat 10.1 with JDK 17
FROM tomcat:10.1-jdk17

# Clean default Tomcat webapps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy your WAR file and rename to ROOT.war
COPY ROOT.war /usr/local/tomcat/webapps/ROOT.war

# Add MySQL JDBC driver (for DB connection)
ADD https://repo1.maven.org/maven2/mysql/mysql-connector-java/8.0.33/mysql-connector-java-8.0.33.jar /usr/local/tomcat/lib/

# Optional: disable shutdown port for security
RUN sed -i 's/<Server port="8005"/<Server port="-1"/' /usr/local/tomcat/conf/server.xml

# Expose default Tomcat port
EXPOSE 8080

# Start Tomcat server
CMD ["catalina.sh", "run"]
