# VitalEdge

A Windows desktop health and fitness application built with VB.NET and Windows Forms. Track your BMI, monitor activities, earn HealthPoints, and stay updated with health news and events. Built for Oh My Code (OMC) May 2024 Competition.

## Features

- **User Authentication** - Secure login and registration with BCrypt password hashing
- **BMI Calculator** - Calculate Body Mass Index with categorized results (Underweight, Normal, Overweight, Obesity)
- **Activity Tracker** - Track running and walking activities, calculate calories burned
- **HealthPoints System** - Earn points through activities that can be used as discount vouchers for health events
- **Health News & Events** - Stay updated with curated health articles and upcoming fitness events
- **User Profile** - Manage your profile picture and account settings

## Screenshots

| ![1](./Resources/Images/Screenshots/1.jpg) | ![2](./Resources/Images/Screenshots/2.jpg) | ![3](./Resources/Images/Screenshots/3.jpg) |
| ------------------------------------------ | ------------------------------------------ | ------------------------------------------ |
| ![4](./Resources/Images/Screenshots/4.jpg) | ![5](./Resources/Images/Screenshots/5.jpg) | ![6](./Resources/Images/Screenshots/6.jpg) |
| ![7](./Resources/Images/Screenshots/7.jpg) | ![8](./Resources/Images/Screenshots/8.jpg) | ![9](./Resources/Images/Screenshots/9.jpg) |

## Tech Stack

- **Language:** VB.NET
- **Framework:** .NET 8.0 Windows Forms
- **Database:** MySQL
- **Libraries:**
  - [BCrypt.Net-Next](https://www.nuget.org/packages/BCrypt.Net-Next/) - Password hashing
  - [FontAwesome.Sharp](https://www.nuget.org/packages/FontAwesome.Sharp/) - Icons
  - [MySql.Data](https://www.nuget.org/packages/MySql.Data/) - MySQL connectivity

## Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [MySQL Server](https://dev.mysql.com/downloads/mysql/)
- Visual Studio 2022 (recommended)

## Database Setup

1. Create a MySQL database named `vitaledge`
2. Create the `users` table:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    healthpoints INT DEFAULT 0,
    profile_picture LONGBLOB
);
```

3. Update the connection string in the source files if needed:

```
server=localhost;user id=root;password=1234;database=vitaledge
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/amirshahrani/VitalEdge.git
```

2. Open `VitalEdge.sln` in Visual Studio

3. Restore NuGet packages:

```bash
dotnet restore
```

4. Build and run the application:

```bash
dotnet run
```

## Project Structure

```
VitalEdge/
├── Forms/                  # Application forms
│   ├── formCalculator.vb   # BMI calculator
│   ├── formHome.vb         # Main navigation hub
│   ├── formLogin.vb        # User login
│   ├── formSignin.vb       # User registration
│   ├── formForgot.vb       # Password reset
│   ├── formNews.vb         # Health news & events
│   ├── formProfile.vb      # User profile management
│   ├── formResult.vb       # BMI results display
│   ├── formTracker.vb      # Activity tracking
│   └── formWelcome.vb      # Welcome screen
├── Helper/
│   └── FontHelper.vb       # Custom font loader
├── Resources/
│   ├── Fonts/              # Custom fonts (Inter)
│   └── Images/             # App icons and images
├── formMain.vb             # Main application form
├── User.vb                 # User data module
└── VitalEdge.vbproj        # Project file
```

## Usage

1. **Register** - Create a new account with username, email, and password
2. **Login** - Access your account with email and password
3. **Home** - View your personalized welcome screen
4. **BMI Calculator** - Enter your age, height, and weight to calculate BMI
5. **Activity Tracker** - Log your running or walking distance to earn HealthPoints
6. **News** - Browse health articles and upcoming fitness events
7. **Profile** - Update your profile picture or log out
