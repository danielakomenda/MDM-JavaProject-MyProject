# docker buildx build --platform linux/amd64 -t komendan/mdm-java-project:latest --push .
# docker build -t komendan/mdm-java-project:latest .


# Stage 1: Build the Svelte Frontend
FROM node:16 as frontend-build
WORKDIR /app/frontend
COPY frontend/package.json frontend/package-lock.json ./
RUN npm install
COPY frontend/ .
RUN npm run build


FROM openjdk:21-jdk-slim
WORKDIR /usr/src/app
COPY . .
RUN ./mvnw -Dmaven.test.skip=true package

EXPOSE 8082
CMD ["java","-jar","/usr/src/app/target/javaproject-0.0.1-SNAPSHOT.jar"]