# nexus3-swarm

docker build -t myapp:latest .
docker tag myapp:latest 127.0.0.1:8082/repository/docker-hosted/myapp:latest

docker login 127.0.0.1:8082
docker push 127.0.0.1:8082/repository/docker-hosted/myapp:latest

# Setting Port 8082
Admin > Repo > Setting > docker-hosted > http fill 8082

# สร้าง Cleanup Policy ใน Nexus:
เข้าสู่ Nexus Repository Manager UI.
ไปที่ Administration > Repository > Cleanup Policies.
คลิกที่ Create cleanup policy เพื่อสร้าง policy ใหม่.
กรอกข้อมูลสำหรับ policy ใหม่ เช่น ชื่อ, format (Docker), และเงื่อนไข (criteria) ที่ต้องการ เช่น:
## Last downloaded: ลบ images ที่ไม่ได้ถูกดาวน์โหลดในช่วงเวลาที่กำหนด (เช่น 30 วัน).
## Last blob updated: ลบ images ที่ไม่ได้ถูกอัปเดตในช่วงเวลาที่กำหนด.