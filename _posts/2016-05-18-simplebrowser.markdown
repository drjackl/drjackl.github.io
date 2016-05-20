---
published: true
title: SimpleBrowser
layout: post
---
![SimpleBrowser app screenshots](http://drjackl.github.io/simplebrowser.png)

## The App
SimpleBrowser is a privacy-oriented web browser with a draggable navigation toolbar.

**Skills:** No storyboard, WebKit (WKNavigationDelegate), UIGestureRecognizer (Tap, Pan, Pinch, LongPress)

## Details
The main `ViewController` has a text field for the url and the rest below is the web view. The privacy-oriented part kicks in when the app resigns the active state at which point the browser is cleared. A `FloatingToolbar` view is a four movable a button panel for commands: back, forward, refresh, stop. The toolbar may also be moved (Pan), resized (Pinch), and rearranged (LongPress).