# Comrade Homes – Backend

A backend API for **Comrade Homes**, a student accommodation platform that helps students find rooms, hostels, bedsitters and apartments near their universities and colleges in Kenya.

## 1. Project Overview

The Comrade Homes backend manages:

- Student and landlord accounts.
- University and college information.
- Property listings and accommodation details.
- Property image uploads.
- Student booking enquiries.
- Landlord subscriptions and payments.
- Administrator management.

## 2. Technology Stack

| Technology | Purpose |
|---|---|
| Node.js | Backend runtime |
| Express.js | REST API framework |
| Supabase | Backend platform |
| PostgreSQL | Database |
| Supabase Storage | Property image storage |
| Supabase Auth | User authentication |
| JavaScript | Backend programming |

## 3. Main Features

### User Management
- Student registration and login.
- Landlord registration and login.
- Administrator accounts.
- Role-based access control.

### Property Management
- Add new accommodation.
- Update property information.
- Delete property listings.
- View available properties.
- Search and filter properties.

### Institution Management
- Register universities and colleges.
- Allow students to select their institution.
- Find accommodation near selected institutions.

### Image Management
- Upload property photographs.
- Store images in Supabase Storage.
- Retrieve image URLs for property listings.

### Booking Management
- Receive student booking enquiries.
- Store booking information.
- Track booking enquiry status.

### Landlord Payments
- Registration fee: KSh 1,000.
- Monthly subscription: KSh 100.
- Track payment status and listing expiry.

Payment processing will be integrated separately.

## 4. Installation

Make sure you have installed:

- Node.js
- npm
- Visual Studio Code

Clone or open the project folder.

Install dependencies:

```bash
npm install
```

Install the backend packages:

```bash
npm install express dotenv cors @supabase/supabase-js
```

Install development tools:

```bash
npm install --save-dev nodemon
```

## 5. Environment Variables

Create a `.env` file in the backend root directory.

```env
PORT=5000
SUPABASE_URL=your_supabase_project_url
SUPABASE_SERVICE_ROLE_KEY=your_secret_service_role_key
```

**Security:** Never upload `.env` to GitHub. Never expose the Supabase service-role key in frontend code.

Add `.env` to `.gitignore`.

## 6. Suggested Backend Structure

```text
backend/
│
├── config/
│   └── supabase.js
│
├── controllers/
│   ├── authController.js
│   ├── propertyController.js
│   ├── bookingController.js
│   └── landlordController.js
│
├── middleware/
│   ├── authMiddleware.js
│   └── errorMiddleware.js
│
├── routes/
│   ├── authRoutes.js
│   ├── propertyRoutes.js
│   ├── bookingRoutes.js
│   └── landlordRoutes.js
│
├── services/
│   └── storageService.js
│
├── .env
├── .gitignore
├── package.json
├── server.js
└── README.md
```

This is the proposed structure; files will be created as the backend is implemented.

## 7. API Endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| GET | `/api/properties` | Get properties |
| GET | `/api/properties/:id` | Get one property |
| POST | `/api/properties` | Add property |
| PUT | `/api/properties/:id` | Update property |
| DELETE | `/api/properties/:id` | Delete property |
| POST | `/api/auth/register` | Register user |
| POST | `/api/auth/login` | User login |
| GET | `/api/institutions` | Get institutions |
| POST | `/api/bookings` | Create booking enquiry |

These are planned endpoints; they must be implemented before they can be used.

## 8. Database

The backend will use Supabase PostgreSQL.

Planned database tables:

- `profiles`
- `institutions`
- `properties`
- `property_images`
- `bookings`
- `payments`

Database access must be protected using appropriate authentication and Row Level Security (RLS) policies.

## 9. Running the Backend

Start the development server:

```bash
npm run dev
```

Or, if using Node directly:

```bash
node server.js
```

The development API will run at:

```text
http://localhost:5000
```

## 10. Deployment

The backend can be deployed using a Node.js-compatible hosting service.

The frontend can be hosted separately on Netlify.

Configure environment variables securely on the hosting platform before deployment.

## 11. Project Goal

To provide a reliable student accommodation platform where students can discover suitable housing near their institutions and landlords can manage their property listings.

**Comrade Homes – Find your place near campus.**