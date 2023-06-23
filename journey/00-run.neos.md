<walkthrough-metadata>
  <meta name="title" content="Deploy to Cloud Run after building a container from source." />
  <meta name="description" content="Learn how to build, containerize, store and deploy a container image to Google Cloud Run." />
  <meta name="component_id" content="1053799" />
  <meta name="keywords" content="deploy, containers, console, run" />
  <meta name="short_id" content="true" />
</walkthrough-metadata>

# Deploy to Cloud Run after building a container from source.

## ![Cloud Run Logo][intro image]

In this tutorial we'll learn how to remotely build a container image from source code, store the image in Artifact Registry and deploy it to Cloud Run. After that, we'll familiarize ourselves with the Cloud Run UI, it's API and explore some of the avaliable options to tweak our service.

<walkthrough-tutorial-difficulty difficulty="2"></walkthrough-tutorial-difficulty>

Estimated time:
<walkthrough-tutorial-duration duration="15"></walkthrough-tutorial-duration>

To get started, click **Start**.

[intro image]: https://walkthroughs.googleusercontent.com/content/images/run.png

## Project setup

First, let's make sure we got the correct project selected. Go ahead and select the provided project ID.

<walkthrough-project-setup billing="true"></walkthrough-project-setup>

<walkthrough-enable-apis apis="cloudbuild.googleapis.com,
run.googleapis.com,
artifactregistry.googleapis.com">
</walkthrough-enable-apis>

## Exploring the code

Take some time and 
<walkthrough-editor-open-file filePath="cloudshell_open/serverless/container/main.go">
familiarize yourself with the code
</walkthrough-editor-open-file>
in `container/`.

Also have a look at the dependencies reference in the GO module. You can navigate to it's [upstream repository](https://github.com/helloworlddan/tortune) to figure out what it does.

Once you've understood what's going on, you can try to run that app directly in Cloud Shell, running the following in the terminal:

```bash
go run main.go
```

This compiles and starts the web server. You can now use Cloud Shell Web Preview on port 8080 to check out your application. You can find the Web Preview at the top right in Cloud Shell.

<walkthrough-editor-pointer cssSelector="[id$=web-preview-button]">Web Preview</walkthrough-editor-pointer>

## Building and deploying the code

