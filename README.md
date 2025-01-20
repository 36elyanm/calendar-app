const express = require("express");
const cors = require("cors");
const bodyParser = require("body-parser");

const app = express();
app.use(cors());
app.use(bodyParser.json());

let events = []; // Temporary storage for events

// Get all events
app.get("/events", (req, res) => {
  res.json(events);
});

// Add a new event
app.post("/events", (req, res) => {
  const event = req.body;
  events.push(event);
  res.status(201).json({ message: "Event added" });
});
npm start
npm start

// Start the server
const PORT = 5000;
app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
