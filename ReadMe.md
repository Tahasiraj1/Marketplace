# Clothing Brand Marketplace - Avion

## Overview

The Clothing Brand Marketplace is an e-commerce platform designed to bring a wide variety of stylish and high-quality clothing brands to customers worldwide. This marketplace offers users a seamless shopping experience, allowing them to browse a diverse collection of clothing, select their desired products, and make secure purchases with ease. The platform also serves as a hub for clothing brands to showcase their latest collections and reach a larger customer base.

Live Demo: https://hackathon-2-flax.vercel.app/

## Features

- **User Authentication**: Secure sign-up and login functionality for users to create accounts and access personalized features.
- **Product Catalog**: A wide selection of clothing items from various brands, categorized by type (e.g., shirts, jeans, dresses, accessories).
- **Search and Filters**: Advanced search options and filters to help users find exactly what they’re looking for.
- **Product Details**: Each product includes detailed descriptions, multiple images, size options, and pricing information.
- **Shopping Cart**: Users can add items to their cart, review their selections, and proceed to checkout.
- **Payment Integration**: Secure payment gateway integration to process transactions safely.
- **Order Tracking**: Real-time tracking of orders after purchase, allowing users to monitor their shipments.
- **Brand Showcase**: Clothing brands can create profiles to display their latest collections, bestsellers, and upcoming releases.

## Technologies Used

- **Frontend & Backend**: Next.js, a full-stack React framework, for both the frontend and backend. Next.js allows for server-side rendering, API routes, and full-stack capabilities all in one framework.
- **Frontend UI**: Tailwind CSS, Shadcn UI components for building a modern and responsive user interface.
- **Database**: MongoDB Atlas for cloud-hosted database management.
- **ORM**: Prisma ORM for writing efficient and scalable queries to interact with the MongoDB Atlas database.
- **Content Management**: Sanity CMS for flexible product data management, allowing easy integration and updating of product information across the marketplace.
- **Authentication**: Clerk Auth for secure and easy-to-integrate user authentication, including sign-ups, logins, and session management.
- **Payment Integration**: Stripe or PayPal API for secure payment processing.

## Getting Started

To run the Clothing Brand Marketplace locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone <repo-url>
   ```

2. **Navigate to the project directory**:
   ```bash
   cd clothing-brand-marketplace
   ```

3. **Install the dependencies**:
   ```bash
   npm install
   ```

4. **Set up environment variables**:
   Create a `.env.local` file in the root of the project and add the following variables (make sure to replace the placeholder values):
   - `NEXT_PUBLIC_SANITY_PROJECT_ID=<your-sanity-project-id>`
   - `NEXT_PUBLIC_SANITY_DATASET=<your-sanity-dataset>`
   - `NEXTAUTH_SECRET=<your-secret-key>`
   - `MONGODB_URI=<your-mongodb-connection-string>`
   - `STRIPE_SECRET_KEY=<your-stripe-secret-key>`
   
5. **Start the development server**:
   ```bash
   npm run dev
   ```

6. **Visit the app**:
   Open your browser and go to `https://hackathon-2-flax.vercel.app/` to see the marketplace in action.

7. **Project Structure**

The project follows a simplified directory structure, making it easy to manage both the frontend and backend within a single Next.js project. Below is the structure of the application:

![Project Structure](public/images/ProjectStructure.PNG)

## User Flow Diagram

Here is a diagram showing the typical user flow for the Clothing Brand Marketplace:

![User Flow Diagram](public/images/Untitled-2024-11-29-2003.png)

This diagram highlights the key steps a user takes from visiting the homepage, browsing products, adding items to the cart, and completing the checkout process.


## Test Case Documentation

You can View the test cases in CSV format from the following link below: 
[View Test Cases (CSV)](public/assets/test-cases.csv)


## Contributing

We welcome contributions! If you would like to improve the project, feel free to fork the repository, create a branch, and submit a pull request. Be sure to include a description of your changes and any relevant issue numbers.
