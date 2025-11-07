# Vikunja Task Management

A Docker Compose setup for running Vikunja, a self-hosted task management application, with PostgreSQL database.

## 🚧 Work in Progress

This is a **first push** of the project setup. More configuration and customization will be added later.

## What's Included

- **Vikunja**: Open-source task management application (v1.0.0-rc2)
- **PostgreSQL**: Database backend (v18)
- **Docker Compose**: Container orchestration
- **Environment Configuration**: Separate files for public and secret configurations

## Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd chores.leshicodes.info/vikunja
   ```

2. **Set up environment variables**
   ```bash
   cp .env.secrets.example .env.secrets
   ```
   
   Edit `.env.secrets` and replace the default values:
   - `VIKUNJA_DATABASE_PASSWORD`: Set a secure database password
   - `VIKUNJA_SERVICE_JWTSECRET`: Generate a random secret for JWT tokens

3. **Start the services**
   ```bash
   docker-compose up -d
   ```

4. **Access Vikunja**
   
   Open your browser and go to: `http://workstation.jjambrose.info:3456`

## Configuration

### Environment Files

- **`.env`**: Public configuration (committed to git)
  - Database connection settings
  - Service URLs
  - Timezone configuration

- **`.env.secrets`**: Secret configuration (gitignored)
  - Database passwords
  - JWT secrets
  - Other sensitive data

### Volumes

- `./files`: Vikunja file storage
- `./db`: PostgreSQL data directory

Both directories are automatically created and excluded from git.

## Services

### Vikunja
- **Port**: 3456
- **Image**: vikunja/vikunja:1.0.0-rc2
- **Container**: vikunja

### Database
- **Image**: postgres:18
- **Container**: vikunja_db
- **User**: vikunja
- **Database**: vikunja

## Notes

- The database container includes a health check to ensure PostgreSQL is ready before Vikunja starts
- All sensitive data is stored in `.env.secrets` which is excluded from version control
- The setup uses variable references to avoid duplicating passwords between services

## TODO

- [ ] Add SSL/TLS configuration
- [ ] Set up backup strategies
- [ ] Configure logging
- [ ] Add monitoring/health checks
- [ ] Document advanced configuration options
- [ ] Add update procedures

## Security

Make sure to:
- Change all default passwords in `.env.secrets`
- Generate a strong JWT secret
- Keep `.env.secrets` file secure and never commit it to version control

---

*This is an initial setup that will be expanded and refined in future iterations.*