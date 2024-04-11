<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Multiple Document Upload and Download</title>
</head>
<body>
  <h1>Upload Documents</h1>
  <input type="file" id="fileInput" multiple>
  <button onclick="uploadFiles()">Upload</button>

  <h1>Uploaded Documents</h1>
  <ul id="fileList"></ul>

  <h1>Download Documents</h1>
  <button onclick="downloadFiles()">Download All</button>

  <script>
    function uploadFiles() {
      const fileInput = document.getElementById('fileInput');
      const fileList = document.getElementById('fileList');
      
      while (fileList.firstChild) {
        fileList.removeChild(fileList.firstChild);
      }

      for (const file of fileInput.files) {
        const listItem = document.createElement('li');
        listItem.textContent = file.name;
        fileList.appendChild(listItem);
      }
    }

    function downloadFiles() {
      const fileInput = document.getElementById('fileInput');
      for (const file of fileInput.files) {
        const url = URL.createObjectURL(file);
        const link = document.createElement('a');
        link.href = url;
        link.download = file.name;
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
        URL.revokeObjectURL(url);
      }
    }
  </script>
</body>
</html>

