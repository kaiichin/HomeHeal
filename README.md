# HomeHeal 🏥

HomeHeal is a professional digital rehabilitation platform designed to bridge the gap between clinical physical therapy and home-based recovery. It allows therapists to prescribe precise exercise protocols and enables patients to track their daily progress with clinical data.
Website link, hosted at Vercel: https://home-heal.vercel.app/

## 🔐 Login Credentials (Test Data)

**Therapist Account:**
- **Email**: `therapist@homeheal.com`
- **Password**: `password`

**Patient Account:**
- **Email**: `patient@homeheal.com`
- **Password**: `password`

---

## 🚀 Key Feature

### For Physical Therapists

- Exercise Library: Create and manage a comprehensive database of rehabilitation movements.
- Protocol Builder: Bundle exercises into specific recovery routines (Protocols) with custom sets and reps.
- Patient Assignment: Assign digital protocols to patients with set durations (e.g., 30 or 60 days).
- Clinical Monitoring: Monitor patient recovery in real-time through pain scores and difficulty ratings logged by the patient.

### For Patients

- Digital Prescriptions: Access clear instructions for home exercises directly from a mobile or desktop dashboard.
- Daily Session Logs: Record completed sessions along with critical recovery data:
    - Pain Score (0-10): Clinical metric for intensity tracking.
    - Difficulty Rating (1-5): Feedback on movement ease.
    - Personal Notes: Communication channel for feedback to the therapist.
- Progress Tracking: View history of completed sessions to maintain accountability.

## 🛠️ Tech Stack

- **Framework:** Laravel 11 (PHP)
- **Frontend:** Tailwind CSS & Alpine.js
- **Database:** MySQL (Hosted via Railway)
- **Hosting:** Vercel (Serverless)
- **Authentication:** Laravel Breeze (Customized for Role-Based Access)

## 📥 Installation & Setup

1.  **Clone the Repository**
    Open your terminal (Command Prompt or PowerShell) and navigate to where you want the project:
    ```bash
    git clone <repository-url>
    cd HomeHeal
    ```

2.  **Install Backend Dependencies**
    ```bash
    composer install
    ```

5.  **Install Frontend Dependencies**
    ```bash
    npm install && npm run build
    ```

6.  **Environment Setup:** Copy .env.example to .env and configure your Railway database credentials.
    Copy the example environment file:
    ```bash
    cp .env.example .env
    ```

7.  **Generate App Key**
    ```bash
    php artisan key:generate
    ```

8.  **Setup Database Tables & Data**
    Run migrations and seed the database with test data:
    ```bash
    php artisan migrate --seed
    ```

9.  **Start local Server**
    ```bash
    php artisan serve
    ```

---

## ☁️ Vercel Deployment Notes

HomeHeal is optimized for Vercel's serverless environment. To ensure stability, the following environment variables must be set in the Vercel Dashboard:

- ```bash SESSION_DRIVER=cookie ```: Required because the Vercel filesystem is read-only.
- ```bash LOG_CHANNEL=stderr ```: Ensures application logs are visible in Vercel's log viewer.
- ```bash APP_KEY```: Your generated Laravel application key.
- ```bash DB_HOST```: Your Railway Public Proxy host (do not use .internal hosts).


## 🛡️ Security & Authorization
-The project uses Laravel Policies to ensure data privacy:
- Therapists can only view and manage their own created protocols.
- Patients can only view protocols assigned specifically to them.
- Session logging is restricted to users with the patient role.
