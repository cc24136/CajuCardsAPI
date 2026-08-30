# CajuCards API

Backend API for the CajuCards multiplayer card game.

The project provides the REST API and real-time communication used by the CajuCards Flutter application, including user data, cards, match history, emotes, shop features, and online matches.

## Technologies

- Node.js
- Express.js
- Socket.IO
- PostgreSQL
- Supabase
- REST API

## Main Routes

All REST endpoints are available under:

`/api`

### Users

`/api/users`

Handles user profiles, account-related data, emotes, and player rewards.

Examples:

- `GET /api/users/me` — Get the current user's profile
- `PATCH /api/users/me` — Update the current user's profile
- `GET /api/users/me/emotes` — Get the user's emotes
- `POST /api/users/me/emotes` — Add an emote to the user
- `POST /api/users/me/claim-victory` — Claim a victory reward
- `GET /api/users/:id` — Get a user profile

Most user routes require authentication.

### Cards

`/api/cards`

Handles the cards available in the game.

- `GET /api/cards` — List all cards
- `GET /api/cards/:id` — Get a specific card
- `POST /api/cards` — Create a card
- `PATCH /api/cards/:id` — Update a card
- `DELETE /api/cards/:id` — Delete a card

Card creation, updates, and deletion are restricted to authenticated admin users.

### Match History

`/api/match-history`

Handles stored information about previous matches.

### Emotes

`/api/emotes`

Handles the emotes available to players.

### Shop

`/api/shop`

Handles shop-related game data and purchases.

## Multiplayer

Online matches use Socket.IO for real-time communication between players and the server.

The server manages active matches while the REST API handles persistent game and user information.

## Frontend

The Flutter application is available here:

[CajuCards](https://github.com/cc24136/CajuCards)
