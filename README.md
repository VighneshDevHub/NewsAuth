# NewsGuard AI

**NewsGuard AI** is an advanced news authenticity verification and key-phrase extraction platform. Leveraging cutting-edge technologies like Flask, PostgreSQL, Google Custom Search API, and Ollama's AI capabilities, this tool empowers users to evaluate the credibility of news articles. It provides a seamless user experience for analyzing news sources, extracting key phrases, and offering insights on the authenticity of the information being presented.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [License](#license)

## Features

- **News Authenticity Verification**: Analyze news articles for reliability using trusted source verifications.
- **Key Phrase Extraction**: AI-driven key phrase extraction using Ollama's model.
- **Search Integration**: Integrated Google Custom Search API to cross-reference news sources.
- **User Authentication**: Secure login and user management powered by Flask-Login and Flask-WTF.
- **Email Contact**: Built-in Flask-Mail functionality to allow users to get in touch.
- **Secure Forms**: CSRF protection for all forms.
- **PostgreSQL Support**: Persistent data storage using PostgreSQL and Flask-SQLAlchemy ORM.

## Tech Stack

- **Backend**: Python, Flask
- **Database**: PostgreSQL, Flask-SQLAlchemy
- **API Integration**: Google Custom Search API, Ollama
- **Email Service**: Flask-Mail
- **Security**: CSRF protection, Flask-WTF, Flask-Login

## Installation

Follow these steps to set up the project locally:

### Prerequisites

- Python 3.8+
- PostgreSQL
- Virtualenv (recommended)

### Steps

1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/newsguard-ai.git
    cd newsguard-ai
    ```

2. **Create Virtual Environment**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # For Linux/Mac
    venv\Scripts\activate     # For Windows
    ```

3. **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4. **Setup PostgreSQL Database**
   - Create a new PostgreSQL database:
     ```sql
     CREATE DATABASE newsguard_ai;
     ```

   - Configure the database connection URI in `config.py`:
     ```python
     SQLALCHEMY_DATABASE_URI = 'postgresql://username:password@localhost/newsguard_ai'
     ```

5. **Set Environment Variables**
   - Create a `.env` file with the following information:
     ```
     FLASK_APP=run.py
     FLASK_ENV=development
     SECRET_KEY=your_secret_key
     MAIL_USERNAME=your_email
     MAIL_PASSWORD=your_email_password
     ```

6. **Run Database Migrations**
    ```bash
    flask db upgrade
    ```

7. **Run the Application**
    ```bash
    flask run
    ```

Your application should now be running on `http://127.0.0.1:5000/`.

## Configuration

### Google Custom Search API
- Obtain an API key from Google Custom Search and add it to the configuration.

### Ollama Integration
- Integrate the Ollama key phrase extraction model following the provided API setup instructions.

### Email Configuration
- Configure Flask-Mail by setting up your email credentials in the `.env` file.

## Usage

Once the application is up and running:

1. **Register and Log In**: Sign up or log in to access the news verification and key phrase extraction features.
2. **Analyze News**: Submit a URL or paste a news article for verification. The app will cross-reference the article using Google Custom Search and extract key phrases using Ollama's model.
3. **View Results**: Check the credibility score, key phrases, and associated trusted sources.
4. **Contact Us**: Use the built-in contact form to send inquiries or feedback directly.

## Project Structure
<pre>
newsguard-ai/
│
├── app/                    
│   ├── __init__.py          # App Factory
│   ├── models.py            # Database Models
│   ├── routes.py            # Application Routes
│   ├── forms.py             # Flask-WTF Forms
│   └── utils.py             # Helper Functions (e.g., API calls)
│
├── migrations/              # Database Migrations
│
├── templates/               # HTML Templates
│
├── static/                  # Static Files (CSS, JS)
│
├── config.py                # Configuration File
├── run.py                   # Entry point to start Flask App
├── requirements.txt         # Python Dependencies
├── README.md                # Project ReadMe
└── .env                     # Environment Variables

</pre>