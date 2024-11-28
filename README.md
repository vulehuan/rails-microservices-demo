# Rails Microservices Demo

## Overview

This project demonstrates a microservices architecture using Ruby on Rails 7, showcasing best practices for building scalable and modular web applications.

## Architecture Components

- **Framework**: Ruby on Rails 7
- **Database**: PostgreSQL
- **Web Server**: Nginx
- **Authentication**: JWT (JSON Web Tokens)
- **Authorization**: CanCanCan
- **Error Tracking**: Sentry
- **Testing Framework**: RSpec
- **Code Coverage**: SimpleCov
- **Containerization**: Docker & Docker Compose

## Microservices Repositories

This project includes the following microservices as Git submodules:

1. **Shop Service**
   - Repository: [rails-microservices-shop](https://github.com/vulehuan/rails-microservices-shop)
   - Responsible for managing the main shopping interface and user interactions

2. **Product Service**
   - Repository: [rails-microservices-product-service](https://github.com/vulehuan/rails-microservices-product-service)
   - Handles product catalog, inventory, and product-related operations

3. **Order Service**
   - Repository: [rails-microservices-order-service](https://github.com/vulehuan/rails-microservices-order-service)
   - Manages order processing, tracking, and related functionalities

## Prerequisites

- Docker
- Docker Compose
- Git

## Project Setup

### 1. Clone the Repository

```bash
git clone https://github.com/vulehuan/rails-microservices-demo.git
cd rails-microservices-demo
```

### 2. Initialize Submodules

```bash
git submodule update --init --recursive
git submodule foreach --recursive git checkout main
```

### 3. Configure Hosts

Add the following entries to your `/etc/hosts` file:

```
127.0.0.1 product.local
127.0.0.1 shop.local
127.0.0.1 order.local
```

### 4. Start Services

```bash
docker-compose up -d
```

## Services

- **Product Service**: Manages product-related operations
- **Shop Service**: Handles shopping and catalog functionalities
- **Order Service**: Manages order processing and tracking

## Authentication & Authorization

- JWT is used for secure, stateless authentication
- CanCanCan provides role-based access control

## Monitoring & Debugging

- Sentry integration for real-time error tracking
- SimpleCov generates comprehensive code coverage reports

## Testing

To run the test suite:
```bash
bundle exec rspec
```

To view code coverage report:
```bash
open coverage/index.html
```