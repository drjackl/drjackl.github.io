---
published: false
title: FoodAlert
layout: post
---
### The App
FoodAlert is a personal locations repository. A user can search for places, save places, create categories for these places, add notes, and be notified when the user comes within range (half a mile) of a place.

**Frameworks/Classes Used:** NSCoding

### Architecture
- The CoinViewController maintains and flips between the two main ViewControllers (VC) of this app: the MapVC and the ListTableVC.
- A SearchVC gets displayed on top of these views when the user wants to search.
- A CalloutVC gets displayed on the map whenever the user selects a map item.
- Categories are selected and added through a custom modal controller