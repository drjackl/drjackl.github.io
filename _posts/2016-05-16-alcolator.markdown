---
published: true
title: Alcolator
layout: post
---
![Alcolator app screenshots](http://drjackl.github.io/alcolator.png)

## The App
This app calculates the equivalent drinks of wine or whiskey from beers. The user inputs the number of beers and alcoholic percentage. The number of drinks of wine or whiskey is displayed.

**Skills:** Storyboard, UIKit (UIButton, UILabel, UITextField, UISlider) 

## Details
A `MainMenuViewController` serves as the root view controller (VC) from which the user can choose WIne or Whiskey. Wine refers to `ViewController` and Whiskey refers to `WhiskeyViewController` which subclasses `ViewController` and overrides the `calculateAlcoholEquivalent` method.