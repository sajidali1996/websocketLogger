<!DOCTYPE HTML>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download WebSocket Data Logging App</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <button onclick="downloadApp()">Download App</button>

    <script type="text/javascript">
        async function downloadApp() {
            const githubRawURL = 'https://raw.githubusercontent.com/sajidali1996/websocketLogger/main/techAppDataLogger.html';

            try {
                const response = await fetch(githubRawURL);
                const appCode = await response.text();

                const blob = new Blob([appCode], { type: 'text/html' });
                const link = document.createElement('a');
                link.href = URL.createObjectURL(blob);
                link.download = 'WebSocket_Data_Logging_App.html';
                link.click();
            } catch (error) {
                console.error('Error downloading the app:', error);
            }
        }
    </script>
</body>
</html>
