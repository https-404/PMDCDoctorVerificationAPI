
# PMDCDoctorVerificationAPI

This project provides an API to verify doctor's registration numbers against the Pakistan Medical Commission (PMC) database. It uses FastAPI for the web framework and Selenium for web scraping.

## Features

- Validate the format of the registration number.
- Scrape the PMC website to check the registration details.
- Return the doctor's details if found; otherwise, return an error message.

## Installation

### Prerequisites

- Python 3.7+
- Google Chrome browser
- ChromeDriver

### Steps

1. **Clone the repository:**

    ```bash
    git clone https://github.com/https-404/PMDCDoctorVerificationAPI.git
    cd PMDCDoctorVerificationAPI
    ```

2. **Create and activate a virtual environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install the dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

## Running the API

1. **Start the FastAPI server:**

    ```bash
    uvicorn main:app --reload
    ```

2. **API will be accessible at:**

    ```
    http://127.0.0.1:8000
    ```

## API Usage

### Endpoint

- **POST /check_registration/**

### Request Body

```json
{
    "reg_num": "123456-A"
}
```

### Response

- **Success** (200 OK)

    ```json
    {
        "registration_number": "123456-A",
        "name": "Dr. John Doe",
        "father_name": "Mr. Doe",
        "status": "Active"
    }
    ```

- **Invalid Registration Number Format** (400 Bad Request)

    ```json
    {
        "detail": "Invalid registration number format"
    }
    ```

- **Doctor Not Found** (404 Not Found)

    ```json
    {
        "detail": "Doctor details not found"
    }
    ```

- **Error** (500 Internal Server Error)

    ```json
    {
        "detail": "An error occurred"
    }
    ```

## Project Structure

```
PMDCDoctorVerificationAPI/
│
├── main.py                   # FastAPI application code
├── requirements.txt          # List of dependencies
├── README.md                 # Project documentation
│
└───venv/                     # Virtual environment directory
```

## Contributing

1. **Fork the repository**
2. **Create a new branch**

    ```bash
    git checkout -b feature_branch
    ```

3. **Make your changes**
4. **Commit your changes**

    ```bash
    git commit -m "Your commit message"
    ```

5. **Push to the branch**

    ```bash
    git push origin feature_branch
    ```

6. **Create a Pull Request**

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [FastAPI](https://fastapi.tiangolo.com/)
- [Selenium](https://www.selenium.dev/)
- [Uvicorn](https://www.uvicorn.org/)
- [webdriver-manager](https://pypi.org/project/webdriver-manager/)

## Contact

For any inquiries, please contact me at [https-404](https://github.com/https-404).
