# Weather Dashboard Demo

This project demonstrates how to build a weather dashboard using Python and AWS. It fetches weather data from the OpenWeather API and saves it to an AWS S3 bucket. The application follows best practices for project structure, version control, and dependency management.

## Project Structure

weather-dashboard-demo/ │ ├── src/ │ ├── init.py │ └── weather_dashboard.py │ ├── tests/ │ ├── data/ │ ├── .env ├── README.md ├── requirements.txt


### Folders:

- **`src/`**: Contains all the main Python code.
- **`tests/`**: For unit tests.
- **`data/`**: Local storage for development testing.

### Files:

- **`__init__.py`**: Makes the directory a Python package.
- **`weather_dashboard.py`**: Main logic for fetching weather and interacting with AWS.
- **`requirements.txt`**: Lists all dependencies for the project.
- **`.env`**: Stores sensitive environment variables (e.g., API keys).

## Setup

### 1. Get API Key from OpenWeather

- Go to [OpenWeather API](https://openweathermap.org/api) and register to get an API key.

### 2. Set Up Project

- Clone the repository and navigate into the project folder:

```bash``` git init

```bash``` git branch -M main


- Add the following files to .gitignore to avoid tracking sensitive or unnecessary files:
  
```bash``` echo ".env" >> .gitignore

```bash``` echo "__pycache__/" >> .gitignore

```bash``` echo "*.zip" >> .gitignore


### 3. Install Dependencies

Create and activate a virtual environment, then install the required dependencies:

```bash``` pip install -r requirements.txt

### 4. Configure AWS Credentials

Run the following command to configure your AWS credentials:

```bash``` aws configure

### 5. Set Up Environment Variables

Create a .env file and add your API key and AWS bucket name:

```bash``` echo "OPENWEATHER_API_KEY=your-api-key" >> .env

```bash``` echo "AWS_BUCKET_NAME=weather-dashboard-${RANDOM}" >> .env


## Code Explanation

weather_dashboard.py

This Python script handles the following tasks:

- Fetch weather data from OpenWeather API.
- Save the data to an AWS S3 bucket.
- Create the S3 bucket if it doesn't exist.

Key Methods:

- create_bucket_if_not_exists(): Checks if the S3 bucket exists, and creates it if it doesn't.
- fetch_weather(city): Fetches weather data for a given city from the OpenWeather API.
- save_to_s3(weather_data, city): Saves the weather data to an S3 bucket.
  
### 6. Running the Script

To run the script:

```bash``` python3 src/weather_dashboard.py


### Sample Output

##### When you run the script, you'll see output like this:

Fetching weather for Philadelphia...

Temperature: 72°F

Feels like: 70°F

Humidity: 65%

Conditions: clear sky

Weather data for Philadelphia saved to S3!


