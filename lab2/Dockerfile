FROM my-alpine-jdk:1.0 as builder
WORKDIR /opt/app
COPY .mvn .mvn
COPY pom.xml mvnw ./
RUN ./mvnw dependency:go-offline
COPY ./src ./src
RUN ./mvnw clean install

FROM my-alpine-jdk:1.0
WORKDIR /opt/app
COPY --from=builder /opt/app/target/*.jar /opt/app/app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/opt/app/*.jar"]

USER 1001

