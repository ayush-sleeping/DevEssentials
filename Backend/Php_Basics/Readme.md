## Php required for Laravel ( Learning Notes )
> A short and comprehensive guide to Php fundamentals, structure, and best practices
- What is Php
> Php is a popular general-purpose scripting language that is especially suited to web development. Fast, flexible and pragmatic, Php powers everything from your blog to the most popular websites in the world.

All fundamental PHP concepts
OOP principles (crucial for Laravel)
Modern PHP features
Security basics
Database foundations


<div id="top"></div>

<!-- ---------------------------------------------------------------------------------------------------------------------- -->

### 📋 Table of Contents

| Section | Topic | Description | Used In Laravel For |
|---------|---------------------|------------------------------------------|---------------------|
| **CORE PHP FUNDAMENTALS** |   |                                          |                     |
| 1 | [PHP Basics](#php-basics) | Variables, constants, data types, syntax | Basic Laravel coding, config files |
| 2 | [Arrays](#arrays) | Indexed, associative, multidimensional arrays | Config arrays, request data, collections foundation |
| 3 | [Functions](#functions) | Function definition, parameters, return values, type hints | Helper functions, custom functions |
| 4 | [Control Structures](#control-structures) | if/else, foreach, switch statements | Controllers, blade logic, data processing |
| **OBJECT-ORIENTED PHP** | | | |
| 5 | [Classes & Objects](#classes-and-objects) | Class definition, properties, methods, visibility (public/private/protected) | Models, Controllers, Services, Custom classes |
| 6 | [Constructors](#constructors) | __construct method, constructor parameters | Model initialization, dependency injection |
| 7 | [Inheritance](#inheritance) | extends keyword, parent::, method overriding | Extending Laravel classes (Controller, Model) |
| 8 | [Interfaces](#interfaces) | interface keyword, implementing contracts | Repository pattern, service contracts |
| 9 | [Traits](#traits) | trait keyword, use in classes | Laravel's built-in traits, custom reusable code |
| 10 | [Static Methods and Properties](#static-methods--properties) | static keyword, self::, static:: | Facades, Model static methods, static calls |
| 11 | [Abstract Classes](#abstract-classes) | abstract keyword, abstract methods | Base classes, template method pattern |
| **ESSENTIAL MAGIC METHODS** | | | |
| 12 | [__construct & __destruct](#construct-and-destruct) | Constructor and destructor methods | Object initialization, cleanup |
| 13 | [__get, __set, __isset](#get-set-isset) | Property overloading | Eloquent attribute access, dynamic properties |
| 14 | [__call & __callStatic](#call-and-callstatic) | Method overloading | Eloquent query scopes, Facade calls |
| 15 | [__toString](#tostring) | String representation of objects | Model string conversion, debugging |
| **NAMESPACES & AUTOLOADING** | | | |
| 16 | [Namespaces](#namespaces) | namespace declaration, use statements | Organizing Laravel classes, avoiding conflicts |
| 17 | [PSR-4 Autoloading](#psr-4-autoloading) | Composer autoloading, class mapping | Laravel's autoloading system |
| **MODERN PHP FEATURES** | | | |
| 18 | [Type Declarations](#type-declarations) | Scalar types, return types, nullable types | Method parameters, return values in Laravel |
| 19 | [Null Coalescing](#null-coalescing) | ?? and ??= operators | Safe data access, default values |
| 20 | [Arrow Functions](#arrow-functions) | fn() syntax | Collection methods, short callbacks |
| 21 | [Match Expression](#match-expression) | match() instead of switch | Cleaner conditional logic |
| 22 | [Named Arguments](#named-arguments) | function(param: value) syntax | Method calls with many parameters |
| **CLOSURES & CALLBACKS** | | | |
| 23 | [Anonymous Functions](#anonymous-functions) | function() {}, variable scope | Route definitions, collection methods |
| 24 | [Closures with use()](#closures-with-use) | Variable binding in closures | Accessing outer variables in callbacks |
| **ARRAYS & DATA HANDLING** | | | |
| 25 | [Array Functions](#array-functions) | array_map, array_filter, array_reduce | Data transformation, collection operations |
| 26 | [Array Destructuring](#array-destructuring) | list(), [...] syntax | Multiple assignment, parameter unpacking |
| 27 | [JSON Operations](#json-operations) | json_encode, json_decode | API responses, data serialization |
| **ERROR HANDLING** | | | |
| 28 | [Exceptions](#exceptions) | try/catch/finally, throw | Laravel exception handling |
| 29 | [Custom Exceptions](#custom-exceptions) | Extending Exception class | Custom Laravel exceptions |
| **DATABASE ESSENTIALS** | | | |
| 30 | [PDO Basics](#pdo-basics) | Database connections, prepared statements | Understanding Eloquent foundation |
| **COMPOSER & DEPENDENCIES** | | | |
| 31 | [Composer Basics](#composer-basics) | composer.json, require, autoload | Package management, Laravel installation |
| **REFLECTION (BASIC)** | | | |
| 32 | [Reflection Basics](#reflection-basics) | ReflectionClass, method inspection | Understanding dependency injection |
| **SECURITY ESSENTIALS** | | | |
| 33 | [Input Sanitization](#input-sanitization) | filter_var, htmlspecialchars | Request validation, XSS prevention |
| 34 | [Password Hashing](#password-hashing) | password_hash, password_verify | User authentication |





<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### PHP Basics
> variables, constants, data types, syntax (Used in Basic Laravel coding, config files)

### 🔹 Concept
- **Variables**: Store data (`$name = "Ayush";`). Use `$camelCase` for variables, `$UPPER_SNAKE_CASE` for constants.
- **Constants**: Immutable values using `define()` or `const`. Use for config, environment, or global values.
- **Data Types**: String, Integer, Float, Boolean, Array, Object, NULL. Type juggling is common, but type hints are recommended for reliability.
- **Syntax**: Case-sensitive, statements end with `;`. Use `<?php ... ?>` tags for PHP code blocks.
- **Best Practice**: Always initialize variables before use. Prefer single quotes for simple strings, double quotes for interpolation.

### 💻 Example
```php
<?php
$name = "Ayush"; // variable
define("APP_NAME", "LaraBaseX"); // constant

$age = 23;
$isDev = true;

```

Laravel Usage
- `.env` file variables are loaded into config files using `env()` helper.
- Example in `config/app.php`:
```php
'name' => env('APP_NAME', 'Laravel'),
```
- Use constants for environment-specific values (e.g., API keys, app name).
- Type safety is important for config values (use explicit casting if needed).

**Pro Tip:** Use `var_dump($variable);` for debugging variable types and values.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Arrays

🔹 Concept
- Indexed Arrays: Numeric keys.
- Associative Arrays: String keys.
- Multidimensional Arrays: Nested arrays.

💻 Example
```php
<?php
// Indexed
$fruits = ["Apple", "Banana", "Mango"];

// Associative
$user = [
  "name" => "Ayush",
  "role" => "Developer"
];

// Multidimensional
$users = [
  ["name" => "Ayush", "role" => "Dev"],
  ["name" => "Sam", "role" => "Admin"]
];
```

🚀 Laravel Usage
- Config arrays:

```php
'timezone' => 'UTC',
'locale' => 'en',
```
- Request data: $request->all(); returns associative array.
- Collections are built on arrays (collect($users)).

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Functions

🔹 Concept
- Definition: Reusable blocks of code.
- Parameters: Input values.
- Return Values: Output result.
- Type Hints: Ensure correct data types.

💻 Example
```php
<?php
function greet(string $name, int $age): string {
  return "Hello $name, age $age";
}

echo greet("Ayush", 23);

```

Laravel Usage
- Helper functions: url(), view(), asset()
- Custom helper in app/helpers.php:
```php
function formatPrice($amount) {
    return '₹' . number_format($amount, 2);
}
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Control Structures

🔹 Concept
- if / else: Conditional branching.
- foreach: Loop through arrays.
- switch: Multi-case conditions.

💻 Example
```php
<?php
$role = "admin";

if ($role === "admin") {
  echo "Welcome Admin!";
} elseif ($role === "user") {
  echo "Welcome User!";
} else {
  echo "Access Denied";
}

$users = ["Ayush", "Sam", "Ravi"];
foreach ($users as $user) {
  echo $user;
}

switch ($role) {
  case "admin":
    echo "Admin Access";
    break;
}
```



<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->




### Classes and Objects

🔹 Key Concepts
- **Object-Oriented Programming (OOP)**: PHP supports OOP, which is essential for scalable Laravel apps.
- **Class**: Blueprint for objects. Defines properties (variables) and methods (functions).
- **Object**: Instance of a class. Created using `new ClassName()`.
- **Properties**: Variables inside a class. Can be `public`, `protected`, or `private`.
- **Methods**: Functions inside a class. Control object behavior.
- **Visibility**: Controls access to properties/methods:
  - `public`: Accessible everywhere.
  - `protected`: Accessible in class and subclasses.
  - `private`: Accessible only in the class itself.
- **$this**: Refers to the current object instance.
- **Best Practice**: Use private/protected for sensitive data, public for API surface.

🔹 Example
```php
class User {
    public $name;       // public property
    private $email;     // private property

    public function setEmail($email) {
        // Validate email format before setting
        if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
            $this->email = $email;
        }
    }

    public function getEmail() {
        return $this->email;
    }
}

$user = new User();
$user->name = "Ayush";          // direct access (public)
$user->setEmail("test@test.com");
echo $user->getEmail();         // test@test.com
```

🔹 Laravel Usage & Tips
- **Models**: `class User extends Model {}` — Eloquent ORM uses classes for database tables.
- **Controllers**: `class UserController extends Controller {}` — Handles HTTP requests.
- **Services**: Custom classes for business logic, injected into controllers.
- **Mass Assignment**: Use `$fillable` or `$guarded` in models to control property assignment.
- **Accessors/Mutators**: Define `getXAttribute`/`setXAttribute` methods in models for custom property logic.
- **Type Declarations**: Use typed properties (PHP 7.4+) for reliability: `public string $name;`

**Pro Tip:** Use docblocks (`/** ... */`) above classes and methods for better IDE support and documentation.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Constructors

🔹 Understanding
- Special method: __construct()
- Automatically called when an object is created.
- Useful for initializing values or dependency injection.

🔹 Example

```php
class Product {
    public $name;

    // Constructor with parameter
    public function __construct($name) {
        $this->name = $name;
    }
}

$product = new Product("Laptop");
echo $product->name; // Laptop
```

🔹 Real-life in Laravel
Dependency Injection in Controllers:

```php
class UserController extends Controller {
    protected $service;

    public function __construct(UserService $service) {
        $this->service = $service;   // Laravel auto-injects
    }
}
```

- Used in Models when initializing properties.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### Functions

🔹 Concept
- **Definition**: Reusable blocks of code. Use functions to avoid repetition and improve maintainability.
- **Parameters**: Input values. Use type hints for clarity and reliability.
- **Return Values**: Output result. Always specify return type if possible.
- **Type Hints**: Ensure correct data types. Use scalar and object type hints for strictness.
- **Anonymous Functions & Closures**: Useful for callbacks, especially in Laravel collections and routes.
- **Best Practice**: Keep functions small and focused. Use docblocks for documentation.

� Example
```php
<?php
function greet(string $name, int $age): string {
  return "Hello $name, age $age";
}

🔹 Real-life in Laravel

// Anonymous function
$sayHello = function($name) {
    return "Hello, $name!";
};
echo $sayHello("Sam");
```

Laravel Usage
- Helper functions: `url()`, `view()`, `asset()`
- Custom helper in `app/helpers.php`:
```php
function formatPrice($amount) {
    return '₹' . number_format($amount, 2);
}
```
- Use closures in routes and collections:
```php
Route::get('/greet', function() {
    return 'Hello from Laravel!';
});
```
- Use type-hinted parameters and return types in controllers/services for reliability.

**Pro Tip:** Use `fn($x) => $x * 2;` for concise arrow functions (PHP 7.4+).
- Controllers: class UserController extends Controller
- Models: class User extends Authenticatable
- FormRequests, Migrations, etc. all extend base classes.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Interfaces


##### Control Structures

🔹 Concept
- **if / else**: Conditional branching. Use strict comparison (`===`) for reliability.
- **foreach**: Loop through arrays and collections. Use for processing lists, request data, etc.
- **switch / match**: Multi-case conditions. Use `match` (PHP 8+) for cleaner, expression-based logic.
- **while / do-while / for**: Other loop types for advanced iteration.
- **Best Practice**: Keep logic simple and readable. Avoid deeply nested conditions.

� Example
```php
<?php
$role = "admin";

if ($role === "admin") {
    echo "Welcome Admin!";
} elseif ($role === "user") {
    echo "Welcome User!";
} else {
    echo "Access Denied";
}

$users = ["Ayush", "Sam", "Ravi"];
foreach ($users as $user) {
    echo $user;
}
```

```php
<?php
    case "admin":
        echo "Admin Access";
        break;
    case "user":
        echo "User Access";
        break;
    default:
        echo "Guest Access";
}

// PHP 8+ match expression
$result = match($role) {
        'admin' => 'Admin Access',
        'user' => 'User Access',
        default => 'Guest Access',
};
echo $result;
```

Laravel Usage
- Controllers:

```php
if ($user->isAdmin()) {
        return redirect('/admin');
}
```
- Blade Templates:
```blade
@if($user->isAdmin())
     <p>Welcome Admin</p>
@else
     <p>Welcome User</p>
@endif
```

- Use control structures for request validation, authorization, and data processing in middleware/controllers.

**Pro Tip:** Use `match` for cleaner multi-case logic and avoid fall-through bugs.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Traits

```php
trait Loggable {
    public function log($msg) {
        echo "[LOG]: $msg\n";
    }
}

class User {
    use Loggable;
}

$user = new User();
$user->log("User created.");
```

Real-life Usage:
- Laravel uses traits like Illuminate\Database\Eloquent\SoftDeletes
- Custom traits for reusable methods (e.g., logging, formatting, helpers)

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Static Methods and Properties

- Static members belong to the class itself, not an object.
- They are accessed using ClassName::method() or self:: .
- Example:
```php
<?php
class MathHelper {
    public static $pi = 3.14;

    public static function square($n) {
        return $n * $n;
    }
}

echo MathHelper::$pi; // 3.14
echo MathHelper::square(5); // 25
```

Real-life Usage:
- Laravel Facades (e.g., Cache::get(), Route::post())
- Static factory methods in models (User::create())
- Shared utilities/helpers without object creation

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Abstract Classes

- Abstract classes cannot be instantiated.
- They provide a base blueprint with abstract methods that must be implemented in child classes.
- Example :

```php
<?php
abstract class Shape {
    abstract public function area();
}

class Circle extends Shape {
    private $radius;
    public function __construct($r) {
        $this->radius = $r;
    }
    public function area() {
        return pi() * $this->radius * $this->radius;
    }
}

$circle = new Circle(5);
echo $circle->area(); // 78.54
```

Real-life Usage:
- Base service classes (e.g., PaymentGateway → PayPal, Stripe)
- Laravel’s abstract classes (e.g., Illuminate\Console\Command)
- Template Method Pattern

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### Constructors

🔹 Key Concepts
- **__construct()**: Special method called when an object is created. Used for initialization.
- **Parameters**: Pass values to set up object state (e.g., `$user = new User('Ayush')`).
- **Dependency Injection**: Pass dependencies (services, repositories) into classes for loose coupling—core to Laravel architecture.
- **Default Values**: Constructors can have default parameter values.
- **Parent Constructors**: Use `parent::__construct()` to call base class constructor in inheritance.
- **Best Practice**: Keep constructors simple; avoid heavy logic.

🔹 Example
```php
class Product {
    public $name;
    public $price;

    // Constructor with parameters and default value
    public function __construct($name, $price = 0) {
        $this->name = $name;
        $this->price = $price;
    }
}

$product = new Product("Laptop", 50000);
echo $product->name; // Laptop
echo $product->price; // 50000
```

🔹 Laravel Usage & Tips
- **Dependency Injection in Controllers**:
```php
class UserController extends Controller {
    protected $service;

    public function __construct(UserService $service) {
        $this->service = $service;   // Laravel auto-injects UserService
    }
}
```
- **Model Initialization**: Use constructors for setting up model state, but prefer Eloquent events (`creating`, `created`) for DB logic.
- **Service Providers**: Use constructors to inject dependencies into services/providers.
- **Parent Constructors**: Always call `parent::__construct()` if extending a base class with its own constructor.

**Pro Tip:** Use type hints in constructor parameters for reliability and auto-completion: `public function __construct(string $name, int $price)`
<br>

<!-- ------------------------------------------------------------------------------------- -->

### Get Set Isset
→ Property Overloading
- These magic methods let you intercept access to object properties that are not directly accessible (private/protected/undefined).
- Syntax:

```php
class User {
    private $data = [];

    public function __get($name) {
        return $this->data[$name] ?? null;
    }

    public function __set($name, $value) {
        $this->data[$name] = $value;
    }

    public function __isset($name) {
        return isset($this->data[$name]);
    }
}

$user = new User();
$user->name = "Ayush";     // __set is triggered
echo $user->name;          // __get is triggered → "Ayush"
var_dump(isset($user->name)); // __isset is triggered → true
```

Laravel Connection:
- Eloquent Models use this heavily.
```php
$user = User::find(1);
echo $user->name;   // Internally uses __get for attribute access
$user->email = "x@test.com"; // __set
```

- So whenever you access $user->name, it’s not a real property—Eloquent fetches it via __get.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Call and CallStatic
→ Method Overloading
- These are triggered when you call a method that doesn’t exist on the object.

- Syntax:

```php
class Magic {
    public function __call($name, $arguments) {
        return "Called $name with args: " . implode(", ", $arguments);
    }

    public static function __callStatic($name, $arguments) {
        return "Static call $name with args: " . implode(", ", $arguments);
    }
}

$obj = new Magic();
echo $obj->hello("world");     // __call → "Called hello with args: world"
echo Magic::greet("Ayush");    // __callStatic → "Static call greet with args: Ayush"
```

Laravel Connection:
- Eloquent Dynamic Scopes

```php
User::whereName("Ayush")->get();
// "whereName" doesn’t exist as real method.
// __callStatic intercepts and builds query.
```

- Facades (e.g., Cache::get('key')) → __callStatic handles forwarding the call.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Tostring
→ String Representation
- Defines how an object is converted to a string.
- Syntax:

```php
class User {
    private $name;
    public function __construct($name) { $this->name = $name; }

    public function __toString() {
        return "User: " . $this->name;
    }
}

$user = new User("Ayush");
echo $user; // "User: Ayush"
```

Laravel Connection:
- Useful for debugging models.
```php
public function __toString() {
    return $this->name;
}
```

- Now echo $user directly prints the user’s name.
- Without it, echo $user would throw an error.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Namespaces
→ Organizing Code
- Namespaces prevent class name conflicts and provide autoloading structure.
- Syntax:
```php
// File: App/Models/User.php
namespace App\Models;

class User {
    public function greet() {
        return "Hello from App\Models\User";
    }
}

// File: index.php
use App\Models\User;

$user = new User();
echo $user->greet();
```

Laravel Connection:
- Every Laravel class has a namespace (App\Models, App\Http\Controllers, etc.).
- Example:
```php
namespace App\Http\Controllers;

use App\Models\User;

class UserController extends Controller {
    public function index() {
        return User::all();
    }
}
```

- Here, use App\Models\User; tells PHP which User class to load (because User could exist in multiple places).

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### PSR 4 Autoloading

Concept
- PSR-4 is a PHP standard for autoloading classes based on their namespace and directory structure.
- Composer (composer.json) maps namespaces → folder paths.
- Laravel fully relies on PSR-4 autoloading.

Syntax / Example :
```json
// composer.json
"autoload": {
  "psr-4": {
    "App\\": "app/"
  }
}
```

```php
// File: app/Models/User.php
namespace App\Models;

class User {}
```

➡ Now you can use it anywhere:
```php
use App\Models\User;

$user = new User();
```

Laravel Use Case
- Laravel’s entire structure (Controllers, Models, Middleware) uses PSR-4 autoloading.
- Run composer dump-autoload after adding new classes.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Type Declarations

Concept
- Define the expected type for function arguments & return values.
- Supports scalar types (int, string, bool, array, float, mixed, object),
- Return types with : type
- Nullable types with ?type

Syntax / Example :
```php
function addNumbers(int $a, int $b): int {
    return $a + $b;
}

function findUser(?int $id): ?User {
    return $id ? User::find($id) : null;
}
```

Laravel Use Case
- Strong typing in Controllers, Services, Models.

- Example:
```php
public function store(Request $request): JsonResponse
```

Ensures method always returns a JsonResponse.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Null Coalescing

📌 Concept
- ?? → Returns left-hand value if it exists & not null, otherwise right-hand.
- ??= → Assigns default value if variable is null.

Example
```php
$username = $_GET['user'] ?? 'Guest';  // if 'user' not set → 'Guest'

$data['count'] ??= 0;  // set default if null
```

Laravel Use Case
```php
$name = $request->input('name') ?? 'Anonymous';

$user->role ??= 'member'; // set default role
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Arrow Functions

Concept
- Short syntax for anonymous functions.
- Automatically inherit variables from parent scope (no use needed).

Example
```php
$nums = [1, 2, 3];

$squares = array_map(fn($n) => $n * $n, $nums);
// [1, 4, 9]
```

Laravel Use Case
```php
$users = User::all()->map(fn($user) => $user->email);

$filtered = collect([1,2,3,4])->filter(fn($n) => $n % 2 === 0);
```

Quick Summary Table
| Feature               | Syntax                               | Laravel Usage                         |
| --------------------- | ------------------------------------ | ------------------------------------- |
| **PSR-4 Autoloading** | `"App\\": "app/"` in `composer.json` | Auto-load classes in Laravel          |
| **Type Declarations** | `function foo(int $x): string`       | Strong typing in controllers/services |
| **Null Coalescing**   | `$a = $x ?? 'default';`              | Safe request/data access              |
| **Arrow Functions**   | `fn($x) => $x * 2`                   | Collections, Eloquent callbacks       |

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->



### Match Expression

Definition:
- Introduced in PHP 8.
- Works like switch, but returns a value and has strict type comparison.

Syntax:
```php
$result = match($status) {
    200 => 'OK',
    404 => 'Not Found',
    500 => 'Server Error',
    default => 'Unknown',
};
```

Key Points:
- Unlike switch, it does not fall through.
- Always returns a value (expression, not statement).

Laravel Use Case:
- Cleaner handling of request statuses, enum-like logic.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Named Arguments

Definition:
- Introduced in PHP 8.
- Allows passing arguments to functions by name instead of order.

Syntax:
```php
function createUser($name, $email, $role = 'user') {}

createUser(
    email: 'john@example.com',
    name: 'John Doe',
    role: 'admin'
);
```

Key Points:
- Improves readability for functions with many params.
- Allows skipping optional parameters.


Laravel Use Case:
- Useful for service classes, mailables, or jobs with multiple params.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Anonymous Functions

Definition:
- Functions without a name, stored in variables or passed as arguments.

Syntax:
```php
$greet = function($name) {
    return "Hello, $name!";
};

echo $greet("Ayush");
```

Key Points:
- Can be assigned to variables.
- Used as callbacks in array functions, collections, etc.

Laravel Use Case:
- In routes:
```php
Route::get('/hello', function () {
    return "Hello World!";
});
```

In collections:
```php
$users->map(function($user) {
    return $user->name;
});
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Closures with use()

Definition:
- Closures can capture variables from the surrounding scope using use.

Syntax:
```php
$greeting = "Hello";

$sayHello = function($name) use ($greeting) {
    return "$greeting, $name!";
};

echo $sayHello("Ayush"); // Hello, Ayush!
```

Key Points:
- use allows access to outer scope variables inside a closure.
- Useful in callbacks where extra context is needed.

Laravel Use Case:
- Query builder:

```php
$status = 'active';
User::where(function($query) use ($status) {
    $query->where('status', $status);
})->get();
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Array Functions

Key Functions:
- array_map() → Apply a callback to each array element.
- array_filter() → Filter elements using a condition.
- array_reduce() → Reduce array to a single value.

Use Cases in Laravel:
- Transforming API response data.
- Filtering collection items.
- Summing or reducing values from arrays.

Example:
```php
$numbers = [1, 2, 3, 4, 5];

// array_map
$squared = array_map(fn($n) => $n * $n, $numbers);
// [1, 4, 9, 16, 25]

// array_filter
$even = array_filter($numbers, fn($n) => $n % 2 === 0);
// [2, 4]

// array_reduce
$sum = array_reduce($numbers, fn($carry, $n) => $carry + $n, 0);
// 15
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Array Destructuring

PHP Features:
- list() → Assign values to multiple variables at once.
- [...] (short syntax from PHP 7.1).

Use Cases in Laravel:
- Unpacking values from database rows.
- Cleaner assignments when handling arrays.

Example:
```php
$user = ['Ayush', 'Mumbai', 23];

// Using list()
list($name, $city, $age) = $user;

// Short destructuring
[$name, $city, $age] = $user;

echo "$name lives in $city, age $age";
// Output: Ayush lives in Mumbai, age 23
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### JSON Operations

Functions:
- json_encode() → Convert PHP array/object → JSON string.
- json_decode() → Convert JSON string → PHP array/object.

Use Cases in Laravel:
- API request/response handling.
- Storing structured data in database columns.
- Serializing data for front-end apps.

Example:
```php
$data = ['name' => 'Ayush', 'role' => 'Developer'];

// Encode
$json = json_encode($data);
// {"name":"Ayush","role":"Developer"}

// Decode as array
$array = json_decode($json, true);
// ['name' => 'Ayush', 'role' => 'Developer']
```

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Exceptions

Keywords:
- try {} → Code to attempt.
- catch(Exception $e) {} → Handle errors.
- finally {} → Always executed (cleanup).
- throw → Raise an exception.

Use Cases in Laravel:
- Handling DB query failures.
- API request failures.
- Custom validation or business logic errors.

Example:
```php
try {
    if (!file_exists("data.txt")) {
        throw new Exception("File not found!");
    }
    $content = file_get_contents("data.txt");
} catch (Exception $e) {
    echo "Error: " . $e->getMessage();
} finally {
    echo "Process complete.";
}
```

Quick Summary
- Array Functions → ```array_map, array_filter, array_reduce``` → Transform & process data.
- Array Destructuring → ```list() / [...]``` → Multiple assignment in one line.
- JSON Operations → ```json_encode, json_decode``` → API + serialization.
- Exceptions → ```try/catch/finally, throw``` → Error handling in Laravel apps.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Custom Exceptions

Extending the Exception class for better error management in Laravel apps.
```php
class InvalidUserException extends Exception {
    public function report() {
        // Log to error log
        \Log::error("Invalid user: " . $this->getMessage());
    }

    public function render($request) {
        return response()->json([
            'error' => 'Invalid User',
            'message' => $this->getMessage()
        ], 400);
    }
}

// Usage
throw new InvalidUserException("User not found!");
```

Key Points
- Helps in domain-specific error handling.
- Laravel allows custom exception report() and render() methods.
- Useful in APIs for consistent JSON error responses.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### PDO Basics


Foundation of Laravel’s Eloquent ORM → PDO handles low-level DB connection.

```php
$dsn = "mysql:host=localhost;dbname=testdb";
$user = "root";
$pass = "";

try {
    $pdo = new PDO($dsn, $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    $stmt = $pdo->prepare("SELECT * FROM users WHERE id = ?");
    $stmt->execute([1]);
    $user = $stmt->fetch();
} catch (PDOException $e) {
    echo "Error: " . $e->getMessage();
}
```

Key Points
- Prepared statements prevent SQL injection.
- Laravel’s DB::select(), Eloquent ORM → built on PDO.
- Essential for understanding query performance & debugging.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Composer Basics

Dependency manager for PHP, used heavily in Laravel projects.
```bash
# Initialize composer
composer init

# Install Laravel
composer create-project laravel/laravel blog

# Install a package
composer require guzzlehttp/guzzle

# Autoload custom classes
composer dump-autoload
```

Key Points
- composer.json → project dependencies & metadata.
- require → installs packages.
- Autoloading (psr-4) → Laravel auto-discovers classes.
- Core for Laravel installation, updates, and packages.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Reflection Basics

PHP Reflection API allows inspecting classes, methods → used in Laravel’s dependency injection.
```php
class User {
    public function __construct(public $name) {}
}

$reflect = new ReflectionClass(User::class);
$constructor = $reflect->getConstructor();
$params = $constructor->getParameters();

foreach ($params as $param) {
    echo $param->getName(); // Output: name
}
```

Key Points
- Used in Laravel’s service container to auto-resolve dependencies.
- Helps with method inspection & dynamic class usage.
- Important for advanced package development.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->


### Input Sanitization

Protect Laravel apps from XSS, injections, and bad data.

```php
// Prevent XSS
$name = htmlspecialchars($_POST['name'], ENT_QUOTES, 'UTF-8');

// Email validation
$email = filter_var($_POST['email'], FILTER_VALIDATE_EMAIL);

// Laravel way (Request Validation)
$request->validate([
    'email' => 'required|email',
]);
```

Key Points
- filter_var() → validate/sanitize inputs.
- htmlspecialchars() → prevent HTML/JS injection.
- Laravel’s Request Validation automates sanitization.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->

### Password Hashing

Secure authentication foundation in Laravel.

```php
// Hash password
$hash = password_hash("secret123", PASSWORD_BCRYPT);

// Verify password
if (password_verify("secret123", $hash)) {
    echo "Password correct!";
}

// Laravel way
use Illuminate\Support\Facades\Hash;

Hash::make('secret123'); // store
Hash::check('secret123', $hashedPassword); // verify
```

Key Points
- Always hash passwords, never store plain text.
- password_hash() uses modern algorithms (bcrypt, argon2).
- Laravel uses Hash facade (bcrypt by default).
- Core for user authentication system.

<p align="right"><a href="#top"><img src="https://img.shields.io/badge/-Back%20to%20Top-blueviolet?style=for-the-badge" /></a></p>

#

<br>

<br>

<!-- ------------------------------------------------------------------------------------- -->
