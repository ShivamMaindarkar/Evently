# Evently — Production Event Booking Portal

A full-stack event booking platform evolved from the original Java/MySQL terminal project. It includes a responsive 3D/glassmorphism UI, authentication, event catalogue, booking inventory, ticket history, admin event management, PostgreSQL, Docker and a Razorpay-ready payment endpoint.

## Stack
- React + Vite + Framer Motion + Lucide
- Node.js + Express
- PostgreSQL
- JWT + bcrypt
- Razorpay-ready payments
- Docker / Render / Railway compatible

## Local development
1. Install Node.js 22+ and PostgreSQL, or use Docker.
2. Copy `.env.example` to `.env` and update `DATABASE_URL` and `JWT_SECRET`.
3. Run `npm install` and `npm --prefix client install`.
4. Run `npm run seed` once.
5. Run `npm run dev`.
6. Open the Vite URL shown in terminal (normally http://localhost:5173).

### Docker
`docker compose up --build`
Then open `http://localhost:5000`.

Demo admin: `admin@evently.app` / `Admin@123` (change it before production).

## Production deployment
Recommended beginner-friendly setup: deploy this repository to Render as a Web Service and create a managed PostgreSQL database. Set `DATABASE_URL`, `JWT_SECRET`, `CLIENT_URL`, and Razorpay keys as environment variables. Build command: `npm install && npm --prefix client install && npm run build`. Start command: `node server/index.js`.

For real payments, add Razorpay production keys and wire the checkout UI to `/api/payments/order` plus signature verification/webhooks before going live. Never commit secrets.

## Important production checklist
- Change the seeded admin password.
- Use a strong JWT secret.
- Configure HTTPS and a production domain.
- Add Razorpay signature verification + webhook handling before accepting real money.
- Add rate limiting, structured logging, email/SMS notifications, image storage, seat-map locking and refund/cancellation policies for a full commercial launch.
- Replace demo Unsplash images with licensed event artwork you own or have permission to use.

This project is an original event-booking experience; it is not affiliated with or a copy of BookMyShow.
