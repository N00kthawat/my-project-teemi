FROM node:18-alpine

WORKDIR /app

# คัดลอกไฟล์ package.json และ package-lock.json
COPY package*.json ./

# ติดตั้ง dependencies
RUN npm install --legacy-peer-deps

# คัดลอกโค้ดแอปพลิเคชัน
COPY . .

# Rebuild bcrypt
RUN npm rebuild bcrypt --build-from-source

# เปิดพอร์ตที่แอปพลิเคชันจะทำงาน
EXPOSE 5000

# เริ่มต้นแอปพลิเคชัน
CMD ["npm", "start"]
