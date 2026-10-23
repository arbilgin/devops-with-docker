FROM amazoncorretto:8-alpine-full

COPY . .

RUN chmod +x ./mvnw && ./mvnw package

EXPOSE 8080

CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]