---
title: CorBus - Coming Soon
excerpt:  ![CorBus](http://i.imgur.com/t3esSPS.png) This app was first created as a submission for the OSU Corvallis Bus Hackathon by myself and [Russell Barnes](https://www.linkedin.com/profile/view?id=263525323). The hackathon consisted of around 8 hours of coding. We started out with using the iOS Google Maps SDK because the format of the bus route lines was made using Google's [Polyline Encoding Algorithm](https://developers.google.com/maps/documentation/utilities/polylinealgorithm). Our initial idea involved using a blurred street view in the background of each stop in a list of table view cells, but this ended up looking awful (not to mention the blurring obscured Google's logo/legal links, which is not allowed). Instead, we ended up using solid backgrounds based on the various bus lines' bus colors, and it turned out fairly well. We ended up winning *Best Overall App* at the hackathon.
layout: generic
---

![CorBus](http://i.imgur.com/t3esSPS.png)

This app was first created as a submission for the OSU Corvallis Bus Hackathon by myself and [Russell Barnes](https://www.linkedin.com/profile/view?id=263525323). The hackathon consisted of around 8 hours of coding. We started out with using the iOS Google Maps SDK because the format of the bus route lines was made using Google's [Polyline Encoding Algorithm](https://developers.google.com/maps/documentation/utilities/polylinealgorithm). Our initial idea involved using a blurred street view in the background of each stop in a list of table view cells, but this ended up looking awful (not to mention the blurring obscured Google's logo/legal links, which is not allowed). Instead, we ended up using solid backgrounds based on the various bus lines' bus colors, and it turned out fairly well. We ended up winning *Best Overall App* at the hackathon.

![CorBus at the OSU Corvallis Bus Hackathon](http://i.imgur.com/WMQrlXu.png)

The above image shows what the app looked like when we presented it at the end of the hackathon.It is a list of bus stops near the current location of the user sorted by distance. The user can tap on the table view cell to expand the map to a full screen view. At that point, the app was called "The Corvallis Bus App." At the end of the hackathon, however, we knew that the app was nowhere near complete. Soon enough, however, school took over as a priority.

Some of my classmates at OSU had been planning an "App Challenge" competition that ended on May 10th. Russell and I decided to polish up our bus app for the competition. One of our first changes was the change of the app's name from "The Corvallis Bus App" to "CorBus." Oddly enough, "The Corvallis Bus App" didn't seem to fit as an App Name below its icon on iOS, so we made some compromises. Next, we replaced Google Maps with Apple Maps. Google Maps' performance seemed pretty subpar, so after testing Apple Maps as an alternative on a seperate git branch, we quickly came to like it more than the Google counterpart. There were some disappointments involved with the switch, however.

Firstly, Apple Maps does not have any data for 3D buildings in Corvallis. The close-up Google Maps view of a particular stop was pretty awesome due to the 3D buildings that were rendered nearby. Secondly, Google's map markers also allowed custom colors, which made theming the markers with the color of the particular bus route fairly easy. Apple's default `MKPinAnnotationView` only comes in 3 varieties, so we had to create a custom annotation view for the stops. Finally, after finding a way to translate Google's Encrypted Polyline Algorithm to use with Apple Maps, though we were able to display the polyline correctly, Apple's maps has issues with displaying the polyline at an angle. Instead of a smooth line into the distance, Apple Maps renders polylines at different fixed widths based on distance to the camera. This means that at a certain point, the polyline gets fatter with no smooth transition.

![Apple Maps' polyline rendering at an angle](http://i.imgur.com/Zuh08Rq.png)

Despite these concerns, however, Apple Maps still had better performance overall, so we stuck with it. After talking with some people about the App, we found that the most requested feature that we didn't yet have was some kind of overall list of routes, so we incorporated a list of routes into the app. The list of routes can easily be revealed by swiping the main interface to the left.

![The OSU App Challenge build of CorBus](http://i.imgur.com/vUlPlV7.png)

The above is an image of what the app looked like when we were demoing it during the OSU App Challenge. There were two things that bugged me, however. Our main screen didn't have an indication as to what route a listed stop was part of other than the color, and the custom bus stop icons that we made seemed blurry no matter what we tried to do. After winning the award for [Best Usability](http://blogs.oregonstate.edu/eecsnews/2014/05/15/teamwork-takes-app-challenge-new-level/) at the OSU App Challenge, I figured out a way to kill two birds with one stone. I changed the bus stop icons to simply be `UILabel`s that showed the route number. After making some other optimizations and creating some annotated screenshots, I just submitted the App to the App Store. Average review time as of today is 4 days, and I'm hoping for the best.

![CorBus 1.0](http://i.imgur.com/1UEpZfD.png)