# Laravel 10 Routing Guide

To view the routing diagram included in this project, you'll need to download the yEd Graph Editor:
📥 Download yEd: [https://www.yworks.com/products/yed](https://www.yworks.com/products/yed)

## Laravel 10 Routing Overview

### Basic Routing
- Define routes in `routes/web.php` for web interfaces and `routes/api.php` for API endpoints
- Basic route structure: `Route::method('uri', callback)`
- Available HTTP methods: `get`, `post`, `put`, `patch`, `delete`, `options`

### Route Parameters
- Required parameters: `Route::get('/user/{id}', ...)`
- Optional parameters: `Route::get('/user/{name?}', ...)`
- Regular expression constraints: `->where('id', '[0-9]+')`
- Global constraints in `RouteServiceProvider`

### Named Routes
- Assign names to routes: `Route::get('/profile', ...)->name('profile')`
- Generate URLs: `route('profile')`
- Redirect to named routes: `redirect()->route('profile')`

### Route Groups
- Route prefixes:
  ```php
  Route::prefix('admin')->group(function () {
      // Matches "/admin/users"
      Route::get('users', function () {
          // ...
      });
  });
  ```
- Middleware groups
- Namespace grouping
- Route name prefixes

### Route Model Binding
- Implicit binding: `Route::get('/users/{user}', ...)`
- Explicit binding in `RouteServiceProvider`
- Customizing the key name: `getRouteKeyName()`

### Rate Limiting
- Using `throttle` middleware
- Configure in `RouteServiceProvider`
- Custom rate limiters

### Fallback Routes
- Define a fallback route when no other routes match
- `Route::fallback(function () { ... })`

### Route Caching
- Speed up route registration
- Run `php artisan route:cache`
- Clear with `php artisan route:clear`

For more detailed information, visit the <a href="https://laravel.com/docs/10.x/routing" target="_blank">Laravel Documentation</a>

