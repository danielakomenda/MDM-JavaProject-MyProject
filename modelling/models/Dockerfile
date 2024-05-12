# docker buildx build --platform linux/amd64 -t komendan/model-service:latest --push .
# docker build -t komendan/model-service:latest .

FROM deepjavalibrary/djl-serving:latest
COPY fruitclassifier /opt/ml/model/fruitclassifier
EXPOSE 8080
RUN ls -al /opt/ml/model/