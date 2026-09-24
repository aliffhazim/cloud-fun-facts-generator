# Amplify Frontend Plan

## Stack
React (via Amplify Hosting)

## Pages
- Single page app, one screen

## UI Elements
- Title: "☁️ Cloud Fun Facts Generator"
- Big button: "Give me a fact"
- Toggle: "Make it witty ✨" (calls witty=true)
- Fact display card (fades in on new fact)

## State
- loading (while waiting on API Gateway call)
- currentFact
- wittyMode (boolean)

## API Call
- GET request to API Gateway /fact endpoint, includes witty param if toggled
