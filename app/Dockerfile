FROM tomcat:8-jre8  
MAINTAINER dagotma

ADD *.war /usr/local/tomcat/webapps/
ADD *.properties /usr/local/tomcat/lib/
ADD logback.xml /usr/local/tomcat/lib/

CMD ["catalina.sh", "run"] 

