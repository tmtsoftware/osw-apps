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

## Potential issue with osw-apps

The Coursier cache for channel URLs gets out of date (The content of apps.json is cached under ~/.cache/coursier (~/Library/Application Support/Coursier/channels on Mac) and not updated to reflect any changes made there during development). Solution: 
```
\rm -rf  ~/.cache/coursier/v1/https/raw.githubusercontent.com/tmtsoftware/osw-apps/, then rerun/rebuild
```

There is a potential problem with ocs-apps: Previous versions of TMT projects use this command to start apps:

```
cs launch --channel https://raw.githubusercontent.com/tmtsoftware/osw-apps/master/apps.json ...
```

The latest versions now use a different branch:
```
cs launch --channel https://raw.githubusercontent.com/tmtsoftware/osw-apps/branch-6.0.x/apps.json ...
```

If we update the master branch of osw-apps for scala3/pekko, etc., it will break previous versions of csw, esw and other projects (both at build and runtime).

So, don't update the master branch.
