# Sling Syncer

This project syncs your current scheduled shift data from [Sling](getsling.com) to Google Calendar for the next month.

It allows you to bypass the restriction where you can't generate a calendar link in the free version of Sling.

## Prerequisites

- Node.js
- Docker
- Docker Compose
- Google API credentials

## Setup

1. **Clone the repository:**

    ```sh
    git clone https://github.com/DevGamer9991/sling-syncer.git
    cd sling-syncer
    ```

2. **Install dependencies:**

    ```sh
    npm install
    ```

3. **Create a .env file** in the project directory and add your environment variables:
   ```env
    SLING_TOKEN=your_sling_token
    ORG_ID=your_org_id
    USER_ID=your_user_id
    GOOGLE_CALENDAR_ID=your_google_calendar_id
    REDIRECT_URL=your_redirect_url
   ```

4. **Create Google API credentials:**

    - Go to the [Google Cloud Console](https://console.cloud.google.com/).
    - Create a new project or select an existing project.
    - Enable the Google Calendar API for your project.
    - Create OAuth 2.0 credentials and download the credentials.json file.
    - Set the redirect URL to either a public IP by port forwarding port 3000 or by using a local IP on the same network and same port.
    - Place the credentials.json file in the project directory.

5. **Build and run the Docker container:**

    ```sh
    docker-compose up --build
    ```

## Usage

The application will fetch shift data from the Sling API and create events in your Google Calendar. It will run the job daily at midnight.

## License

This project is licensed under the MIT License.
