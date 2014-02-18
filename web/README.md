Kickflip API Docs
=============

Documentation for the web Kickflip API.

## Setting up

Before you use the Kickflip API, you must first get your access tokens from the Kickflip dashboard.

## Authentication

Kickflip uses OAuth2 as an authentication protocol.

Whatever OAuth2 library that you're using should be smart enough to understand what it needs to do simply by pointing it
to

    https://app.kickflip.io/o/

as the appropriate OAuth2 endpoint.

## Users

All Kickflip streams must be started by Kickflip users. Users are necessary to make sure that people cannot overwrite
each other . Users can be ephemeral, and clients can create new users as much as they like. However, in most situations
a single user per client will suffice.

To create a new user, call

    https://app.kickflip.io/new/user/

You can also POST an optional **username** to define a username, otherwise one will be randomly generated.

Note that all responses will be in JSON format.

## Streams

Kickflip streams

### Starting a new Stream

Kickflip clients must call the start stream endpoint in order to get the most recent access tokens and the instructions
for the stream parameters.

To start a stream, first call:

    https://app.kickflip.io/stream/start/

supplying the user's **uuid**, as well as an optional **lat** and **lon** for geo-coded streams, and an optional
**private** for private streams.

### Pausing

    https://app.kickflip.io/stream/pause/

### Resuming
    https://app.kickflip.io/stream/resume/

### Stopping
    https://app.kickflip.io/stream/stop/