# Chores - Task Management with Donetick

A self-hosted task management solution using **Donetick** - a modern, collaborative chore and task tracking application.

## 🎯 Solution Chosen: Donetick

After evaluating various self-hosted task management options, **Donetick** was selected for its:
- Clean, modern interface
- Collaborative features for household/team task management  
- Docker-based deployment
- Active development and community

## Quick Start

```bash
cp .env.secrets.example .env.secrets
# Edit .env.secrets with your configuration
docker-compose up -d
```

## Features

- Task creation and assignment
- Recurring chore scheduling
- Progress tracking
- Multi-user collaboration
- Mobile-friendly interface

## Configuration

The setup includes:
- PostgreSQL database for data persistence
- Custom configuration via `config/selfhosted.yml`
- Environment-based secrets management
- Persistent data storage in `donetick/data/`