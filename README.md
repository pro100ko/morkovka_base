# Knowledge Bot

A Telegram bot for managing and testing knowledge about products and categories. Built with Python and aiogram, designed to run efficiently on Render's free tier.

## Features

- User Management
  - Registration and authentication
  - Role-based access control (admin/user)
  - Session management
  - Activity tracking

- Test Management
  - Create and edit tests
  - Multiple question types
  - Time limits and scoring
  - Test results tracking

- Knowledge Base
  - Category management
  - Product management
  - Search functionality
  - Product viewing

- Admin Panel
  - User management
  - Test management
  - Category and product management
  - Statistics and monitoring

## Technical Features

- Efficient resource management
  - Connection pooling for database operations
  - Memory usage monitoring and limits
  - Rate limiting for API requests
  - Automatic cleanup of old data

- Robust error handling
  - Comprehensive logging
  - Graceful error recovery
  - Transaction management
  - Backup and restore capabilities

- Monitoring and maintenance
  - System health monitoring
  - Performance metrics collection
  - Database backup and migration
  - Resource usage tracking

## Project Structure

```
.
├── alembic/              # Database migrations
├── backups/             # Database backups
├── data/               # Data files
├── handlers/           # Bot command handlers
│   ├── admin.py       # Admin commands
│   ├── user.py        # User commands
│   └── knowledge.py   # Knowledge base commands
├── migrations/         # Migration files
├── monitoring/         # Monitoring tools
├── scripts/           # Utility scripts
├── tests/             # Test files
├── utils/             # Utility modules
│   ├── db_pool.py     # Database connection pool
│   ├── keyboards.py   # Keyboard layouts
│   ├── message_utils.py # Message handling
│   └── resource_manager.py # Resource management
├── config.py          # Configuration
├── dispatcher.py      # Bot dispatcher
├── logging_config.py  # Logging setup
├── main.py           # Application entry point
├── middleware.py     # Middleware components
├── sqlite_db.py      # Database operations
└── requirements.txt   # Dependencies
```

## Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/knowledge-bot.git
cd knowledge-bot
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create a `.env` file with your configuration:
```env
# Bot settings
BOT_TOKEN=your_bot_token
WEBAPP_HOST=0.0.0.0
WEBAPP_PORT=8000
WEBHOOK_URL=https://your-domain.com/webhook
ENABLE_WEBHOOK=true

# Admin settings
ADMIN_IDS=123456789,987654321
ENABLE_ADMIN_PANEL=true

# Database settings
DB_FILE=knowledge_bot.db
DB_BACKUP_DIR=backups
DB_MIGRATIONS_DIR=migrations
DB_POOL_SIZE=5

# Resource limits
MAX_MEMORY_USAGE_MB=512
MAX_CPU_USAGE_PERCENT=80
RATE_LIMIT_MESSAGES=20
RATE_LIMIT_CALLBACKS=30
RATE_LIMIT_WINDOW=60

# Monitoring
ENABLE_METRICS=true
METRICS_DIR=metrics
METRICS_RETENTION_DAYS=7
```

5. Initialize the database:
```bash
python scripts/migrate_db.py
```

6. Run the bot:
```bash
python main.py
```

## Development

### Running Tests
```bash
python -m pytest tests/
```

### Database Migrations
To create a new migration:
1. Create a new JSON file in `migrations/` with a sequential number
2. Add your SQL queries to the file
3. Run migrations:
```bash
python scripts/migrate_db.py
```

### Database Backups
To create a backup:
```bash
python scripts/backup_db.py
```

### System Monitoring
To monitor system health:
```bash
python scripts/monitor_system.py
```

## Deployment

The bot is designed to run on Render's free tier. Follow these steps to deploy:

1. Create a new Web Service on Render
2. Connect your GitHub repository
3. Set the following:
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `python main.py`
   - Environment Variables: Add all variables from your `.env` file

## Resource Management

The bot is optimized for Render's free tier limitations:
- Memory limit: 512MB
- CPU: Shared
- Storage: 1GB
- Bandwidth: Limited

To ensure efficient operation:
- Database connections are pooled
- Memory usage is monitored
- Rate limiting is enforced
- Old data is automatically cleaned up
- Backups are compressed

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

# Morkovka Base

Современная, адаптивная корпоративная база знаний, разработанная для сотрудников, чтобы легко находить информацию о продуктах и документацию.

## Особенности

- **Современный дизайн**: Чистый, профессиональный интерфейс с градиентными фонами и плавными анимациями
- **Адаптивная верстка**: Отлично работает на настольных компьютерах, планшетах и мобильных устройствах
- **Категории продуктов**: Организованные категории продуктов с визуальными иконками и описаниями
- **Карточки продуктов**: Детальная информация о продуктах с функциями, версиями и кнопками действий
- **Якорная навигация**: Быстрые кнопки навигации в верхней части страниц продуктов
- **Функция поиска**: Встроенная возможность поиска (может быть расширена с интеграцией бэкенда)
- **Плавные анимации**: CSS переходы и JavaScript анимации для лучшего пользовательского опыта

## Структура

```
├── index.html              # Главная страница с кнопками категорий
├── styles.css              # Основная таблица стилей с адаптивным дизайном
├── script.js               # JavaScript для интерактивности
└── products/               # Страницы категорий продуктов
    ├── software.html       # Страница программных продуктов (пример)
    ├── hardware.html       # Страница аппаратных продуктов (создать)
    ├── services.html       # Страница услуг (создать)
    ├── cloud.html          # Страница облачных решений (создать)
    ├── security.html       # Страница продуктов безопасности (создать)
    └── analytics.html      # Страница продуктов аналитики (создать)
```

## Настройка GitHub Pages

### Вариант 1: Автоматическая настройка (Рекомендуется)

1. **Отправка в GitHub**: Отправьте этот репозиторий в ваш аккаунт GitHub
2. **Включение GitHub Pages**:
   - Перейдите в ваш репозиторий на GitHub
   - Нажмите на вкладку **"Settings"**
   - Прокрутите вниз до раздела **"Pages"**
   - В разделе **"Source"** выберите **"Deploy from a branch"**
   - Выберите ветку **"main"** и папку **"/ (root)"**
   - Нажмите **"Save"**

3. **Доступ к сайту**: Ваша база знаний будет доступна по адресу:
   `https://pro100ko.github.io/morkovka_base/`

### Вариант 2: Ручная настройка

1. **Создайте новый репозиторий** на GitHub
2. **Клонируйте репозиторий** на ваш локальный компьютер
3. **Скопируйте все файлы** из этого проекта в репозиторий
4. **Зафиксируйте и отправьте** изменения
5. **Следуйте шагам автоматической настройки** выше

## Настройка

### Добавление новых категорий продуктов

1. Создайте новый HTML файл в папке `products/` (например, `hardware.html`)
2. Скопируйте структуру из `software.html`
3. Обновите карточки продуктов с вашими конкретными продуктами
4. Добавьте ссылку на категорию в `index.html`

### Изменение стилей

- Отредактируйте `styles.css` для изменения цветов, шрифтов и макета
- Дизайн использует CSS пользовательские свойства для легкого темирования
- Все компоненты адаптивны и мобильно-дружелюбны

### Добавление функциональности поиска

Текущий поиск показывает уведомление. Для реализации реального поиска:

1. **Клиентский поиск**: Добавьте JavaScript для фильтрации карточек продуктов
2. **Серверный поиск**: Интегрируйте с поисковым API или базой данных
3. **Внешний поиск**: Используйте сервисы как Algolia или Elasticsearch

## Поддержка браузеров

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## Производительность

- Оптимизированные изображения и иконки с использованием Font Awesome CDN
- Минифицированные CSS и JavaScript (рекомендуется для продакшена)
- Ленивая загрузка для лучшей производительности
- Адаптивные изображения и эффективные CSS Grid макеты

## Вклад в проект

1. Форкните репозиторий
2. Создайте ветку функции
3. Внесите ваши изменения
4. Протестируйте на разных устройствах и браузерах
5. Отправьте pull request

## Лицензия

Этот проект лицензирован под MIT License - см. файл LICENSE для деталей.

## Поддержка

По вопросам или поддержке:
- Создайте issue в GitHub репозитории
- Обратитесь в IT-отдел для внутренней поддержки
- Проверьте документацию в самой базе знаний

---

**Примечание**: Это статический шаблон веб-сайта. Для динамических функций, таких как аутентификация пользователей, поиск в реальном времени или управление контентом, вам потребуется интегрировать с серверной службой или CMS.
