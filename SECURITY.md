# Security Policy

## Reporting Security Vulnerabilities

If you discover a security vulnerability in this project, please report it by emailing the repository owner or creating a private security advisory on GitHub.

## Security Best Practices

### Environment Variables

**IMPORTANT**: Never commit sensitive credentials to version control!

1. **Use `.env` files for local development**
   - Copy `backend/.env.example` to `backend/.env`
   - Add your actual credentials to `.env`
   - The `.env` file is already in `.gitignore`

2. **MongoDB Connection**
   - Never hardcode MongoDB URIs with credentials in source code
   - Use environment variables via `python-dotenv`
   - Rotate credentials immediately if accidentally exposed

3. **Production Deployment**
   - Use platform-specific secret management (e.g., GitHub Secrets, Heroku Config Vars)
   - Never commit production credentials
   - Use different credentials for development and production

### If Credentials Were Exposed

If you accidentally commit credentials:

1. **Immediately rotate/revoke the exposed credentials**
   - Change your MongoDB password in MongoDB Atlas
   - Generate new API keys if applicable

2. **Remove credentials from Git history**
   ```bash
   # Use BFG Repo-Cleaner or git filter-branch
   # WARNING: This rewrites Git history
   ```

3. **Update all systems using the old credentials**

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |

## Dependencies

Keep all dependencies up to date to avoid known vulnerabilities:

```bash
# Backend
pip install --upgrade -r backend/requirements.txt

# Frontend
cd frontend
npm audit fix
```
