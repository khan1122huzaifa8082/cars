# RaceCars - Complete Website Replica

## 🎯 What's Included

Your complete RaceCars website replica includes:

### ✅ Backend (Django)
- Full REST API with Django REST Framework
- SQLite Database with models for Cars, Categories, Services, Reviews, and Contacts
- Admin panel for content management
- CORS enabled for frontend integration
- Pagination and filtering support
- Image upload support

### ✅ Frontend (HTML/CSS/JavaScript)
- 6 responsive pages (Home, Browse, Details, Services, About, Contact)
- Modern design matching professional racing sites
- Advanced filtering and search functionality
- Review system
- Contact form
- Mobile-friendly responsive design
- Progressive enhancement

### ✅ Ready-to-Use Features
- Sample database populated with 4 cars and 4 services
- Search and filter by category, condition, price
- Car details with full specifications
- Customer review system
- Contact inquiry system
- About page with team information
- Social media integration ready

---

## 🚀 Quick Start (Windows)

### For Backend:
```bash
cd backend
setup.bat
```
This will:
1. Install all dependencies
2. Create the database
3. Create admin user
4. Load sample data

Then run:
```bash
run.bat
```

### For Frontend:
```bash
cd frontend
run.bat
```

---

## 🚀 Quick Start (Linux/Mac)

### For Backend:
```bash
cd backend
chmod +x setup.sh
./setup.sh
```

Then run:
```bash
chmod +x run.sh
./run.sh
```

### For Frontend:
```bash
cd frontend
chmod +x run.sh
./run.sh
```

---

## 📚 Default Sample Data

After running `populate_db`, you'll have:

**Cars:**
- Ferrari 488 GTB - $245,000
- Lamborghini Huracán - $261,000
- Porsche 911 Turbo - $203,000
- McLaren 720S - $309,000

**Categories:**
- Sports Cars
- Classic Racing
- Formula Replica
- Luxury Performance

**Services:**
- Racing Maintenance
- Custom Modifications
- Professional Detailing
- Racing Training

---

## 🔐 Admin Credentials

You'll create these during setup:
- Username: (your choice)
- Password: (your choice)
- Email: (your choice)

---

## 📊 Database Schema

### Cars Table
- ID, Title, Slug
- Price, Year, Make, Model
- Condition (new/used/refurbished)
- Engine Type, Horsepower, Top Speed
- Acceleration, Transmission, Fuel Type
- Color, Mileage
- Category (Foreign Key)
- Featured, Available status
- Images and Gallery

### Categories Table
- ID, Name, Slug, Description

### Services Table
- ID, Title, Slug, Description
- Image, Active status

### Contacts Table
- ID, Name, Email, Phone
- Subject, Message
- Car (Foreign Key, optional)
- Reply status

### Reviews Table
- ID, Car (Foreign Key)
- Name, Email, Rating (1-5)
- Comment, Approved status

---

## 🌐 API Endpoints Reference

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/cars/ | List all cars |
| GET | /api/cars/featured/ | Get featured cars |
| GET | /api/cars/{slug}/ | Get car details |
| POST | /api/cars/{slug}/add_review/ | Add review to car |
| GET | /api/categories/ | List categories |
| GET | /api/services/ | List services |
| POST | /api/contact/ | Submit contact form |

---

## 🎨 Customization Guide

### Change Company Name
1. Edit `frontend/index.html` - Change "RaceCars" in navbar
2. Edit `frontend/assets/css/style.css` - Update colors if needed
3. Edit `backend/racecars/settings.py` - Update site name in admin

### Change Colors (Primary Red Theme)
Edit `frontend/assets/css/style.css`:
```css
:root {
    --primary-color: #c41e3a;      /* Change this */
    --secondary-color: #1a1a1a;    /* Or this */
    --accent-color: #ffd700;       /* Or this */
}
```

### Change Contact Info
Edit footer in all HTML files:
- Email: info@racecars.com
- Phone: +1 (555) 123-4567
- Address: Update in contact.html

### Add New Cars (Without Admin)
Use Django admin at `http://localhost:8000/admin/`
1. Go to Cars section
2. Click "Add Car"
3. Fill in all fields
4. Save

---

## 📱 Pages Overview

| Page | Path | Purpose |
|------|------|---------|
| Home | index.html | Hero, featured cars, categories, services |
| Browse | browse-cars.html | All cars with filters and search |
| Details | car-detail.html | Full car specs, reviews, inquiry |
| Services | services.html | All services offered |
| About | about.html | Company info, team, values |
| Contact | contact.html | Contact form, business hours |

---

## 🛠️ Troubleshooting

### Port 8000 Already in Use?
```bash
python manage.py runserver 8001
# Then update API_BASE_URL in frontend/assets/js/main.js
```

### Port 3000 Already in Use?
```bash
python -m http.server 4000
# Open http://localhost:4000 instead
```

### Database Issues?
```bash
# Delete and recreate database
rm db.sqlite3
python manage.py migrate
python manage.py populate_db
```

### CORS Errors?
Make sure backend is running and the API_BASE_URL in main.js points to the correct backend URL.

### Images Not Showing?
Images need to be uploaded through admin panel. The frontend expects images at `/media/cars/`

---

## 📦 Project Files

```
cars/
├── README.md              # Full documentation
├── QUICK_START.md         # Quick start guide
├── DETAILED_SETUP.md      # This file
├── .gitignore
├── LICENSE
│
├── backend/
│   ├── manage.py
│   ├── requirements.txt   # Python dependencies
│   ├── setup.bat/.sh      # Setup scripts
│   ├── run.bat/.sh        # Run scripts
│   │
│   ├── racecars/          # Project settings
│   │   ├── settings.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── asgi.py
│   │
│   └── cars_app/          # Main app
│       ├── models.py
│       ├── views.py
│       ├── serializers.py
│       ├── urls.py
│       ├── admin.py
│       ├── apps.py
│       └── management/commands/populate_db.py
│
└── frontend/
    ├── index.html         # Home page
    ├── browse-cars.html   # Car listings
    ├── car-detail.html    # Car details
    ├── services.html      # Services
    ├── about.html         # About us
    ├── contact.html       # Contact form
    ├── run.bat/.sh        # Run scripts
    │
    └── assets/
        ├── css/
        │   └── style.css  # All styling
        │
        ├── js/
        │   ├── main.js          # Main API calls
        │   ├── browse.js        # Browse page logic
        │   ├── car-detail.js    # Detail page logic
        │   ├── services.js      # Services logic
        │   └── contact.js       # Contact form logic
        │
        └── images/        # Place images here
```

---

## 🔒 Security Notes

⚠️ **For Production:**
1. Change `SECRET_KEY` in settings.py
2. Set `DEBUG = False` in settings.py
3. Update `ALLOWED_HOSTS` with your domain
4. Use environment variables for sensitive data
5. Setup HTTPS
6. Use a production database (PostgreSQL)
7. Setup proper email backend

---

## 📈 Next Steps

1. ✅ Test the application locally
2. ✅ Customize branding and colors
3. ✅ Add your own car inventory
4. ✅ Upload real images
5. ✅ Configure email for contact forms
6. ✅ Deploy to production

---

## 💡 Tips & Tricks

### Add Sample Cars Quickly
The `populate_db` command creates 4 sample cars. To add more:
1. Modify `/backend/cars_app/management/commands/populate_db.py`
2. Add car data to the `cars_data` list
3. Run: `python manage.py populate_db`

### Custom Fields
Need to add fields to cars? Edit:
1. `backend/cars_app/models.py` - Add field to Car model
2. Run: `python manage.py makemigrations` and `python manage.py migrate`
3. Update admin.py to show new field

### Enable Email Notifications
In `settings.py`, configure email backend:
```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'
```

---

## 📞 Need Help?

Check these files in order:
1. QUICK_START.md - For quick setup
2. README.md - For full documentation
3. This file - For detailed setup
4. Django docs - https://docs.djangoproject.com/
5. DRF docs - https://www.django-rest-framework.org/

---

## ✨ Features You Have

✅ Full CRUD operations for cars
✅ Advanced search and filtering
✅ Review and rating system
✅ Contact form with email
✅ Admin panel
✅ RESTful API
✅ Responsive design
✅ Pagination
✅ Image galleries
✅ Category management
✅ Service management
✅ Professional styling
✅ Modern JavaScript
✅ Sample data included

---

## 🎉 Ready to Launch!

Your RaceCars website is ready for:
- Local development
- Testing
- Client demos
- Production deployment

Happy coding! 🏁
