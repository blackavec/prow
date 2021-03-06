# Prow: Streamlined Kubernetes Development

_This project is experimental, and has not hit a stable release point_

Prow is a developer tool for creating cloud native applications for Kubernetes.

TL;DR

Start from your source code repository and let Prow transform it for
Kubernetes:

```
$ cd my-app
$ ls
app.py
$ prow new my-app --pack=python
--> Created ./charts/my-app
--> Created ./charts/my-app/Dockerfile
--> Ready to sail
```


Now start it up!

```
$ prow up
--> Building Dockerfile
--> Pushing my-app:latest
--> Deploying to Kubernetes
--> Ready at 10.21.77.7:8080
```

That's it! You're now running your Python app in a Kubernetes cluster.

Behind the scenes, Prow is handling the heavy lifting for you:

- It uses your existing Dockerfile, or creates one for you
- It builds a container image, and pushes it to a registry
- It creates a Helm chart for deploying into Kubernetes
- Using Helm, it deploys your release

From there, you can either let Prow continually rebuild your app, or you can
manually re-run Prow to update the existing app.

## Features

- Prow is language agnostic
- Prow will work with any Kubernetes cluster that supports Helm
- One it scaffolds your chart, you can leave the chart alone, or you can edit
  it to your specific needs.
- Charts can be packaged and delivered to your ops team

