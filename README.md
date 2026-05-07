# Leshine - Australian Prediction Market Platform

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Django](https://img.shields.io/badge/Django-4.2-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

Leshine is a modern prediction market platform designed specifically for the Australian market. It allows users to create and trade on binary prediction markets with real-time pricing, secure transactions, and full regulatory compliance.

## 🚀 Features

### Core Functionality
- **Binary Prediction Markets**: Create and trade on event outcomes
- **Real-time Pricing**: Dynamic pricing based on supply and demand
- **Portfolio Management**: Track positions, P&L, and trading history
- **Market Analytics**: Charts, statistics, and market insights
- **Social Features**: Comments, discussions, and market chat

### Australian Market Compliance
- ✅ **ASIC Compliance**: Know Your Customer (KYC) verification
- ✅ **AML/CFT**: Anti-Money Laundering and Counter-Terrorism Financing
- ✅ **Australian Payments**: Direct Bank Transfers (BSB/Account)
- ✅ **AUD Currency**: All transactions in Australian Dollars
- ✅ **Timezone**: Australia/Sydney

### Technology Stack
- **Backend**: Django 4.2, Django REST Framework
- **Database**: PostgreSQL
- **Cache/Broker**: Redis
- **Task Queue**: Celery
- **API Documentation**: Swagger/OpenAPI
- **Testing**: Pytest, Coverage
- **Deployment**: Docker, Docker Compose

## 📋 Prerequisites

- Python 3.11+
- Docker & Docker Compose (recommended)
- PostgreSQL 15+
- Redis 7+
- Git

## 🛠️ Installation

### Option 1: Docker (Recommended)

```bash
# Clone the repository
git clone https://github.com/tamangdipesh561-commits/leshine.git
cd leshine

# Copy environment file
cp .env.example .env

# Start all services
docker-compose up -d

# Run migrations
docker-compose exec web python manage.py migrate

# Create superuser
docker-compose exec web python manage.py createsuperuser

# Load sample data (optional)
docker-compose exec web python manage.py loaddata fixtures/sample_markets.json
```

### Option 2: Local Development

```bash
# Clone the repository
git clone https://github.com/tamangdipesh561-commits/leshine.git
cd leshine

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy environment file
cp .env.example .env

# Run migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Start development server
python manage.py runserver
```

## 📚 API Documentation

Once the application is running, visit:

- **Swagger UI**: http://localhost:8000/api/docs/
- **ReDoc**: http://localhost:8000/api/redoc/
- **Admin Panel**: http://localhost:8000/admin/

## 📁 Project Structure

```
leshine/
├── leshine/
│   ├── settings.py          # Django settings
│   ├── urls.py              # URL routing
│   └── wsgi.py              # WSGI configuration
├── accounts/
│   ├── models.py            # User models
│   ├── serializers.py       # DRF serializers
│   ├── views.py             # API views
│   └── tests.py             # Unit tests
├── markets/
│   ├── models.py            # Market models
│   ├── serializers.py       # Market serializers
│   ├── views.py             # Market views
│   └── tests.py             # Tests
├── trading/
│   ├── models.py            # Trading models
│   ├── serializers.py       # Trading serializers
│   ├── views.py             # Trading views
│   └── tests.py             # Tests
├── payments/
│   ├── models.py            # Payment models
│   ├── serializers.py       # Payment serializers
│   ├── views.py             # Payment views
│   └── tests.py             # Tests
├── requirements.txt         # Python dependencies
├── Dockerfile               # Docker configuration
├── docker-compose.yml       # Docker Compose configuration
└── manage.py                # Django management script
```

## 🔑 API Endpoints

### Authentication
- `POST /api/v1/auth/register/` - Register new user
- `POST /api/v1/auth/login/` - User login
- `POST /api/v1/auth/logout/` - User logout
- `POST /api/v1/auth/refresh/` - Refresh token

### Markets
- `GET /api/v1/markets/` - List all markets
- `POST /api/v1/markets/` - Create new market
- `GET /api/v1/markets/{id}/` - Get market details
- `PUT /api/v1/markets/{id}/` - Update market
- `DELETE /api/v1/markets/{id}/` - Delete market
- `GET /api/v1/markets/{id}/comments/` - Get market comments

### Trading
- `GET /api/v1/positions/` - List user positions
- `POST /api/v1/trades/` - Place a trade
- `GET /api/v1/trades/{id}/` - Get trade details
- `GET /api/v1/portfolio/` - Get portfolio summary

### Payments
- `GET /api/v1/accounts/` - List user bank accounts
- `POST /api/v1/accounts/` - Add bank account
- `POST /api/v1/deposits/` - Deposit funds
- `POST /api/v1/withdrawals/` - Withdraw funds
- `GET /api/v1/transactions/` - Transaction history

## 🧪 Testing

```bash
# Run all tests
pytest

# Run tests with coverage
pytest --cov=leshine

# Run specific test file
pytest tests/test_markets.py

# Run with verbose output
pytest -v
```

## 🚀 Deployment

### Production Checklist
- [ ] Set `DEBUG=False` in `.env`
- [ ] Generate new `SECRET_KEY`
- [ ] Configure `ALLOWED_HOSTS`
- [ ] Set up SSL/TLS certificates
- [ ] Configure email backend
- [ ] Set up AWS S3 for media storage
- [ ] Configure Stripe API keys
- [ ] Enable database backups
- [ ] Set up monitoring and logging
- [ ] Configure rate limiting

### Deploy with Docker

```bash
# Build production image
docker build -t leshine:latest .

# Push to registry
docker tag leshine:latest your-registry/leshine:latest
docker push your-registry/leshine:latest

# Deploy
docker-compose -f docker-compose.prod.yml up -d
```

## 📖 Documentation

- [API Reference](./docs/API.md)
- [Installation Guide](./docs/INSTALLATION.md)
- [Contributing](./CONTRIBUTING.md)
- [Architecture](./docs/ARCHITECTURE.md)

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## ⚖️ Legal Disclaimer

Leshine is designed for the Australian market and complies with relevant Australian financial regulations. Users must ensure their use of the platform complies with all applicable laws and regulations, including those related to gambling and financial services.

## 📞 Support

For issues, questions, or suggestions, please:
1. Check existing GitHub issues
2. Create a new GitHub issue with detailed information
3. Contact: support@leshine.com

## 🔐 Security

If you discover a security vulnerability, please email security@leshine.com instead of using the issue tracker.

---

**Made with ❤️ for the Australian market**
