# DalalAlsaudia
DalalAlsaudia
## نظرة عامة (Overview)

هذا التطبيق عبارة عن منصة متكاملة لإدارة وعرض العقارات للإيجار. يتكون من واجهة أمامية مبنية بتقنية Next.js وخلفية مبنية بتقنية Express.js، مع قاعدة بيانات PostgreSQL.

This application is a comprehensive real estate rental platform. It consists of a Next.js frontend and an Express.js backend with a PostgreSQL database.

## المميزات الرئيسية (Key Features)

- **البحث عن العقارات**: بحث متقدم مع تصفية حسب السعر، عدد الغرف، الحمامات، والمرافق
- **البحث الجغرافي**: العثور على العقارات بناءً على الموقع
- **أدوار المستخدمين**: مستأجرين ومديري عقارات مع صلاحيات مختلفة
- **إدارة العقارات**: إنشاء وتحرير قوائم العقارات مع تحميل الصور
- **نظام الإيجار**: إدارة عقود الإيجار وطلبات التأجير

- **Property Search**: Advanced search with filtering by price, beds, baths, amenities
- **Geospatial Search**: Find properties based on location
- **User Roles**: Tenants and property managers with different permissions
- **Property Management**: Create and edit property listings with photo uploads
- **Leasing System**: Manage leases and rental applications

## التقنيات المستخدمة (Technologies Used)

### الواجهة الأمامية (Frontend)
- Next.js 15
- React 19
- TypeScript
- Redux (Redux Toolkit)
- Tailwind CSS
- Radix UI
- Mapbox

### الخلفية (Backend)
- Express.js
- TypeScript
- Prisma ORM
- PostgreSQL with PostGIS
- AWS S3 (for image storage)
- JWT Authentication

## متطلبات النظام (System Requirements)

- Node.js (v16+)
- npm or yarn
- PostgreSQL database with PostGIS extension
- AWS S3 bucket (for image storage)

## تثبيت وتشغيل التطبيق (Installation & Setup)

### إعداد الخلفية (Backend Setup)

1. انتقل إلى مجلد الخادم (Navigate to the server directory):

```bash
cd server

cd server && npm install  
npm audit fix
npm init -y 
npm i 
npm i express body-parser cors dotenv helmet morgan jsonwebtoken multer uuid axios @terraformer/wkt aws-sdk/client-s3 aws-sdk/lib-storage

npm i -D rimraf concurrently nodemon shx ts-node typescript @types/cors @types/morgan @types/node @types/jsonwebtoken @types/multer @types/terraformer-wkt @types/uuid

npx tsc --init
npm i prisma @prisma/client
npm i -D @types/prisma
npx prisma init
npx prisma generate
npx prisma migrate dev
npx prisma migrate dev --name init
npx prisma migrate reset
npx prisma studio
npx prisma seed
npm run prisma:generate
npm run seed
npm run dev
npm run build
Update available 6.3.0 -> 6.5.update                           
npm i --save-dev prisma@latest                            
npm i @prisma/client@latest     

```

2. قم بتثبيت الاعتماديات (Install dependencies):

```bash
npm install
npm i lucide-react dotenv date-fns react-filepond filepond filepond-plugin-image-exif-orientation filepond-plugin-image-preview framer-motion mapbox-gl lodash react-hook-form zod @hookform/resolvers
npm i -D @types/node @type/uuid
npm run dev
npx shadcn@latest init --tailwind
npx shadcn@latest init -d shadcn@2.3.0
```

3. قم بإنشاء ملف البيئة (Create an environment file) `.env` في مجلد الخادم مع المتغيرات التالية:

```
DATABASE_URL="postgresql://username:password@localhost:5432/real_estate?schema=public"
PORT=3002
JWT_SECRET=your_jwt_secret
AWS_REGION=your_aws_region
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
S3_BUCKET_NAME=your_s3_bucket_name
```

4. قم بتوليد عميل Prisma (Generate Prisma client):

```bash
npx prisma generate
```

5. قم بتشغيل الهجرات (Run migrations) (إذا كنت تستخدم قاعدة بيانات جديدة):

```bash
npx prisma migrate dev
```

6. قم بتشغيل الخادم (Run the server):

```bash
cd client
npm run dev
npm install -g npm
npm cache clean --force
npx shadcn@latest init -d 
npx shadcn@latest add avatar badge button card checkbox command dialog deopdown-menu form input label navigation-menu radio-group select separator sheet sidebar skeleton slider sonner switch table tabs textarea tooltip

npm i react-redux @reduxjs/toolkit dotenv --legacy-peer-deps
npm i @fortawesome/fontawesome-svg-core @fortawesome/free-brands-svg-icons @fortawesome/react-fontawesome --legacy-peer-deps
npm i aws-amplify @aws-amplify/ui-react --legacy-peer-deps

```

الخادم سيعمل على المنفذ 3002: http://localhost:3002

### إعداد الواجهة الأمامية (Frontend Setup)

1. انتقل إلى مجلد العميل (Navigate to the client directory):

```bash
cd client
npm run dev
```

2. قم بتثبيت الاعتماديات (Install dependencies):

```bash
npm install
```

3. قم بإنشاء ملف البيئة (Create an environment file) `.env.local` في مجلد العميل مع المتغيرات التالية:

```
NEXT_PUBLIC_API_URL=http://localhost:3002
NEXT_PUBLIC_MAPBOX_ACCESS_TOKEN=your_mapbox_access_token
```

4. قم بتشغيل تطبيق الواجهة الأمامية (Run the frontend application):

```bash
npm run dev
```

التطبيق سيعمل على المنفذ 3000: http://localhost:3000

## هيكل المشروع (Project Structure)

### الواجهة الأمامية (Frontend)

```
client/
├── public/              # Static assets
├── src/
│   ├── app/             # Next.js app router pages
│   │   ├── (auth)/      # Authentication related pages
│   │   ├── (dashboard)/ # Dashboard pages for users
│   │   └── (nondashboard)/ # Public pages
│   ├── components/      # Reusable UI components
│   ├── hooks/           # Custom React hooks
│   ├── lib/             # Utility functions
│   ├── state/           # Redux state management
│   └── types/           # TypeScript type definitions
```

### الخلفية (Backend)

```
server/
├── prisma/              # Prisma schema and migrations
├── src/
│   ├── controllers/     # Request handlers
│   ├── middleware/      # Express middleware
│   ├── routes/          # API routes
│   └── index.ts         # Server entry point
```

## استخدام التطبيق (Using the Application)

### التسجيل وتسجيل الدخول (Registration & Login)

1. قم بزيارة الصفحة الرئيسية: http://localhost:3000
2. انقر على "تسجيل الدخول" أو "إنشاء حساب"
3. اختر نوع الحساب: مستأجر أو مدير عقارات

### البحث عن العقارات (Searching Properties)

1. استخدم شريط البحث في الصفحة الرئيسية للبحث حسب الموقع
2. استخدم الفلاتر لتحديد نطاق السعر، عدد الغرف، وغيرها من المعايير
3. استعرض نتائج البحث على الخريطة أو في عرض القائمة

### إدارة العقارات (للمديرين) (Property Management - for Managers)

1. قم بتسجيل الدخول كمدير عقارات
2. انتقل إلى لوحة التحكم
3. انقر على "إضافة عقار جديد" لإنشاء قائمة عقار جديدة
4. قم بتحميل الصور وإدخال تفاصيل العقار

### تقديم طلب استئجار (للمستأجرين) (Applying for a Rental - for Tenants)

1. قم بتسجيل الدخول كمستأجر
2. ابحث عن العقار المطلوب
3. انقر على "تقديم طلب" على صفحة تفاصيل العقار
4. أكمل نموذج الطلب وقم بتقديمه

## استكشاف الأخطاء وإصلاحها (Troubleshooting)

### مشاكل الاتصال بقاعدة البيانات (Database Connection Issues)

- تأكد من أن خدمة PostgreSQL تعمل
- تحقق من صحة سلسلة اتصال قاعدة البيانات في ملف `.env`
- تأكد من تثبيت امتداد PostGIS

### مشاكل تحميل الصور (Image Upload Issues)

- تحقق من صحة مفاتيح AWS في ملف `.env`
- تأكد من أن دلو S3 يسمح بالوصول العام للقراءة

### مشاكل الخريطة (Map Issues)

- تأكد من صحة رمز وصول Mapbox في ملف `.env.local`

## المساهمة (Contributing)

نرحب بالمساهمات! يرجى اتباع هذه الخطوات:

1. قم بعمل fork للمستودع
2. قم بإنشاء فرع للميزة الجديدة (`git checkout -b feature/amazing-feature`)
3. قم بعمل commit للتغييرات (`git commit -m 'Add some amazing feature'`)
4. قم بدفع الفرع (`git push origin feature/amazing-feature`)
5. قم بفتح طلب سحب

## الترخيص (License)

هذا المشروع مرخص بموجب رخصة MIT.





post gress   config

host :localhost
port :5432   9052
user :postgres
password :osama5555


CREATE EXTENSION IF NOT EXISTS "postgis"



mapbox account : https://account.mapbox.com/
username : 89fares    pas: dekHo5-zysgiz-xuxqoz

map style : https://docs.mapbox.com/help/tutorials/create-a-map-style/
const map = new mapboxgl.Map({
      container: mapContainerRef.current!,
      style: "mapbox://styles/89fares/cma6vsrwf00f001sl0rt42p41",




…or create a new repository on the command line
echo "# realstate" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/OsamaDeghidy/realstate.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin https://github.com/OsamaDeghidy/realstate.git
git branch -M main
git push -u origin main