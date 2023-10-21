# HOF_AND_Functional_Programming_JavaScript-_Assignment


Ques 1 . Reverse String.

Ans  function reverseString(str) {
  let reversed = "";
  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }
  return reversed;
}

const originalString = "Hello, World!";
const reversedString = reverseString(originalString);
console.log(reversedString); // Outputs: "!dlroW ,olleH"



Ques 2  Random Number Generator with Delay and Progress Indication:

Ans   To create a random number generator with a delay and progress indication, you can use JavaScript and HTML to build a simple web application. Here's an example of how you can do it:


<!DOCTYPE html>
<html>
<head>
    <title>Random Number Generator</title>
</head>
<body>
    <h1>Random Number Generator</h1>
    <button id="startButton">Start</button>
    <p id="progress">Progress: 0%</p>
    <p id="result"></p>

    <script>
        // Function to generate a random number
        function generateRandomNumber() {
            return Math.floor(Math.random() * 100) + 1;
        }

        // Function to update the progress and result
        function updateProgressAndResult(progress, number) {
            document.getElementById('progress').textContent = `Progress: ${progress}%`;
            document.getElementById('result').textContent = `Random Number: ${number}`;
        }

        // Function to generate a random number with a delay
        function generateNumberWithDelay() {
            const maxProgress = 100;
            const delay = 100; // Delay in milliseconds
            let progress = 0;

            const interval = setInterval(function() {
                progress += 10;
                if (progress > maxProgress) {
                    clearInterval(interval);
                    const randomNumber = generateRandomNumber();
                    updateProgressAndResult(maxProgress, randomNumber);
                } else {
                    updateProgressAndResult(progress, null);
                }
            }, delay);
        }

        // Event listener for the "Start" button
        document.getElementById('startButton').addEventListener('click', function() {
            generateNumberWithDelay();
        });
    </script>
</body>
</html>



In this example, we have created a simple web page with a "Start" button that triggers the random number generation process with a progress indicator. When you click the "Start" button, it will display the progress as it generates the random number and then show the generated random number when it's done. The delay between progress updates is set to 100 milliseconds.

You can adjust the delay and the maximum progress according to your requirements. This is a basic example, and you can customize it further as needed.

Ques 3     Build a feature for Store's Inventory.


Ans   Creating a feature for a store's inventory is a broad task, as it can encompass various functionalities and requirements. Below is a basic outline of how you can build a simple inventory management feature for a store using JavaScript, HTML, and CSS. This feature allows you to add, view, and search for products in the inventory.

<!DOCTYPE html>
<html>
<head>
    <title>Store Inventory</title>
    <style>
        /* Add your CSS styles here */
        /* Styling for buttons, input fields, tables, etc. */
    </style>
</head>
<body>
    <h1>Store Inventory Management</h1>

    <!-- Add Product Form -->
    <h2>Add Product</h2>
    <form id="addProductForm">
        <label for="productName">Product Name:</label>
        <input type="text" id="productName" required>
        <label for="productPrice">Price:</label>
        <input type="number" id="productPrice" required>
        <button type="submit">Add Product</button>
    </form>

    <!-- Product List -->
    <h2>Product List</h2>
    <table>
        <thead>
            <tr>
                <th>Product Name</th>
                <th>Price</th>
            </tr>
        </thead>
        <tbody id="productList">
            <!-- Product entries will be displayed here -->
        </tbody>
    </table>

    <!-- Search Product Form -->
    <h2>Search Product</h2>
    <form id="searchProductForm">
        <label for="searchKeyword">Search by Name:</label>
        <input type="text" id="searchKeyword">
        <button type="submit">Search</button>
    </form>

    <!-- Search Results -->
    <h2>Search Results</h2>
    <table>
        <thead>
            <tr>
                <th>Product Name</th>
                <th>Price</th>
            </tr>
        </thead>
        <tbody id="searchResults">
            <!-- Search results will be displayed here -->
        </tbody>
    </table>

    <script>
        // JavaScript code for inventory management
        const addProductForm = document.getElementById('addProductForm');
        const productList = document.getElementById('productList');
        const searchProductForm = document.getElementById('searchProductForm');
        const searchResults = document.getElementById('searchResults');

        addProductForm.addEventListener('submit', function(event) {
            event.preventDefault();
            const productName = document.getElementById('productName').value;
            const productPrice = document.getElementById('productPrice').value;
            
            // Add the product to the inventory
            // You can use an array or a database to store products and update the product list.

            // Clear the form
            document.getElementById('productName').value = '';
            document.getElementById('productPrice').value = '';
        });

        searchProductForm.addEventListener('submit', function(event) {
            event.preventDefault();
            const searchKeyword = document.getElementById('searchKeyword').value;
            
            // Search for products that match the keyword
            // Display the search results in the searchResults table.

            // Clear the form
            document.getElementById('searchKeyword').value = '';
        });
    </script>
</body>
</html>

In this basic example, we have provided a simple HTML layout for adding products, viewing the product list, and searching for products by name. The JavaScript code outlines the event listeners for adding products and searching for products, but the actual implementation of adding, storing, and searching for products will depend on your specific requirements and might involve using a server, a database, or client-side storage options. You can customize this structure and functionality to fit the needs of your store's inventory feature.

Ques 4   Filtering and Capitalizing: Books Published After 2010 with Author Names.

Ans  To filter and capitalize the author names of books published after 2010, you can use JavaScript. Here's an example of how you can achieve this with an array of book objects:

    // Sample array of book objects
const books = [
  { title: "Book 1", author: "John Smith", year: 2005 },
  { title: "Book 2", author: "Jane Doe", year: 2015 },
  { title: "Book 3", author: "Bob Johnson", year: 2012 },
  { title: "Book 4", author: "Alice Brown", year: 2019 }
];

// Function to filter and capitalize author names of books published after 2010
function filterAndCapitalizeAuthors(books) {
  const filteredBooks = books.filter(book => book.year > 2010);
  
  const result = filteredBooks.map(book => {
    // Capitalize the first letter of each word in the author's name
    const authorName = book.author.split(' ')
      .map(word => word.charAt(0).toUpperCase() + word.slice(1))
      .join(' ');
    return { title: book.title, author: authorName };
  });

  return result;
}

const filteredBooks = filterAndCapitalizeAuthors(books);
console.log(filteredBooks);






In this code:

1 We have an array of book objects with titles, authors, and publication years.

2 The filterAndCapitalizeAuthors function filters the books published after 2010 using the filter method.

3 It then uses the map method to capitalize the first letter of each word in the author's name.

4 The result is an array of books with author names capitalized and published after 2010.

The filteredBooks array will contain the filtered and capitalized book information, and you can use it as needed in your application.


Ques 5  URL Validation


Ans   URL validation in JavaScript can be done using regular expressions. Regular expressions are powerful tools for pattern matching and can be used to validate URLs. Below is a simple example of how to validate a URL in JavaScript:

function isValidURL(url) {
  // Regular expression pattern to match a URL
  const urlPattern = /^(https?:\/\/)?([\da-z.-]+)\.([a-z.]{2,6})([/\w .-]*)*\/?$/;

  // Use the RegExp test method to check if the URL matches the pattern
  return urlPattern.test(url);
}

// Example usage:
const url1 = "https://www.example.com";
const url2 = "http://subdomain.example.co.uk/path/to/page";
const url3 = "invalid-url";

console.log(isValidURL(url1)); // true
console.log(isValidURL(url2)); // true
console.log(isValidURL(url3)); // false


In the code above:

* We define a function isValidURL that takes a URL as input.

* We use a regular expression pattern to match URLs. This pattern allows for URLs starting with "http://" or "https://", followed by domain and path components. It's a basic example and can be modified to suit your specific requirements.

* We use the test method of the regular expression to check if the URL matches the pattern. The method returns true if the URL is valid and false otherwise.

This is a basic URL validation method. Note that URL validation can become quite complex due to the various URL formats and schemes. For more robust URL validation, you can use existing libraries like validator.js or adjust the regular expression pattern to meet your specific needs.



Ques 6 LinkedIn Profile URL Validator.

Ans  To validate LinkedIn profile URLs specifically, you can create a custom function in JavaScript that checks whether a given URL is a valid LinkedIn profile URL. Here's an example of a function that does that:

function isValidLinkedInProfileURL(url) {
  // Regular expression pattern for a LinkedIn profile URL
  const linkedinPattern = /^(https:\/\/)?(www\.)?linkedin\.com\/in\/[a-zA-Z0-9-]+\/?$/;

  // Use the RegExp test method to check if the URL matches the pattern
  return linkedinPattern.test(url);
}

// Example usage:
const url1 = "https://www.linkedin.com/in/johndoe/";
const url2 = "https://www.linkedin.com/in/jane-smith-123/";
const url3 = "https://www.linkedin.com/company/company-name";

console.log(isValidLinkedInProfileURL(url1)); // true
console.log(isValidLinkedInProfileURL(url2)); // true
console.log(isValidLinkedInProfileURL(url3)); // false


In this code:

* We define a function isValidLinkedInProfileURL that takes a URL as input.

* We use a regular expression pattern (linkedinPattern) that matches LinkedIn profile URLs. This pattern checks for URLs that start with "https://www.linkedin.com/in/" followed by a valid LinkedIn username or profile identifier. It allows for profiles with hyphens in the name.

* We use the test method of the regular expression to check if the URL matches the LinkedIn pattern. The method returns true if the URL is a valid LinkedIn profile URL and false otherwise.

This function will work for most LinkedIn profile URLs, but keep in mind that LinkedIn may change its URL format in the future. You may need to update the regular expression pattern accordingly to ensure accurate validation.




