FROM maven:3.9.6-eclipse-temurin-21-alpine as builder

COPY . .
RUN mvn dependency:resolve
RUN mvn package

EXPOSE 80

FROM eclipse-temurin:21-jre-alpine

COPY --from=builder . .

CMD ["java", "-jar", "target/worker-jar-with-dependencies.jar"]