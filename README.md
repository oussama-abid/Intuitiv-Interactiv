# Digital Thesis Library

A platform where universities publish final theses so they can be found and read online, while each university keeps control over who may access what. It has three parts: a web app, a REST API and a mobile app.

Bachelor final project at **Intuitiv Groupe** (Tunisia), February to June 2022, developed as a team.

## Features

**For students and readers**
- Browse and search theses by institution, field, supervisor and company
- Submit a thesis for publication: PDF with cover image and, if available, patent and research files
- Request to borrow a document and read it online; downloading is blocked to protect the authors
- Follow requests and loans in the profile, with notifications when a request is approved or rejected

**For administrators**
- Approve or reject new accounts, thesis submissions and loan requests
- Set a maximum loan period and a limit on open requests per user
- Dashboard with charts on documents, requests and users
- Manage institutions, fields, supervisors, companies and criteria

**Mobile app**
- The same catalogue in a Flutter app, with a built-in PDF reader

## Tech stack

| Part | Folder | Stack |
|---|---|---|
| REST API | `backendlaravel/` | Laravel, PHP, MySQL, token authentication |
| Web app | `frontendproject/` | Vue.js 3, Vue Router, Axios, Chart.js, Bootstrap 5 |
| Mobile app | `mobile/project/` | Flutter, Dart, Dio, Syncfusion PDF viewer |

The remaining folders (`pluto`, `natone-html`, `sidebar-01`, `sidebar-09`) are HTML design templates the interface was based on.

## My contribution

- **REST API:** data model, migrations and CRUD for all entities, token login and protected routes
- **File uploads** for theses and submission requests, with validation of file types and dates
- **Approval flows** for accounts, submissions and loans, including loan limits and maximum loan days
- **Notifications** in the backend and the web app
- **Admin dashboard** in Vue.js with charts, search and filters
- **Flutter mobile app** and the contact form by email

## Run locally

**API**
```bash
cd backendlaravel
composer install
cp .env.example .env   # set your MySQL credentials
php artisan key:generate
php artisan migrate --seed
php artisan serve      # http://127.0.0.1:8000
```

**Web app**
```bash
cd frontendproject
npm install
npm run serve
```

**Mobile app**
```bash
cd mobile/project
flutter pub get
flutter run
```

The web and mobile apps expect the API at `http://127.0.0.1:8000`.
