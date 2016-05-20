---
published: false
title: FoodAlert
layout: post
---
### The App
FoodAlert is a personal locations repository. A user can search for places, save places, create categories for these places, add notes, and be notified when the user comes within range (half a mile) of a place.

**Frameworks/Classes Used:** MapKit, CoreLocation, UILocalNotification, UISearchBarDelegate, NSXMLParserDelegate, NSCoding, UITableView

### Architecture
- The CoinViewController maintains and flips between the two main ViewControllers (VC) of this app: the MapVC and the ListTableVC.
- A SearchVC appears on top of these views when the user wants to search.
- A CalloutVC gets displayed on the map whenever the user selects a map item.
- Categories are selected and added through a custom modal controller.

### Selected Details
- Spot is the model object representing a place or location. 
- The DataSource always tracks an array of savedSpots, from which the user can add and delete.
- savedSpots is never used directly to present Spots because we allow the user to filter by Category; as a result, savedSpotsBeingShown always tracks what is visible to the user.
- SearchVC parses XML from Google Suggest API and updates as user types.
- The app reuses the CategorySelectVC custom modal both to select a Category for a Spot and to filter current saved Spots being shown.

### An Implementation Challenge: Persisting Data