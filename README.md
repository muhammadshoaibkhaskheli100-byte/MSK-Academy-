MSK ACADEMY — WEBSITE STARTER PACKAGE
=====================================

Included:
- index.html: responsive website preview with Student ID + password login interface.
- supabase_schema.sql: starting PostgreSQL/Supabase schema for a production backend.

DEMO LOGIN (PREVIEW ONLY)
- Student ID: MSK1001
- Password: student123
- Admin ID: ADMIN001
- Password: admin123

HOW TO PREVIEW ON ANDROID
1. Download and extract the ZIP using your phone's file manager.
2. Open the extracted folder and tap index.html. If your phone cannot preview it, upload the folder to GitHub Pages or ask someone to open it on a computer.
3. The demo login is hard-coded for preview only. Do NOT use these demo credentials for real students.

WHAT WORKS IN THIS PREVIEW
- Student ID/password demo login.
- Student dashboard and test catalogue.
- Three sample subject quizzes (Biology, Chemistry, Physics).
- Timed MCQs, next/previous navigation, auto-submit when time ends.
- Score calculation, answer explanations, review and browser-local result history.
- Admin preview panel.

WHAT IS NOT PRODUCTION-READY
This is a frontend preview, not yet a fully secure live exam service:
- Accounts and passwords are demo-only and hard-coded in the browser.
- Results are saved in the current browser's local storage, not a shared database.
- The admin panel is not securely protected.
- Payment processing and paid-test approval are not connected.
- Question answers are included in the sample frontend code and can be inspected.
- There is no secure server-side grading yet.

PRODUCTION BUILD CHECKLIST
1. Create a Supabase project and apply supabase_schema.sql.
2. Set up Supabase Auth. Store only auth user IDs, student IDs, names and roles in profiles; never store plaintext passwords.
3. Build a secure Student ID login flow (the backend resolves Student ID to the associated auth account without exposing private user data).
4. Add server-side/Edge Functions for test access checks, answer submission, grading, result storage, account creation and admin management.
5. Keep answer keys private; never send correct answers to the browser before the test is submitted.
6. Add payment verification. For manual bank/wallet payments, admin confirms the transaction in the actual account and then approves access. Never trust screenshots alone and never ask students for PINs or OTPs.
7. If integrating a payment gateway, use an officially supported merchant integration and verify payment status server-side.
8. Test database Row Level Security policies and authorization with separate student/admin accounts before launch.
9. Publish the frontend using HTTPS (e.g. GitHub Pages) and add a custom domain if desired.

SECURITY WARNING
Do not advertise this preview as a secure paid test platform. A production system needs a configured backend and security testing. The SQL is a starting point and should be reviewed before deployment.
