# ![GA Logo](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Auth Research Lab

---

Authentication is a complex and exciting topic that involves using many of the concepts we've already studied as well as several new ideas. 

An authentication system allows the registration / signup of new users and allows those users to sign in. It has to be able to identify each user and keep their information private and secure.

Being able to develop secure user login systems is in fact a whole career and life path in and of itself, but understanding the broad concepts of **Auth** is critically import for all developers. 

Describing auth flow and understanding key terms are very common **interview questions** for junior developers, so lets take some time to research and understand auth and the related concepts.

## Setup

Fork and clone this repository and answer the questions as you research directly in the README. You do not have to pull request and submit this lab, but you will want to have it on hand for reference in the future. 

## Auth Concepts Worksheet

#### Define the following

1. *Authentication*
    * The purpose of authentication is to verify that someone or something is who or what they claim to be.
2. *Authorization*
    * Authorization is the security process that determines a user or service's level of access.
3. Explain how *authentication* and *authorization* are related but distinct concepts.
    * Authentication and authorization are similar in that they are two parts of the underlying process that provides access. Consequently, the two terms are often confused in information security as they share the same "auth" abbreviation. Authentication and authorization are also similar in the way they both leverage identity. For example, one verifies an identity before granting access, while the other uses this verified identity to control access.
4. *Sessions vs Token based auth*
    * The session method makes the server store most of the details (cookies), while in the case of the token-based one the client stores them(JSON web tokens).
    * How Session Authentication Works
        * You attempt to log in using your credentials.
        * Your login credentials are verified, and the server creates a session with a session ID for you. This session is stored in the database.
        * Your session ID is stored in your browser (client) as a cookie.
        * Upon subsequent requests, your cookie is verified against the session ID stored in the server. If it’s a match, the request is considered valid and processed.
        * If you log out of an application, the session ID is destroyed on both the client and server sides.

    * How Token Authentication Works
        * You attempt to log in using your user credentials.
        * The server verifies your credentials, and if valid, it returns a signed token.
        * The signed token is then stored on the client-side. It can either be stored in your local storage, in your session storage, or within a cookie.
        * The token is placed in the header for subsequent requests to your server as an “authorization header”. The server then decodes the token in the header and processes it if it is valid.
        * If you log out from an application, the token is deleted from the client-side, preventing further interactions.	

5. *json web token (also know as a jwt)*
    * A JWT is essentially a JSON-encoded representation of a claim, which may be transferred between two entities. The claim is signed digitally by the token’s issuer. The recipient party of this token may use this digital signature to demonstrate ownership in the future. 
        * This token is made up of three components:
            * A header that specifies the algorithm used to encrypt the contents of the token
            * A payload that contains “claims” (information the token securely transmits)
            * A signature that can be used to verify the authenticity of the information.

6. *Encoding, encryption and hashing* along with the uses for and differences between the three
    * -encoding: conversion of data from one format to another.  This does not make the data a secret. The encoded data can be decoded back to its original format. Encoding ensures the integrity and usability of data.
        * Encoding uses:. when data cannot be transferred in its current format between systems or applications. Note: encoding is NOT used to protect or secure data because it is easy to reverse.

    * - encryption:  Encryption is the process of securely encoding data in such a way that only authorized users with a key or password can decrypt the data to reveal the original
        * encryption uses: when data needs to be protected so those without the decryption keys cannot access the original data. 
    
    * - Hashing - Hashing is a one-way process where data is transformed into a fixed length alphanumeric string. This string is known as a hash or message digest. A hash cannot be reversed back to the original data because it is a one-way operation
        * - hash uses: (1) verifying the integrity of data (known as a “check sum”), i.e. if two pieces of identical data are hased using the same hash function, the resulting hash will be identical
        * 2) hashing is the used as a data transformation technique in qutheication processes for computer systems and applications, i.e. instead of storing a password, simply store the hash of the “salted password.” A salt is a random string appended to a password that only the authentication process system knows which guarantees that if two users have teh same password, the stored hashes are still different
7. *oAuth* (pronounced oh-Auth)
    * OAuth is a standard that apps can use to provide client applications with “secure delegated access”. OAuth works over HTTPS and authorizes devices, APIs, servers, and applications with access tokens rather than credentials.

#### Explore and then describe the following npm packages:

1. [bcrypt](https://www.npmjs.com/package/bcrypt)
    * A library to help you hash passwords. Besides incorporating a salt to protect against rainbow table attacks, bcrypt is an adaptive function: over time, the iteration count can be increased to make it slower, so it remains resistant to brute-force search attacks even with increasing computation power.
2. [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)
    * JWT, or JSON Web Token, is an open standard used to share security information between two parties — a client and a server. Each JWT contains encoded JSON objects, including a set of claims. JWTs are signed using a cryptographic algorithm to ensure that the claims cannot be altered after the token is issued.
3. [passport](https://www.npmjs.com/package/passport)
    * also describe what a *strategy* is in the context of this npm package
        * Used to authenticate requests
        * Passport is Express-compatible authentication middleware for Node.js.
        * Passport's sole purpose is to authenticate requests, which it does through an extensible set of plugins known as strategies. Passport does not mount routes or assume any particular database schema, which maximizes flexibility and allows application-level decisions to be made by the developer. The API is simple: you provide Passport a request to authenticate, and Passport provides hooks for controlling what occurs when authentication succeeds or fails.


---

## Licensing
1. All content is licensed under a CC-BY-NC-SA 4.0 license.
2. All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.