# tire_bot

### Структура проекта

    tire_bot/
    │
    ├── app/
    │   ├── main.py                
    │   ├── config.py
    │   ├── logger.py
    │
    │   ├── bot/
    │   │   ├── handlers/          # Telegram handlers
    │   │   │   ├── start.py
    │   │   │   ├── booking.py
    │   │   │   ├── services.py
    │   │   │   ├── price.py
    │   │   │   ├── admin.py
    │   │   │   └── ai.py
    │   │   │
    │   │   ├── keyboards/
    │   │   │   ├── main_menu.py
    │   │   │   ├── booking_kb.py
    │   │   │   └── common.py
    │   │   │
    │   │   ├── middlewares/
    │   │   │   └── db.py
    │   │   │
    │   │   └── router.py
    │   │
    │   ├── core/
    │   │   ├── services/          # бизнес-логика
    │   │   │   ├── booking_service.py
    │   │   │   ├── user_service.py
    │   │   │   ├── branch_service.py
    │   │   │   ├── price_service.py
    │   │   │   └── ai_service.py
    │   │   │
    │   │   └── utils/
    │   │       ├── datetime.py
    │   │       └── validators.py
    │   │
    │   ├── db/
    │   │   ├── models/
    │   │   │   ├── user.py
    │   │   │   ├── booking.py
    │   │   │   ├── branch.py
    │   │   │   ├── service.py
    │   │   │   └── product.py
    │   │   │
    │   │   ├── repositories/
    │   │   │   ├── user_repo.py
    │   │   │   ├── booking_repo.py
    │   │   │   └── branch_repo.py
    │   │   │
    │   │   ├── database.py
    │   │   └── session.py
    │   │
    │   ├── integrations/
    │   │   ├── telegram/
    │   │   ├── payments/
    │   │   └── ai/
    │   │
    │   └── schemas/               # DTO / pydantic
    │       ├── booking.py
    │       └── user.py
    │
    ├── migrations/                # Alembic
    ├── tests/
    ├── docker/
    │   ├── Dockerfile
    │   └── docker-compose.yml
    │
    └── requirements.txt

### 🧩 Ключевые сущности (БД)

    User
    id
    telegram_id
    name
    phone
    created_at

    Branch (филиалы)
    id
    name
    address
    timezone

    Service
    id
    name
    description
    duration_minutes
    price

    Booking
    id
    user_id
    branch_id
    service_id
    date
    time
    status (pending / confirmed / cancelled)

    Product (шины)
    id
    name
    brand
    size
    price
    stock