# Node DevSecOps Pipeline

This project is a simple Node.js API integrated with a DevSecOps CI pipeline using GitHub Actions.

It demonstrates how to:
- Lint code with ESLint
- Enforce security policies with Conftest
- Validate Kubernetes configuration
- Analyze dependencies and filesystem with Trivy
- Build and scan a Docker image

---

## Run locally

```bash
npm install
npm start
````

The API will be available at:

```
http://localhost:3000
```

---

## Run with Docker

```bash
docker build -t node-devsecops .
docker run -p 3000:3000 node-devsecops
```

---

## CI / Security Pipeline

The project includes a GitHub Actions pipeline that performs:

* ESLint (code quality)
* YAML linting
* Conftest (Kubernetes security policies)
* Trivy filesystem scan
* Trivy Docker image scan

---

## Trivy Reports

After each pipeline execution:

1. Go to the **Actions** tab in the repository
2. Open the latest workflow run
3. Scroll down to the **Artifacts** section
4. Download:

   * `trivy-fs-report`
   * `trivy-image-report`

These reports contain detected vulnerabilities in JSON format.
The pipeline does not fail if it detects vulnerabilities.