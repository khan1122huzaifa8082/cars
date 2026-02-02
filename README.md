# RaceCars Website Replica

A professional racing and performance vehicle marketplace website with Django backend and modern HTML/CSS/JavaScript frontend.

## Project Structure

```
cars/
├── backend/           # Django REST API
│   ├── manage.py
│   ├── requirements.txt
│   ├── racecars/     # Project settings
│   └── cars_app/     # Main application
├── frontend/         # HTML/CSS/JavaScript
│   ├── index.html
│   ├── browse-cars.html
│   ├── car-detail.html
│   ├── services.html
│   ├── about.html
│   ├── contact.html
│   └── assets/       # CSS and JavaScript files
└── README.md
```

## Features

### Frontend
- **Home Page**: Hero section, featured cars, categories, services overview
- **Browse Cars**: Advanced filtering, search, pagination
- **Car Details**: Full specifications, reviews, image gallery
- **Services**: Service listings with detailed information
- **About Us**: Company information, team, values
- **Contact**: Contact form with email integration

### Backend (Django)
- RESTful API with Django REST Framework
- Car catalog management
- Category management
- Services management
- Contact form handling
- Review system
- Admin panel for content management

## Setup Instructions

### Backend Setup

1. **Install Python dependencies:**
   ```bash
   cd backend
   pip install -r requirements.txt
   ```

2. **Apply migrations:**
   ```bash
   python manage.py migrate
   ```

3. **Create superuser:**
   ```bash
   python manage.py createsuperuser
   ```

4. **Load sample data:**
   ```bash
   python manage.py populate_db
   ```

5. **Run the development server:**
   ```bash
   python manage.py runserver
   ```

   The API will be available at `http://localhost:8000/api`

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Open in a browser or use a local server:**
   - Option 1: Use Python's built-in server
     ```bash
     python -m http.server 3000
     ```
   - Option 2: Use VS Code Live Server extension
   - Option 3: Open `index.html` directly (limited functionality)

3. **Access the website at:**
   - `http://localhost:3000/` (if using Python server)
   - Or directly open HTML files in browser

## API Endpoints

### Cars
- `GET /api/cars/` - List all cars with pagination
- `GET /api/cars/{slug}/` - Get specific car details
- `GET /api/cars/featured/` - Get featured cars
- `POST /api/cars/{slug}/add_review/` - Add a review

**Query Parameters:**
- `search` - Search by title or make
- `category` - Filter by category slug
- `condition` - Filter by condition (new, used, refurbished)
- `min_price` - Minimum price filter
- `max_price` - Maximum price filter
- `page` - Page number
- `page_size` - Items per page

### Categories
- `GET /api/categories/` - List all categories
- `GET /api/categories/{slug}/` - Get specific category

### Services
- `GET /api/services/` - List all services
- `GET /api/services/{slug}/` - Get specific service

### Contact
- `POST /api/contact/` - Submit contact form
- `GET /api/contact/` - List contacts (admin only)

## Database Models

### Car
- Title, slug, description
- Price, year, make, model
- Condition (new, used, refurbished)
- Engine specs (type, horsepower, top speed, acceleration)
- Transmission, fuel type, color, mileage
- Category relationship
- Featured status, availability
- Image and gallery support

### Category
- Name, slug, description

### Service
- Title, slug, description
- Image, active status

### Contact
- Name, email, phone
- Subject, message
- Associated car
- Reply status

### Review
- Car relationship
- Name, email, rating (1-5)
- Comment
- Approval status

## Admin Panel

Access the Django admin panel at `http://localhost:8000/admin`

Login with superuser credentials and manage:
- Cars and inventory
- Categories
- Services
- Contact inquiries
- Reviews

## Customization

### Adding New Cars
1. Go to Django admin
2. Click "Add Car" in the Cars section
3. Fill in all required information
4. Click Save

### Modifying Styling
Edit `frontend/assets/css/style.css` to customize:
- Colors (update CSS variables in `:root`)
- Layout and spacing
- Responsive breakpoints

### Updating API Base URL
If running backend on different port/domain:
1. Edit `frontend/assets/js/main.js`
2. Change `API_BASE_URL` variable to your backend URL

## Technologies Used

### Backend
- Django 4.2.7
- Django REST Framework 3.14.0
- Django CORS Headers
- Pillow (Image handling)
- SQLite (default database)

### Frontend
- HTML5
- CSS3 (Flexbox, Grid)
- Vanilla JavaScript (ES6+)
- Font Awesome Icons

## Features Included

✅ Responsive design (mobile, tablet, desktop)
✅ Advanced filtering and search
✅ Shopping cart ready
✅ Review system
✅ Contact form with email support
✅ Admin panel for content management
✅ RESTful API
✅ Pagination
✅ Image gallery
✅ Social media links
✅ SEO-friendly URLs
✅ Error handling
✅ Loading states

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance Optimization

- Lazy loading for images
- Pagination for large datasets
- Debounced search queries
- Cached API responses
- Minified CSS and JavaScript ready

## Future Enhancements

- User authentication and profiles
- Wishlist functionality
- Payment gateway integration
- Advanced analytics
- Live chat support
- Blog section
- Mobile app

## Support

For issues or questions, contact: support@racecars.com

## License

© 2024 RaceCars. All rights reserved.
