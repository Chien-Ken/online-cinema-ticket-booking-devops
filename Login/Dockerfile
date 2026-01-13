# Dùng image Java 17 runtime nhẹ nhất (alpine)
FROM eclipse-temurin:17-jre-alpine

# Tạo thư mục làm việc trong container
WORKDIR /app

# Copy file JAR chính xác của bạn vào container và đổi tên thành app.jar (dễ quản lý)
COPY target/se2Assignment-0.0.1-SNAPSHOT.jar app.jar

# Lệnh chạy ứng dụng khi container khởi động
ENTRYPOINT ["java", "-jar", "app.jar"]

# Mở port mà app của bạn dùng
EXPOSE 8082
