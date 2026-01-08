# Sports Betting Records Management System

A sports betting records management system built with Vue 3 + Spring Boot, supporting CRUD operations for betting records, statistical analysis, and data visualization.

## Tech Stack

### Frontend
- Vue 3 + Composition API
- TypeScript
- Vite
- Element Plus
- Tailwind CSS
- Pinia (State Management)
- Vue Router
- ECharts (Charts)
- Axios (HTTP Client)

### Backend
- Spring Boot 2.7.18
- MyBatis Plus
- MySQL 8.0
- JWT Authentication
- BCrypt Password Encryption
- Maven

## Features

### User Management
- User registration/login
- JWT Token authentication
- User profile management
- Password modification

### Betting Records Management
- CRUD operations for betting records
- Batch operations support
- Multi-condition filtering
- Paginated display

### Statistical Analysis
- Overall statistics (bet count, amount, profit, etc.)
- Statistics by date
- Statistics by league
- Statistics by bet type
- Win rate analysis

### Data Visualization
- Profit trend charts
- League distribution pie charts
- Bet type statistics charts
- Date statistics bar charts

## Project Structure

```
sports_lottery_website/
├── frontend/                 # Frontend project
│   ├── src/
│   │   ├── components/      # Components
│   │   ├── views/          # Pages
│   │   ├── stores/         # Pinia state management
│   │   ├── router/         # Router configuration
│   │   ├── types/          # TypeScript type definitions
│   │   └── utils/          # Utility functions
│   ├── package.json
│   ├── vite.config.ts
│   ├── tsconfig.json
│   ├── tailwind.config.js
│   └── index.html
├── backend/                 # Backend project
│   ├── src/main/java/com/sports/lottery/
│   │   ├── controller/     # Controllers
│   │   ├── service/        # Service layer
│   │   ├── mapper/         # Data access layer
│   │   ├── entity/         # Entity classes
│   │   ├── dto/            # Data transfer objects
│   │   ├── config/         # Configuration classes
│   │   └── util/           # Utility classes
│   ├── src/main/resources/
│   │   ├── mapper/         # MyBatis XML mapping files
│   │   ├── sql/            # Database scripts
│   │   └── application.yml # Configuration file
│   └── pom.xml
└── README.md
```

## Quick Start

### Requirements
- Node.js 16+
- Java 8+
- MySQL 8.0+
- Maven 3.6+

### Database Setup

1. Create MySQL database:
```sql
CREATE DATABASE sports_lottery DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

2. Execute initialization script:
```bash
mysql -u root -p sports_lottery < backend/src/main/resources/sql/schema.sql
```

### Backend Setup

1. Navigate to backend directory:
```bash
cd backend
```

2. Modify database configuration (if needed):
Edit the database connection information in `src/main/resources/application.yml`.

3. Compile and start:
```bash
mvn clean compile
mvn spring-boot:run
```

Backend service will start at http://localhost:8080

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start development server:
```bash
npm run dev
```

Frontend application will start at http://localhost:5173

## API Endpoints

### User Related
- `POST /api/user/register` - User registration
- `POST /api/user/login` - User login
- `GET /api/user/info` - Get user information
- `PUT /api/user/info` - Update user information
- `PUT /api/user/password` - Change password

### Betting Records Related
- `GET /api/betting/records` - Paginated query of betting records
- `POST /api/betting/records` - Add betting record
- `POST /api/betting/records/batch` - Batch add betting records
- `PUT /api/betting/records/{id}` - Update betting record
- `DELETE /api/betting/records/{id}` - Delete betting record
- `DELETE /api/betting/records/batch` - Batch delete betting records

### Statistics Related
- `GET /api/betting/statistics` - Get user statistics
- `GET /api/betting/statistics/daily` - Get daily statistics
- `GET /api/betting/statistics/league` - Get league statistics
- `GET /api/betting/statistics/bettype` - Get bet type statistics

## Default Accounts

The system initializes with the following test accounts:

- Username: `admin`, Password: `123456`
- Username: `testuser`, Password: `123456`

## Development Notes

### Frontend Development
- Use Vue 3 Composition API for components
- Use TypeScript for type safety
- Use Element Plus component library
- Use Tailwind CSS for styling
- Use Pinia for state management

### Backend Development
- Use Spring Boot 2.7.18 (Java 8 compatible)
- Use MyBatis Plus for data access
- Use JWT for authentication
- Use BCrypt for password encryption
- Follow RESTful API design principles

## Deployment

### Frontend Deployment
```bash
cd frontend
npm run build
```
Deploy the `frontend/dist` directory to your web server.

### Backend Deployment
```bash
cd backend
mvn clean package
java -jar target/lottery-backend-1.0.0.jar
```

## License

MIT License

## Contributing

Issues and Pull Requests are welcome to improve this project.