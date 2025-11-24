# minimal-laravel-v1

## Overview

A minimal bulletin board system (BBS) built with Laravel 12. This application provides basic functionality for creating posts and adding comments, demonstrating fundamental CRUD operations in Laravel.

Features:
- Create, read, update, and delete posts
- Add and delete comments on posts
- Simple and clean UI

## Tech Stack

- **Framework**: Laravel 12.x
- **Language**: PHP 8.2+
- **Database**: MySQL
- **Frontend**: Blade Templates
- **Development Tools**:
  - Laravel Sail (Docker environment)
  - Laravel Pint (Code style)
  - Laravel Pail (Log viewer)
  - PHPUnit (Testing)

## Setup

1. Clone the repository

2. Install dependencies:
```bash
composer install
npm install
```

3. Copy the environment file:
```bash
cp .env.example .env
```

4. Generate application key:
```bash
php artisan key:generate
```

5. Configure your database in `.env`:
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

6. Run migrations:
```bash
php artisan migrate
```

## Usage

```bash
./vendor/bin/sail up -d
./vendor/bin/sail down

./vendor/bin/sail mysql laravel
./vendor/bin/sail tinker
```

Start the development server:

```bash
# Using built-in server
php artisan serve

# Or using the dev script (runs server, queue, logs, and vite)
composer dev
```

Access the application at `http://localhost:8000` (or `http://localhost` when using Sail)

### Available Routes
- `/` - List all posts
- `/posts/create` - Create a new post
- `/posts/{id}` - View post details with comments
- `/posts/{id}/edit` - Edit a post
- Post and comment deletion via forms

## Directory Structure

```
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── PostController.php      # Post CRUD operations
│   │   │   └── CommentController.php   # Comment operations
│   │   └── Requests/
│   │       └── PostRequest.php         # Post validation
│   └── Models/
│       ├── Post.php                    # Post model
│       └── Comment.php                 # Comment model
├── database/
│   ├── migrations/                     # Database migrations
│   └── seeders/                        # Database seeders
├── resources/
│   └── views/
│       ├── components/
│       │   └── layout.blade.php        # Base layout
│       ├── posts/                      # Post views
│       └── index.blade.php             # Home page
└── routes/
    └── web.php                         # Web routes
```

## License

This repository is for personal/private use only.
