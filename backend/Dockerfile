# Build
FROM openjdk:17-alpine as builder
ADD . /builder
WORKDIR /builder
RUN ./gradlew build
RUN ls /builder/build/libs/

# Run
FROM openjdk:17-alpine
WORKDIR /app
EXPOSE 8080
COPY --from=builder /builder/build/libs/converter-0.0.1.jar /app/converter.jar
CMD ["java", "-jar", "converter.jar" ]