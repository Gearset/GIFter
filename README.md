# GIFter

The GIF-to-Chatter app for Lightning Platform you didn't know you needed!

![image](https://user-images.githubusercontent.com/746259/36634388-9d7b0b9e-1958-11e8-83df-dfc65ace47b3.png)

## Get a GIPHY API Key

Fork this repo for your demo.

Go to [https://developers.giphy.com/](https://developers.giphy.com/) and create an new app. Grab the API Key and update the `apiKey` in `force-app/main/default/GIPHY.resource`.

## Install the Salesforce CLI

Run `npm install -g @salesforce/cli`

## Authorize your DevHub
```
sf org login web --set-default-dev-hub --alias MyDevHub
```

## Create an Unlocked Package

Create an Unlocked package:
```
sf package create --name "GIFter" --path force-app --package-type Unlocked
```

This will only take a moment, and you'll have the following output:

```
=== Ids
NAME                   VALUE
─────────────────────  ──────────────────
Package2 Id            0Ho6A0000004C9hSAE
Subscriber Package Id  0336A0000001JQ6QAM
```
Grab the `Package2 Id`.

Open the `sfdx-project.json` file and replace `YOUR_PACKAGE_ID` with the ID from above (e.g. `0Ho6A0000004C9hSAE`).

## Create an unlocked package version

Go to https://app.gearset.com/packaging and select your DevHub.

Click **Create new package version** and click **Next**.

Select this repo and branch and click **Next**.

Select all of the items in the comparison and click **Create unlocked package version**.

Enter the package details:
|Field|Value|
|-----|-----|
|Version name|ver 0.1|
|Version number|0.1.0.NEXT|
|Validation|Skip validation|
|Install key|test1234|

Click **Create package version**.

## Install package into a scratch org

Go to https://app.gearset.com/salesforce-connections and click **Create scratch org** on your Dev Hub.

Give the scratch org a name.

In **Install an unlocked package**, add your package version ID and install key from the previous step.

In **Assign permission sets**, enter `GIFter`.

Click **Create scratch org**.

## Open scratch org

Go to https://app.gearset.com/salesforce-connections and find your scratch org under your Dev Hub. Click **Log in**.

In the App Launcher, search `GIFter`. Once GIFter opens, run a search.

```

Enjoy!
