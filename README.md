# Rebel Performance Website Booking System

A server-side fitness and training website built with Node.js, Express, EJS, and MongoDB. It allows visitors to view available training classes and lets members sign up, log in, and manage class bookings.

## Features

- View training classes, schedules, instructors, and prices
- Create and update member profiles
- Log in with a membership ID
- Create, view, find, update, and delete bookings
- Generate attendance reports for a trainee within a date range
- Server-rendered pages using EJS

## Technology Stack

- Node.js
- Express
- EJS
- MongoDB and Mongoose
- Morgan
- dotenv
- Moment.js

## Prerequisites

Make sure the following are installed:

- Node.js
- npm
- MongoDB running locally

The application connects to MongoDB at:

```text
mongodb://localhost:27017/rebel_performance
```

## Installation

Clone the repository and install the dependencies:

```bash
npm install
```

## MongoDB Setup

Start MongoDB locally, then create or use the `rebel_performance` database. Mongoose creates the `members` and `bookings` collections automatically when data is first added.

The connection configuration is currently in `app.js`:

```javascript
mongodb://localhost:27017/rebel_performance
```

## Running the Application

Start the server with:

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in a browser.

The port can be changed with an environment variable:

```bash
PORT=4000 npm start
```

On Windows PowerShell, use:

```powershell
$env:PORT=4000
npm start
```

## Main Routes

| Route | Description |
| --- | --- |
| `/` | Home page and training class catalogue |
| `/about` | About Rebel Performance |
| `/help` | Help and support page |
| `/members/signup` | Create a member profile |
| `/members/login` | Log in with a membership ID |
| `/booking` | View all bookings |
| `/booking/new` | Create a booking |
| `/booking/find` | Search for bookings |
| `/booking/update/:id` | Update a booking |
| `/report` | Generate an attendance report |

## Project Structure

```text
.
├── app.js                 # Express application and MongoDB setup
├── bin/
│   └── www                # HTTP server entry point
├── models/
│   ├── booking.js         # Booking Mongoose model
│   └── member.js          # Member Mongoose model
├── public/
│   ├── images/
│   └── stylesheets/
├── routes/
│   ├── booking.js         # Booking routes
│   ├── index.js           # Main website routes
│   ├── members.js         # Member routes
│   └── report.js          # Attendance report routes
├── views/
│   ├── pages/
│   ├── partials/
│   └── *.ejs              # Rendered website pages
├── training_classes.json  # Training class catalogue
├── package.json
└── package-lock.json
```

## Data Models

### Member

- Membership ID
- Trainee name
- Email address
- Phone number
- Creation and update timestamps

### Booking

- Trainee name
- Membership ID
- Class name
- Training date
- Card number, expiry date, and security code
- Creation and update timestamps

## Security Note

This project is intended as a server-side development exercise. Booking and member operations are not production-ready authentication or payment flows. Card details and membership passwords should not be collected or stored in an insecure manner in a real deployment.
