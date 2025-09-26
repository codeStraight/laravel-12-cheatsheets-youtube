# Laravel Routing Cheatsheet (Episode 2)

This cheatsheet contains all the code examples from the Laravel Routing tutorial along with very brief explanations for quick reference.

---

## 1. Default Route (welcome view)
```php
use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return view('welcome');
});
```
➡️ Defines the homepage route `/` and returns the **welcome view**.

---

## 2. Basic Route Returning Text
```php
use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return 'Hello, world!';
});
```
➡️ Example of a simple route returning plain text instead of a view.

---

## 3. Route with Parameter
```php
use Illuminate\Support\Facades\Route;

Route::get('/product/{id}', function ($id) {
    return "Product with ID: $id";
});
```
➡️ Defines a dynamic route where `{id}` is passed as a parameter.

---

## 4. Route with Optional Parameter
```php
Route::get('/products/{category?}', function ($category = null) {
    if ($category) {
        return "Products in category: $category";
    } else {
        return "All products";
    }
});
```
➡️ Parameter `{category?}` is optional. If missing, defaults to showing “All products.”

---

## 5. Route with Numeric Constraint
```php
use Illuminate\Support\Facades\Route;

Route::get('/product/{id}', function ($id) {
    return "Product with ID: $id";
})->where('id', '[0-9]+');
```
➡️ Adds a **constraint**: `id` must be numeric.

---

## 6. Route with Alphanumeric Constraint
```php
Route::get('/users/{username}', function ($username) {
    return "User name: $username";
})->where('username', '[a-zA-Z0-9]+');
```
➡️ Restricts `username` to alphanumeric only.

---

## 7. Route with `whereAlpha()`
```php
Route::get('/product/{title}', function (string $title) {
    return 'Product Title: ' . $title;
})->whereAlpha('title');
```
➡️ Ensures the parameter contains **only letters**.

---

## 8. Route with `whereNumber()`
```php
Route::get('/product/{number}', function (string $number) {
    return 'Product Number: ' . $number;
})->whereNumber('number');
```
➡️ Ensures the parameter is **numeric only**.

---

## 9. Route with `whereAlphaNumeric()`
```php
Route::get('/product/{title}', function (string $title) {
    return 'Product Title: ' . $title;
})->whereAlphaNumeric('title');
```
➡️ Ensures the parameter contains **letters and numbers only**.

---

## 10. Route with `whereIn()`
```php
Route::get('/category/{category}', function (string $category) {
    return 'Product category: ' . $category;
})->whereIn('category', ['movie', 'song', 'painting']);
```
➡️ Restricts `category` to specific allowed values.

---

## 11. Named Route Example
```php
use Illuminate\Support\Facades\Route;

Route::get('/product/{id}', function ($id) {
    return "Product with ID: $id";
})->name('product.show');
```
➡️ Assigns a name (`product.show`) to the route for easy reference.

---

## 12. Using Named Route in Blade View
```php
<!-- welcome.blade.php -->
<a href="{{ route('product.show', ['id' => 5]) }}">View Product</a>
```
➡️ Generates a link using the route name `product.show`.

---

## 13. Admin Routes Without Grouping
```php
Route::get('/admin/dashboard', function () {
    return "Admin Dashboard";
})->name('admin.dashboard');

Route::get('/admin/settings', function () {
    return "Admin Settings";
})->name('admin.settings');

Route::get('/admin/profile', function () {
    return "Admin Profile";
})->name('admin.profile');
```
➡️ Defines admin routes **individually** with names.

---

## 14. Admin Routes Using Group
```php
use Illuminate\Support\Facades\Route;

Route::prefix('admin')->name('admin.')->group(function () {
    Route::get('/dashboard', function () {
        return 'Admin Dashboard';
    })->name('dashboard');

    Route::get('/settings', function () {
        return 'Admin Settings';
    })->name('settings');
    
    Route::get('/profile', function () {
        return 'Admin Profile';
    })->name('profile');
});
```
➡️ Groups admin routes with common **prefix** and **name**.

---

## 15. Fallback Route Example
```php
Route::fallback(function () {
    return 'Page Not Found';
});
```
➡️ Handles any request that doesn’t match defined routes.

---

## 16. Custom Fallback Returning a View
```php
return view('errors.404');
```
➡️ Displays a **404 error view** when no routes match.

---

## 17. Custom Fallback Redirect
```php
return redirect('/');
```
➡️ Redirects the user to the homepage if route not found.

---

## 18. Custom Fallback JSON Response
```php
return response()->json(['message' => 'Page Not Found'], 404);
```
➡️ Returns a **JSON 404 response** for APIs.

---

## 19. Artisan Command: List All Routes
```bash
php artisan route:list
```
➡️ Shows a list of all registered routes in the application.

---

## 20. Artisan Command: Exclude Vendor Routes
```bash
php artisan route:list --except-vendor
```
➡️ Lists only **application routes**, excluding vendor package routes.

---

## 21. Artisan Command: Only Vendor Routes
```bash
php artisan route:list --only-vendor
```
➡️ Lists only **third-party (vendor) routes**.

---

## 22. Artisan Command: Filter by Prefix
```bash
php artisan route:list --path=admin
```
➡️ Shows only routes that start with a specific prefix (like `admin`).

---

✅ End of Cheatsheet.
