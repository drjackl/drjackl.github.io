---
published: false
title: Picstagram
layout: post
---
## The App
This app replicates Instagram using Instagram's own API and feeds. Users can scroll through their own feed, view pictures full-screen, crop and add photo filters, and add comments.

**Skills:** No storyboard, UITableView, UICollectionView, Key-Value Observing, NSNotificationCenter, CocoaPods (UICKeyChainStore, AFNetworking)

## Architecture
Once logged in, the main feed is loaded into the root view controller (VC) `ImagesTableViewController`. Here, the user can Like things and add comments tapping on the `ComposeCommentView`. The user can start a workflow to post an image with a cool filter by tapping the camera button: `ImageLibraryVC` --> `CropImageVC` --> `PostToInstagramVC`.

The `DataSource` maintains an array of `Media` items which represents the feed. Each `Media` contains various properties including the authoring `User` and an array of `Comment`s.



