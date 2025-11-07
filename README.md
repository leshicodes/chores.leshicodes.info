# Chores - Task Management Evaluation

A collection of Docker Compose setups for evaluating different self-hosted task management applications.

## 🚧 Work in Progress

This is a **multi-app evaluation project** where I'm testing various open-source task management solutions to find the best fit. Each application has its own folder with dedicated configuration.

## Project Structure

```
chores.leshicodes.info/
├── <app-name>/           # Each app gets its own directory
│   ├── docker-compose.yml
│   ├── .env
│   ├── .env.secrets
│   └── data/             # App-specific data storage
└── README.md
```

## Getting Started

1. Navigate to any application directory
2. Copy the example secrets file: `cp .env.secrets.example .env.secrets`
3. Edit `.env.secrets` with your configuration
4. Start the application: `docker-compose up -d`

Each application runs on its own port to avoid conflicts. Check the individual `.env` files for specific port assignments.

## Configuration

Each application maintains its own:
- Environment configuration (`.env` and `.env.secrets`)
- Docker Compose setup  
- Data persistence and volumes
- Unique port allocation

## Evaluation Goals

- Compare features, usability, and performance
- Test setup complexity and maintenance requirements
- Evaluate mobile compatibility and API availability
- Assess backup/export capabilities
- Document pros and cons of each solution

## Security Notes

- Each app uses isolated `.env.secrets` files for sensitive data
- Generate unique passwords and secrets for each application
- All secrets are excluded from version control via `.gitignore`
