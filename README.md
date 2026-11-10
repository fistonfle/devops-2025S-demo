# devops-2025S-demo
class demo for devops class
pretending to add more details to the readme
completed.

## Local Django secret

The Django `SECRET_KEY` is read from `DJANGO_SECRET_KEY`. Create a local `.env`
file (already ignored by Git) before running the app:

```sh
python3 -c "import secrets; print('DJANGO_SECRET_KEY=' + secrets.token_hex(32))" > .env
```

## Security checks

Install the pre-commit hooks with `pre-commit install`. They run Ruff formatting,
Ruff linting, and Gitleaks on staged changes. The Security GitHub Actions workflow
runs Bandit, Gitleaks, Trivy, and Checkov on pull requests. Bandit is currently
non-blocking so low-severity code findings can be triaged without blocking the
build; secrets, fixed CRITICAL image vulnerabilities, and Terraform findings
remain blocking. Record scan findings and their dispositions in
[`SECURITY-REGISTER.md`](./SECURITY-REGISTER.md).
