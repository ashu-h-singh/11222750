Title: URL Shortener Web Application
📌 Project Purpose
The main goal of this project is to create a full-stack web application where users can:

Convert long URLs into short, unique links.

Customize the shortened link with their own shortcode.

Set an expiration time for the short link.

View analytics, such as how many times each link was clicked, when, from where, and by whom.

The system is designed to mimic real-world applications like Bit.ly or TinyURL but implemented from scratch using modern technologies.

🧠 Core Features
✅ 1. Shorten Long URLs
The user can input up to 5 long URLs at a time.

They can optionally set:

A custom shortcode (like myLink123)

An expiry time in minutes

If no expiry is set, the system defaults to 30 minutes.

✅ 2. Redirect Functionality
When someone visits a shortened link (e.g., http://localhost:3000/abc123), they are automatically redirected to the original long URL.

This happens client-side using React Router (not through a server redirect like traditional backend apps).

✅ 3. Analytics / Statistics Page
Displays a list of all shortened URLs.

For each:

The original and shortened URL

When it was created

When it will expire

How many times it has been clicked

Click details also include:

Timestamp

Referrer (where the click came from)

Mock location (e.g., India)

✅ 4. Input Validation
Checks that URLs are in a valid format.

Custom shortcodes must be alphanumeric and within a specific length.

Expiry must be a valid integer.

✅ 5. Logging Middleware
Every action in the app is logged using a custom logging middleware (not console.log).

Logs include:

Request time

Type of action (shorten, click, redirect)

Status of the request

🧱 System Architecture
📍 1. Frontend (/client)
Built with React (JavaScript) using functional components and hooks.

Styled with Tailwind CSS for a responsive and modern look.

Uses React Router to manage:

Page navigation

Redirection for short URLs

Handles:

Input forms

Validation

Displaying shortened links and stats

Logging actions using middleware

📍 2. Backend (/server)
Built using Node.js and Express.js.

Contains:

API routes (/api/shorten, /r/:code, /api/stats)

Controllers for each action

Mongoose model for storing URL data in MongoDB

Middleware for:

Logging

Input validation

Handles:

URL creation and uniqueness

Redirect logic

Click logging

Analytics

🧱 System Architecture
📍 1. Frontend (/client)
Built with React (JavaScript) using functional components and hooks.

Styled with Tailwind CSS for a responsive and modern look.

Uses React Router to manage:

Page navigation

Redirection for short URLs

Handles:

Input forms

Validation

Displaying shortened links and stats

Logging actions using middleware

📍 2. Backend (/server)
Built using Node.js and Express.js.

Contains:

API routes (/api/shorten, /r/:code, /api/stats)

Controllers for each action

Mongoose model for storing URL data in MongoDB

Middleware for:

Logging

Input validation

Handles:

URL creation and uniqueness

Redirect logic

Click logging

Analytics

🧪 Testing & Logging
Logging middleware captures every request to track activity.

Simulated click tracking is done on redirect.

Data is stored and updated in MongoDB.

Middleware ensures consistent behavior across endpoints.

🛠️ How It Works – User Flow
User opens the site.

Enters a long URL and submits (can add expiry/custom shortcode).

Frontend sends request to backend.

Backend stores the data and returns the shortened URL.

User receives and copies the short link.

When anyone opens the short link:

App fetches the original URL

Increments click count

Logs click details

Redirects to the long URL

Stats page shows all past short links and usage info.
