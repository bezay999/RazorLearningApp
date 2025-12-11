# RoomBookingApp — C# Razor Pages Project

This is a C# Razor Pages web application that displays information about a meeting or training room, including its name, type, capacity, amenities, available time slots, and booking confirmations. The app also dynamically shows the current date and time and checks room availability based on the current hour.

## Features

- Display room details (name, type, capacity, projector availability)
- Show the current date and time dynamically
- Check room availability based on the current hour
- Use `@switch` to display room type
- List amenities and equipment
- Display available time slots using a `@for` loop
- Generate booking confirmations using a `@while` loop
- Conditional rendering based on projector availability

## Code Highlights

```cshtml
@page
@model IndexModel
@{
    string roomName = "Conference room A";
    string roomType = "training";
    int capacity = 12;
    bool hasProjector = true;
    string date = DateTime.Now.ToString("MMMM dd, yyyy - hh:mm tt");
    int currentHour = DateTime.Now.Hour;
    List<string> amenities = new List<string> {"Whiteboard", "Projector", "Conference Phone", "WiFi"};
    int startHour = 9;
    int endHour = 17;
    int confirmationNumber = 1001;
    int totalSlots = 8;
    int count = 0;
    List<string> equipment = new List<string>() {"Laptop", "HDMI Cables", "Remote Control", "Microphone"};
}
<h1>@roomName</h1>
<p>@date</p>
<p>Capacity: @capacity</p>
<p>Has projector: @hasProjector</p>

@if (currentHour >= 9 && currentHour <= 17)
{
    <h3>Room is available for booking</h3>
}
else if (currentHour >= 18 && currentHour <= 20)
{
    <h3>Room available for after-hours booking (additional fees apply)</h3>
}
else
{
    <h3>Room is closed</h3>
}
```
### How to Run
	
  1.	Make sure you have .NET 6.0+ SDK installed.
	2.	Navigate to the project folder in terminal.
	3.	Run the project.
	4.	Open your browser and go to the URL displayed in the console (e.g., https://localhost:5001).

Purpose

This project demonstrates:
	•	Razor Pages in ASP.NET Core
	•	Using C# variables, loops (@for, @while), and conditionals (@if, @switch) in views
	•	Dynamically rendering content based on runtime data
	•	Basic web application structure in ASP.NET Core
