# book-cafe
This code sets up the basic structure of the book cafe management system. It includes a book catalog section where books are displayed in a table, and a form to add new books. You can expand the HTML structure, update the CSS styling accordingly, and add appropriate JavaScript code to handle the desired functionalities.
<!DOCTYPE html>
<html>
<head>
  <title>Book Cafe Management</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <h1>Book Cafe Management</h1>

  <div class="container">
    <h2>Book Catalog</h2>

    <table id="bookTable">
      <tr>
        <th>Title</th>
        <th>Author</th>
        <th>Genre</th>
      </tr>
      <!-- Book catalog will be dynamically added here -->
    </table>

    <h2>Add a New Book</h2>

    <form id="addBookForm">
      <label for="title">Title:</label>
      <input type="text" id="title" name="title">

      <label for="author">Author:</label>
      <input type="text" id="author" name="author">

      <label for="genre">Genre:</label>
      <input type="text" id="genre" name="genre">

      <button type="submit">Add Book</button>
    </form>
  </div>

  <script src="script.js"></script>
</body>
</html>
#css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 20px;
}

h1 {
  text-align: center;
}

.container {
  margin-bottom: 20px;
}

table {
  width: 100%;
  border-collapse: collapse;
}

th, td {
  padding: 8px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

button {
  padding: 8px 16px;
}
#js
document.addEventListener('DOMContentLoaded', function() {
  const addBookForm = document.getElementById('addBookForm');
  const bookTable = document.getElementById('bookTable');

  addBookForm.addEventListener('submit', function(event) {
    event.preventDefault(); // Prevent form submission

    // Get the input values
    const title = document.getElementById('title').value;
    const author = document.getElementById('author').value;
    const genre = document.getElementById('genre').value;

    // Create a new table row with the input values
    const newRow = document.createElement('tr');
    newRow.innerHTML = `
      <td>${title}</td>
      <td>${author}</td>
      <td>${genre}</td>
    `;

    // Append the new row to the table
    bookTable.appendChild(newRow);

    // Clear the form fields
    addBookForm.reset();
  });
});
