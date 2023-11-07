## Interview questions for PHP, Laravel & MySQL by sabbir

________________________________________________________________
### Interview Questions for PHP: 
#### **: What is method overriding in PHP ?
Method overriding in PHP is a fundamental concept of OOP, allowing a subclass to provide it's own implementation for a method that is inherited from the parent class(superclass). Here are the rules for method overriding: 
- Have to have same method name.
- Have to have same number of parameters.
- Have to have same types of parameters.

Here is an example of how method overriding works in PHP:
```php
class Animal {
    public function speak() {
        echo 'Animal speak';
    }
}

class Dog extends Animal {
    /**
     *  Here is the method overriding happens.
     * You cannot have any params.
     */
    public function speak() {
        echo 'Dog Barks';
    }
}

```


#### **: What is method overloading in PHP ?
Method overloading allows you define multiple methods with the same name in a class but with different parameter list. This means you can create different versions of a method that performs different actions depending on the parameters passed to the method. However, unlike other programming languages, PHP does not natively support method overloading by changing the number or types of arguments. Instead you can manually handle the parameters passed to method to handle the method overloading in PHP. 

Here is an example:
```php
class Math {
    public static function sum(int $a): int {
        if(func_num_args() == 1) {
            return $a;
        } 

        // or whatever you want to do with the parameters
        return array_sum(func_get_args());
    }
}
```

#### **: What is PEAR in PHP?
PEAR in PHP stands for "PHP Extension and Application Repository." It is a framework and distribution system for reusable PHP components, including libraries, packages, and extensions.

#### 1: Is PHP a case sensitive language?
Yes, PHP is a case-sensitive language, meaning that it distinguishes between uppercase and lowercase letters in variable names, function names, and other identifiers.

#### 2: What is the meaning of ‘escaping to PHP’?
"Escaping to PHP" refers to the process of embedding PHP code within an HTML document using PHP tags (<?php and ?>). This allows you to mix PHP code with HTML to create dynamic web pages.

#### 3: What are the different types of PHP variables?

In PHP, variables can be categorized into different types based on their data types or what they store. The main types of PHP variables are:

  1. **Scalar Variables**:
    - *Integer*: Stores whole numbers, e.g., `$num = 42`.
    - *Float (or Double)*: Stores floating-point numbers (numbers with decimal points), e.g., `$pi = 3.14`.
    - *String*: Stores text or characters, e.g., `$name = "John"`.
    - *Boolean*: Stores either `true` or `false`, e.g., `$is_active = true`.

  2. **Compound Variables**:
    - *Array*: Stores multiple values in an ordered list, e.g., `$fruits = array("apple", "banana", "cherry")`.
    - *Object*: Stores instances of user-defined classes, e.g., `$car = new Car()`.

  3. **Special Variables**:
    - *Resource*: A special type used to hold references to external resources like database connections, file handles, etc.
    - *NULL*: Represents a variable with no value or an undefined value, e.g., `$empty_var = null`.

  4. **Superglobals**:
    - Variables that are predefined in PHP and are accessible from any part of the script. These include `$_GET`, `$_POST`, `$_REQUEST`, `$_SESSION`, `$_COOKIE`, `$_SERVER`, `$_ENV`, and more. They are used to handle HTTP requests, manage sessions, and access server-related information.

  5. **Variables with Special Prefixes**:
    - These variables have special meanings:
      - `$GLOBALS`: A superglobal that allows access to variables in the global scope.
      - `$_SESSION`: A superglobal used for session variables.
      - `$_POST` and `$_GET`: Superglobals for handling form data sent via HTTP POST and GET methods.
      - `$_COOKIE`: A superglobal for handling cookies.
      - `$_SERVER`: A superglobal containing server-related information.

These are the main types of PHP variables. Each type serves a specific purpose and is used in different situations within PHP scripts.

#### 4: What are the rules for naming a PHP variable?
Rules for naming a PHP variable:
- Variable names must start with a letter or underscore.
- Variable names can only contain letters, numbers, and underscores.
- Variable names are case-sensitive.
- Variable names should not be PHP reserved words.


#### 5:  What are the rules to determine the “truth” of any value which is not already of the Boolean type?
In PHP, values are considered "truthy" if they are not:
- Empty strings
- Zero (0 or 0.0)
- NULL
- False (false boolean)
- An empty array


#### 6: What is NULL?
NULL is a special value in PHP that represents the absence of a value or a variable that has not been assigned any value.


#### 7: How do you define a constant in PHP?
To define a constant in PHP, you can use the define() function. For example:
```php
define("MY_CONSTANT", 42);
```

#### 8: What is the purpose of constant() function?
The `constant()` function in PHP is used to retrieve the value of a constant by providing its name as a string. For example, `constant("MY_CONSTANT")` would return the value of the constant named "MY_CONSTANT."

#### 9: What are the differences between PHP constants and variables?
Differences between PHP constants and variables:
- Constants are defined using `define()` and cannot be changed after definition, while variables can change their values.
- Constants are typically used for values that should not be altered during the script's execution, like configuration settings.
- Variables are used for data that can change during the script's execution.

#### 10: Name some of the constants  in PHP and their purpose.
Some common PHP constants and their purposes:
- `PHP_VERSION`: Holds the current PHP version
- `PHP_OS`: Represents the name of the operating system.
- `DIRECTORY_SEPARATOR`: Contains the directory separator for the current OS.
- `E_ERROR`, `E_WARNING`, etc.: Error reporting constants for different error levels.


#### 11: What is the difference between PHP4 and PHP5?
PHP5 introduced significant improvements and new features compared to PHP4, including:
- Enhanced object-oriented programming support.
- Introduction of visibility keywords (public, private, protected).
- Improved support for exceptions.
- Better performance and memory management
- Support for new data types, like the SimpleXML extension for parsing XML.


#### 12: What is the meaning of a final class and a final method?
In PHP, a final class cannot be extended or subclassed, and a final method within a class cannot be overridden in any subclass. It's used to prevent further modification or extension of the class or method.


#### 13:  How can you compare objects in PHP?
To compare objects in PHP, you can use the `==` operator to check if they are equal in terms of properties and values, or the `===` operator to check if they are the same instance. The `==` operator compares values, while the `===` operator compares both values and data types.

#### 14: How can PHP and Javascript interact?
PHP and JavaScript can interact through AJAX (Asynchronous JavaScript and XML) requests, which allow JavaScript to make requests to a PHP script on the server, retrieve data, and update the webpage without a full page refresh. They can also communicate through cookies, sessions, and embedding JavaScript code within PHP-generated HTML.


#### 15: What are the data types in PHP?
Common data types in PHP include:
- Integer (int)
- Float (float)
- String (string)
- Boolean (bool)
- Array
- Object
- NULL
- Resource
- Callable
- Iterable (introduced in PHP 7.1)


#### 16: What are constructor and destructor in PHP?
In PHP, a constructor is a special method called when an object of a class is created. It is used to initialize object properties. A destructor is a method that is called when an object is no longer referenced or when the script ends. It can be used to perform cleanup tasks.


#### 17: What are include() and require() functions?
`include()` and `require()` are PHP functions used to include external files in a script. They include and evaluate the specified file. If the file is not found or has an error, `require()` will produce a fatal error, while `include()` will only produce a warning.

#### 18: What is the main difference between require() and require_once()?
The main difference between `require()` and `require_once()` is that if the same file is included multiple times in a script, `require_once()` will ensure that it is included only once, preventing duplication.


#### 19:  What are different types of errors available in Php ?
Different types of errors in PHP:
- Parse errors (syntax errors)
- Fatal errors
- Warnings
- Notices
- Deprecated errors
- User-generated errors using `trigger_error()`


#### 20: What are the different types of Array in PHP?
Different types of arrays in PHP:
- Indexed arrays (numeric keys)
- Associative arrays (key-value pairs)
- Multidimensional arrays (arrays within arrays)
- Constant arrays (created with define())
- Typed arrays (introduced in PHP 8.0, with predefined data types for array elements)



#### 21: What is the difference between “echo” and “print” in PHP?
In PHP, both echo and print are used to output text or data to the screen. However, there are some differences:
- `echo` is a language construct, while `print` is a function. This means that `echo` is slightly faster and more versatile in terms of what it can output.
- `echo` can output multiple values separated by commas, while `print` can only output one value and always returns 1.
- `echo` does not have a return value, while` print` returns 1.
- `echo` is often used for simple output, while `print` is less commonly used in modern PHP code.

#### 22: Name some of the functions in PHP.
PHP has a wide range of built-in functions. Some commonly used functions include `strlen`, `strpos`, `substr`, `date`, `array`, `explode`, `implode`, `file_get_contents`, `file_put_contents`, `mail`, and many more.


#### 23: What is the main difference between asp net and PHP?
`ASP.NET` is a web application framework developed by Microsoft, while PHP is a server-side scripting language. Some key differences include:
- `ASP.NET` is typically used with the `C#` or Visual Basic.NET languages, while `PHP` has its own scripting language.
- `ASP.NET` is often used with Microsoft technologies like IIS and SQL Server, while `PHP` is platform-agnostic and can run on various web servers and databases.
- `ASP.NET` is integrated with the Windows ecosystem, whereas PHP is more open-source and cross-platform.
- `ASP.NET` uses a compiled approach, while PHP is interpreted.


#### 24: What is the use of session and cookies in PHP?
Sessions and cookies are used to maintain state information between HTTP requests in PHP:
- Sessions are server-side mechanisms for storing and retrieving data for a specific user across multiple pages during their visit to a website. They are typically more secure but require server resources.
- Cookies are small pieces of data stored on the client-side (user's browser). They can be used to store user-specific information and are sent with each HTTP request. They are less secure, as the user can view and modify them.


#### 25: What is the difference between $message and $$message in PHP?
- `$message` is a variable that holds a single value.
- `$$message` is a variable variable. It takes the value of $message and treats it as the name of another variable whose value it represents.
For example, if `$message` contains the value `"varName"`, then `$$message` is equivalent to `$varName`.

#### 26:  How can we create a database using PHP and MySQL? 
To create a database using PHP and MySQL, you typically need to perform the following steps:
1. Connect to your MySQL server using PHP (e.g., mysqli_connect or PDO).
2. Execute an SQL query to create a new database (e.g., CREATE DATABASE database_name).
3. Check if the database creation was successful.
4. Close the database connection.
Here's a simplified example using `mysqli`:
```php
$servername = "localhost";
$username = "username";
$password = "password";

// Create a connection
$conn = mysqli_connect($servername, $username, $password);

// Check connection
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}

// Create a new database
$sql = "CREATE DATABASE mydb";
if (mysqli_query($conn, $sql)) {
    echo "Database created successfully";
} else {
    echo "Error creating database: " . mysqli_error($conn);
}

// Close the connection
mysqli_close($conn);

```

#### 27: What is GET and POST method in PHP?
GET and POST are two HTTP request methods used to send data to a web server:
- GET: Data is appended to the URL as query parameters. It's primarily used for retrieving data. It has a limitation on the amount of data that can be sent (the data is visible in the URL).
- POST: Data is sent in the body of the HTTP request. It's used for sending larger amounts of data, like form submissions, and is more secure as the data is not visible in the URL.


#### 28: What is the use of callback in PHP?
A callback in PHP is a reference to a function or method that can be passed as an argument to another function. Callbacks are often used for customizing the behavior of functions, especially in scenarios like sorting arrays or handling asynchronous operations.

For example, the `usort` function can take a callback function to customize the sorting behavior of an array.



#### 29: What are PHP Magic Methods/Functions?
PHP magic methods are special methods with double underscores (e.g., `__construct`, `__destruct`, `__get`, `__set`, etc.) that provide predefined functionality in classes. They are automatically called by the PHP interpreter in response to specific events. Magic methods are commonly used for object initialization, property access, and more.

#### 30: How can you encrypt password using PHP?
You should never store plain text passwords in a database. Instead, you should hash the passwords using a secure hashing algorithm like bcrypt. Here's a simplified example of how to hash and verify passwords in PHP:
```php
// Hashing a password
$password = "user_password";
$hashed_password = password_hash($password, PASSWORD_BCRYPT);

// Verifying a password
$entered_password = "user_input_password";
if (password_verify($entered_password, $hashed_password)) {
    // Password is correct
} else {
    // Password is incorrect
}
```

#### 31: How to connect to a URL in PHP?
To connect to a URL in PHP, you can use functions like `file_get_contents()` or `cURL`. Here's an example using `file_get_contents()`:
```php
$url = "https://example.com";
$data = file_get_contents($url);
```
For more advanced requests with options like setting headers and handling cookies, you can use the cURL library.


#### 32: What is Type hinting in PHP?
Type hinting in PHP is a feature that allows you to specify the data type of a function's parameters or return value. This helps improve code clarity and can catch type-related errors early. For example:
```php
function add(int $a, int $b): int {
    return $a + $b;
}
```

#### 33: What is the difference between runtime exception and compile time exception?
Runtime exceptions (also called runtime errors) occur during the execution of a program, while compile-time exceptions (also called compile-time errors) occur during the compilation of the code. Compile-time errors prevent the program from being compiled and executed, whereas runtime exceptions can occur after the program has started running.


#### 34: Is PHP a loosely typed language?
Yes, PHP is a loosely typed language. In PHP, you don't need to explicitly declare data types for variables, and variables can change their data type during runtime. This flexibility can lead to unexpected behaviors if not handled carefully.


#### 35: What is required to use the image function?
To use image functions in PHP, you need the GD (Graphics Draw) library extension enabled on your PHP server. You can enable it in your PHP configuration or compile PHP with GD support.


#### 36: Mention the popular Content Management Systems (CMS) in PHP?
Some popular PHP-based Content Management Systems (CMS) include WordPress, Joomla, Drupal, and Magento.


#### 37: Mention some of the constants in PHP and their purpose.
PHP has many predefined constants. Some common ones include:
`__LINE__`, `__DIR__`, `__CLASS__` and more.

#### 38: Explain the uses of explode() and implode() functions.
- `explode()`: This function is used to split a string into an array based on a delimiter. For example, you can split a comma-separated string into an array of values.
- `implode()`, also known as `join()`: This function is used to join the elements of an array into a single string using a specified delimiter.

#### 39: How to make a connection with MY SQL server?
To connect to a MySQL server in PHP, you can use functions like `mysqli_connect`, PDO, or the newer `MySQLi` (MySQL Improved) functions. Here's an example using MySQLi:
```php
$servername = "localhost";
$username = "username";
$password = "password";
$database = "dbname";

$conn = mysqli_connect($servername, $username, $password, $database);

if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
```


#### 40: Explain the difference between mysqli_connect and mysqli_pconnect.
- `mysqli_connect`: This function establishes a regular (non-persistent) connection to the MySQL server. The connection is closed when the PHP script finishes execution.
- `mysqli_pconnect`: This function establishes a persistent connection to the MySQL server, which remains open even after the PHP script finishes execution. Persistent connections can reduce connection overhead but may have some limitations and drawbacks.


#### 41: How do we access the data transfer through the URL with the POST method?
Data transferred through the `POST` method is accessed using the `$_POST` superglobal in PHP. For example:
```php
$value = $_POST['input_name'];
```
Here, `input_name` is the name of the input field in an HTML form that was submitted with the POST method.


#### 42: Explain the unlink() function in PHP.
The `unlink()` function in PHP is used to delete a file from the server. For example:
```php
$file_path = "path/to/file.txt";
if (unlink($file_path)) {
    echo "File deleted successfully.";
} else {
    echo "Error deleting file.";
}
```

#### 43: Explain what does the unset() function mean?
The `unset()` function in PHP is used to destroy a variable, making it no longer available for use in the script. It can also be used to remove elements from an array. For example:
```php
$variable = "Hello";
unset($variable); // $variable is now undefined

$array = [1, 2, 3];
unset($array[1]); // Removes the element at index 1

```

#### 44: What is the process to automatically run off incoming data?
It's not clear what you mean by "run off incoming data." If you are referring to processing incoming data automatically, you typically use server-side scripts to handle and process data received from web forms or other sources.

#### 45: Describe what the function get_magic_quotes_gpc() means.
`get_magic_quotes_gpc()` was a function used to check if PHP's "Magic Quotes" feature was enabled. Magic Quotes automatically added backslashes to incoming data to protect against SQL injection and other security issues. However, this feature is deprecated in modern PHP versions, and it's no longer available. You should not use it in new code.

#### 46: Can we remove the HTML tags from the data?
Yes, you can remove HTML tags from data in PHP using functions like `strip_tags()`. For example:
```php
$text = "<p>This is <b>some</b> text.</p>";
$clean_text = strip_tags($text);
echo $clean_text; // Output: "This is some text."
```

#### 47: What is the procedure to cast types in PHP?
You can cast types in PHP using explicit type casting. For example, to cast a variable to an integer, you can use (int) or (integer):
```php
$string = "123";
$integer = (int)$string; // Cast to integer
```

#### 48: Explain what accessing a class via:: means.
In PHP, you can access class properties and methods using the `::` operator. It's used to access static properties and methods or constants of a class. For example:
```php
class MyClass {
    const MY_CONSTANT = 42;

    public static function myMethod() {
        // ...
    }
}

$constant_value = MyClass::MY_CONSTANT;
MyClass::myMethod();
```

#### 49: In PHP, objects used are passed by value or passed by reference.
In PHP, objects are passed by reference. When you pass an object to a function or assign it to another variable, you are working with a reference to the same object. Any changes made to the object inside the function or through the new variable will affect the original object.


#### 50: Explain what Persistent Cookie is.
A persistent cookie (also known as a long-term cookie) is a type of HTTP cookie that remains on the user's device for an extended period, even after the browser is closed. It has an expiration date set in the future. Persistent cookies are typically used to remember user preferences or login sessions over an extended period.


#### 51: At what phase do sessions end in PHP?
Sessions in PHP typically end when the user's browser is closed, or when the session is explicitly destroyed using `session_destroy()` or when it times out due to inactivity. The session timeout is determined by the `session.gc_maxlifetime` setting in the PHP configuration.


#### 52: Explain what $GLOBALS is.
`$GLOBALS` is a `superglobal` array in PHP that is used to access global variables from within functions or methods. It allows you to access variables that are outside the current scope.



#### 53: What does $_SERVER mean?
`$_SERVER` is a superglobal array in PHP that provides information about the server environment, request, and other server-related data. It includes information like headers, file paths, and server information.


#### 54: What do $_FILES mean?
`$_FILES` is a superglobal array in PHP that is used to access and manage file uploads submitted via HTML forms with the enctype="multipart/form-data" attribute. It provides information about uploaded files, such as file names, MIME types, and file sizes.


#### 55: Explain the use of the header() function in PHP. 
The `header()` function in PHP is used to send HTTP headers, such as setting cookies, redirecting to a different page, specifying content type, and more. It must be called before any actual output is sent to the browser. It allows you to control various aspects of the HTTP response.


#### 56: How do you execute a PHP script from the command line?
To execute a PHP script from the command line, you can use the php command followed by the script's filename, like this:
```ssh
php script.php
```


#### 57: What are the different PHP array functions?
PHP provides a variety of array functions for manipulating arrays. Some common ones include `array_push()`, `array_pop()`, `array_shift()`, `array_unshift()`, `count()`, `array_merge()`, `array_slice()`, `array_key_exists()`, and many more.


#### 58: Explain the difference between the functions strstr() and stristr().
- `strstr()`: This function is used to find the first occurrence of a substring within a string. It is case-sensitive, so it will only match if the case matches.
- `stristr()`: This function is also used to find the first occurrence of a substring within a string, but it is case-insensitive, meaning it will match regardless of the case.
```php
$string = "Hello, World!";
$result = strstr($string, "world"); // $result is FALSE
$result = stristr($string, "world"); // $result is "World!"
```


#### 59: What rules determine the “truth” of any value not already of the Boolean type?
The "truthiness" of a value in programming languages like PHP is often determined by its evaluation in a boolean context. In PHP, values that are considered "truthy" include non-empty strings, non-zero numbers, and non-empty arrays. Values that are considered "falsy" include an empty string, zero, and empty arrays.


#### 60: What is the difference between a single-quoted string and a double-quoted string?
The main difference between single-quoted strings and double-quoted strings in PHP is that variables and escape sequences inside double-quoted strings are interpolated and evaluated, while in single-quoted strings, they are treated as literal characters.


#### 61: Which function can be used to exit from the script after displaying the error message?
The `die()` or `exit()` function can be used to exit from a script after displaying an error message in PHP.


#### 62: Which function is used in PHP to check the data type of any variable?
The `gettype()` function is used in PHP to check the data type of a variable.


#### 63: How can you increase the maximum execution time of a script in PHP?
You can increase the maximum execution time of a script in PHP using the `set_time_limit()` function or by modifying the max_execution_time directive in the PHP configuration `(php.ini)` file.


#### 64: What is meant by ‘passing the variable by value and reference’ in PHP?
Passing a variable by value in PHP means that you are passing a copy of the variable to a function or assignment, so changes made to the variable within the function or assignment do not affect the original variable outside. Passing a variable by reference means that you are passing a reference to the original variable, and changes made to it within the function or assignment will affect the original variable.


#### 65: Explain type casting and type juggling.
Type casting is the explicit conversion of one data type to another, while type juggling is the automatic conversion of data types in expressions. For example, in type casting, you might explicitly convert a string to an integer using `(int)` like `(int)`$str, while in type juggling, PHP might automatically convert a string to an integer if it's used in an arithmetic operation.


#### 66: How can you retrieve data from the MySQL database using PHP?
To retrieve data from a MySQL database using PHP, you can use functions provided by the `MySQLi` extension or PDO (PHP Data Objects). You'll typically establish a database connection, create SQL queries, execute them, and fetch results using functions like `mysqli_query()`, `mysqli_fetch_assoc()`, or prepared statements in PDO.


#### 67: How can you create a session in PHP?
To create a session in PHP, you can use the `session_start()` function. This function initializes a session or resumes the current session if one exists.

#### 68: Which function you can use in PHP to open a file for reading or writing or for both?
In PHP, you can use the `fopen()` function to open a file for reading, writing, or both, depending on the mode you specify. For example, `fopen('file.txt', 'r')` opens a file for reading, and `fopen('file.txt', 'w')` opens a file for writing.


#### 69: What is the difference between include() and require()?
`include()` and `require()` are both used to include and execute the content of another PHP file in the current script. The main difference is in how they handle errors. `include()` will generate a warning and continue executing the script if the file is not found, while `require()` will generate a fatal error and stop script execution. Use `include()` when the included file is not critical, and use `require()` when it's essential.


#### 70: Which function is used in PHP to delete a file?
The `unlink()` function is used in PHP to delete a file.


#### 71: What is the use of strip_tags() method?
The `strip_tags()` method is used to remove HTML and PHP tags from a string. It can be used to sanitize user input or to extract plain text from an HTML document.


#### 72: How can you send an HTTP header to the client in PHP?
You can send an HTTP header to the client in PHP using the `header()` function. For example, `header("Location: http://example.com");` can be used to redirect the user to another URL.


#### 73: Which functions are used to count the total number of array elements in PHP?
The `count()` and `sizeof()` functions are commonly used to count the total number of elements in an array in PHP.


#### 74: How can you upload a file using PHP?
To upload a file using PHP, you typically create an HTML form with an `<input type="file">` element, and then use PHP to process the uploaded file. You can use the $_FILES superglobal to access the uploaded file's information and move it to the desired location on the server using functions like `move_uploaded_file()`.


#### 75: Which function is used in PHP to search a particular value in an array?
You can use the `in_array()` function in PHP to search for a particular value in an array. It returns true if the value is found in the array, false otherwise.


#### 76: What is the use of the $_REQUEST variable?
The `$_REQUEST` variable in PHP is a superglobal array that is used to collect data from both HTTP GET and POST requests. It contains data from the `$_GET`, `$_POST`, and `$_COOKIE` superglobal arrays. However, it's important to use this variable with caution as it can potentially lead to security vulnerabilities, such as data injection and should be sanitized or validated before use.


#### 77: How long does a PHP session last for?
The duration of a PHP session is determined by the session settings in the PHP configuration. By default, a session lasts until the user closes their browser, or until a specific timeout is reached. You can configure the session's lifetime using the `session.gc_maxlifetime` directive in your php.ini file.


#### 78: What is the use of mysqli_real_escape_string() function?
The `mysqli_real_escape_string()` function is used to escape and sanitize user input that is going to be used in SQL queries. It helps prevent SQL injection by escaping special characters, making the input safe to use in database queries.


#### 79: Which functions are used to remove whitespaces from the string?
PHP provides several functions to remove whitespaces from a string, including `trim()`, `ltrim()`, and `rtrim()`. These functions remove whitespace characters (spaces, tabs, newlines) from the beginning, end, or both ends of a string, respectively.


#### 80: What is a persistence cookie?
A persistence cookie, often referred to as a persistent or long-term cookie, is a type of HTTP cookie that doesn't expire when the user closes the web browser. Instead, it persists on the user's computer for a specified duration, typically set by the website, and can be used to remember user preferences or login information over extended periods.


#### 81: How can a cross-site scripting attack be prevented by PHP?
Cross-site scripting (XSS) attacks can be prevented in PHP by sanitizing and validating user input, escaping output data when displaying it in web pages, and using security mechanisms like input validation, output encoding, and content security policies (CSP). Additionally, using functions like `htmlspecialchars()` to escape user input when rendering it in HTML can help prevent XSS attacks.


#### 82: What is meant by public, private, protected, static and final scopes?
Public, private, protected, static, and final are access modifiers and scopes in PHP:
- `public`: Members marked as public can be accessed from anywhere, both inside and outside the class.
- `private`: Members marked as private are only accessible within the class itself.
- `protected`: Members marked as protected can be accessed within the class and its subclasses.
- `static`: Static members are associated with the class rather than instances of the class.
- `final`: Final classes or methods cannot be extended or overridden by subclasses.




#### 83: How can image properties be retrieved in PHP?
To retrieve image properties in PHP, you can use functions like `getimagesize()` or image-related functions from the GD or Imagick extensions. `getimagesize()` returns an array with information about the image, including its size, width, height, and MIME type.


#### 84: What is the difference between abstract class and interface?
An abstract class in PHP is a class that cannot be instantiated and is meant to be extended by other classes. It can contain abstract methods (methods without implementation) that must be implemented in the child classes. An interface, on the other hand, is a contract that defines a set of methods that implementing classes must provide, but it cannot contain any method implementations. Classes can implement multiple interfaces but can only extend one abstract class.


#### 85: What is garbage collection?
Garbage collection in PHP is the process of automatically identifying and cleaning up memory that is no longer in use, releasing it back to the system. PHP uses a reference counting mechanism and a cyclic garbage collector to manage memory automatically. This helps prevent memory leaks and ensures efficient memory usage.


#### 86: What is PDO?
PDO (PHP Data Objects) is a PHP extension that provides a consistent interface for interacting with databases, regardless of the specific database system being used. PDO allows you to work with multiple database systems (e.g., MySQL, PostgreSQL, SQLite) using the same set of functions, making it a more portable and secure way to work with databases in PHP.


#### 87: What does isset() function?
The `isset()` function in PHP is used to check if a variable or array element is set and is not null. It returns true if the variable exists and is not null, and false if it does not exist or is null.

#### 88: Explain some of the PHP array functions?
Some of the commonly used PHP array functions include `count()`, `array_push()`, `array_pop()`, `array_shift()`, `array_unshift()`, `array_merge()`, `array_reverse()`, `array_slice()`, `array_splice()`, `in_array()`, and `array_search()`. These functions allow you to perform various operations on arrays, such as adding, removing, and searching for elements.


#### 89: What are the functions to be used to get the image’s properties (size, width and height)?
To get an image's properties such as size, width, and height in PHP, you can use the `getimagesize()` function. It returns an array that contains information about the image, including these properties.


#### 90: What is the difference between Session and Cookie?
The main differences between sessions and cookies in PHP are as follows:
- Sessions are typically stored on the server, while cookies are stored on the client's browser.
- Sessions are more secure for storing sensitive data, as they are not exposed to the client.
- Cookies have an expiration date and can be long-term (persistent), while sessions usually expire when the user closes the browser.
- Sessions are often used to store user-specific data across multiple pages, while cookies are often used for tracking user preferences or login information.



#### 91:  How to set cookies in PHP?
To set cookies in PHP, you can use the setcookie() function. Here's an example of how to set a cookie:

```php
setcookie("user", "John Doe", time() + 3600, "/");
```
This code sets a cookie named "user" with the value "John Doe" that will expire in 1 hour (3600 seconds) and is accessible from the root directory ("/").


#### 92: What is sql injection ?
SQL injection is a security vulnerability that occurs when an attacker inserts malicious SQL code into input fields or parameters, which are then executed by a web application's database. This can allow the attacker to manipulate the database, retrieve, modify, or delete data, and potentially gain unauthorized access to a system.


#### 93: Distinguish between urlencode and urldecode?
`urlencode()` and `urldecode()` are functions used to encode and decode URLs in PHP. `urlencode()` is used to convert special characters in a string to URL-encoded format, making it safe to include in a URL. `urldecode()` is used to reverse the process and decode a URL-encoded string back to its original form.


#### 94: What is the use of htmlentities() function in PHP?
The `htmlentities()` function in PHP is used to convert characters with special meaning in HTML to their corresponding HTML entities. This is often used to prevent cross-site scripting (XSS) attacks by encoding user-generated content before it is displayed in a web page.


#### 95: What is the difference between mysqli and PDO?
The main differences between mysqli and PDO in PHP are:
- `mysqli` is specific to MySQL databases, while PDO is more universal and can work with multiple database systems.
- `mysqli` provides both procedural and object-oriented interfaces, while PDO primarily uses object-oriented methods.
- `PDO` supports prepared statements and named placeholders, making it more secure against SQL injection.
- `mysqli` has better support for stored procedures and multi-query execution.
- `PDO` is considered more extensible and suitable for working with various database backends.


#### 96: What is MIME in PHP?
MIME (Multipurpose Internet Mail Extensions) is a standard used in PHP and other programming languages to define the type and structure of data files, especially for email and the internet. MIME types describe the format of a file, such as text, image, audio, or video, and help applications determine how to handle or display the data.


#### 97: Explain session_start() function and session_destroy() function in PHP?
- `session_start()` is used to initialize a session or resume the current session. It must be called at the beginning of a script that intends to use sessions. It creates a unique session identifier for each user and can store session data on the server.

- `session_destroy()` is used to destroy the current session. It deletes all session data associated with the user and effectively logs them out. It is often used when a user wants to log out of a website.

#### 98: What is the command line for executing a PHP script?
To execute a PHP script from the command line, you can use the php command followed by the script's filename. For example:
```shell
php myscript.php
```

#### 99: What are __wakeup and __sleep methods in PHP?
- `__wakeup()` is called when an object is unserialized. You can use it to perform any necessary cleanup or initialization when an object is recreated from its serialized form.
- `__sleep()` is called before an object is serialized. You can specify which object properties should be included in the serialization process by returning an array of property names from this method.

#### 100: What is the role of the lambda function used in PHP?
In PHP, a lambda function (also known as an anonymous function) is a small, anonymous function that can be used as an argument to higher-order functions or assigned to variables. It is typically used for short, simple operations where defining a full function is unnecessary. Lambda functions can be created using the fn keyword (available in PHP 7.4 and later) or by using function(). They are often used in array functions like `array_map()`, `array_filter()`, and `usort()`. Lambda functions provide a more concise way to define functions on the fly without explicitly naming them.

#### 101: What do you mean by object-oriented programming?
Object-oriented programming (OOP) is a programming paradigm that uses objects, which are instances of classes, to structure and organize code. In OOP, the key concepts are classes and objects. Classes define the blueprint for creating objects, and objects are instances of classes that encapsulate data and behavior (methods). OOP promotes the principles of encapsulation, inheritance, and polymorphism to create modular, reusable, and maintainable code.

#### 102: What are the characteristics of OOPs?
The characteristics of object-oriented programming (OOP) include:
- `Encapsulation`: This refers to the bundling of data (attributes or properties) and methods (functions) that operate on the data into a single unit called a class. Objects of the class can access and manipulate the data through defined interfaces.
- `Inheritance`: Inheritance allows a class (subclass or derived class) to inherit properties and behaviors from another class (superclass or base class). It promotes code reuse and hierarchy.
- `Polymorphism`: Polymorphism enables objects of different classes to be treated as objects of a common superclass. It allows for method overriding and dynamic method dispatch, making code more flexible.
- `Abstraction`: Abstraction is the process of simplifying complex reality by modeling classes based on essential properties and behaviors while hiding unnecessary details.
- `Modularity`: OOP promotes the creation of self-contained modules (classes) that can be developed and maintained independently, enhancing code modularity and reusability.



#### 103: What is a class and object?
- Class: A class is like a blueprint or template for creating objects. It defines the structure and behavior of objects.
- Object: An object is an instance of a class. It is a concrete realization of the class's blueprint, with its own data and behavior.

#### 104: What do you mean by Inheritance?
When a class inherits attributes or methods from another class, this is called inheritance.

There are different types of inheritance in object oriented programming:
- **Single Inheritance**: Single inheritance occurs when a class inherits from only one parent class. 
- **Multiple Inheritance(Interface Inheritance)**: Multiple inheritance refers to a class inheriting properties and methods from more than one parent class. PHP does not supports multiple inheritance. But you can implements multiple interfaces or you can use traits for this purpose.
- **Multi-level Inheritance**: Multiple inheritance involves a chain of classes where one class inherits from another, and subsequent classes inherits from those classes.
- **Hierarchical Inheritance**: Hierarchical inheritance occurs when multiple child classes inherit from a single parent class. Each child class my have it's own unique properties and methods, but they share the common behavior from the parent class.
- **Hybrid inheritance**: Hybrid inheritance is a combination of two or more types of inheritance within the same program. While PHP supports only single and interface | traits inheritance, combining them can lead to hybrid inheritance.

Here are some examples: 
```php

/**
 * Single Inheritance Example:
 */
class Vehicle
{
  protected $brand;
  protected $model;
  protected $year;

  public function __construct($brand, $model, $year)
  {
    $this->brand = $brand;
    $this->model = $model;
    $this->year = $year;
  }

  public function getInfo()
  {
    return "Brand: $this->brand, Model: $this->model, Year: $this->year";
  }
}

class Car extends Vehicle
{
  private $fuel_type;

  public function __construct($brand, $model, $year, $fuel_type)
  {
    parent::__construct($brand, $model, $year);
    $this->fuel_type = $fuel_type;
  }

  /**
   * Method overriding
   */
  public function getInfo()
  {
    return parent::getInfo() . " Fuel type: $this->fuel_type";
  }
}

$aVehicle = new Vehicle('Bus', 'No model', 2020);
// echo $aVehicle->getInfo();

// $car = new Car('Toyota', 'Carmy', 2022, 'Gasoline');
// echo $car->getInfo();


/**
 * Multiple Inheritance: In PHP, you cannot use multiple inheritance. You have to use interfaces or traits to implement multi-inheritance in PHP.
 */
interface Communication
{
  public function makeCall($phone_number);
  public function sendText($phone_number, $message);
}

interface Multimedia
{
  public function takePhoto();
  public function playMusic($song);
}

class Smartphone implements Communication, Multimedia
{
  public function makeCall($phone_number)
  {
    echo "Calling $phone_number" . PHP_EOL;
  }

  public function sendText($phone_number, $message)
  {
    echo "Sending text to $phone_number: $message" . PHP_EOL;
  }
  public function takePhoto()
  {
    echo "Taking a photo" . PHP_EOL;
  }
  public function playMusic($song)
  {
    echo "Playing the song named: $song";
  }
}

$iPhone = new SmartPhone();
// $iPhone->sendText('01309900000', 'Hi there!');


/**
 * Multi-level inheritance: Multi-level inheritance is a concept where a chain of classes is created, where each child class inherits from it's parent, forming a hierarchy. Like: Your grand-father -> your-father -> you 😀 
 */
class Employee
{
  protected $name;
  protected $employeeId;

  public function __construct($name, $employeeId)
  {
    $this->name = $name;
    $this->employeeId = $employeeId;
  }

  public function getDetails()
  {
    return "Employee ID: $this->employeeId, Name: $this->name";
  }
}

class Manager extends Employee
{
  protected $department;

  public function __construct($name, $employeeId, $department)
  {
    parent::__construct($name, $employeeId);
    $this->department = $department;
  }

  /**
   * Method overrides
   */
  public function getDetails()
  {
    return parent::getDetails() . ", Department: $this->department (Manager)";
  }
}

class Director extends Manager
{
  protected $responsibilities;

  public function __construct($name, $employeeId, $department, $responsibilities)
  {
    parent::__construct($name, $employeeId, $department);
    $this->responsibilities = $responsibilities;
  }

  /**
   * Method overrides
   */
  public function getDetails()
  {
    return parent::getDetails() . ", Responsibilities: $this->responsibilities (Director)";
  }
}

$employee = new Employee("John Doe", "E123");
$manager = new Manager("Alice Smith", "M456", "Marketing");
$director = new Director("Eve Johnson", "D789", "Finance", "Financial strategy");

// Calling methods
echo "Employee Info: " . $employee->getDetails() . PHP_EOL;
echo "Manager Info: " . $manager->getDetails() . PHP_EOL;
echo "Director Info: " . $director->getDetails() . PHP_EOL;
```

#### 105: What is Polymorphism?
Polymorphism is one of the fundamental concepts in object oriented programming(OOP). It allows objects of different classes to be treated as objects of a common superclass. It enables you to write more flexible and extensible codes. 

In PHP, Polymorphism is achieved through method overriding and interfaces. Let's look at an example:
```php
interface Animal {
    public function speak();
}

class Dog implements Animal {
    public function speak() {
        echo 'Woof! Woof!';
    }
}

class Cat implements Cat {
    public function speak() {
        echo 'Meow! Meow!';
    }
}
```
Now you create instances of these classes and use polymorphism to treat them as instances of the common interface `Animal`;

#### 106: How is the static keyword used in the program?
The `static` keyword is used to define class-level variables and methods that belong to the class itself, not to instances of the class.

#### 107:  Name the types of constructors.
There are two types of constructors:
- Default Constructor (No-Argument Constructor)
- Parameterized Constructor (accepts arguments)

#### 108: What do PHP namespaces mean?
PHP namespaces are used to organize code elements (classes, functions, constants) into logical groups, preventing naming conflicts and improving code organization.


#### 109: Describe the types of access modifiers in PHP.
PHP has three main access modifiers:
- Public: Accessible from anywhere.
- Protected: Accessible within the class and its subclasses.
- Private: Accessible only within the class.

#### 110: Is operator overloading supported by PHP?
PHP does not support operator overloading, which means you can't define custom behaviors for operators like + or - for your classes.


#### 111: What is the difference between encapsulation and abstraction?
- Encapsulation: Protecting data and controlling access to it within a class.
- Abstraction: Simplifying complex systems by focusing on essential features and ignoring unnecessary details.

#### 112: What is the purpose of the yield keyword in PHP?
The `yield` keyword in PHP is used to create generators, allowing you to iterate over large data sets efficiently by pausing and resuming a function's execution to save memory and processing time.

#### 113: What are the types of Polymorphism?
There are two main types of polymorphism in OOP:
- Compile-time (Static) Polymorphism: This is achieved through method overloading and operator overloading. Method overloading is when a class has multiple methods with the same name but different parameters. The correct method to call is determined at compile time based on the method's signature.
- Runtime (Dynamic) Polymorphism: This is achieved through method overriding. Method overriding occurs when a subclass provides a specific implementation for a method that is already defined in its superclass. The correct method to call is determined at runtime based on the actual object's type.


#### 114: What is the use of traits in PHP?
Traits in PHP allow you to reuse code in multiple classes without inheritance. Traits provide a mechanism for code reuse and composition by allowing the inclusion of methods and properties from a trait into a class. This is useful when multiple classes need to share common functionality, but you want to avoid the limitations of single inheritance.


#### 115: What is the use of the finalize method?
The `finalize` method is not a standard method in PHP or most modern programming languages. It may be a concept from older languages like Java, where it was used for resource cleanup and is related to garbage collection. In modern PHP, resource management is typically handled automatically by the language, and you don't need a `finalize` method.

#### 116: Explain Polymorphism with the help of an example.
Polymorphism is best explained through an example of method overriding, which demonstrates runtime polymorphism. Consider a class hierarchy with a base class `Shape` and two subclasses, `Circle` and `Rectangle`. All of them have a calculateArea method. When you call calculateArea on a Shape object, the specific version of the method in the actual subclass will be executed.
```php
class Shape {
    public function calculateArea() {
        // Common code for all shapes
    }
}

class Circle extends Shape {
    public function calculateArea() {
        // Calculate area specific to a circle
    }
}

class Rectangle extends Shape {
    public function calculateArea() {
        // Calculate area specific to a rectangle
    }
}

$circle = new Circle();
$rectangle = new Rectangle();

echo $circle->calculateArea();    // Calls the Circle's method
echo $rectangle->calculateArea(); // Calls the Rectangle's method
```
This demonstrates polymorphism because the same method name is used, but the actual behavior is determined by the type of the object.



#### 117: What is the use of the final keyword in PHP?
The `final` keyword in PHP is used to restrict the inheritance and overriding of methods and classes. When you declare a class or method as final, it means that it cannot be extended or overridden by any subclass. It's used to prevent further modification or specialization of a class or method.



#### 118:  What is Interface in PHP?
An interface in PHP defines a contract that a class must adhere to. It specifies a set of method signatures that a class implementing the interface must provide. Interfaces provide a way to achieve abstraction and ensure that classes follow a certain structure without specifying the implementation details. A class can implement multiple interfaces, enabling it to define multiple contracts.


#### 119:  What is method overloading and how do you use it in PHP OOPs?
Method overloading in PHP allows you to define multiple methods with the same name but different parameters in a class. PHP does not support traditional method overloading as seen in some other languages. Instead, the latest defined method with a particular name and set of parameters will be the one used. It's more about method replacement than overloading. You can achieve similar behavior by using default parameter values or variable-length argument lists (variadic functions) in your methods.


#### 120: What is hybrid inheritance?
Hybrid inheritance is a combination of different types of inheritance, typically involving multiple inheritance (a class inheriting from more than one class) and hierarchical inheritance (a class with multiple subclasses). While some languages support hybrid inheritance, PHP does not directly support multiple inheritance, so achieving hybrid inheritance may require using interfaces and composition.


#### 121: What is static polymorphism?
Static polymorphism, also known as compile-time polymorphism, is achieved through method overloading or operator overloading. The correct method or operator to use is determined at compile time based on the method or operator signature.


#### 122: What is dynamic polymorphism?
Dynamic polymorphism, also known as runtime polymorphism, is achieved through method overriding. The correct method to call is determined at runtime based on the actual object's type, allowing objects of different classes to be treated as objects of a common superclass.

#### 123: Differentiate between overloading and overriding.
- **Method Overloading**: Method overloading involves having multiple methods with the same name in a class, but with different parameters. The correct method to call is determined at compile time based on the method's signature. It is a form of compile-time (static) polymorphism.
- **Method Overriding**: Method overriding occurs when a subclass provides a specific implementation for a method that is already defined in its superclass. The correct method to call is determined at runtime based on the actual object's type. It is a form of runtime (dynamic) polymorphism.


#### 124: What is data abstraction?
Data abstraction is the process of simplifying complex systems by modeling classes based on essential properties and behaviors while hiding unnecessary details. It allows you to focus on the high-level structure of data and operations without getting into the specifics of how data is stored or processed. Data abstraction is a key concept in object-oriented programming, and it promotes modularity and maintainability.


#### 125:  How to achieve data abstraction?
Data abstraction can be achieved through the use of classes and objects in object-oriented programming. You create classes that represent abstract data types, define the public interface (methods) that should be accessible, and hide the internal details (private properties and methods). By doing this, you encapsulate the data and provide a way for other code to interact with the data only through well-defined, abstract methods.


#### 126: Differentiate between data abstraction and encapsulation.
- **Data Abstraction**: Data abstraction is about simplifying complex systems by defining high-level structures, focusing on what data and operations are needed, and ignoring unnecessary details. It is a broader concept that includes encapsulation.
- **Encapsulation**: Encapsulation, on the other hand, is one of the techniques used to achieve data abstraction. It involves bundling the data (attributes) and methods that operate on the data into a single unit (a class) and controlling access to that data. Encapsulation is a specific way to implement data abstraction.


#### 127: What is the difference between OOP and SOP?
- **OOP (Object-Oriented Programming):** OOP is a programming paradigm that uses objects and classes to structure and organize code. It promotes concepts like encapsulation, inheritance, and polymorphism, making it easier to create modular, reusable, and maintainable code.
- **SOP (Structured or Procedural Programming):** SOP is a programming paradigm that uses procedures or functions to organize code. It is based on a top-down approach where the code is structured around procedures that perform specific tasks. It does not emphasize the use of objects and classes.

The main difference is the approach to structuring code. OOP focuses on objects and their interactions, while SOP organizes code around procedures or functions.


#### 128: What is the difference between dependency injection and factory design pattern?
- Dependency Injection (DI): Dependency injection is a design pattern that focuses on providing a class with its dependencies (usually other objects or services) from the outside, rather than having the class create its dependencies. It promotes loose coupling between classes, making them more modular and easier to test.
- Factory Design Pattern: The Factory Design Pattern is used to create objects without specifying the exact class of object to be created. It provides a method (the factory method) for creating objects of a particular class or its subclasses. This pattern allows you to abstract the process of object creation.


The key difference is that DI is about providing dependencies to a class, while the Factory Design Pattern is about creating objects without necessarily knowing their concrete types.


#### 129: What libraries would be useful for OOP development in PHP?
For OOP development in PHP, you can consider using various libraries and frameworks, depending on your project requirements. Some popular libraries and frameworks that promote OOP principles in PHP development include:
- Symfony: A high-performance PHP framework that encourages the use of OOP and provides a wide range of components for various tasks.
- Laravel: A popular PHP framework that utilizes OOP principles for building web applications. It includes an elegant and expressive syntax.
- Doctrine: An Object-Relational Mapping (ORM) library for PHP that allows you to work with databases using OOP concepts.
- Composer: While not a library, Composer is a dependency management tool that helps you install and autoload PHP libraries in your OOP projects.
- PHPStan: A static analysis tool for PHP that helps ensure type safety and adherence to OOP principles.
- PHPUnit: A testing framework for PHP that facilitates unit testing in an object-oriented context.


#### 130: If a class inherits two methods with the same name from its parent class and both have the same number of parameters, then what happens when you try to instantiate this class?
If a class inherits two methods with the same name from its parent class, and both methods have the same number of parameters, the behavior can vary depending on the programming language and how it handles method resolution. In some languages, the method from the most specific subclass is called, while in others, you might encounter an ambiguity error, and you would need to explicitly specify which method to call using parent class names. The exact behavior depends on the language's rules for method resolution and may vary between programming languages.

________________________________________________________________
### Interview Questions for MySQL: 
#### 0: How to get the current MySQL version?
To get the current MySQL version, you can use the following methods:

Command Line (Linux/Unix): Use the command `mysql --version`.
Command Line (Windows): Use the command `mysql -V`.
MySQL Client: Log in to the MySQL client and run the SQL query `SELECT VERSION();`
phpMyAdmin: The MySQL version is typically displayed on the initial page
MySQL Workbench: You can find the MySQL version in the "Server Status" section.

#### 1: What is the MySQL server’s default port?
The default port for MySQL server is 3306.

#### 2: How many different tables are present in MySQL?
The number of different tables in a MySQL database can vary widely and depends on the specific database schema and the data model used. There is no fixed or standard number of tables in MySQL. The number of tables is determined by the design and requirements of the database. Some databases may have just a few tables, while others can have many tables to represent different data entities and relationships.

#### 3: What is Difference between CHAR_LENGTH and LENGTH?
`CHAR_LENGTH` counts the number of characters, while `LENGTH` counts the number of bytes in a string.


#### 4: What do you understand by % and _ in the like statement?
`%` matches any sequence of characters (including zero).
`_` matches any single character.

#### 5: How many index columns can be created in a table?
There's no strict limit; you can create multiple indexes on a table, but be cautious of performance implications.

#### 6: What are string types available for columns?
Common string types include VARCHAR, CHAR, TEXT, and ENUM.


#### 7: Explain the main difference between FLOAT and DOUBLE?
FLOAT is a single-precision floating-point number, while DOUBLE is a double-precision floating-point number. DOUBLE provides higher precision but uses more storage.

#### 8: Explain the difference between having and where clause in MySQL.
- `WHERE` filters rows before aggregation.
- `HAVING` filters results after aggregation.

#### 9: How can we add a column in MySQL?
Use the `ALTER TABLE` statement with the `ADD COLUMN` clause to add a new column to an existing table.

 
#### 10: How to delete columns in MySQL?
Use the `ALTER TABLE` statement with the `DROP COLUMN` clause to delete a column from an existing table.


#### 11: How to delete a table in MySQL?
Use the `DROP TABLE` statement followed by the table name to delete a table in MySQL.


#### 12: How to get the top 10 rows?
Use the `SELECT` statement with `LIMIT 10` to retrieve the top 10 rows from a table.


#### 13: What is the use of the ‘DISTINCT’ keyword in MySQL?
The `DISTINCT` keyword is used to retrieve unique values from a column in a table. It ensures that only distinct values are returned, eliminating duplicates.

#### 14: Which storage engines are used in MySQL?
Common storage engines in MySQL include InnoDB, MyISAM, and MEMORY. Each engine has unique features and is suitable for different use cases.

#### 15: How to create a table in MySQL?
Use the `CREATE TABLE` statement to define the table structure, specify column names and data types, and set constraints like primary keys and foreign keys.


#### 16: What types of relationships are used in MySQL?
Common types include one-to-one, one-to-many, and many-to-many relationships. These are established using keys like primary and foreign keys.


#### 17: How to insert Date in MySQL? 
You can insert a date into a MySQL table using the `INSERT` statement with a valid date format, like `YYYY-MM-DD`.


#### 18: What is join? Tell different join in MySQL.
A join is used to combine rows from two or more tables based on a related column between them. Common joins include INNER JOIN, LEFT JOIN (or LEFT OUTER JOIN), RIGHT JOIN (or RIGHT OUTER JOIN), and FULL JOIN (or FULL OUTER JOIN).


#### 19: What is a primary key? How to drop the primary key in MySQL? 
A primary key is a unique identifier for each record in a table. To drop a primary key, use the `ALTER TABLE` statement with the `DROP PRIMARY KEY` clause.


#### 20: What is InnoDB?
InnoDB is a popular storage engine in MySQL known for its support of transactions, foreign keys, and ACID compliance. It's widely used for reliable and transaction-safe database operations.


#### 21: What is the difference between UNION and UNION ALL in MySQL?
- `UNION` removes duplicate rows.
- `UNION ALL` includes all rows, even duplicates

#### 22: What is a `timestamp` in MySQL?
A `timestamp` in MySQL is a data type used to store date and time values with a time zone.

#### 23: What is the use of ENUMs in MySQL?
ENUMs are used to represent a set of predefined values for a column. They help ensure data consistency and limit possible values.


#### 24: How can you control max size of heap in MySQL?
You can set the max heap size using the `--max-heap-table-size` and `--tmp-table-size` parameters in your MySQL configuration.

#### 25: What is a view? How to create a view? 
A view is a virtual table created from the result of a SQL query. To create a view, use the `CREATE VIEW` statement, specifying the query defining the view.

#### 26: Where MyISAM table will be stored and also give MyISAM formats of storage?
MyISAM tables are stored in the database directory as separate files. Common MyISAM storage formats include .MYD (data), .MYI (index), and .frm (table format) files.

#### 27:  How can we save images in MySQL?
Images can be saved in MySQL by storing them in a BLOB (Binary Large Object) column. BLOBs can store binary data, such as images, as part of a table's record.

#### 28: What are trigger and how many TRIGGERS are available in MySQL table?
Triggers are database objects that automatically perform actions in response to predefined events. In MySQL, you can create AFTER INSERT, AFTER UPDATE, and AFTER DELETE triggers for tables.

#### 29: What are Access Control Lists?
Access Control Lists (ACLs) are lists of permissions that specify which users or system processes are granted access to objects, as well as what operations are allowed on given objects in a system.

#### 30: What are various ways to create an index?
You can create indexes using CREATE INDEX statements, by defining primary keys, or by using the ALTER TABLE statement. Common index types are B-tree, hash, and full-text indexes.


#### 31: What are a clustered index and a non clustered index?
In MySQL, the concept of a clustered index is mainly associated with the InnoDB storage engine. A clustered index determines the physical order of rows in a table and is typically based on the primary key. A non-clustered index doesn't affect the physical order of rows and is separate from the data.


#### 32: How to validate emails using a single query?
You can validate emails using regular expressions in a query. For example, `SELECT email FROM users WHERE email REGEXP '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,4}$'`;

#### 33: How can you handle the –secure-file-priv in MySQL?
You can set the `--secure-file-priv` option in the MySQL configuration file to specify a directory where MySQL can write secure files for data import/export operations.

#### 34:  How do you create a database in MySQL?
Use the `CREATE DATABASE` statement to create a new database in MySQL.

#### 35: How do you create a table using MySQL?
Use the `CREATE TABLE` statement to define and create a new table in a MySQL database. Specify the table's structure, column names, data types, and constraints.


#### 36: What is BLOB in MySQL?
BLOB stands for Binary Large Object. It's a MySQL data type used to store binary data, such as images, audio, or other non-text data.


#### 37: How to add users in MySQL?
You can add users in MySQL using the `CREATE USER` statement or through a client application. You need to specify their username and password.


#### 38: What are MySQL Triggers?
MySQL triggers are database objects that automatically execute actions (e.g., SQL statements) in response to specific events, such as INSERT, UPDATE, or DELETE operations on a table.

#### 39: How many Triggers are possible in MySQL?
In MySQL, you can create multiple triggers for each table. The number of triggers you can create is not strictly limited, but it's good practice to keep them manageable for clarity and maintainability.

#### 40: What is the MySQL server?
The MySQL server is the core component of the MySQL database management system. It handles database operations, such as querying, updating, and managing data.


#### 41: What are the MySQL clients and utilities?
MySQL provides various client applications and utilities like the command-line client, MySQL Workbench, phpMyAdmin, and others. These tools allow you to interact with and manage MySQL databases.


#### 42: Can you explain the logical architecture of MySQL?
The logical architecture of MySQL includes components like the Query Optimizer, Storage Engines, and the SQL Layer. The Query Optimizer optimizes queries, the Storage Engines handle data storage and retrieval, and the SQL Layer manages SQL parsing and execution.


#### 43: What is Scaling in MySQL?
Scaling in MySQL refers to the process of increasing the capacity and performance of a MySQL database system to handle growing workloads and user demands. It can involve techniques like sharding, replication, and clustering to distribute and manage data across multiple servers.

#### 44: What is the purpose of the SHOW TABLES command in MySQL?
The SHOW TABLES command is used to list the tables in the current database.

#### 45: What is normalization and denormalization in the context of database design?
Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity. Denormalization is the opposite, where data is intentionally duplicated to optimize query performance.


#### 46: What is the ACID properties in the context of database transactions?
ACID stands for `Atomicity, Consistency, Isolation, and Durability`. These properties ensure that database transactions are reliable, and data remains consistent even in the face of errors.

#### 47: How can you prevent SQL injection in MySQL?
To prevent SQL injection, use parameterized queries or prepared statements. These techniques ensure that user inputs are treated as data and not executable SQL code.


#### 48: What is the difference between a LEFT JOIN and a RIGHT JOIN in MySQL?
A LEFT JOIN retrieves all records from the left table and matching records from the right table, while a RIGHT JOIN retrieves all records from the right table and matching records from the left table.


#### 49: What is a stored procedure in MySQL?
A stored procedure is a set of SQL statements that can be executed as a single unit. It is stored in the database and can be called multiple times with different parameters.

#### 50: How do you export data from a MySQL table to a CSV file?
You can export data to a CSV file using the `SELECT...INTO OUTFILE` statement or by using MySQL client utilities like `mysqldump` with the `--tab` option.


________________________________________________________________
### Interview Questions for Laravel: 
#### 0: Explain the MVC architecture and how Laravel implements it.
Laravel follows the Model-View-Controller (MVC) architecture. Models represent the data, Views display it, and Controllers handle user requests and manage the flow between Models and Views.


#### 1: What is Eloquent ORM, and how does it work in Laravel?
Eloquent is Laravel's ORM (Object-Relational Mapping). It allows you to work with databases using object-oriented syntax, making database interactions more convenient.


#### 2: What is Blade templating in Laravel?
Blade is Laravel's templating engine. It simplifies the creation of views by allowing you to write clean, readable template files with dynamic content.


#### 3: How does routing work in Laravel, and what are the different types of routes?
Laravel's routing maps URLs to controller actions. It includes route definition and handling for various HTTP request methods. There are named, resource, and wildcard routes, among others.



#### 4: What are middleware in Laravel, and how are they used?
Middleware is code that filters HTTP requests entering your application. It can be used for authentication, logging, CORS, and more.


#### 5: Explain dependency injection in Laravel.
Dependency injection is a technique used in Laravel to resolve dependencies for classes and functions. The Laravel service container manages this, making it easy to inject dependencies.


#### 6: What are Laravel migrations, and why are they important?
Migrations are version control for your database schema. They allow you to modify the database structure using PHP code and can be rolled back.


#### 7: How does authentication and authorization work in Laravel?
Laravel provides built-in tools for user authentication and role-based authorization. It's handled through middleware and policies.


#### 8: What are seeders in Laravel?
Seeders are used to populate database tables with sample data. They help in database testing and development.


#### 9: What are factories in Laravel?
Factories are used to generate fake data for testing and seeding databases. They are particularly useful for testing.


#### 10: How to implement soft delete in Laravel?
Soft delete is a feature in Laravel that allows you to mark records as deleted without actually removing them from the database. It's useful for data retention and recovery.

#### 11: What are Models?
In Laravel, Models represent the data structure and business logic of your application's database tables. They are used to interact with the database.


#### 12: What are Relationships in Laravel?
Relationships in Laravel define how different models are related to each other in terms of database associations, such as one-to-one, one-to-many, and many-to-many.


#### 13: What is Eloquent in Laravel?
Eloquent is Laravel's ORM (Object-Relational Mapping) system that enables you to work with databases using object-oriented syntax and models.


#### 14: What is throttling and how to implement it in Laravel?
Throttling is a rate-limiting mechanism used to control the number of requests a user can make in a specified time frame. It can be implemented in Laravel using middleware or route middleware to protect routes.


#### 15:  What are facades?
Facades in Laravel provide a simple and consistent interface to various services in the application. They offer an easy way to access services like the database, caching, and more.


#### 16:  What are Events in Laravel?
Events in Laravel are used to announce and listen for specific events in your application. They are useful for decoupling components and responding to various activities.


#### 17: What is Localization in Laravel?
Localization in Laravel is the process of translating your application's content into multiple languages. It allows your application to be used by speakers of different languages.


#### 18: What are Requests in Laravel?
Requests in Laravel handle HTTP requests. They provide validation, authorization, and input handling for your application.

#### 19: How to do request validation in Laravel?
Request validation in Laravel is done by creating request classes. These classes define the rules for validating incoming HTTP requests.


#### 20: What is a Service Container in Laravel?
The Service Container in Laravel is a powerful tool for managing class dependencies and performing dependency injection. It's used to resolve, bind, and manage class instances in the application.

#### 21: What is a Service Provider?
A Service Provider in Laravel is responsible for binding classes and services in the service container, registering components, and performing any bootstrapping needed for your application.


#### 22: What is the register and boot method in the Service Provider class?
The `register` method is used to bind services into the container, while the `boot` method is used for any additional actions needed after all service providers have been registered.


#### 23: How to define routes in Laravel?
Routes in Laravel are defined in the `routes/web.php` or `routes/api.php` files using the Route facade or closure functions.


#### 24: What are named routes?
Named routes in Laravel allow you to define a unique name for a route. This makes it easier to reference the route in your application, such as for URL generation or redirection.


#### 25: What are route groups?
Route groups in Laravel are used to group multiple routes together and apply common middleware or other attributes to those routes.


#### 26: What is Middleware and how to create one in Laravel?
Middleware in Laravel is a filter that can be applied to HTTP requests entering the application. You can create middleware using the make:middleware Artisan command.


#### 27: What are collections?
Collections in Laravel provide a convenient way to work with arrays of data. They offer various methods for data manipulation and transformation.


#### 28: What are contracts?
Contracts in Laravel define the methods that a class must implement, providing a way to ensure that classes follow specific interfaces.


#### 29: What are queues in Laravel?
Queues in Laravel enable delayed or background execution of tasks. They are used to handle time-consuming operations outside the regular request cycle.


#### 30: What are accessors and mutators?
Accessors are used to format and retrieve attributes from models. Mutators are used to set or modify attribute values before saving to the database in Laravel models.


#### 31: Explain the concept of eager loading in Laravel.
Eager loading is a technique in Laravel to load related models (e.g., for relationships like `belongsTo` or `hasMany`) to avoid the "N+1 query problem" and improve performance.


#### 32: How do you handle AJAX requests in Laravel?
Laravel provides built-in support for handling AJAX requests. You can use the Request object and return JSON or other responses in your controller methods.


#### 33: What are macros in Laravel, and how do you define them?
Macros in Laravel allow you to extend existing classes with additional methods. You can define them using the `macro` method provided by Laravel's Macroable trait.

#### 34:What are the common tools used to send emails in Laravel?
Common tools for sending emails in Laravel include the built-in mail driver, `SMTP`, and third-party services like `Mailgun` or `SendGrid`.


#### 35: Explain validations in laravel?
Validations in Laravel are rules and filters applied to user input to ensure it meets specific criteria, such as required fields, email format, and custom rules. Laravel provides a convenient way to define and enforce these rules in your application.


#### 36: How to install laravel via composer ?
To install Laravel via Composer, use the command: `composer create-project --prefer-dist laravel/laravel project-name`.


#### 37: Explain Laravel’s service container?
Laravel's service container is a tool for managing class dependencies and performing dependency injection. It automatically resolves and injects dependencies into your classes, facilitating better code organization and testability.

#### 38: How to enable query log in Laravel?
You can enable query log in Laravel by calling `DB::enableQueryLog()` before executing queries and then retrieve the logged queries using `DB::getQueryLog().`


#### 39: How to use custom table in Laravel Model?
In a Laravel Model, you can specify a custom table by setting the $table property to the desired table name. For example: `protected $table = 'custom_table'`;.


#### 40: List types of relationships available in Laravel Eloquent?
Laravel Eloquent supports relationships like `belongsTo`, `hasOne`, `hasMany`, `belongsToMany`, `morphTo`, and `morphMany`, among others.

#### 41: How to clear cache in Laravel?
You can clear the cache in Laravel using the `php artisan cache:clear` command.


#### 42: What do you understand by Unit testing?
Unit testing is a software testing technique in which individual components or units of code are tested in isolation to ensure they perform as expected. In Laravel, PHPUnit is often used for writing unit tests to validate the correctness of specific parts of the application.


#### 43: Explain the Service container and its advantages.
The Service container in Laravel is a powerful tool for managing class dependencies and performing dependency injection. Its advantages include facilitating cleaner, more maintainable code, improving testability, and enabling the resolution of dependencies automatically, making it easier to manage and extend your application.


#### 44: What is the use of PHP compact function?
The `compact` function in PHP is used to create an array from variables. In Laravel, it's often used to pass data to views by compacting variables into an array for use in Blade templates.


#### 45: What do you understand by ORM?
ORM stands for Object-Relational Mapping. It's a technique used to map database tables and records to objects in object-oriented programming languages, such as Laravel's Eloquent ORM. ORM simplifies database interactions by allowing developers to work with database data as if they were working with objects and classes.


#### 46: How can someone change the default database type in Laravel?
To change the default database type in Laravel, you can edit the `DB_CONNECTION` value in the .env file to the desired database type (e.g., `mysql`, `pgsql`, `sqlite`, etc.).


#### 47: In which directory controllers are kept in Laravel?
Controllers in Laravel are typically stored in the `app/Http/Controllers` directory.


#### 48: What do you know about Closures in Laravel?
Closures are anonymous functions used in Laravel to define small, reusable code blocks. They are often used in routes and middleware to perform specific actions at runtime.


#### 49: How will you describe Fillable Attribute in a Laravel model?
The `fillable` attribute in a Laravel model is an array that defines which model attributes can be mass-assigned when using methods like `create` or `update`. It helps protect against overwriting sensitive attributes.


#### 50:How can we check the Laravel current version?
You can check the current Laravel version installed in your project by running the command `php artisan --version` in the command line.


#### 51: How can we get data between two dates using Query in Laravel?
You can retrieve data between two dates in Laravel using the whereBetween method in a query. For example: `$data = Model::whereBetween('date_column', [$startDate, $endDate])->get();`.


#### 52: How do you do soft deletes?
In Laravel, soft deletes are implemented by adding the `use SoftDeletes` trait to your Eloquent model and defining the `deleted_at` column in the corresponding database table. Soft deleted records are not removed from the database but marked as deleted by setting the `deleted_at` timestamp. You can use the withTrashed and onlyTrashed methods to retrieve soft deleted records.


#### 53: How do you generate migrations?
You can generate a migration in Laravel using the artisan command `php artisan make:migration`. For example: `php artisan make:migration create_table_name`. This will create a new migration file in the `database/migrations` directory, where you can define the schema for your database table.


#### 54: How do you mock a static facade methods?
To mock a static facade method in Laravel for testing, you can use a package like Mockery or PHPUnit. You can create a mock object of the facade and define the expected behavior using these tools. Example:
```php
use Illuminate\Support\Facades\Facade;

Facade::shouldReceive('staticFacadeMethod')->andReturn('mocked result');
```
#### 55: List some Aggregates methods provided by query builder in Laravel?
Some aggregate methods provided by Laravel's query builder include `count()`, `sum()`, `avg()`, `min()`, and `max()`. These methods allow you to perform calculations on data columns in your database tables.


#### 56: What is Closure in Laravel?
In Laravel, a Closure is an anonymous function that can be used as a callback or as a parameter for various methods. Closures are often used in routes, middleware, and as callback functions for various operations within the application.


#### 57: What is autoloading classes in PHP?
Autoloading classes in PHP is the process of automatically including the necessary class files when they are needed, without requiring manual `require` or `include` statements. Autoloading simplifies code organization and makes it more maintainable.


#### 58: What is CSRF protection and CSRF token?
`CSRF` (Cross-Site Request Forgery) protection is a security feature in Laravel that helps prevent malicious websites from making unauthorized requests on behalf of a user. Laravel generates and verifies CSRF tokens to ensure that the requests are coming from trusted sources and not from potentially harmful external sites.

#### 59: What template is used by the Laravel engine?
Laravel uses the Blade template engine for building dynamic views. Blade provides a clean and expressive way to write templates with features like control structures, template inheritance, and more.


#### 60: What is reverse Routing in Laravel?
Reverse routing in Laravel allows you to generate URLs for named routes. Instead of hardcoding URLs in your application, you can use route names to generate URLs dynamically. This makes it easier to maintain and update URLs throughout your application, especially when routes change.
