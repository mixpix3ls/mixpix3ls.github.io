---
layout: post
title:  "Create a Virtual Machine in Google Cloud Platform (Part 1)"
date:   2019-05-13
categories: Cloud
---

# Introduction

Google Cloud Platform (GCP) is a cloud computing platform offered by Google containing many services spanning infrastructure-as-a-service (IaaS), platform-as-a-service (PaaS) and software-as-a-service (SaaS). This enabled workloads of varying complexity to run on GCP, from static websites to sophisticated applications using managed databases and serverless technology.

In this tutorial, you will execute the steps required to create a Linux Virtual Machine (VM) in GCP using the Google Cloud Console. You will then log in to that VM, install the Nginx web server and expose the VM to the internet.

# Prequisites

* A Google account
* Access to the [Google Cloud Console]

# Google Cloud Console

## Project settings

1. To get started, log in to the [Google Cloud Console]
2. Click on the *Select a project* drop-down menu and click `NEW PROJECT`
3. On the *New Project* screen, under **Project name** enter `vmdemo` and under  **Location** select `No organization`
4. Click on the *Select a project* drop-down menu, choose `vmdemo` and click *Open*

## Create a VM


1. Click on the search field in the banner (look for the magnifying glass icon), type `Virtual Machines` and choose *Instances - Compute Engine*
2. On the *VM instances* page, click `Create`
3. Enter the following details on the *Create an instance* page:
	* **Name**: `instance1`
	* **Region**: `us-central1 (Iowa)`
	* **Zone**: `us-central1-c`
	* **Machine type**: `micro` (1 shared vCPU | .6 GB memory | f1.micro)
	* **Boot disk**: `New 10 GB standard persistent disk`
	  * **Image**: `Debian GNU/Linux 9 (stretch)`
	* **Identity and API access**: 
	  * **Service account**: `Compute Engine default service account`
	  * **Access scopes**: `Allow default access`
	* **Firewall**: Select `Allow HTTP traffic`
	* Skip all the other settings (use defaults for them)
4. Scroll to the bottom of the page and click `Create`

## Verify VM creation

1. One the *Compute Engine > VM instances* page, verify that the VM that you created in the last section is present with a green check
2. Click on the `SSH` button for your VM (do not click the drop-down)

You should now be in a separate browser window with a Shell on your VM!


[Google Cloud Console]: https://console.cloud.google.com

