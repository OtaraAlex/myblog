---
title: What is a JWT and how to generate one
slug: generate-a-random-jwt-secret
summary: Store information in an easy-to-access manner, both for developers and computers using a JWT.
description: 
date: 2023-12-13T20:02:27+03:00
categories: []
tags: [JSON Web Tokens]
draft: false
---

JWT is becoming more popular for securing APIs. But what is JWT exactly? And how does it work?

## What is a JWT?
JWT or JSON Web Token is an open standard, [RFC 7519](https://datatracker.ietf.org/doc/html/rfc7519), used to share security information between two parties — a client and a server. 

Each JWT contains encoded JSON objects, including a set of claims. JWTs are signed using a cryptographic algorithm to ensure that the claims cannot be altered after the token is issued.

#### What is JSON?
JSON stands for JavaScript Object Notation and is a text-based format for transmitting data across web applications.

It stores information in an easy-to-access manner, both for developers and computers. It can be used as a data format by any programming language and is quickly becoming the preferred syntax for APIs, surpassing [XML](https://aws.amazon.com/what-is/xml/#:~:text=Extensible%20Markup%20Language%20(XML)%20lets,%2C%20and%20third%2Dparty%20applications.).

#### What are Tokens?
A token is a string of data that represents something else, such as an identity.

### When to use JSON Web Tokens?
Here are some scenarios where JSON Web Tokens are useful:

1. #### Authorization

   This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

2. #### Information Exchange

   JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

## How to generate a JWT
Run this script on the terminal:

``````javascript
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
``````

This script will generate a random 64 bit [ASCII](https://en.wikipedia.org/wiki/ASCII) string

Let’s dive in a little deeper:

- `node -e` tells Node.js to evaluate a script, in this case, a Javascript string.
- `crypto` is the cryptographic module forming part of Node.js core. It is already installed as part of Node.js, no extra npm package is involved.
- `randomBytes()` is a function that generates cryptographically strong pseudo-random data. It will return a Buffer object.
- `toString()` is a method of the Buffer class that decodes the object to a string according to the specified character encoding, which, in this case, is `hex`, viz. hexadecimal.

Each of the 64 characters can be:

* A numbers from 0 to 9
* A character: A, B, C, D, E and F

There are codes in the ASCII table that will not be used, but the random results are perfect for JWT tokens nevertheless.