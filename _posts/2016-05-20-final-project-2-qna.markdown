---
published: true
title: Final Project 2: QnA
layout: post
---
![QnA app screenshots](http://drjackl.github.io/qna.png)

## The App
QnA is a social networking forum that allows users to sign up, log in, create a profile, ask questions, and suggest answers. It uses Firebase as a backend to persist all data except profile images, which uses Cloudinary.

**Skills:** dispatch_async, drawRect:(CGRect), UITableView, UICollectionView, Photos, CocoaPods (UICKeyChainStore, Firebase, Cloudinary)

## Architecture
There are 4 major components of this app:

1. Signup/Login
2. Profile (Viewing/Editing)
3. Questions
4. Answers

## Selected Details 
Each component has a corresponding ViewController (VC). Of note:

- QuestionsVC and AnswersVC each use a `UITableView` and each have cells (QuestionCell & AnswerCell) subclassed from a PostCell which is a `UITableViewCell`.
- A UserButton is the profile picture one taps on to bring up a Profile so it's always initialized with the Firebase reference for that user.
- The `DataSource` syncs Firebase with a list of questions and holds information about a user when logged in, including answers voted on.

## An Implementation Challenge: Answers
There's an `Answer` model object, but no Question object. This is because `Answer`s are more complex because I'm sorting by most voted on and at the time, I didn't realize I could query Firebase like that. The app observes this Firebase query and although a separate Answer is not needed anymore, there was no real incentive for refactoring it out.
