# Security Finding Register

| Scan | Finding | Disposition | Justification / follow-up |
|---|---|---|---|
| Bandit | B105: hard-coded Django `SECRET_KEY` in `campus_notifier/settings.py` | Remediated | The setting now requires `DJANGO_SECRET_KEY` from the environment. The old `django-insecure-` development placeholder remains in Git history; it was not a production credential. Rotate it if it was ever used outside local development. |
| Trivy | Pull-request scan result pending | Pending | Record the CRITICAL finding count and disposition after the image job runs. |
| Checkov | Pull-request scan result pending | Pending | Record each Terraform finding and remediate it or document a justified suppression after the IaC job runs. |
