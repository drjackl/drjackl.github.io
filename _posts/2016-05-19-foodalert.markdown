---
published: true
title: FoodAlert
layout: post
---
![FoodAlert app screenshots](http://drjackl.github.io/foodalert.png)

### The App
FoodAlert is a personal locations repository. A user can search for places, save places, create categories for these places, add notes, and be notified when the user comes within range (half a mile) of a place.

**Frameworks/Classes Used:** MapKit (MKLocalSearch, MKAnnotationView), CoreLocation, UILocalNotification, UISearchBarDelegate, NSXMLParserDelegate, NSCoding, UITableView

### Architecture
- The CoinViewController maintains and flips between the two main ViewControllers (VC) of this app: the MapVC and the ListTableVC.
- A SearchVC appears on top of these views when the user wants to search.
- A CalloutVC gets displayed on the map whenever the user selects a map item.
- Categories are selected and added through a custom modal controller.

### Selected Details
- `Spot` is the model object representing a place or location. 
- The `DataSource` always tracks an array of savedSpots, from which the user can add and delete.
- savedSpots is never used directly to present Spots because we allow the user to filter by Category; as a result, savedSpotsBeingShown always tracks what is visible to the user.
- SearchVC parses XML from Google Suggest API and updates as user types.
- The app reuses the CategorySelectVC custom modal both to select a Category for a Spot and to filter current saved Spots being shown.

### Implementation Challenges: Nearby Notifications
![FoodAlert notification](http://drjackl.github.io/foodalert-notifcation.png)
This app uses region monitoring to notify the user when nearing a saved Spot. There are several challenges:

- `CLRegion`'s identifier is the only place to customize a region so I encoded the Spot name here so that notifications could present the nearby Spot's name (as opposed to coordinates).
- Apple documentation specifies that a `UILocalNotification` must either have a region or date set. Since entering is triggered by CoreLocation's `didEnterRegion:` delegate method, notifications should not have a region set or else the notification gets delayed until the next region event (which would be when the user exits the event)
- Since regions are a shared resource among other apps too, the array of Spots being monitored is refreshed periodically based on Spots closest to current location.