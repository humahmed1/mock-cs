FROM openjdk:11
ADD target/cs-0.0.1-SNAPSHOT.jar cs-mock.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "cs-mock.jar"]