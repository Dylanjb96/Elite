# **Elite Stay**

The **Elite Stay** is a Booking hotel website built using Django to allow customers to view and book hotel, edit and see their bookings and how much they spent in booking, along with invoices. The application allows customers to choose date for check-in and check-out, select room and prices, manage their bookings, and leave reviews. The admin can manage and see their customers profiles, receive reviews, invoices, payment status. The app is built to prioritize user-friendliness, quick responsiveness, and strong security.

---

## **Table of Contents**

1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Application Structure](#application-structure)
4. [Database Models](#database-models)
5. [Features and Functionality](#features-and-functionality)
    - [User Registration](#user-registration)
    - [User Sign-in](#user-login)
    - [Dashboard (Customers & Admin)](#dashboard-customer-and-admin)
    - [Profile Management](#profile-management)
    - [Booking Management](#booking-management)
    - [Review System](#review-system)
    - [Logout and Error Handling](#logout-and-error-handling)
6. [Interactive Components](#interactive-components)
7. [Security and Authentication](#security-and-authentication)
8. [Deployment and Setup](#deployment-and-setup)


---

## **Project Overview**

The platform consists of two primary user types:

- **Customers**: Users who can book hotels.
- **Admin**: Professionals who provide services and manage customers' bookings & payments.

---

## **Technologies Used**

### **Backend**

- **Python 3.12.3**: Main programming language.
- **Django 5.1.1**: Web framework providing routing, ORM, and admin interface.
- **Django ORM**: To interact with the PostgreSQL database.
- **PostgreSQL**: Relational database management system for storing data.
- **Django Crispy Forms 2.3.0**: For better form handling and rendering.
- **Django Mathfilters 1.0.0** To perform basic arithmetic operations (add, sub, divide, multiply) in Django templates.
- **Django Jazzmin 3.0.0** Provides a modern and highly customizable theme for Django's default admin interface.

### **Frontend**

- **HTML/CSS**: For page structuring and design.
- **Bootstrap**: CSS framework for responsive design.
- **Font Awesome**: For icons and design enhancements.
- **JavaScript**: For adding interactivity to the application.
- **jQuery 3.7.1**: For simplified DOM manipulation and AJAX handling.

### **Other**
- **Jazzin**: Admin interface for Elite Stay.
- **Environs**: For cleaner code and reducing runtime errors.

---

## **Application Structure**

The project is organized into the following Django apps:

1. **admin/**: Manages users' profiles, bookings, hotels, prices, coupons and reviews. Manages the creation, modification, and deletion of bookings.
2. **customers/**: Handles customers profiles, payment and bookings.

The main directories and files are:

- `settings.py`: Defines the project's configuration, including database connections, static file handling, and installed apps.
- `urls.py`: The main URL routing file, directing incoming requests to their corresponding views or applications.
- `manage.py`: A command-line tool used for managing various aspects of the project, such as running the server and performing migrations.

---

## **Database Models**

The application relies on PostgreSQL for data storage, with Django ORM handling all the database interactions. Key models are:

1. **User Model**: Handles user authentication, profiles, contact details, password and hotel they booked.
2. **Admin Model**:
   - Edit, add and delete hotel details, profile details. Also add coupon information.
3. **Hotel Model**:
   - Represents users who uploaded their hotel to the website, with location, contact details, FAQs and prices of different room types.
4. **Booking Model**:
   - Contains booking details like room, date, and duration, customer, and payment status.
5. **Review Model**:
   - Stores reviews and ratings (1-5 stars).

---

## **Features and Functionality**

### **User Registration**

- **Home Page**: Provides buttons for users to register or log in.
- **Registration Page**:
  - The user selects either sign-in or sign-up.
  - The registration form.
  - Validation guarantees that the input is accurate and complete.

### **User Login**

- **Home Page**: The user can click **Sign In**.
- **Sign in Page**:
  - Users input their email and password.
  - If the sign-in is successful, the user is redirected to the Home page.

### **Dashboard**

#### **Customer Dashboard**
- The customer can change thier password, change and edit thier profile, view thier wallet, notifications, bookings and invoices.

#### **Admin Dashboard (Jazzmin)**
- Displays all bookings being made by the customers, check the payment status, view their contact and booking details.
- Options to view, edit, and delete bookings.
- The admin can manage rooms, view customers' reviews and apply coupon for customers to use for future bookings.

### **Booking Management**

- **Booking Page**:
  - Customers can select hotels, check-in and check-out date on the calender, and leave a review of the hotel. 
  - Bookings and payment status are saved in the database and displayed on the dashboard.
- **Booking Edit Page**:
  - Customers can modify thier bookings, contact details and save changes.
- **Booking Delete Page**:
  - Customers can delete booking before confirmation of thier booking.

### **Review System**

- **Customers**: Can leave reviews for hotels.
- **Admin/Customers**: Can view reviews and ratings from customers.
  
### **Logout and Error Handling**

- **Logout**: Customers can log out from anywhere in the application.
- **Error Handling**: The application shows error messages during form submissions (e.g., invalid data or incorrect credentials).

---

## **Interactive Components**

- **Calendar**: 
  - Users can view the calender and select the date for check-in and check-out.
  - AJAX is used to fetch, update, and manage booking data in real-time.

- **Payment**:
  - Users can select the payment method. They can use mock cards for Flutterwave or Stripe payments.
  - For Flutterwave payment, use the card number: 4187427415564246, Expiry: 09/32 and CVV: 828.
  - For Stripe payment, use the card number:  4242 4242 4242 4242, Expiry: 12/34 and CVV: Any 3 number.  
  
- **Bootstrap & Responsive Design**: Ensures a seamless and user-friendly experience across all devices, including desktops, tablets, and mobile phones, by automatically adjusting the layout to fit various screen sizes.

---

## **Security and Authentication**

- **Django Auth**: Provides secure user authentication and session management.
- **CSRF Protection**: CSRF tokens are used to secure forms and prevent CSRF attacks.
- **Password Hashing**: Passwords are stored using Django’s built-in hashing mechanism.
- **Role-based Access Control**: Based on the user access. If they create superuser account, they can access the admin and customer interfaces. If not, they can only access the customer interface (Elite Stay website).

---

## **Deployment and Setup**

### **Prerequisites**

- **Python 3.12.1** installed.
- **PostgreSQL** installed and configured.

### **Installation Steps**

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Dylanjb96/Elite-Stay.git
   cd Elite Stay

2. **Create a virtual environment**:

   ```bash
   python3 -m venv myenv
   source myenv/bin/activate  # For Linux/macOS
   myenv\Scripts\activate     # For Windows
    pip install -r requirements.txt

3. **(Optional) Create Superuser account**:

  ```bash
  python manage.py createsuperuser
  Username: The username for your superuser account.
  Email address: The email associated with this superuser.
  Password: Choose a strong password (you'll be asked to confirm it).


4. **Admin Interface (Jazzmin)**:

    ```bash
    python manage.py runserver 
    navigate to localhost:8000/admin 

5. **Customer / User Interface**:

    ```bash
    python manage.py runserver
    navigate to http://127.0.0.1:8000/
