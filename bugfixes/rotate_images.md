# Rotate Images

## Open your cloud shell

Open your devshell 


<walkthrough-spotlight-pointer spotlightId="devshell-activate-button"
                               text="Open Cloud Shell">
</walkthrough-spotlight-pointer>


**Time to complete**: About 60 minutes; Most of it is just waiting

**Prerequisites**: A GCP account

Click the **Continue** button to move to the next step.


## Make a directory for the images
First we make a space to copy the images into
```bash
cd /temp
mkdir images

```

## Get the images
Then we pull them all down
```bash 
gsutil -m  cp -r gs://grownome.appspot.com/images/ ./images 

```

## Rotate them
Install imagemagick for this cloud shell session.
```bash
sudo apt-get install imagemagick -q

```
**imagemagick will not be there next time your start, the cloud shell can be customized though**
Find all of the images you downloaded then rotate them with magick.
```bash
find ./images -print| xargs -I{}  magick {}  -rotate "90>" {} 
```
**xargs takes the output of the previous command and uses each line as the argument to another**

## Push them back up
Then we pull them all down
```bash 
gsutil -m  cp -r  ./images  gs://grownome.appspot.com/images/
```

## Great Job
You did some operations. Great job.

<walkthrough-conclusion-trophy></walkthrough-conclusion-trophy

