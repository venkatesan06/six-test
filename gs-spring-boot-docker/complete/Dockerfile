
FROM maven AS build
COPY . /app
WORKDIR /app
RUN mvn clean package

FROM openjdk
WORKDIR /usr/src/myapp
COPY --from=build /app/target/*.jar App.jar
CMD java -jar App.jar
