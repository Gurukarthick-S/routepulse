
RoutePulse.txt
100%
# RoutePulse 🚍
### Smart Campus Transport Optimization System

RoutePulse is a MERN stack web application designed to improve campus transportation by monitoring vehicle capacity, tracking simulated vehicle locations, detecting scheduling conflicts, and recommending feasible transport plan adjustments.

The system compares an optimized transport plan against a fixed baseline to help evaluate improvements in transportation efficiency, passenger demand handling, and schedule reliability.

## 🎯 Project Objective

The objective of RoutePulse is to develop a smart campus transportation planning system that identifies operational issues and recommends practical improvements while respecting real-world transport constraints.

## ✨ Key Features

- **Transport Dashboard:** View transportation statistics and operational status.
- **Route Management:** Manage campus routes and their associated stops.
- **Vehicle Management:** Track vehicle availability and passenger capacity.
- **Schedule Management:** Organize trips and identify scheduling conflicts.
- **Passenger Demand Analysis:** Compare passenger demand with vehicle capacity.
- **Simulated GPS Tracking:** Display simulated vehicle movement and estimated arrival times.
- **Operational Alerts:** Identify overcrowding, capacity violations, and schedule issues.
- **Route Optimization:** Recommend feasible adjustments to routes, schedules, or vehicle assignments.
- **Baseline Comparison:** Compare the proposed plan against the original transport plan.
- **Constraint Validation:** Check that recommendations satisfy vehicle capacity, availability, travel-time, and scheduling requirements.

> Note: Features are implemented progressively. The availability of each feature depends on the current development stage.

## 🛠️ Tech Stack

### Frontend
- React.js
- Vite
- Axios
- React Router
- Lucide React
- Recharts
- CSS

### Backend
- Node.js
- Express.js
- Mongoose
- REST API

### Database
- MongoDB

### Development Tools
- Git and GitHub
- npm
- Nodemon
- Visual Studio Code

## 🏗️ System Architecture

```text
RoutePulse
│
├── client/                 # React frontend
│   ├── public/
│   └── src/
│       ├── services/
│       │   └── api.js
│       ├── App.jsx
│       ├── App.css
│       └── main.jsx
│
├── server/                 # Express backend
│   ├── config/
│   │   └── db.js
│   ├── app.js
│   ├── seed.js
│   ├── .env
│   └── package.json
│
├── .gitignore
└── README.md
```

The frontend communicates with the backend through REST API endpoints. The backend handles application logic and database operations, while MongoDB stores transportation data.

## ⚙️ Prerequisites

Install the following before running the application:

- Node.js and npm
- MongoDB local server or a MongoDB Atlas account
- Git (optional)
- Visual Studio Code (recommended)

## 🚀 Installation and Setup

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd routepulse
```

If the project already exists on your computer, open a terminal in the `routepulse` folder instead.

### 2. Install frontend dependencies

```bash
cd client
npm install
npm install axios react-router-dom lucide-react recharts
```

### 3. Install backend dependencies

Open another terminal:

```bash
cd routepulse/server
npm install
```

### 4. Configure environment variables

Create `server/.env`:

```env
PORT=5000
CLIENT_URL=http://localhost:5173
MONGODB_URI=mongodb://127.0.0.1:27017/routepulse
```

For MongoDB Atlas, replace the local MongoDB URI with your Atlas connection string.

Create `client/.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

**Important:** Never commit `.env` files or database credentials to GitHub.

### 5. Start the backend

From the `server` directory:

```bash
npm run dev
```

The backend should connect to MongoDB and start on port `5000`.

### 6. Start the frontend

From the `client` directory, run:

```bash
npm run dev
```

Vite will display the local frontend URL, typically:

```text
http://localhost:5173
```

## 🔍 Verify the Backend

Open the following URL in your browser:

```text
http://localhost:5000/api/health
```

The expected response is:

```json
{
  "message": "Server is running!"
}
```

If the backend cannot connect to MongoDB, verify that MongoDB is running and that `MONGODB_URI` is correct.

## 🧪 Seed the Initial Scenario

If `server/seed.js` has been configured with the sample campus transport scenario, run:

```bash
cd server
npm run seed
```

This creates or updates the example baseline scenario in MongoDB. The included routes, passenger demand, vehicle capacities, schedules, and simulated GPS records are sample data and should be replaced or adapted for the intended campus.

## 📊 Optimization Approach

RoutePulse follows a constraint-aware optimization workflow:

1. Load the original transport baseline.
2. Analyze passenger demand, vehicle capacity, schedules, and simulated vehicle positions.
3. Detect operational issues and constraint violations.
4. Generate candidate adjustments to vehicle assignments or trip schedules.
5. Validate each candidate against the required constraints.
6. Compare feasible candidates using operational metrics.
7. Present the selected recommendation and its trade-offs.
8. Compare the proposed plan against the unchanged baseline.

Hard constraints must be validated separately from the optimization score. A plan that violates a mandatory capacity or scheduling requirement must not be presented as a feasible recommendation.

## 📈 Evaluation Metrics

The system can evaluate plans using metrics such as:

- Passenger demand served
- Vehicle capacity utilization
- Overcrowding and capacity violations
- Estimated waiting time
- Schedule conflicts
- Estimated arrival-time accuracy
- Number of feasible trips
- Operational efficiency compared with the baseline

The final evaluation should use measured results from the implemented system rather than assumed improvements.

## 🔐 Security and Configuration

- Store credentials in environment variables.
- Do not commit database connection strings or secrets.
- Configure CORS for the frontend origin.
- Validate incoming API data.
- Add authentication and authorization before exposing protected operations.
- Use appropriate error handling for database and API failures.

## 🗺️ Future Enhancements

- Real-time GPS integration
- Live passenger demand collection
- Interactive route maps
- Advanced optimization algorithms
- Historical demand forecasting
- Authentication and role-based access
- Exportable reports and analytics
- Cloud deployment

## 👨‍💻 Project Information

**Project Name:** RoutePulse  
**Project Type:** Full-Stack Web Application  
**Category:** Smart Campus Transportation and Route Optimization  
**Development Approach:** Individual Project  
**Frontend:** React.js  
**Backend:** Node.js and Express.js  
**Database:** MongoDB

## 📄 License

This project is currently developed for educational and demonstration purposes. Add a suitable open-source license if you intend to distribute it publicly.
Displaying RoutePulse.txt.
