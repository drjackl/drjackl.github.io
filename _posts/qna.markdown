---
published: false
title: QnA
layout: post
---
# Summary
QnA is a social networking forum that allows users to sign up, log in, create a profile, ask questions, and suggest answers. It uses Firebase as a backend to persist data and Cloudinary to store images for profiles.

<screenshots>

# Architectural Overview
There are 4 major components of this app, both on the frontend and backend:
1. Signup/Login
2. Profile (Viewing/Editing)
3. Questions
4. Answers

1. Signup/Login
Signup and Login fairly simple Each have their respective ViewController (VC) though they are similar with the standard two text fields for username and password.

Of note is that logging in saves an access token in Keychain so the user doesn't have to log in anymore after. The app uses this access token to stamp the user on any posts made or changes to their profile