---
layout: projects
title: Road Map
permalink: /roadmap/
---

Planned, upcoming, and proposed features for the FeedHenry project.

<div class="project-title" markdown="1">

## Current Roadmap

Here are our current plans: their JIRAs, documentation, and relevant discussions.

</div>

<div class="project-text" markdown="1">

</div>



<div class="project-title" markdown="1">

##  Proposals

These are ideas, features, etc that are still being reviewing, fleshed out, planned, scheduled, etc.

</div>

<div class="project-text" markdown="1">


### Extract the Sync Client into a library that the RHMAP SDK uses


The library should be in the feedhenry Github organisation https://github.com/feedhenry 
There should be an Open Source license for the library
The naming convention for the library is ‘fh-sync-<platform>’ e.g. ‘fh-sync-android’, ‘fh-sync-js’, ‘fh-sync-ios’, ‘fh-sync-dotnet’
The RHMAP SDK library will need to be re-published to the relevant repository e.g. NPM for JS, Maven for Android.


### Modify the Sync Client to remove the dependency on the RHMAP SDK

There are 3 parts to this change:
* Sync calls will not require any RHMAP SDK classes directly. This will allow the Sync Client to be used standalone. Examples of how to do this technically.
The Sync Client could make its own direct calls to the Cloud App. However, thought needs to be given to any extra headers or params that the sdk usually includes in cloud calls.
Dependency injection sounds like a valid option too, where an implementation of well known interface is passed into the Sync Client.
The Sync Client can be told about where the Sync Server is programmatically (or via well known configuration patterns). For example, when initialising the Sync Client, you can pass in the server url. This change will remove the dependency on having an fhconfig.properties (or similar) file.
Sync Clients depend on a storage client provided by the SDK. This is at least the case in the js sdk.


### Update RHMAP Client App templates to use the RHMAP SDK with the extracted Sync Client

Identify any Client App Templates for the Sync Client being extracted. The list of templates is maintained at https://github.com/feedhenry/fh-template-apps/blob/master/global.json 
Update the RHMAP SDK version being used in each template to the latest version using the separate Sync library


### Add a sync getting started guide to feedhenry.org

The guide should give an end to end example of getting a standalone App running with the Sync Client, talking to a standalone Node.js application running the Sync Server



### Add an example Sync client App & Server to github, based off the Getting Started Guide

These examples should work ‘out of the box’, and ‘locally’, without any RHMAP dependency
Little or no configuration should be required to get the examples working



### Add all Sync documentation to feedhenry.org

Work with the docs team (Paul Wright) to identify an upstream/downstream process for having all sync docs available on feedhenry.org, and also included in the RH Customer Portal. There are ~10 sync docs

### Promisify/Rxify the API (client and server)

### Server Side typings

Expand the client polling support to have better platform integration (IE integrate with Android's sync scheduling so we get preferred treatment under Marshmallow's new power saving model and O's super ### agressive model)

### Maybe have some code for sending push notifications to wake up an app that needs to sync as well?

### Improve test coverage and begin to get performance metrics on the native clients.

I would love for a true Javascript client library. IE Something that doesn't need to be run in a web ### browser.

We could proof it by writing a simple UWP (Windows Desktop) app, Fedora desktop app (yay company cross promotion) etc, React Native mobile app, etc.

### How about TypeScript? We should definitely include definitions if we don't do it as purely TypeScript.

### Modify sync-acceptance-testing repo to work with the standalone sync client & server


</div>


