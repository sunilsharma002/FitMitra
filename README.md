# FitMitra - Personal Fitness Management Application

FitMitra is a comprehensive fitness management application built with Spring Boot and Java Swing that helps users track their workouts, nutrition, goals, and daily health metrics.

## Features

### 1. User Management
- User registration with secure password hashing (SHA-256)
- User authentication and login
- Profile management (update personal information, fitness goals)

### 2. Dashboard
- Real-time fitness statistics (BMI, weight, workout consistency)
- Daily tracking for water intake, calories, and steps
- Meal time reminders based on current time
- Daily routine schedule
- Live workout reminders

### 3. Workout Management
- Create and manage custom workout routines
- Pre-defined workout plans
- Exercise timer with rest intervals
- Track exercises by day of the week
- View workout history and statistics

### 4. Nutrition Management
- Pre-defined meal database with nutritional information
- Create custom meals with detailed nutrition facts
- Track daily meal consumption
- View meal history
- Calculate total daily calories and macros

### 5. Goals Management
- Pre-defined fitness goals (weight loss, muscle gain, etc.)
- Create custom fitness goals
- Track goal progress
- Mark goals as complete

### 6. AI Chatbot Assistant
- Fitness advice and tips
- Workout recommendations
- Nutrition guidance
- Powered by OpenRouter AI API

## Technology Stack

- **Backend**: Spring Boot 3.4.5
- **Database**: MySQL 8.0
- **ORM**: Spring Data JPA with Hibernate
- **UI**: Java Swing with FlatLaf dark theme
- **Build Tool**: Maven
- **Java Version**: 17

## Prerequisites

- Java 17 or higher
- MySQL 8.0 or higher
- Maven (optional - project includes Maven Wrapper)

> **Quick Start:** See [QUICKSTART.md](QUICKSTART.md) for a 3-step setup guide!

## Database Setup

1. Install MySQL and start the MySQL service

2. Create a MySQL user (if not using root):
```sql
CREATE USER 'root'@'localhost' IDENTIFIED BY '1234';
GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost';
FLUSH PRIVILEGES;
```

3. The application will automatically create the database `fitmitra_01` on first run

4. Run the schema initialization:
```bash
mysql -u root -p1234 < src/main/resources/schema.sql
```

## Configuration

Update `src/main/resources/application.properties` if needed:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/fitmitra_01?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=1234
spring.jpa.hibernate.ddl-auto=update
```

## Installation & Running

### Quick Start

1. **Setup Database:**
```bash
mysql -u root -p1234 < src/main/resources/schema.sql
```

2. **Run Application:**

**Windows:**
```bash
mvnw.cmd spring-boot:run
```

**Linux/Mac:**
```bash
./mvnw spring-boot:run
```

### Using Maven (if installed)

```bash
mvn spring-boot:run
```

## Default Test User

After running the schema.sql, you can login with:
- **Username**: test
- **Password**: test (hashed as SHA-256)

## Project Structure

```
fitmitra_01/
├── src/
│   ├── main/
│   │   ├── java/com/fitmitra/
│   │   │   ├── config/          # Database configuration
│   │   │   ├── model/           # Entity classes
│   │   │   ├── repository/      # JPA repositories
│   │   │   ├── service/         # Business logic
│   │   │   ├── ui/              # Swing UI frames
│   │   │   └── FitMitraApplication.java
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── schema.sql       # Database schema
│   │       └── data.sql         # Initial data
│   └── test/
├── pom.xml
└── README.md
```

## Key Components

### Models
- **User**: User account information
- **Workout**: Exercise routines and schedules
- **Meal**: Nutrition and meal information
- **Goal**: Fitness goals and targets
- **DailyTracking**: Daily health metrics (water, calories, steps)

### Services
- **UserService**: User authentication and management
- **WorkoutService**: Workout CRUD operations
- **MealService**: Meal and nutrition management
- **GoalService**: Goal tracking and management
- **DailyTrackingService**: Daily metrics tracking

### UI Frames
- **LoginFrame**: User authentication
- **RegisterFrame**: New user registration
- **DashboardFrame**: Main dashboard with statistics
- **WorkoutFrame**: Workout management
- **NutritionFrame**: Meal and nutrition tracking
- **GoalsFrame**: Goal management
- **ProfileFrame**: User profile editing
- **ChatBot**: AI fitness assistant

## Features in Detail

### Dashboard Statistics
- Current weight and BMI with category
- Workout consistency (days per week)
- Top exercise by frequency
- Total exercises and reps
- Active fitness goal

### Daily Tracking
- Water intake (target: 3000ml)
- Calories consumed (target: 2200 kcal)
- Steps count (target: 10,000 steps)
- Update values throughout the day

### Workout Timer
- Start/stop exercise timer
- Automatic rest timer (5 minutes)
- Visual countdown display

## Troubleshooting

### Database Connection Issues
- Verify MySQL is running: `mysql -u root -p`
- Check credentials in `application.properties`
- Ensure database `fitmitra_01` exists

### Build Issues
- Clean Maven cache: `mvn clean`
- Update dependencies: `mvn dependency:resolve`
- Check Java version: `java -version` (should be 17+)

### UI Issues
- Ensure FlatLaf dependency is included
- Check for Swing EDT violations in logs

## Future Enhancements

- [ ] Export workout/meal data to PDF
- [ ] Social features (share progress with friends)
- [ ] Integration with fitness trackers
- [ ] Mobile app version
- [ ] Advanced analytics and charts
- [ ] Meal planning with recipes
- [ ] Video tutorials for exercises

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

## 📞 Support & Contact

For questions, issues, or contributions:
- GitHub: [https://github.com/sunilsharma002]
- Email: [sunil703354@gmail.com]
- LinkedIn: [https://www.linkedin.com/in/sunilsharma002/]

---
