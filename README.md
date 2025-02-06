# Cloudinary Setup for Next.js with Prisma ORM

## 🚀 Introduction

This guide provides a setup for integrating **Cloudinary** in a **Next.js** application using **Prisma ORM**. Cloudinary is a powerful cloud-based media management solution that allows seamless image and video uploads, transformations, and delivery optimization.

## 📌 Features

- **Cloudinary API integration** for image upload and management.
- **Prisma ORM** for database operations.
- **Next.js API route setup** for secure server-side uploads.
- **Optimized image delivery** using Cloudinary transformations.

## 📂 Project Structure

```
/cloudinary-nextjs-prisma
│── /app
│   ├── /api
│   │   ├── /upload
│   │   │   ├── route.ts      # API route for handling file uploads to database
│   │   ├── cloudinaryUploader.ts       # API route for handling file uploads to cloudinary
│── /app
│   ├── page.tsx            # Main UI for image uploads
│── /components
│   ├── /ui
│   │   ├──  button.tsx
│   │   ├──  input.tsx
│   │   ├──  label.tsx
│── /lib
│   ├── cloudinary.ts       # Cloudinary configuration
│   ├── prisma.ts       # Database schema configuration
│   ├── utils.ts
│── .env.example               # Environment variables
│── next.config.js           # Next.js configuration
│── package.json             # Project dependencies
│── README.md                # Documentation
```

## ⚙️ Installation

1. Clone this repository:

   ```sh
   git clone https://github.com/Marwyn02/cloudinary-nextjs-prisma.git
   cd cloudinary-nextjs-prisma
   ```

2. Install dependencies:

   ```sh
   npm install  # or yarn install
   ```

3. Set up environment variables:
   Create a `.env.local` file in the root directory and add:

   ```env
   CLOUDINARY_CLOUD_NAME=your_cloud_name
   CLOUDINARY_API_KEY=your_api_key
   CLOUDINARY_API_SECRET=your_api_secret
   DATABASE_URL=your_prisma_database_url
   ```

   Replace values with your **Cloudinary API credentials** and **Prisma database URL**.

4. Generate Prisma client and apply migrations:

   ```sh
   npx prisma generate
   npx prisma migrate dev --name init
   ```

5. Start the development server:
   ```sh
   npm run dev  # or yarn dev
   ```

**⚠️ Important:** The application requires an internet-accessible Cloudinary account for full functionality.

## 🔧 Usage

1. Open `http://localhost:3000` in your browser.
2. Select an image and click **Upload**.
3. The image is uploaded to Cloudinary.

## 🔗 API Endpoints

### `POST /api/upload`

- **Description:** Handles image saves in the database.
- **Request Body:**
  ```json
  {
    "image": "base64_encoded_image_data"
  }
  ```
- **Response:**

  ```json
  {
    "imageUrl": "https://res.cloudinary.com/..."
  }
  ```

  ### `POST /api/cloudinaryUploader.ts`

- **Description:** Handles image uploads to Cloudinary.
- **Request Body:**
  ```json
  {
    "fileUrl": "",
    "fileName" "",
  }
  ```
- **Response:**
  ```json
  {
    "result": ""
  }
  ```

## 🛠 Technologies Used

- **Next.js** (Frontend & API Routes)
- **Cloudinary API** (Image Hosting & Optimization)
- **Prisma ORM** (Database Management)
- **TypeScript** (Type Safety)
- **Tailwind CSS** (Optional for Styling)

## 🔥 Future Improvements

- Implement **image transformations** for optimized delivery.
- Add **authentication** for secure file management.
- Enhance **error handling** and user feedback.

## 🤝 Contributing

Feel free to **fork** this repo, improve it, and submit a **pull request**! 🚀

## 📝 License

This project is open-source and available under the **MIT License**.

---

💡 **Need help?** Contact me at jhunmarwynsumargo@gmail.com or open an issue on GitHub!
