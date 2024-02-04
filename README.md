# practice
# これを見出しです
> 引用
  これをサイトを引用してます。


* リストの１
* リストの２
* リストの３
***
1.リストの１

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>User ID Search</title>
</head>
<body>

  <h2>User ID Search</h2>
  
  <!-- Generate Ten Sample Data -->
  <ul>
    <li>001</li>
    <li>002</li>
    <li>003</li>
    <li>004</li>
    <li>005</li>
    <li>006</li>
    <li>007</li>
    <li>008</li>
    <li>009</li>
    <li>010</li>
  </ul>

  <form action="#" method="get" onsubmit="return searchUsers()">
    <label for="startUserId">Start User ID: </label>
    <input type="text" id="startUserId" name="startUserId" pattern="^(0[1-9]|10)$" title="Please enter a valid User ID between 001 and 010" required>

    <label for="endUserId">End User ID: </label>
    <input type="text" id="endUserId" name="endUserId" pattern="^(0[1-9]|10)$" title="Please enter a valid User ID between 001 and 010" required>

    <button type="submit">Search</button>
  </form>

  <!-- Display Searched User IDs -->
  <div id="searchResult"></div>

  <script>
    function searchUsers() {
      var startUserId = parseInt(document.getElementById('startUserId').value, 10);
      var endUserId = parseInt(document.getElementById('endUserId').value, 10);

      // Placeholder for searched user IDs
      var searchedUserIds = [];

      // Sample data
      var sampleData = Array.from({ length: 10 }, (_, i) => String(i + 1).padStart(3, '0'));

      // Filter user IDs based on the search criteria
      for (var i = startUserId; i <= endUserId; i++) {
        searchedUserIds.push(sampleData[i - 1]);
      }

      // Display the searched user IDs
      var searchResultElement = document.getElementById('searchResult');
      searchResultElement.textContent = 'Searched User IDs: ' + searchedUserIds.join(', ');

      return false; // Prevents the form from actually submitting in this example
    }
  </script>

</body>
</html>
