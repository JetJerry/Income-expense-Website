# Income & Expense Tracker

A comprehensive web application for tracking personal income and expenses with detailed analytics, user authentication, and customizable preferences. Built with Django and featuring an interactive dashboard for financial insights.

## 🎯 Overview

The Income & Expense Tracker is a full-featured financial management application that allows users to:
- Track expenses with categories and descriptions
- Monitor income from multiple sources
- View detailed statistics and charts
- Analyze spending patterns with visual representations
- Manage user preferences and settings
- Access a secure, authenticated dashboard

## ✨ Features

### 📊 Core Functionality
- **Expense Management**: Add, edit, and delete expenses with categories, amounts, and dates
- **Income Tracking**: Record income from various sources with detailed descriptions
- **Category Management**: Create and organize custom expense categories and income sources
- **User Authentication**: Secure user registration, login, and password management
- **User Preferences**: Customizable user settings and preferences

### 📈 Analytics & Insights
- **Interactive Dashboards**: Real-time visualization of financial data
- **Chart Analytics**: Multiple chart types for expense and income analysis
- **Statistical Reports**: Comprehensive statistics on spending and earnings
- **Search Functionality**: Easy search across expenses and income records
- **Currency Support**: Support for multiple currencies

### 🔐 Security
- User authentication and authorization
- Secure password management with reset functionality
- Account activation via email
- CSRF protection
- Django security middleware

### 🎨 User Interface
- Responsive Bootstrap-based design
- Interactive charts and graphs
- Clean, intuitive dashboard layout
- Mobile-friendly interface
- Sidebar navigation

## 🛠️ Tech Stack

### Backend
- **Django 5.1.7**: Python web framework
- **Python 3.12**: Programming language
- **SQLite/PostgreSQL**: Database (SQLite for development, PostgreSQL for production)

### Frontend
- **HTML5**: Markup
- **CSS3**: Styling (Bootstrap, custom CSS)
- **JavaScript**: Interactivity and client-side logic
- **Chart.js**: Data visualization

### Dependencies
- `psycopg2`: PostgreSQL adapter
- `validate-email`: Email validation
- `django-heroku`: Heroku deployment utilities
- `gunicorn`: Production WSGI server
- `waitress`: Alternative WSGI server

## 📁 Project Structure

```
expensewebsite/
├── authentication/          # User authentication & management
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── utils.py
│   └── templates/
│       ├── login.html
│       ├── register.html
│       ├── activate_account.html
│       ├── reset-password.html
│       └── set-newpassword.html
│
├── expenses/               # Expense tracking module
│   ├── models.py          # Expense & Category models
│   ├── views.py
│   ├── urls.py
│   ├── admin.py
│   └── templates/
│       ├── index.html
│       ├── add_expense.html
│       ├── edit-expense.html
│       └── stats.html
│
├── userincome/            # Income tracking module
│   ├── models.py          # UserIncome & Source models
│   ├── views.py
│   ├── urls.py
│   ├── admin.py
│   └── templates/
│       ├── index.html
│       ├── add_income.html
│       └── edit_income.html
│
├── userpreferences/       # User preferences management
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── signals.py
│   └── templates/
│       └── index.html
│
├── expensewebsite/        # Main project settings
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   ├── asgi.py
│   └── __init__.py
│
├── templates/             # Global templates
│   ├── base.html
│   ├── base_auth.html
│   ├── index.html
│   ├── admin/
│   └── partials/          # Reusable template components
│
├── expensewebsite/static/ # Static files
│   ├── css/
│   │   ├── bootstrap.min.css
│   │   ├── main.css
│   │   ├── dashboard.css
│   │   ├── adminstyle.css
│   │   └── [other styles]
│   ├── js/
│   │   ├── chart.js
│   │   ├── expensecharts.js
│   │   ├── getCategoryData.js
│   │   ├── main.js
│   │   ├── register.js
│   │   ├── searchExpenses.js
│   │   ├── searchIncome.js
│   │   ├── stats.js
│   │   └── userStats.js
│   └── img/
│
├── currencies.json        # Currency configuration
├── db.sqlite3            # Development database
├── manage.py             # Django management script
├── Pipfile               # Pipenv dependencies
├── Procfile              # Heroku deployment config
└── README.md             # This file
```

## 🚀 Getting Started

### Prerequisites
- Python 3.12+
- pip or pipenv
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/income-expense-website.git
   cd income-expense-website/expensewebsite
   ```

2. **Create a virtual environment**
   ```bash
   # Using venv
   python -m venv venv
   venv\Scripts\activate
   
   # Or using pipenv
   pipenv install
   pipenv shell
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   
   # Or if using pipenv
   pipenv install
   ```

4. **Apply database migrations**
   ```bash
   python manage.py migrate
   ```

5. **Create a superuser (admin account)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Collect static files**
   ```bash
   python manage.py collectstatic
   ```

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

8. **Access the application**
   - Open your browser and navigate to `http://localhost:8000`
   - Admin panel: `http://localhost:8000/admin`

## 📊 Database Models

### Expenses App
- **Expense**: Records user expenses with amount, date, description, category, and owner reference
- **Category**: Defines expense categories for organization

### UserIncome App
- **UserIncome**: Records user income with amount, date, description, source, and owner reference
- **Source**: Defines income sources

### UserPreferences App
- **UserPreference**: Stores user-specific settings and preferences

## 🔗 API Endpoints

### Authentication
- `/auth/login/` - User login
- `/auth/register/` - User registration
- `/auth/logout/` - User logout
- `/auth/password-reset/` - Password reset request
- `/auth/set-new-password/` - Set new password

### Expenses
- `/expenses/` - View all expenses
- `/expenses/add/` - Add new expense
- `/expenses/edit/<id>/` - Edit expense
- `/expenses/delete/<id>/` - Delete expense
- `/expenses/stats/` - View expense statistics

### Income
- `/income/` - View all income records
- `/income/add/` - Add new income
- `/income/edit/<id>/` - Edit income
- `/income/delete/<id>/` - Delete income

### Preferences
- `/preferences/` - Manage user preferences

## 🎯 Key Features Explained

### Dashboard
The main dashboard provides an at-a-glance view of:
- Total expenses and income
- Expense breakdown by category
- Income breakdown by source
- Recent transactions
- Quick action buttons

### Statistics
Comprehensive statistical analysis including:
- Spending trends over time
- Category-wise expense distribution
- Monthly/yearly comparisons
- Income source breakdown

### Search & Filter
Users can:
- Search expenses by description or category
- Filter by date range
- Sort by amount or date
- Quick category/source filtering

## 🔧 Configuration

### Settings File (`expensewebsite/settings.py`)
Key configurations:
- `DEBUG`: Set to `False` in production
- `ALLOWED_HOSTS`: Add your domain for production
- `INSTALLED_APPS`: Configured apps (expenses, userincome, userpreferences, authentication)
- `DATABASES`: Database configuration (SQLite default, PostgreSQL for production)
- Database migrations for data persistence

### Currency Support
Currency data is stored in `currencies.json` for multi-currency support.

## 🚢 Deployment

### Heroku Deployment
1. Create a `Procfile` (already included):
   ```
   web: waitress-serve --port=$PORT expensewebsite.wsgi:application
   ```

2. Create a `.env` file with production settings:
   ```
   DJANGO_SETTINGS_MODULE=expensewebsite.settings
   SECRET_KEY=your-secret-key-here
   DEBUG=False
   ALLOWED_HOSTS=your-domain.herokuapp.com
   ```

3. Deploy using Heroku CLI:
   ```bash
   heroku login
   git push heroku main
   ```

## 📝 Development

### Creating a New Feature
1. Create a new app: `python manage.py startapp feature_name`
2. Define models in `models.py`
3. Register in `INSTALLED_APPS` in `settings.py`
4. Create views and URLs
5. Create templates
6. Run migrations: `python manage.py makemigrations && python manage.py migrate`

### Running Tests
```bash
python manage.py test
```

### Database Migrations
```bash
# Create migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Show migration status
python manage.py showmigrations
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -m 'Add new feature'`
4. Push to branch: `git push origin feature/new-feature`
5. Submit a pull request

## 📋 Roadmap

- [ ] Mobile app (React Native/Flutter)
- [ ] Advanced budget planning
- [ ] Bill reminders
- [ ] Investment tracking
- [ ] Tax report generation
- [ ] Data export (PDF/CSV)
- [ ] Recurring transactions
- [ ] Budget alerts
- [ ] Multi-user family accounts

## 🐛 Known Issues

- Debug mode is currently enabled (set `DEBUG=True` in settings.py)
- Secret key should be moved to environment variables in production
- Some JavaScript features may need optimization for large datasets

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

Created as a personal finance management tool.

## 📧 Support & Contact

For issues, questions, or suggestions, please open an issue on GitHub or contact the development team.

## 🙏 Acknowledgments

- Django documentation and community
- Bootstrap for responsive UI framework
- Chart.js for data visualization
- All contributors and users

---

**Last Updated**: December 2025

**Status**: Active Development

**Python Version**: 3.12

**Django Version**: 5.1.7
