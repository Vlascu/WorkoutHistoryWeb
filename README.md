# TrackIt
Web app where you can track you gym workouts and your bodyweight over time.

This is a Spring Boot application integrated with PostgreSQL as the database.

Users can:
- Record and view workouts.
- Weight loss / increase performance over time.
- Calculate their BMI.

---

## Prerequisites
- Java 11 or higher
- Maven 3.6 or higher
- PostgreSQL installed (steps below)
- An IDE (e.g., IntelliJ IDEA, Eclipse) or a text editor
- Git installed (optional)

---

## Steps to Set Up PostgreSQL

1. **Download and Install PostgreSQL**
   - Go to the [PostgreSQL Downloads page](https://www.postgresql.org/download/).
   - Select your operating system and follow the installation instructions.
   - During installation, set a username and password for the PostgreSQL administrator account (`postgres` by default).

2. **Start PostgreSQL Server**
   - Open the PostgreSQL service or use the command:
     ```bash
     pg_ctl -D "path_to_data_directory" start
     ```
   - Replace `path_to_data_directory` with the path where PostgreSQL stores its data files.

3. **Create a Database**
   - Access the PostgreSQL shell:
     ```bash
     psql -U postgres
     ```
     Replace `postgres` with your administrator username.
   - Create a new database for the project:
     ```sql
     CREATE DATABASE TrackIt;
     ```

---

## Configure the Spring Boot Application

1. **Navigate to the `application.properties` or `application.yml` File**
   - Open `src/main/resources/application.properties` (or `.yml` if using YAML).

2. **Update the PostgreSQL Configuration**
   - Modify the file to include the PostgreSQL database details:
     ```properties
     spring.datasource.url=jdbc:postgresql://localhost:5432/TrackIt
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     spring.jpa.hibernate.ddl-auto=update
     spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
     ```
     Replace:
     - `your_username` with your PostgreSQL username.
     - `your_password` with your PostgreSQL password.

3. **Verify Database Connection**
   - Ensure PostgreSQL is running and the details provided in the configuration file are correct.

---

## Build and Run the Application

1. **Clone the Repository (Optional)**
   - If the project is hosted on GitHub, clone it:
     ```bash
     git clone https://github.com/Vlascu/TrackIt.git
     ```
   - Navigate to the project directory:
     ```bash
     cd your-repository
     ```

2. **Build the Project**
   - Run the Maven command to build the application:
     ```bash
     mvn clean install
     ```

3. **Run the Application**
   - Start the Server Spring Boot application:
     ```bash
     mvn spring-boot:run
     ```
   - Alternatively, run the generated JAR file:
     ```bash
     java -jar target/your-application.jar
     ```
   - Open the Angular Client app and run:
     ```bash
     ng serve -o
     ```
