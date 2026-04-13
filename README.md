# PocketLancer
**Full-Stack Freelance & Home Services Marketplace**

[![Live Demo](https://img.shields.io/badge/Live-pocketlancer.org-blue)](https://pocketlancer.org)
[![GitHub](https://img.shields.io/badge/GitHub-dedeepreddyseelam-black)](https://github.com/dedeepreddyseelam/PocketLancer)
[![Android APK](https://img.shields.io/badge/Android-APK_Available-green)](https://pocketlancer.org)

## Authors
* **S. Dedeep Reddy** (Y22ACS553)
* **M. Siva Sai Krishna** (Y22ACS497)
* **T. Swetha** (Y22ACS576)
* **S. Sravanthi** (Y22ACS563)
---

## 🔗 Quick Links

- **🌐 Live Platform:** [pocketlancer.org](https://pocketlancer.org)
- **📱 Android App:** Available as Capacitor-wrapped APK
- **💻 GitHub Repository:** [github.com/dedeepreddyseelam/PocketLancer](https://github.com/dedeepreddyseelam/PocketLancer)

---

## 📋 Overview

PocketLancer is a comprehensive freelance and home services marketplace that connects service providers with clients for both digital freelance work and local home services. The platform bridges the gap between skilled professionals and individuals seeking quality services, operating as a two-sided marketplace with robust features for both service providers and clients.

**Key Innovation:** Hybrid marketplace combining digital freelancing (logo design, web development, content writing) with location-based home services (plumbing, electrical work, cleaning), all within a unified platform accessible via web and mobile.

### Target Users
- **Freelancers:** Digital professionals offering remote services
- **Home Service Providers:** Local professionals (plumbers, electricians, cleaners, etc.)
- **Clients:** Individuals and businesses seeking professional services
- **Platform Admins:** System administrators managing the marketplace

---

## ✨ Key Features

### 🎯 Core Marketplace Features
- **Dual Service Categories**
  - Digital Freelance Services (remote work)
  - Home Services (location-based)
- **Advanced Search & Filtering**
  - Filter by category, price range, location, ratings
  - Real-time search with instant results
- **Secure Payment Integration**
  - Razorpay payment gateway integration
  - Escrow-style payment protection
  - Multiple payment methods support

### 👤 Freelancer/Service Provider Features
- **Comprehensive Profile Management**
  - Portfolio showcase with project galleries
  - Skills and expertise listing
  - Service pricing and packages
  - Availability calendar
- **Service Listing Creation**
  - Detailed service descriptions
  - Custom pricing models (fixed/hourly)
  - Category and tag management
- **Order Management Dashboard**
  - Track active and completed orders
  - Client communication tools
  - Revenue analytics

### 🛒 Client Features
- **Service Discovery**
  - Browse services by category
  - View provider profiles and portfolios
  - Read reviews and ratings
- **Booking & Ordering**
  - One-click service booking
  - Requirement specification forms
  - Order tracking and status updates
- **Review & Rating System**
  - Post-service feedback mechanism
  - Star ratings and written reviews
  - Provider response capability

### 🔐 Security & Authentication
- **JWT-Based Authentication**
  - Secure token-based sessions
  - Automatic token refresh
  - Session management
- **Password Security**
  - bcrypt hashing (10 salt rounds)
  - Secure password reset flow
- **Role-Based Access Control**
  - Separate interfaces for clients and providers
  - Admin dashboard access control

### 📱 Mobile Application
- **Capacitor-Wrapped Android APK**
  - Native Android app experience
  - Push notification support
  - Offline capability for browsing
  - Cross-platform codebase (web + mobile)

---

## 🏗️ System Architecture

PocketLancer implements a modern three-tier MERN stack architecture:

```
┌─────────────────────────────────────────────────────────┐
│           PRESENTATION LAYER (Frontend)                 │
│  Next.js 14 + React 18 + Tailwind CSS                  │
│  Responsive Web + Capacitor (Android)                   │
└────────────────────┬────────────────────────────────────┘
                     │ REST API (HTTP/HTTPS)
┌────────────────────▼────────────────────────────────────┐
│          APPLICATION LAYER (Backend)                    │
│  Node.js + Express.js + JWT Authentication             │
│  Razorpay Integration + File Upload (Multer)           │
└────────────────────┬────────────────────────────────────┘
                     │ Mongoose ODM
┌────────────────────▼────────────────────────────────────┐
│              DATA LAYER (Database)                      │
│  MongoDB (NoSQL Document Database)                      │
│  Collections: Users, Services, Orders, Reviews,         │
│  Categories, Transactions                               │
└─────────────────────────────────────────────────────────┘
```

**External Services:**
- **Razorpay** - Payment processing and order management
- **Cloudinary/File Storage** - Image and file uploads
- **Capacitor** - Mobile app wrapper for Android deployment

---

## 💻 Technologies Used

### Frontend Stack
| Technology | Version | Purpose |
|-----------|---------|---------|
| **Next.js** | 14.x | React framework with SSR/SSG |
| **React** | 18.x | Component-based UI library |
| **Tailwind CSS** | 3.x | Utility-first styling |
| **Capacitor** | Latest | Cross-platform mobile runtime |
| **Axios** | Latest | HTTP client with interceptors |

### Backend Stack
| Technology | Version | Purpose |
|-----------|---------|---------|
| **Node.js** | 18.x+ | JavaScript runtime |
| **Express.js** | 4.x | Web application framework |
| **MongoDB** | 6.0+ | NoSQL database |
| **Mongoose** | 7.x+ | MongoDB ODM |
| **JWT** | Latest | Authentication tokens |
| **bcrypt** | Latest | Password hashing |
| **Razorpay SDK** | Latest | Payment integration |

### DevOps & Deployment
- **Hosting:** Custom domain (pocketlancer.org)
- **Database:** MongoDB Atlas (cloud hosting)
- **Version Control:** Git & GitHub
- **Mobile Build:** Capacitor CLI + Android Studio

---

## 🚀 Installation & Setup

### Prerequisites
```bash
Node.js 18.x or higher
MongoDB 6.0 or higher
npm or yarn package manager
Razorpay account (for payments)
Android Studio (for mobile builds)
```

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/dedeepreddyseelam/PocketLancer.git
cd PocketLancer/backend

# Install dependencies
npm install

# Create .env file
cat > .env << EOF
PORT=5000
NODE_ENV=development
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_super_secret_jwt_key_minimum_32_characters
JWT_EXPIRE=7d
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
FRONTEND_URL=http://localhost:3000
EOF

# Start development server
npm run dev

# Start production server
npm start
```

### Frontend Setup

```bash
# Navigate to frontend directory
cd ../frontend

# Install dependencies
npm install

# Create .env.local file
cat > .env.local << EOF
NEXT_PUBLIC_API_URL=http://localhost:5000
NEXT_PUBLIC_RAZORPAY_KEY_ID=your_razorpay_key_id
EOF

# Start development server
npm run dev

# Build for production
npm run build
npm start
```

### Mobile App Build (Android)

```bash
# Install Capacitor CLI
npm install -g @capacitor/cli

# Add Android platform
npx cap add android

# Sync web assets to native project
npx cap sync

# Open in Android Studio
npx cap open android

# Build APK in Android Studio
# Build > Build Bundle(s) / APK(s) > Build APK(s)
```

---

## 🗄️ Database Schema

### Collections Overview

**Users Collection**
```javascript
{
  name: String,
  email: String (unique),
  password: String (hashed),
  role: Enum ['client', 'freelancer', 'admin'],
  profile: {
    bio: String,
    skills: [String],
    location: String,
    profileImage: String
  },
  createdAt: Date
}
```

**Services Collection**
```javascript
{
  provider: ObjectId (ref: User),
  title: String,
  description: String,
  category: String,
  serviceType: Enum ['digital', 'home_service'],
  pricing: {
    type: Enum ['fixed', 'hourly'],
    amount: Number
  },
  images: [String],
  location: String (for home services),
  isActive: Boolean,
  ratings: {
    average: Number,
    count: Number
  }
}
```

**Orders Collection**
```javascript
{
  client: ObjectId (ref: User),
  provider: ObjectId (ref: User),
  service: ObjectId (ref: Service),
  status: Enum ['pending', 'in_progress', 'completed', 'cancelled'],
  amount: Number,
  paymentStatus: Enum ['pending', 'paid', 'refunded'],
  razorpayOrderId: String,
  requirements: String,
  createdAt: Date,
  completedAt: Date
}
```

---

## 🔧 Environment Variables

### Backend (.env)
```env
# Server Configuration
PORT=5000
NODE_ENV=production

# Database
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/pocketlancer

# Authentication
JWT_SECRET=your_super_secret_jwt_key_minimum_32_characters
JWT_EXPIRE=7d

# Payment Gateway
RAZORPAY_KEY_ID=rzp_live_xxxxxxxxxxxxx
RAZORPAY_KEY_SECRET=your_razorpay_secret_key

# File Storage (Optional)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Frontend URL (for CORS)
FRONTEND_URL=https://pocketlancer.org
```

### Frontend (.env.local)
```env
NEXT_PUBLIC_API_URL=https://api.pocketlancer.org
NEXT_PUBLIC_RAZORPAY_KEY_ID=rzp_live_xxxxxxxxxxxxx
```

---

## 📊 Project Statistics

- **Total Routes:** 40+ API endpoints
- **Database Collections:** 6 core collections
- **Frontend Pages:** 25+ pages and components
- **Mobile App Size:** ~15MB (APK)
- **Code Quality:** ESLint + Prettier configured
- **API Response Time:** <200ms average

---

## 🐛 Known Issues & Fixes

### Freelancer Profile Save Bug (Fixed)
**Issue:** Profile name field not saving due to Mongoose validation failure  
**Root Cause:** `req.user.save()` called without password field  
**Solution:** Switched to `User.findByIdAndUpdate` with `$set` operator

### Payment Integration in Capacitor
**Status:** Under development  
**Challenge:** Razorpay checkout working on web, needs Android-specific handling in Capacitor environment

### Notification Routing
**Implementation:** Push notifications enabled only for Android/Capacitor builds, desktop uses in-app bell notifications

---

## 🔮 Future Enhancements

### Planned Features

1. **Advanced Search & Recommendations**
   - AI-powered service recommendations
   - Machine learning-based matching algorithm
   - Collaborative filtering for personalized suggestions

2. **Enhanced Communication**
   - Real-time chat between clients and providers
   - Video call integration for consultations
   - File sharing in conversations

3. **Expanded Payment Options**
   - Multiple payment gateways (Stripe, PayPal)
   - Wallet system for repeat transactions
   - Subscription plans for premium providers

4. **Mobile App Enhancements**
   - iOS app development
   - Native push notifications
   - Offline mode improvements
   - App store deployment

5. **Analytics & Reporting**
   - Provider earnings dashboard
   - Client spending insights
   - Platform-wide analytics for admins
   - Export reports in PDF/Excel

6. **Social Features**
   - Provider verification badges
   - Social media integration
   - Referral program
   - Community forums

---

## 📸 Screenshots

### Web Platform
- Homepage with service categories
- Service listing and filtering
- Provider profile pages
- Order tracking dashboard
- Payment checkout flow

### Mobile App (Android)
- Native mobile interface
- Touch-optimized navigation
- Mobile-first design patterns

---

## 🤝 Contributing

Contributions are welcome! This is a capstone project, but improvements and suggestions are appreciated.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is developed as part of academic requirements at Bapatla Engineering College.

---

## 👨‍💻 About the Developer

**Dedeep Reddy Seelam**  
B.Tech Computer Science and Engineering  
Bapatla Engineering College  

**Connect:**
- GitHub: [@dedeepreddyseelam](https://github.com/dedeepreddyseelam)
- Email: [Your College Email]
- LinkedIn: [Your LinkedIn Profile]

---

## 🙏 Acknowledgements

- **Bapatla Engineering College** - For academic support and resources
- **Project Guide** - [Guide Name], Department of CSE
- **Dr. M. Rajesh Babu** - Head of Department, CSE
- **MongoDB Atlas** - For database hosting
- **Razorpay** - For payment gateway services
- **Capacitor Team** - For cross-platform mobile framework

---

## 📚 Documentation

For detailed documentation, refer to the project thesis:
- [Project Report PDF](./docs/Project_Report.pdf)
- [API Documentation](./docs/API_Documentation.md)
- [Database Schema](./docs/Database_Schema.md)
- [Deployment Guide](./docs/Deployment_Guide.md)

---

## 🎓 Academic Context

**Project Type:** Capstone Project (Final Year B.Tech)  
**Course:** Computer Science and Engineering  
**Institution:** Bapatla Engineering College  
**Academic Year:** 2025-2026  
**Project Duration:** August 2025 - March 2026

---

**⭐ If you find this project useful, please give it a star on GitHub!**

**Built with ❤️ by Dedeep Reddy Seelam | Bapatla Engineering College | 2025-2026**

---

## 📞 Support

For issues and questions:
- **GitHub Issues:** [Report a bug](https://github.com/dedeepreddyseelam/PocketLancer/issues)
- **Email:** [Your Email]
- **Project Website:** [pocketlancer.org](https://pocketlancer.org)

---

*Last Updated: April 2026*
