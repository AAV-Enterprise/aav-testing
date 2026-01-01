# aav-testing

Reusable DevSecOps workflow for GitHub Actions:
- SAST: Semgrep (p/ci)
- Container scan: Trivy (SARIF upload)
- DAST: OWASP ZAP baseline (artifact reports)
- Optional SCA: Snyk (needs SNYK_TOKEN secret in caller repo)

Caller repo example:

```yaml
jobs:
  devsecops:
    uses: aav-andrei/aav-testing/.github/workflows/devsecops-reusable.yml@main
    with:
      compose_file: docker-compose.yml
      zap_target: http://localhost:8080
