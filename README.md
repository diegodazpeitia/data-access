# Go MySQL Play Project

This project is a simple Go application designed to interact with a MySQL database. It demonstrates basic database operations including querying, retrieving, and inserting data.

## Features

- Connects to a MySQL database.
- Queries for albums by artist.
- Retrieves an album by its ID.
- Adds a new album to the database.

## Setup

### Prerequisites

- Go (1.18 or later)
- MySQL
- Go MySQL Driver (`github.com/go-sql-driver/mysql`)

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/diegodazpeitia/data-access.git
   cd data-access
   ```

2. **Install dependencies:**

   ```bash
   go mod tidy
   ```

3. **Set up environment variables:**

   Create a `.env` file in the root of the project with your database credentials:

   ```plaintext
   DBUSER=your_mysql_user
   DBPASS=your_mysql_password
   ```

4. **Create the database schema:**

   Ensure you have a MySQL database named `recordings` and a table named `album` with the following structure:

   ```sql
   CREATE TABLE album (
     id BIGINT AUTO_INCREMENT PRIMARY KEY,
     title VARCHAR(255) NOT NULL,
     artist VARCHAR(255) NOT NULL,
     price DECIMAL(10, 2) NOT NULL
   );
   ```

### Usage

1. **Build and run the application:**

   ```bash
   go run main.go
   ```

2. **Expected output:**

   - Connects to the MySQL database and prints "Connected!" if successful.
   - Displays albums by artist "John Coltrane".
   - Shows details of the album with ID 2.
   - Adds a new album and prints its ID.

## Code Overview

- **`main.go`**: The main entry point of the application, responsible for database connection and CRUD operations.
- **Database Operations**:
  - `albumsByArtist(name string)`: Retrieves all albums by a specified artist.
  - `albumByID(id int64)`: Retrieves an album by its ID.
  - `addAlbum(alb Album)`: Adds a new album to the database.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
