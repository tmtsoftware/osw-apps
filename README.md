# TMT apps channel

The apps.json file holds Application Descriptors for TMT applications which can be consumed using Coursier.
To use these descriptors, add the path of raw apps.json file as a channel as shown below.

```bash
cs launch --channel https://raw.githubusercontent.com/tmtsoftware/osw-apps/master/apps.json <app to launch>:<version|SHA>
```

A more convenient way would be to add apps.json file into the cousier channels. Execute the following command to do so.

```bash
cs install --add-channel https://raw.githubusercontent.com/tmtsoftware/osw-apps/master/apps.json
```

After adding the channel, Cousier will look into saved channels to find the application descriptors whenever needed.

```bash
cs launch <app to launch>:<version|SHA>
```
