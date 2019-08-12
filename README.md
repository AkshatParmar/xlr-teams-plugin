# XL Release Microsoft Teams Plugin


## Preface
This document describes the functionality provided by the 'xlr-msteams-plugin'

## Overview
This plugin provides a notification task to send *Teams* messages to channels or direct messages.
Based of Incoming Webhooks integration connector, which provides a URL within an authorization token to **POST** messages using a **JSON** payload.
Check out [Teams Incoming Webhooks](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors-using) documentation for background information on how to add Connectors to post messages from external sources into Teams 

## Installation
- Clone the repository and run ```./gradlew build``` to build the JAR file.
- Copy the plugin JAR fole into the *'SERVER_HOME/plugins'* directory of XL Release.

## Configuration
This configuration allows you to connect to a server.
Before setting up a notification task it is **required** to setup an MSTeams server defintion within the following information:
- **Title:** Name of the Teams server defintion.
- **Teams URL:** Tokenized URL provided by the Incoming Webhook integration connector for the specific channel.
- **User name:** OPTIONAL Name to use in notifications.
- **User icon:** OPTIONAL Icon to use in notifcations, should be an emoji, e.g ':100:'

## Available Tasks
The available tasks for interfacing with Teams. These utilize the [Microsoft Teams API](https://docs.microsoft.com/en-us/graph/teams-concept-overview) and the provided Teams Connector Authentication Configuration.

## Notification Task
The MSTeams notification task needs the next information:

- **Server:** The Teams server definition to use. (the shared configuration)
- **Channel:** The target for the notification, use `#` to refer to a channel or direct message.
- **Message:** The notification message text, it could be [markdown](https://docs.microsoft.com/en-us/outlook/actionable-messages/message-card-reference)

## Refrences:
* [Microsoft Graph Rest API](https://docs.microsoft.com/en-us/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
