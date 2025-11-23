# BudgetBuddy

<div align="center">
  <h2 align="center">BudgetBuddy</h2>
  <p align="center">
    An app designed to help you manage your personal finances efficiently.
    <br />
    <a href="https://github.com/your-username/BudgetBuddy/"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://your-live-app-url.com/">View Demo</a>
    ·
    <a href="https://github.com/your-username/BudgetBuddy/issues">Report Bug</a>
    ·
    <a href="https://github.com/your-username/BudgetBuddy/issues">Request Feature</a>
  </p>
</div>

## Introduction

BudgetBuddy is a personal finance management application designed to help users track and manage their expenses, set budgets, and visualize their spending habits through charts and graphs. It is built with the MERN stack (MongoDB, Express, React, Node.js) and aims to provide a simple and intuitive interface for better financial management.

## Key Features

- Track income and expenses
- Set monthly or annual budgets
- Visualize spending patterns with graphs
- Categorize expenses (e.g., Food, Transportation, Entertainment)
- Secure authentication and user management
- Responsive design for desktop and mobile
- Automated Expense Entry from Bill Images: Upload bill images to auto-populate expense details
- Admin Functionalities to manage users

## Technologies Used

This project was created using the following technologies:

#### Frontend
- React.js
- Redux (for state management)
- Axios (for making API calls)
- Material UI (for UI components)
- Chart.js (for visualizing data)
- React-chartjs-2 (React wrapper for Chart.js)
- date-fns (for date formatting)

#### Backend
- Express.js
- Node.js
- JWT (for authentication)
- bcryptjs (for password hashing)
- Mongoose (for interacting with MongoDB)
- Multer (for file uploads)
- Tesseract.js (for OCR - reading text from bill images)
- Axios (for API requests)

#### Database
- MongoDB (MongoDB Atlas or Local MongoDB)

## Configuration and Setup

In order to run this project locally, simply fork and clone the repository or download as zip and unzip on your machine.

- Open the project in your preferred code editor.
- Go to terminal -> New terminal (If you are using VS Code)
- Split your terminal into two (run the client on one terminal and the server on the other terminal)

### Client Setup (Frontend)

In the first terminal:
```bash
$ cd client
$ npm install
$ npm install date-fns
$ npm start
```

**Important:** Before starting the client, make sure to remove any `mongoose` imports from client-side files, particularly:
- `client/src/components/dashboard/CalenderExpenseGraph.jsx`

Mongoose should only be used in the backend, not in React components.

### Backend Setup (Server)

In the second terminal (project root directory):

**Step 1: Install Dependencies**
```bash
$ npm install
$ npm install multer tesseract.js axios
```

**Step 2: Environment Configuration**

Create a `.env` file in the root directory and add the following:
```env
PORT=3001
MONGODB_URI=mongodb://localhost:27017/budgetbuddy
ACCESS_TOKEN_SECRET=your_secret_key_here
```

**MongoDB Setup Options:**

**Option A: Local MongoDB**
1. Install [MongoDB Community Edition](https://www.mongodb.com/try/download/community)
2. Use the URI: `mongodb://localhost:27017/budgetbuddy`

**Option B: MongoDB Atlas (Cloud)**
1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Get your connection string (format: `mongodb+srv://username:<password>@cluster.xxxxx.mongodb.net/budgetbuddy`)
4. Replace `<password>` with your actual password

**Generate ACCESS_TOKEN_SECRET:**

Run this command in your terminal to generate a secure random key:
```bash
node -e "console.log(require('crypto').randomBytes(256).toString('base64'));"
```

Copy the output and paste it as your `ACCESS_TOKEN_SECRET` value.

**Step 3: Start the Server**
```bash
$ npm start
```

You should see:
```
Server started in PORT | 3001
DB Connected
```

## Troubleshooting

### Common Issues:

1. **Module not found errors**: Make sure all dependencies are installed in both client and server directories
2. **Database connection failed**: Verify your `MONGODB_URI` is correct and MongoDB is running
3. **Port already in use**: Change the `PORT` value in `.env` to a different port (e.g., 3002)
4. **CORS errors**: Ensure the backend CORS configuration allows requests from your frontend URL

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License.
