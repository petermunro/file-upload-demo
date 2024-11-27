# Docker Volume Demo - File Upload Application

This is a simple web application that demonstrates Docker volumes by providing a file upload interface. Files uploaded through the web interface are stored in a directory that can be mounted as a Docker volume.

## Features

- Drag and drop file upload
- List of uploaded files with size and modification date
- File download functionality
- Real-time updates of the file list
- Modern, responsive UI

## Running with Docker

1. Build the Docker image:
```bash
docker build -t file-upload-demo .
```

2. Run the container with a volume mount:
```bash
docker run -p 5000:5000 -v $(pwd)/uploads:/app/uploads file-upload-demo
```

This will:
- Map port 5000 from the container to your host
- Mount the local `uploads` directory to `/app/uploads` in the container
- Start the application

3. Access the application at http://localhost:5000

## Running Locally (Development)

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Run the application:
```bash
python app.py
```

3. Access the application at http://localhost:5000

## Volume Persistence

The `/app/uploads` directory in the container is designed to be mounted as a volume. All files uploaded through the web interface will be stored in this directory and persist even if the container is stopped or removed, as long as the volume mount is maintained. 