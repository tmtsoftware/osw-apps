# TMT apps channel 

The apps.json file holds Application Discriptors for TMT applications which can be consumed using Coursier.
To use this discriptors, add the path of raw apps.json file as a channel as shown below.
```
cs launch --channel https://raw.githubusercontent.com/tmtsoftware/osw-apps/master/apps.json <app to launch>:<version|SHA>
```

A more convinient way would be to add apps.json file into the cousier channels. Execute the following commad to do so.
```
cs install --add-channel https://raw.githubusercontent.com/tmtsoftware/osw-apps/master/apps.json
```

After adding the channel, Cousier will look into saved channels to find the application descriptors whenever needed.
```
cs launch <app to launch>:<version|SHA>
```
