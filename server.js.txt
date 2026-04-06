// Import express
const express = require('express');

// Create app
const app = express();

// Define port
const PORT = process.env.PORT || 3000;

// Middleware
app.use(express.json());

// Routes
app.get('/', (req, res) => {
    res.send('🚀 Welcome to Sample Node.js App!');
});

app.get('/api/health', (req, res) => {
    res.json({
        status: 'OK',
        uptime: process.uptime(),
        timestamp: new Date()
    });
});

app.post('/api/data', (req, res) => {
    const data = req.body;

    res.json({
        message: 'Data received successfully',
        data: data
    });
});

// Start server
app.listen(PORT, () => {
    console.log(`Server running on http://localhost:${PORT}`);
});
