# 🌐 Hosted Backend

The backend is already deployed and available at:

```text
https://seapedia.zeabur.app
```

If you only want to use the application, **no local backend setup is required**.

The instructions below are only for developers who want to run the backend locally.

---

# 💻 Local Installation & Setup

## 1. Clone the Repository

```bash
git clone <repository-url>
cd <project-folder>
```

---

## 2. Install Dependencies

```bash
npm install
```

---

## 3. Configure Environment Variables

Copy the example environment file:

```bash
cp .env_example.local .env
```

Then update the values in `.env` to match your local PostgreSQL configuration.

---

## 4. Create the Database

Create a PostgreSQL database using the name specified in your `.env` file.

Example:

```text
compfest_18_db
```

---

## 5. Set Up the Database

If you have modified the TypeORM entities and need a new migration, generate one:

```bash
npm run migration:generate
```

Run the migrations:

```bash
npm run migration:run
```

Seed the database:

```bash
npm run seed
```

---

## 6. Start the Backend

```bash
npm run start:dev
```

The API will be available at:

```text
http://localhost:3000
```

---

# 🚀 Local Development Workflow

```text
Clone Repository
        │
        ▼
npm install
        │
        ▼
Copy .env_example.local → .env
        │
        ▼
Configure PostgreSQL
        │
        ▼
Create Database
        │
        ▼
(Optional) npm run migration:generate
        │
        ▼
npm run migration:run
        │
        ▼
npm run seed
        │
        ▼
npm run start:dev
```

> **Note**
>
> `npm run migration:generate` is **only required** when you've modified the TypeORM entities and need to create a new migration.
>
> If you're simply setting up the project from the repository, you can skip this step and run:
>
> ```bash
> npm run migration:run
> ```
