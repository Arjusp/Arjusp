<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Upload & Download</title>
    <style>
        /* Basic styling for the page */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
        }
        #uploadForm {
            text-align: center;
            margin-bottom: 20px;
        }
        #fileList {
            list-style-type: none;
            padding: 0;
        }
        #fileList li {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <h1>Document Upload & Download</h1>
    
    <!-- Form for uploading documents -->
    <div id="uploadForm">
        <input type="file" id="fileInput">
        <button onclick="uploadFile()">Upload</button>
    </div>

    <!-- List to display uploaded documents -->
    <ul id="fileList"></ul>

    <script>
        // Function to handle file upload
        function uploadFile() {
            var fileInput = document.getElementById('fileInput');
            var fileList = document.getElementById('fileList');

            // Get the uploaded file
            var file = fileInput.files[0];

            // Create a new list item to display the file name
            var listItem = document.createElement('li');
            listItem.textContent = file.name;
            fileList.appendChild(listItem);

            // You can send the file to the server for processing here
            // For simplicity, we're not implementing server-side processing in this example
        }

        // Function to handle file download (dummy function for demonstration)
        function downloadFile(fileName) {
            // Simulate downloading the file
            alert('Downloading: ' + fileName);
            // You would typically implement logic here to initiate a download from the server
        }
    </script>
</body>
</html>
