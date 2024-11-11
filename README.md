# Hello Project: Django REST API for Contact Management

The Hello Project is a Django-based REST API designed to manage contact form submissions. It allows users to submit and store their contact information, including name, email, and message, through a single API endpoint. This project is ideal for integrating into applications that require contact form data collection, providing a straightforward, scalable API with JSON responses.

---

## Features

- **Contact Form Submission**: Users can submit their contact details (name, email, and message) via the API.
- **JSON Responses**: API responses are returned in JSON format for compatibility with web and mobile applications.
- **Error Handling**: Provides detailed error messages for invalid submissions or decoding errors.
- **Simple and Extensible**: Designed as a minimal REST API, it can be easily extended to support additional contact fields or functionalities.

---

## Project Structure

- **Model**:
  - `Contact`: Stores contact submissions with fields for `name` (stored as `title`), `email`, and `message` (stored as `description`).
- **Serializer**:
  - `ContactSerializer`: Converts `Contact` model instances to JSON and validates input data.
- **API View**:
  - `ContactAPIView`: A class-based view that processes contact form submissions and validates incoming data.

---

## Getting Started

### Prerequisites

- Python 3.x
- Django and Django REST Framework (to install via `requirements.txt`)

### Installation

1. **Clone the Repository**:
    ```bash
    git clone <repository-url>
    cd hello_project
    ```

2. **Install Dependencies**:
    Install the required Python packages:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run Database Migrations**:
    Set up the SQLite database:
    ```bash
    python manage.py migrate
    ```

4. **Start the Server**:
    Run the Django development server:
    ```bash
    python manage.py runserver
    ```

The API will be available at `http://127.0.0.1:8000/contact/`.

---

## API Documentation

### Endpoint

The Hello Project provides a single endpoint for handling contact submissions:

- **POST /contact/**: Submits a new contact entry. Required fields are:
  - `name`: Name of the user submitting the form.
  - `email`: User's email address.
  - `message`: Message content from the user.

### Example API Request

To submit a new contact entry, send a `POST` request to `/contact/` with a JSON payload:

```json
POST /contact/
{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "message": "Hello, I have an inquiry."
}
