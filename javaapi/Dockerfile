FROM openjdk:8 AS build 
WORKDIR /javaapi
COPY . /javaapi 
RUN apt update && apt install maven -y 
RUN mvn install 

FROM openjdk:8
WORKDIR /java
COPY --form=build /javaapi/target/*.jar /java/java.jar
EXPOSE 9000
CMD ["java","-jar","java.jar"]
