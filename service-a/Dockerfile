FROM public.ecr.aws/docker/library/eclipse-temurin:17 as build
WORKDIR /app
RUN ls -a
COPY . .
RUN pwd
RUN ls -a
COPY target/*.jar /target/*.jar
RUN ls -a
RUN pwd
RUN cd target
RUN ls -a
RUN pwd
RUN cd ..

# RUN mvnw clean package -DskipTests

FROM public.ecr.aws/docker/library/eclipse-temurin:17-jre-alpine
COPY --from=build /app/target/*.jar app.jar
RUN pwd
RUN ls -a
RUN pwd
ENTRYPOINT ["java", "-jar", "/app.jar"]
