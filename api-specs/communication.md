# API Communication Methods

## 1. Synchronous (Instant)
- Your app sends a request
- Waits for the server's reply
- Used for 90% of features (login, posts, etc.)
- Example: Loading a list of communities

## 2. Asynchronous (Background)
- Your app asks for updates
- Server sends updates when ready
- Used for: New notifications, live post updates
- Example: Seeing new likes on your post

## Main Differences

- **Synchronous**: Like a phone call (immediate response)

- **Asynchronous**: Like texting (reply comes later)