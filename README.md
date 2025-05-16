# Ticket Tango Event Manager

A full-stack event management application that allows users to browse, book, and manage events. The application features user authentication, event management, and booking functionality.

## Features

### User Features
- User registration and authentication
- Browse events with search and category filtering
- View detailed event information
- Book events
- View and manage personal bookings
- Responsive design for all devices

### Admin Features
- Admin dashboard for event management
- Create, edit, and delete events
- View all events in a table format
- Search and filter events

## Tech Stack

### Frontend
- React with TypeScript
- Vite for build tooling
- React Router for navigation
- Tailwind CSS for styling
- Shadcn UI components
- Context API for state management

### Backend
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- JWT Authentication
- Role-based authorization

## Project Structure

### Frontend Structure
```
ticket-tango-event-manager/
├── src/
│   ├── components/         # Reusable UI components
│   ├── contexts/          # React contexts (Auth, etc.)
│   ├── lib/               # Utility functions and API
│   ├── pages/             # Page components
│   │   ├── admin/        # Admin-specific pages
│   │   └── ...           # Other pages
│   ├── types/            # TypeScript type definitions
│   └── App.tsx           # Main application component
```

### Backend Structure
```
TicketTango.API/
├── Controllers/          # API endpoints
├── Data/                # Database context and configurations
├── DTOs/                # Data transfer objects
├── Models/              # Entity models
├── Services/            # Business logic
└── Program.cs           # Application entry point
```

## API Endpoints

### Authentication
- `POST /api/Auth/login` - User login
- `POST /api/Auth/register` - User registration

### Events
- `GET /api/Events` - Get all events
- `GET /api/Events/{id}` - Get event by ID
- `POST /api/Events` - Create new event (Admin only)
- `PUT /api/Events/{id}` - Update event (Admin only)
- `DELETE /api/Events/{id}` - Delete event (Admin only)

### Bookings
- `GET /api/Bookings/user` - Get user's bookings
- `POST /api/Bookings` - Create new booking

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- .NET 8 SDK
- SQL Server

### Frontend Setup
1. Navigate to the frontend directory:
   ```bash
   cd ticket-tango-event-manager
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

### Backend Setup
1. Navigate to the backend directory:
   ```bash
   cd TicketTango.API
   ```

2. Update the connection string in `appsettings.json`

3. Run database migrations:
   ```bash
   dotnet ef database update
   ```

4. Start the API:
   ```bash
   dotnet run
   ```

## Environment Variables

### Frontend
Create a `.env` file in the frontend root:
```
VITE_API_URL=https://localhost:60097/api
```

### Backend
Update `appsettings.json`:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Your_Connection_String"
  },
  "JwtSettings": {
    "SecretKey": "Your_Secret_Key",
    "Issuer": "Your_Issuer",
    "Audience": "Your_Audience"
  }
}
```

## Authentication

The application uses JWT (JSON Web Tokens) for authentication. The token is stored in localStorage and included in the Authorization header for all authenticated requests.

## Error Handling

Both frontend and backend implement comprehensive error handling:
- Frontend: Toast notifications for user feedback
- Backend: Global exception handling with appropriate HTTP status codes

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

