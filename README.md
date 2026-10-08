# SecurePipeline

Jenkins-based DevSecOps pipeline: build, test, SAST (SonarQube), SCA (OWASP Dependency-Check),
container scan (Trivy), security gate, and deployment of a small Flask app.

## Run locally

    python3 -m venv venv && . venv/bin/activate
    pip install -r requirements-dev.txt
    pytest -v
    python app.py            # http://127.0.0.1:5000

## Run in Docker

    docker build -t securepipeline-demo:local .
    docker run -d --name securepipeline-demo -p 8081:5000 securepipeline-demo:local
    curl http://localhost:8081/health

## Endpoints

- `GET /` : application message
- `GET /health` : health check (HTTP 200)
