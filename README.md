# Stripe Checkout Demo – Built with Next.js & Stripe

This project is a working demo of a secure Stripe payment integration using *Next.js (App Router), **React, and **Tailwind CSS*. It demonstrates the full Stripe PaymentIntent flow, including frontend form, backend API interaction, and post-payment confirmation.

---

## 💳 Core Features

1. *Checkout Page:*  
   The homepage (/) presents a checkout interface for a fixed payment ($49.99), powered by Stripe's secure components.

2. *Stripe Integration:*
   - Uses @stripe/react-stripe-js and @stripe/stripe-js for client-side payment handling.
   - A PaymentIntent is created via a backend API route.
   - Users fill in their details through Stripe’s UI and confirm the payment.

3. *Backend Logic (API Route):*
   - /api/create-payment-intent creates a secure PaymentIntent using the Stripe Node.js SDK.
   - The client_secret is passed to the client for rendering the payment form.

4. *Success Page:*  
   On successful payment, the user is redirected to /payment-success, which confirms the transaction.

---

## 🛠 Technologies Used

- *Framework:* Next.js (App Router)
- *Frontend:* React, Tailwind CSS
- *Backend:* Node.js (API routes in Next.js)
- *Payment API:* Stripe
- *Language:* TypeScript

---

## 📁 Project Structure

app/ ├── page.tsx                     → Main checkout page ├── payment-success/page.tsx     → Thank you page after successful payment ├── api/create-payment-intent/   → API route to create Stripe PaymentIntent

components/ ├── CheckoutPage.tsx             → Payment form logic (client-side)

lib/ ├── convertToSubcurrency.ts      → Helper to convert dollars to cents (e.g. $49.99 → 4999)

---

## ⚙ How It Works

1. User lands on the checkout page and initiates payment.
2. The frontend requests a client_secret from the server (via the API).
3. Stripe’s embedded PaymentElement collects the user’s card info.
4. Stripe handles secure transaction processing.
5. On success, user is redirected to /payment-success.

---

## ❓ Notes

- The dependency anchor-pki exists in package.json but is not used in this project. It can be safely removed.
- Amount is hardcoded ($49.99) but can be adapted for dynamic input.
- This demo is *not production-ready* but serves as a foundation for integrating Stripe with Next.js.

---

## 🚀 Deployment

You can deploy this project easily on [Vercel]
