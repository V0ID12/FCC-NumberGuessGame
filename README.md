# Number Guessing Game

A terminal number guessing game written in Bash that remembers every player in a PostgreSQL database.

## How it works

1. The script asks for a username.
2. A new player is welcomed and added to the database. A returning player is told how many games they have played and their best score.
3. The script picks a secret number between 1 and 1000 and gives a hint after each guess until the player gets it.
4. Anything that is not a whole number is rejected with a prompt to try again.
5. The finished game is saved with the number of guesses it took.

## Database

Two tables in a `number_guess` database:

- `players`: `user_id`, `username`
- `games`: `game_id`, `user_id`, `number_of_guesses`, `secret_number`

## Files

- `number_guess.sh`: the game.
- `number_guess.sql`: a dump that rebuilds the database.

## Running it

Requires PostgreSQL with a `freecodecamp` user, which is how the course environment is set up.

```bash
psql -U postgres < number_guess.sql
```

```bash
./number_guess.sh
```

## Background

One of the five required projects for freeCodeCamp's Relational Database certification.
