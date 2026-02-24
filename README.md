cd CMD-TOOK

# Tạo .gitignore
echo node_modules/ > .gitignore
echo dist/ >> .gitignore
echo *.log >> .gitignore
echo .env >> .gitignore
echo .DS_Store >> .gitignore

# Tạo README.md
echo # CMD-TOOK > README.md
echo. >> README.md
echo A professional remote terminal application >> README.md

# Tạo backend folder
mkdir backend
mkdir frontend\src\components
mkdir frontend\src\styles

# Tạo backend/package.json
(
echo {
echo   "name": "cmd-took-backend",
echo   "version": "1.0.0",
echo   "main": "server.js",
echo   "scripts": {
echo     "start": "node server.js",
echo     "dev": "nodemon server.js"
echo   },
echo   "dependencies": {
echo     "express": "^4.18.2",
echo     "cors": "^2.8.5",
echo     "dotenv": "^16.0.3"
echo   }
echo }
) > backend\package.json

# Tạo backend/server.js
(
echo const express = require('express');
echo const cors = require('cors');
echo const app = express();
echo app.use(cors(^)^);
echo app.use(express.json(^)^);
echo const PORT = 3001;
echo app.get('/api/system', (req, res^) =^> { res.json({status: 'ok'}^); }^);
echo app.listen(PORT, () =^> { console.log(`Server on port ${PORT}`^); }^);
) > backend\server.js

# Tạo frontend/package.json
(
echo {
echo   "name": "cmd-took-frontend",
echo   "version": "1.0.0",
echo   "type": "module",
echo   "scripts": {
echo     "dev": "vite",
echo     "build": "vite build"
echo   },
echo   "dependencies": {
echo     "react": "^18.2.0",
echo     "react-dom": "^18.2.0"
echo   }
echo }
) > frontend\package.json

# Tạo frontend/vite.config.js
(
echo import { defineConfig } from 'vite'
echo import react from '@vitejs/plugin-react'
echo export default defineConfig({
echo   plugins: [react(^)]
echo }^)
) > frontend\vite.config.js

# Tạo frontend/index.html
(
echo ^<!DOCTYPE html^>
echo ^<html^>
echo ^<head^>
echo     ^<meta charset="UTF-8"^>
echo     ^<title^>CMD-TOOK^</title^>
echo ^</head^>
echo ^<body^>
echo     ^<div id="root"^>^</div^>
echo     ^<script type="module" src="/src/main.jsx"^>^</script^>
echo ^</body^>
echo ^</html^>
) > frontend\index.html

# Tạo frontend/src/main.jsx
(
echo import React from 'react'
echo import ReactDOM from 'react-dom/client'
echo import App from './App.jsx'
echo import './App.css'
echo ReactDOM.createRoot(document.getElementById('root'^)^).render(
echo   ^<React.StrictMode^>
echo     ^<App /^>
echo   ^</React.StrictMode^>
echo ^)
) > frontend\src\main.jsx

# Tạo frontend/src/App.jsx
(
echo import { useState } from 'react'
echo import './App.css'
echo function App(^) {
echo   const [input, setInput] = useState('')
echo   return (
echo     ^<div className="app"^>
echo       ^<h1^>CMD-TOOK^</h1^>
echo       ^<input value={input} onChange={(e^) =^> setInput(e.target.value^)} /^>
echo     ^</div^>
echo   ^)
echo }
echo export default App
) > frontend\src\App.jsx

# Tạo frontend/src/App.css
(
echo * {
echo   margin: 0;
echo   padding: 0;
echo }
echo body {
echo   background: #000;
echo   color: #00ff00;
echo   font-family: 'Courier New', monospace;
echo }
echo .app {
echo   width: 100vw;
echo   height: 100vh;
echo }
) > frontend\src\App.css

# Tạo frontend/src/components/Terminal.jsx
(
echo export default function Terminal({ output ^} ^) {
echo   return ^<div className="terminal"^>{output.map((line, idx^) =^> ^<div key={idx}^>{line}^</div^>^)^}^</div^>
echo }
) > frontend\src\components\Terminal.jsx

# Tạo frontend/src/components/Keyboard.jsx
(
echo export default function Keyboard(^) {
echo   return ^<div className="keyboard"^>Keyboard^</div^>
echo }
) > frontend\src\components\Keyboard.jsx

# Tạo frontend/src/components/ServerStatus.jsx
(
echo export default function ServerStatus(^) {
echo   return ^<div className="server-status"^>Server Status^</div^>
echo }
) > frontend\src\components\ServerStatus.jsx

# Tạo CSS files
(
echo .terminal { background: #000; color: #00ff00; }
) > frontend\src\styles\Terminal.css

(
echo .keyboard { background: #111; }
) > frontend\src\styles\Keyboard.css

(
echo .server-status { background: #222; }
) > frontend\src\styles\ServerStatus.css

echo ✅ Xong! Tất cả files đã tạo!