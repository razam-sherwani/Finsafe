# FinSafe

FinSafe is a cross-platform personal finance app built with Flutter. It helps students track income and expenses, see balances and spending patterns, set budgets and savings goals, generate shareable PDF reports, and get contextual guidance—including optional bank linking (Plaid), receipt capture, and an in-app assistant (Fineas).

FinSafe

## Screenshots


| Welcome | Home | Transactions |
| ------- | ---- | ------------ |
| Welcome | Home | Transactions |



| Reports | Analysis | Spending & trends |
| ------- | -------- | ----------------- |
| Reports | Analysis | Spending          |



| Budgets & goals | Fineas assistant | Settings |
| --------------- | ---------------- | -------- |
| Budgets         | Fineas           | Settings |


Additional UI captures (authentication, alternate transaction and budget views, and supplementary screens) are in `[docs/readme/](docs/readme/)` (`image2.png`, `image4.png`–`image6.png`, `image9.png`, `image14.png`).

## Features

- **Home** — Welcome and balance overview, recent transactions, shortcuts to reports, profile access, and an optional guided tour of the screen.
- **Transactions** — Add, edit, and remove entries; search and filter; group by category; import via **Plaid** or add details manually; scan receipts using the device camera or gallery (ML-based text recognition and receipt helpers).
- **Budgets & savings** — Category budgets with progress, savings goals, and visual feedback.
- **Reports** — General, weekly, and monthly summaries with charts and tables; export and share **PDF** output.
- **Analytics & charts** — Spending by category, inflow/outflow, and period views (e.g. monthly, quarterly, custom ranges) using chart libraries.
- **Fineas assistant** — Chat-style help for finance questions and app usage (`chat_bubbles`, backend via Firebase Cloud Functions as configured in the project).
- **Settings** — Profile, appearance, help, sign-out, and related preferences.

**Sign-in:** Email/password and **Google** are implemented. Sign-in with Apple appears in the UI but is **not** wired up yet.

## Tech stack

- **Framework:** Flutter, Dart SDK `^3.6.1` (package name in `[pubspec.yaml](pubspec.yaml)`: `fbla_finance`).
- **Backend & data:** Firebase (Core, Authentication, Cloud Firestore, Storage, Cloud Functions).
- **Notable packages:** `fl_chart`, Syncfusion charts/PDF, `plaid_flutter`, Google ML Kit (document scanner, text recognition), `receipt_reader`, `pdf` / `share_plus` / `open_file`, `tutorial_coach_mark`, `google_sign_in`, and others as listed in `[pubspec.yaml](pubspec.yaml)`.

## Getting started

### Prerequisites

- [Flutter](https://docs.flutter.dev/get-started/install) (stable channel, compatible with Dart 3.6+)
- A Firebase project with Flutter apps registered for the platforms you target

### Setup

1. Clone the repository and open the project root.
2. Install dependencies:
  ```bash
   flutter pub get
  ```
3. **Firebase:** Ensure `[lib/firebase_options.dart](lib/firebase_options.dart)` matches your Firebase project (e.g. via [FlutterFire CLI](https://firebase.google.com/docs/flutter/setup)). Deploy or configure Firestore rules, Storage, and Cloud Functions as needed for your environment.
4. **Third-party services:** Configure **Plaid** (and any other API keys) in your own secure config or Firebase/backend setup. The repo does not ship production secrets (`[lib/backend/api_key.dart](lib/backend/api_key.dart)` is a placeholder).
5. Run the app:
  ```bash
   flutter run
  ```

## Project structure

- `[lib/pages/](lib/pages/)` — Screens (home, transactions, reports, settings, Plaid, receipt scanner, chat, etc.).
- `[lib/backend/](lib/backend/)` — Auth, Firebase-related helpers, PDF utilities, theming, and shared backend-oriented code.
- `[lib/util/](lib/util/)` — Reusable UI widgets and helpers.
- `[functions/](functions/)` — Firebase Cloud Functions (Node), if used for server-side logic.

## Contributors

- Srihaasa Karyampudi  
- Razam Sherwani  
- Abhinav Ivaturi

## License

FinSafe is released under the [MIT License](LICENSE).