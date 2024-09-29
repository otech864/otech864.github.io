<!DOCTYPE html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proxy Browser</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 0;
        }

        #url-form {
            margin-bottom: 20px;
        }

        #url-input {
            width: 300px;
            padding: 8px;
        }

        #submit-btn {
            padding: 8px 12px;
        }

        iframe {
            width: 100%;
            height: 80vh;
            border: none;
        }
    </style>
</head>
<body>
    <h1>Simple Proxy Browser</h1>
    <form id="url-form">
        <input type="text" id="url-input" placeholder="Enter a URL" />
        <button id="submit-btn" type="submit">Go</button>
    </form>
    <iframe id="proxy-frame" src=""></iframe>

    <script>
        document.getElementById('url-form').addEventListener('submit', function(event) {
            event.preventDefault();
            const urlInput = document.getElementById('url-input').value;
            if (urlInput) {
                const proxyUrl = `http://localhost:3000/proxy/${urlInput}`;
                document.getElementById('proxy-frame').src = proxyUrl;
            }
        });
    </script>
</body>
</html>
