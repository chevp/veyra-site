# Veyra ERP

An enterprise resource planning system for data management with a modern Entity-Component-System architecture.

## Overview

Veyra ERP is designed to streamline and manage business data across various organizational departments and processes. It features a modern Angular frontend with Tailwind CSS and a scalable Java Quarkus backend using Entity-Component-System (ECS) architecture.

## Architecture

### Backend (Java Quarkus)
- **Entity-Component-System (ECS)** architecture for flexible data modeling
- **PostgreSQL** database for reliable data storage
- **S3/MinIO** integration for scalable file storage
- **RESTful APIs** for frontend integration

### Frontend (Angular + Tailwind CSS)
- **Angular 19** with modern component architecture
- **Tailwind CSS** for responsive and modern UI design
- **TypeScript** for type-safe development

### Database Schema (ECS)
The system uses an Entity-Component-System approach where:
- **Entities** represent core business objects
- **Components** contain specific data attributes (Metadata, Storage, Logic)
- **Systems** handle business logic and data processing

### Storage Architecture
- **Database (PostgreSQL)**: Entity relationships, metadata, and component data
- **S3/MinIO**: Binary files, logic.js files, and source maps
- **Versioning**: Full version control with manifest signatures and hashes
- **CDN-ready**: Optimized for content delivery networks

## Project Structure

```
veyra-erp/
├── veyra-erp-backend/          # Java Quarkus backend
│   ├── src/main/java/com/veyra/erp/
│   │   ├── ecs/                # Entity-Component-System base classes
│   │   ├── entities/           # Core entities
│   │   ├── components/         # ECS components
│   │   ├── systems/            # Business logic systems
│   │   └── resources/          # REST API endpoints
│   └── src/main/resources/
├── veyra-erp-ui/              # Angular frontend
│   ├── src/app/               # Angular application
│   ├── tailwind.config.js     # Tailwind CSS configuration
│   └── src/styles.css         # Global styles
├── .gitignore                 # Git ignore rules
├── .gitattributes             # Git attributes
└── README.md                  # This file
```

## Features

### Core ERP Functionality
- **Dashboard** with key metrics and insights
- **Inventory Management** with real-time tracking
- **Customer Management** with detailed profiles
- **Order Processing** with workflow automation
- **Financial Management** with reporting
- **Document Storage** with S3/MinIO integration

### Technical Features
- **Scalable Architecture** using ECS pattern
- **File Storage** with version control and checksums
- **Logic Deployment** with JavaScript/source map storage
- **RESTful APIs** for all operations
- **CORS Support** for frontend integration
- **Development/Production** environment configurations

## Installation

### Prerequisites
- Java 17+
- Node.js 18+
- PostgreSQL 13+
- MinIO or AWS S3 access

### Backend Setup
```bash
cd veyra-erp-backend
./mvnw quarkus:dev
```

### Frontend Setup
```bash
cd veyra-erp-ui
npm install
ng serve
```

### Database Setup
1. Create PostgreSQL database `veyra_erp`
2. Update `application.properties` with your database credentials
3. The schema will be auto-generated on first run

### Storage Setup
1. Set up MinIO or configure AWS S3
2. Create buckets: `veyra-erp-storage` and `veyra-erp-logic`
3. Update S3 configuration in `application.properties`

## Usage

### Development
- Backend: `http://localhost:8080`
- Frontend: `http://localhost:4200`
- API Documentation: `http://localhost:8080/q/swagger-ui`

### API Endpoints
- `GET /api/entities` - List all entities
- `POST /api/entities` - Create new entity
- `GET /api/entities/{id}` - Get entity by ID
- `POST /api/files/upload` - Upload file
- `POST /api/files/upload-logic` - Upload logic file

## Development Commands

```bash
# Backend development
cd veyra-erp-backend
./mvnw quarkus:dev

# Frontend development
cd veyra-erp-ui
ng serve

# Build frontend
ng build

# Run tests
ng test
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for your changes
5. Submit a pull request

## License

This project is licensed under the MIT License.
