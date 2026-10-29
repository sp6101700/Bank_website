# SecureBank – Smart Banking & Automation Demo

> ⚠️ **Fictional educational demo.** No real money, bank accounts, RBI approvals, licences or deposit insurance are involved. All deposits, withdrawals and notifications are **simulated**.

A responsive banking demo website built as a college project. It is a single static file (`index.html`) – plain HTML, CSS and JavaScript, no build step. Data is stored in the browser's `localStorage`.

## Features
- Home, Services, About (FAQ + security tips), Contact, Login and Register pages
- Registration with validation, duplicate prevention, Customer ID and account number generation, hashed passwords (SHA-256 + salt, demo level)
- **OTP login verification**: after the password, a 6-digit OTP (valid 5 minutes, 3 attempts, resend supported) is generated. In demo mode the OTP is shown on screen and logged (masked) in the notification log – it is **not** actually sent
- Customer dashboard: demo balance, account info, recent transactions, notifications
- Deposit and withdrawal (simulated, ₹) with validation, insufficient-balance check, transaction ID and receipt (copy / print)
- Transaction history with search and filters by text, type and date
- Profile page
- Admin dashboard (role-protected): stats, customer search, account status management, all transactions, notification log, data reset
- Automatic notifications after registration, account creation, deposit and withdrawal – logged in **demo mode** (status "Simulated – not sent"); nothing is claimed as delivered

## Demo logins
| Role | Login | Password |
|---|---|---|
| Customer | `aarav@demo.in` | `Demo@1234` |
| Admin | `admin@securebank.demo` | `Admin@123` |

## Run locally
Just open `index.html` in a browser.

## Deploy on GitHub Pages
1. Create a new repository on GitHub (e.g. `securebank-demo`).
2. Upload `index.html`, `README.md`, `LICENSE` and `.gitignore` (Add file → Upload files → Commit).
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select branch `main` and folder `/ (root)`, then **Save**.
5. After a minute your site is live at `https://<your-username>.github.io/securebank-demo/`.

## Limitations
- Static site: there is no real backend or database, so data lives only in each visitor's browser.
- Real OTP / WhatsApp Cloud API / email / SMS delivery needs a server (Node.js + Express) because API tokens must never be placed in frontend code. Demo mode logs messages instead.

## Test checklist
1. Register a new user → success message with Customer ID and account number.
2. Try registering again with the same email → duplicate error.
3. Log in → enter the demo OTP shown on screen → dashboard. (Also try a wrong OTP and Resend OTP.) Deposit ₹1000 → receipt, balance and history update.
4. Withdraw more than the balance → rejected. Withdraw a valid amount → balance updates.
5. Check "Your notifications" on the dashboard.
6. Log in as admin → check customers, status change, transactions and notification log.

## License
MIT – for educational use.
