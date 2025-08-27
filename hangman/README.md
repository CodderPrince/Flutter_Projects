# 🍽️ FoodieLand — A Community-Driven Recipe and Blog Platform

---

<p align="center">
  <img src="https://github.com/CodderPrince/foodieland/blob/development/assets/images/home.png?raw=true" width="260" />
  <img src="https://github.com/CodderPrince/foodieland/blob/development/assets/images/Recipe_Details.png?raw=true" width="260" />
</p>
<p align="center">
  <img src="https://github.com/CodderPrince/foodieland/blob/development/assets/images/Blog_List.png?raw=true" width="260" />
  <img src="https://github.com/CodderPrince/foodieland/blob/development/assets/images/Blog_Post.png?raw=true" width="260" />
</p>
<p align="center">
  <img src="https://github.com/CodderPrince/foodieland/blob/development/assets/images/Contact.png?raw=true" width="260" />
</p>

---

## 🍕 Project Overview

**FoodieLand** is a user-driven Flutter platform designed to connect cooking enthusiasts, allowing them to share recipes, write blogs, and explore the culinary world together. Built with Flutter, GetX for state management, and Supabase for backend services, FoodieLand aims to be a fully community-driven space without the need for a traditional admin panel.

Whether you're a seasoned chef, a home cook, or just someone who loves food, FoodieLand provides the tools to share your passion and discover new flavors.

---

## ✨ Highlights & Feature Deep Dive

### 📝 Feature Set

-   **Authentication:**
    -   Secure user account creation and login via email & password or social media (Google, Facebook, etc.).
    -   Email verification for account activation.
    -   Form validation with mandatory field checks, email format verification, and strong password validation.
    -   Forgot Password functionality.
-   **Home Screen:**
    -   Engaging entry point with a drawer for navigation (Home, Recipes, Blogs, Contact, Profile).
    -   Dynamic slider showcasing featured recipes fetched from the database.
    -   Category section with cards that filter recipe lists.
    -   "Add Recipe" button visible to logged-in users.
    -   Recipe listing grid with thumbnails, titles, and ratings.
    -   Featured Chef section with links to detailed profiles.
    -   Social media handles for platform branding.
-   **Recipe Details Screen:**
    -   Complete information about a specific recipe, including a featured image, title, ingredient list, and step-by-step preparation guide.
-   **Recipe Adding Screen:**
    -   Form for logged-in users to submit new recipes, including fields for the recipe title, short description, image upload, ingredients (multi-line or list format), preparation steps, category selection, and a submit button to save the recipe to the database with the user ID as the author.
-   **Blog List Screen:**
    -   Display of all blog posts with browsing options and an "Add Blog" button for logged-in users.
    -   Blog listing with image, title, and short description.
-   **Blog Post Screen:**
    -   Display of the complete content of a single blog post, including a large featured image, post title, author, full article content, and a related blog posts section.
-   **Blog Adding Screen:**
    -   Form for users to publish blog articles, including fields for the blog title, short description, image upload, full content, and a submit button to save the blog to the database with the user ID as the author.
-   **Contact Us Screen:**
    -   Channel for user communication, including a contact form with fields for name, email, message, subject, and enquiry type, as well as contact details (phone, email, address) and a recent recipes/posts section.
-   **User Profile Screen:**
    -   Management of user accounts, including display of personal details (name, email, profile picture, bio), edit profile details, delete account, and a messages section to store messages received via the "Contact Us" form.

### 📱 UI & UX

-   Clean and intuitive user interface.
-   Visually appealing design with attention to detail.
-   Responsive layout for different screen sizes.

### 🏗️ Architecture & Design

-   Flutter for cross-platform development (Android and iOS).
-   GetX for state management, navigation, and dependency injection.
-   Supabase for backend services (authentication, database).
-   Modular project structure for maintainability and scalability.

---

## ⚙️ Installation & Setup

### ⚠️ Prerequisites

-   Flutter SDK installed
-   Dart SDK installed
-   Supabase account and project set up
-   Firebase account and project set up (for social logins if using)

### ⬇️ Run Locally

1.  Clone the repository:

    ```bash
    git clone https://github.com/CodderPrince/foodieland.git
    cd foodieland
    ```

2.  Install dependencies:

    ```bash
    flutter pub get
    ```

3.  Configure Supabase:

    -   Set up your Supabase project and database schema.
    -   Enable authentication (email/password, social logins).
    -   Implement Row Level Security (RLS) policies to protect your data.
    -   Update `api_constants.dart` with your Supabase URL and Anon Key.

4.  Run the app:

    ```bash
    flutter run
    ```

---

## 🗂️ File & Resource Structure
```
foodieland/
├── android/
├── ios/
├── lib/
│   ├── main.dart
│   ├── config/
│   │   ├── theme.dart
│   │   ├── routes.dart
│   │   ├── api_constants.dart
│   │   ├── app_constants.dart
│   │   └── app_config.dart
│   ├── data/
│   │   ├── models/
│   │   │   ├── recipe_model.dart
│   │   │   ├── blog_model.dart
│   │   │   ├── user_model.dart
│   │   │   └── category_model.dart
│   │   ├── providers/
│   │   │   └── supabase_provider.dart
│   │   ├── repositories/
│   │   │   ├── recipe_repository.dart
│   │   │   └── recipe_repository_impl.dart
│   │   ├── services/
│   │   │   └── image_upload_service.dart
│   │   └── supabase_service.dart
│   ├── modules/                   // Feature modules managed by GetX
│   │   ├── home/                   // Home feature
│   │   │   ├── home_binding.dart    // Dependency Injection with GetX
│   │   │   └── home_controller.dart // State management with GetX
│   │   ├── recipe_details/          // Recipe Details feature
│   │   │   ├── recipe_details_binding.dart
│   │   │   └── recipe_details_controller.dart
│   │   ├── blog_list/             // Blog List feature
│   │   │   ├── blog_list_binding.dart
│   │   │   └── blog_list_controller.dart
│   │   ├── blog_post/             // Blog Post feature
│   │   │   ├── blog_post_binding.dart
│   │   │   └── blog_post_controller.dart
│   │   ├── add_recipe/            // Add Recipe feature
│   │   │   ├── add_recipe_binding.dart
│   │   │   └── add_recipe_controller.dart
│   │   ├── add_blog/              // Add Blog feature
│   │   │   ├── add_blog_binding.dart
│   │   │   └── add_blog_controller.dart
│   │   ├── contact/               // Contact feature
│   │   │   ├── contact_binding.dart
│   │   │   └── contact_controller.dart
│   │   ├── profile/               // User Profile feature
│   │   │   ├── profile_binding.dart
│   │   │   └── profile_controller.dart
│   │   ├── authentication/         // Authentication Feature
│   │   │   ├── login/             // Login Feature
│   │   │   │   ├── login_binding.dart
│   │   │   │   └── login_controller.dart
│   │   │   ├── register/          // Register Feature
│   │   │   │   ├── register_binding.dart
│   │   │   │   └── register_controller.dart
│   │   │   └── forgot_password/   // Forgot Password Feature
│   │   │       ├── forgot_password_binding.dart
│   │   │       └── forgot_password_controller.dart
│   │   └── splash/               // Splash Screen Feature
│   │       ├── splash_binding.dart
│   │       └── splash_controller.dart
│   ├── screens/                   // All screens in one folder
│   │   ├── home_screen.dart       // UI for the Home screen
│   │   ├── recipe_details_screen.dart // UI for Recipe Details screen
│   │   ├── blog_list_screen.dart  // UI for Blog List screen
│   │   ├── blog_post_screen.dart  // UI for Blog Post screen
│   │   ├── add_recipe_screen.dart // UI for Add Recipe screen
│   │   ├── add_blog_screen.dart   // UI for Add Blog screen
│   │   ├── contact_screen.dart    // UI for Contact screen
│   │   ├── profile_screen.dart    // UI for Profile screen
│   │   ├── login_screen.dart      // UI for Login screen
│   │   ├── register_screen.dart   // UI for Register screen
│   │   ├── forgot_password_screen.dart // UI for Forgot Password screen
│   │   └── splash_screen.dart     // UI for Splash screen
│   ├── presentation/            // Reusable widgets (global)
│   │   ├── widgets/
│   │   │   ├── recipe_card.dart
│   │   │   ├── category_button.dart
│   │   │   ├── rounded_button.dart
│   │   │   ├── input_text_field.dart
│   │   │   ├── loading_indicator.dart
│   │   │   ├── custom_app_bar.dart
│   │   │   └── custom_drawer.dart
│   │   ├── theme/
│   │   │   └── app_colors.dart
│   │   └── layout/
│   │       └── responsive_layout.dart
│   ├── routes/                  // Named routes for GetX navigation
│   │   └── app_pages.dart
│   ├── utils/                    // Utility functions, helper classes
│   │   ├── date_formatter.dart
│   │   ├── image_helper.dart
│   │   ├── network_helper.dart
│   │   ├── app_logger.dart
│   │   └── validators.dart
│   └── app.dart                  // Root widget for the application
├── assets/                       // Static assets
│   ├── images/
│   │   ├── logo.png
│   │   ├── placeholder.png
│   │   └── ...
│   ├── fonts/
│   │   ├── OpenSans-Regular.ttf
│   │   └── ...
│   ├── data/
│   │   ├── sample_recipes.json
│   │   └── sample_blogs.json
├── test/                         // Unit tests
│   ├── widget_test.dart
│   └── ...
├── integration_test/             // Integration tests
│   ├── app_test.dart
│   └── ...
├── .gitignore
├── pubspec.yaml
├── pubspec.lock
└── README.md
```


---
## 🗺️ Roadmap & Future Ideas

*   Implement social features like liking, commenting, and sharing recipes/blogs.
*   Add user profiles with the ability to follow other users.
*   Incorporate a recommendation system to suggest recipes and blogs based on user preferences.
*   Develop a robust search functionality to easily find recipes and blogs.
*   Enhance the UI/UX with more animations and transitions.
*   Implement push notifications for new recipes, blogs, and user activity.
*   Add offline support for accessing cached recipes and blogs.

---

## 📜 License & Acknowledgements

**License:** This project is MIT-licensed—see the LICENSE file for details.

**Special thanks**:

*   The Flutter community for the amazing framework and support.
*   The GetX community for the powerful and easy-to-use library.
*   The Supabase team for the scalable and secure backend-as-a-service.

---

## 🤝 Author & Contributions

**Md. An Nahian Prince** (Team Leader)

*   Dept. of CSE, Begum Rokeya University, Rangpur
*   GitHub: [CodderPrince](https://github.com/CodderPrince)

**Team Members:**

*   Shoriful Islam Siam
*   Sakil Ahmed
*   Md. Jahidul Islam
*   S. M. Rakibul Alam

Contributions are welcome—fork the repository, improve modules, and showcase your Flutter skills!

---

*Thank you for exploring FoodieLand — where community meets culinary creativity!*

---
