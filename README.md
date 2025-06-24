<div align="center">

<h1 align="center">Student Exam Score Predictor</h1>

<p align="center">
    <strong>A system for predicting student exam score</strong>
</p>

[![en](https://img.shields.io/badge/lang-en-red.svg)](./README.md)

</div>

## Table of Contents

- [Table of Contents](#table-of-contents)
- [About](#about)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
  - [Connect with me on LinkedIn](#connect-with-me-on-linkedin)
  - [Fork and clone the repository](#fork-and-clone-the-repository)
  - [Project Structure](#project-structure)
- [Build and Run with Docker Compose](#build-and-run-with-docker-compose)
  - [Prerequisites](#prerequisites)
  - [Building and Starting the Application](#building-and-starting-the-application)
- [License](#license)

## About
This project consists of a **Machine Learning** application developed to **predict students’ exam scores** based on several behavioral and health factors. The solution is delivered as an **interactive** **web application using Streamlit**, allowing users to input data and obtain predictions in real time.

## Features

- **Interactive Frontend:** Web interface for displaying air quality data.
- **RESTful API Backend:** Service for data processing and hosting prediction models.
- **ML Model Integration:** Loads a prediction model (`Air_Quality.pkl`) for data analysis.
- **Docker Compose Orchestration:** Simplifies setting up and running all services (frontend and backend) in an isolated environment.
- **CRUD Operations (planned):** For managing user data and monitoring stations.

## Technologies Used

- **Python 3.12:** The core programming language for application logic and machine learning development.
- **Streamlit:** For creating the interactive and user-friendly web interface.
- **Scikit-learn / NumPy / Joblib:** Essential libraries used for machine learning model development, data manipulation, and model persistence.
- **Docker:** For containerizing the application, ensuring environmental consistency and portability.
- **Docker Compose:** For orchestrating and managing the application's services, simplifying the deployment process.

## Contributing
We welcome contributions! If you'd like to help improve this project, please follow the guidelines below.

### Connect with me on LinkedIn

1. Connect with Caio Brayner [LinkedIn](https://www.linkedin.com/in/caiogomesbrayner).

### Fork and clone the repository

1. Fork the repository [(click here to fork now)](https://github.com/Caio-GBrayner/student-habits-vs-academic-performance)
2. Clone your fork: `git clone https://github.com/Caio-GBrayner/student-habits-vs-academic-performance`
3. Create a new branch for your changes: `git checkout -b feature/my-new-feature`
4. Push your commits: `git commit -m "Adds new feature"`
5. Push your changes to your fork: `git push origin feature/my-new-feature`
6. Submit a new Pull Request to the main repository.

### Project Structure
The project structure is organized as follows:
```
student-habits-vs-academic-performance/
├── .dockerignore                          # Files and folders to be ignored by Docker during build
├── docker-compose.yml                     # Defines and orchestrates Docker services (your Streamlit app)
├── README.md                              # Main project documentation
│
├── Deploy/                                # Contains essential files for the Streamlit application deployment
│   ├── app.py                             # The main code for your Streamlit application
│   ├── best_model.pkl                     # The trained Machine Learning model (Joblib format)
│   ├── requirements.txt                   # Python dependencies for the Streamlit application
│   └── Dockerfile                         # Instructions to build the Docker image for the service
│
└── EDA/                                   # Contains files for Exploratory Data Analysis and model training
    ├── student-habits-vs-academic-performance.ipynb # Jupyter Notebook with EDA and model training steps
    └── student_habits_performance.csv     # The dataset used for analysis and training

```
## Build and Run with Docker Compose

To get the system up and running, you'll need Docker and Docker Compose installed.

### Prerequisites

1. Make sure you have the following tools installed on your machine:

    - **Docker Engine:** [Installation instructions](https://docs.docker.com/engine/install/)
    - **Docker Compose:** Usually comes bundled with Docker Desktop. If not, [install it separately.](https://docs.docker.com/compose/install/)

### Building and Starting the Application
Follow these steps to build the images and start the services:

1. **Navigate to the project's root directory** in your terminal (where `docker-compose.yml is located`):

```bash
    cd /path/to/student-habits-vs-academic-performance/
```
2. **Build the images and start the containers:**

```bash
    docker compose up --build
```
- The `--build` command will ensure the images are built (or rebuilt if there are changes in the Dockerfiles).
- This process may take a few minutes the first time, as Docker will download base images and install dependencies.

3. **Access the application:**
Once the containers are running, you can access the Streamlit frontend in your browser at:

`http://localhost:8501/`

4. **Stop the application:**
To stop and remove containers (but keep the built images), use:

```bash
    docker compose down 
```
To stop and remove containers, networks, and images (for a complete cleanup or rebuilding from scratch):

```bash
  docker compose down --volumes --rmi all  
```

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for more details.