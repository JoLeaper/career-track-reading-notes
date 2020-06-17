# Class 12 Reading: Bcrypt and JWT

## Previous Solutions To Password Solutions
- Plain Text: Makes use of only letters. Dangerous because if a hacker gets access to these passwords, the userbase is in danger (which may give the hacker access to other sites).
- One Way Hash: A one way hash is used to scramble a password using a hashing algorithm. Hackers have found a way around the system: continiously guess passwords until they gain access.
- 'Salting' The Password: 'Salting' a password is adding a long string of bytes to the password, making guess very unlikely. But if the source code is leaked, a hacker could find the 'salt.'
- 'Random Salt' Passwords: Each instance of 'salting' is random generated. So while similar to the previous solution, there is no set salt string. This stalls hackers, but they can still access your data with enough time.

## BCrypt
- Slows down the hashing speed in hackers, to the point where it is no longer a viable strategy.
- A Key Factor allows BCrypt is able to adjust cost of hashing.