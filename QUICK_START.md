# RaceCars - Quick Start Guide

## 🚀 Getting Started in 5 Minutes

### Step 1: Install Backend Dependencies

```bash
cd backend
pip install -r requirements.txt
```

### Step 2: Setup Database

```bash
# Create database and tables
python manage.py migrate

# Create admin user
python manage.py createsuperuser
# Follow prompts to create your admin account

# Load sample data
python manage.py populate_db
```

### Step 3: Start Backend Server

```bash
python manage.py runserver
```

Visit `http://localhost:8000/admin` to access the Django admin panel.

### Step 4: Start Frontend Server

Open a new terminal and navigate to the frontend directory:

```bash
cd frontend

# Option A: Using Python's built-in server
python -m http.server 3000

# Option B: Using Node.js http-server
npx http-server -p 3000

# Option C: Use VS Code Live Server extension
# Right-click index.html → "Open with Live Server"
```

### Step 5: Access the Website

Open your browser and visit:
- **Frontend**: `http://localhost:3000/` 
- **API**: `http://localhost:8000/api/`
- **Admin**: `http://localhost:8000/admin/`

---

## 📋 Project Pages

1. **Home** (`index.html`) - Featured cars, categories, services
2. **Browse Cars** (`browse-cars.html`) - Search and filter all vehicles
3. **Car Details** (`car-detail.html?id=1`) - Full car specifications and reviews
4. **Services** (`services.html`) - Available services
5. **About Us** (`about.html`) - Company information
6. **Contact** (`contact.html`) - Contact form

---

## 🛠️ Admin Panel Tasks

### Add New Cars
1. Go to `http://localhost:8000/admin/`
2. Click "Cars" → "Add Car"
3. Fill in vehicle details
4. Save

### Manage Categories
1. Go to Admin Panel
2. Click "Categories" → "Add Category"
3. Fill in name and slug

### View Contact Messages
1. Go to Admin Panel
2. Click "Contacts" to see inquiries

---

## 🔌 API Endpoints

### Get All Cars
```
GET http://localhost:8000/api/cars/
```

### Get Featured Cars
```
GET http://localhost:8000/api/cars/featured/
```

### Get Car Details
```
GET http://localhost:8000/api/cars/ferrari-488-gtb/
```

### Filter Cars
```
GET http://localhost:8000/api/cars/?search=Ferrari&condition=new&min_price=200000
```

### Get All Categories
```
GET http://localhost:8000/api/categories/
```

### Get All Services
```
GET http://localhost:8000/api/services/
```

### Submit Contact Form
```
POST http://localhost:8000/api/contact/
Content-Type: application/json

{
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "+1234567890",
    "subject": "Car Inquiry",
    "message": "Interested in Ferrari 488 GTB",
    "car": 1
}
```

---

## 📱 Responsive Design

The website is fully responsive and works on:
- 📱 Mobile phones (320px+)
- 📱 Tablets (768px+)
- 💻 Desktops (1200px+)

---

## 🎨 Customization

### Change Colors
Edit `frontend/assets/css/style.css` and update CSS variables:

```css
:root {
    --primary-color: #c41e3a;      /* Ferrari Red */
    --secondary-color: #1a1a1a;    /* Dark Black */
    --accent-color: #ffd700;       /* Gold */
}
```

### Update Company Info
Edit the footer in HTML files:
- Company name
- Contact details
- Social media links
- Address

### Add New Pages
1. Create new HTML file in `frontend/`
2. Copy structure from existing pages
3. Update `assets/css/style.css` if needed
4. Add navigation link

---

## 🐛 Troubleshooting

### CORS Errors
Make sure backend is running on `http://localhost:8000`

### Database Errors
```bash
# Reset database
rm db.sqlite3
python manage.py migrate
python manage.py populate_db
```

### Static Files Not Loading
```bash
python manage.py collectstatic
```

### Port Already in Use
```bash
# Change port
python manage.py runserver 8001
# Update API_BASE_URL in main.js
```

---

## 📚 File Structure

```
cars/
├── backend/
│   ├── manage.py
│   ├── requirements.txt
│   ├── db.sqlite3 (created after migrate)
│   ├── racecars/
│   │   ├── settings.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── asgi.py
│   └── cars_app/
│       ├── models.py (Database models)
│       ├── views.py (API views)
│       ├── serializers.py (JSON serializers)
│       ├── urls.py (API routes)
│       └── admin.py (Admin panel)
│
└── frontend/
    ├── index.html
    ├── browse-cars.html
    ├── car-detail.html
    ├── services.html
    ├── about.html
    ├── contact.html
    └── assets/
        ├── css/style.css
        └── js/
            ├── main.js
            ├── browse.js
            ├── car-detail.js
            ├── services.js
            └── contact.js
```

---

## 💡 Sample Data

The `populate_db` command creates:
- 4 categories (Sports, Classic, Formula, Luxury)
- 4 sample cars (Ferrari, Lamborghini, Porsche, McLaren)
- 4 services (Maintenance, Modifications, Detailing, Training)

---

## 🚀 Deployment Ready

The project is ready for deployment:
- Update `DEBUG = False` in `settings.py`
- Set proper `SECRET_KEY`
- Update `ALLOWED_HOSTS`
- Use production database (PostgreSQL recommended)
- Setup email backend for contact forms

---

## 📞 Support

For help:
1. Check the README.md in root directory
2. Review API documentation
3. Check browser console for JavaScript errors
4. Check Django console for backend errors

---

## 🎯 Next Steps

1. ✅ Create sample data with `populate_db` command
2. ✅ Customize colors and branding
3. ✅ Add your company information
4. ✅ Upload real car images
5. ✅ Setup email for contact forms
6. ✅ Deploy to production server

---

Happy coding! 🏁
