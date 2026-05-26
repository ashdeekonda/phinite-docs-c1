---

## title: "Google Calendar"
description: "Configure Google Calendar via service account to create, update, and query events."
icon: "calendar-days"

## Overview

Phinite's Google Calendar integration allows workspace assistants to manage calendar events, schedule meetings, and check availability directly through Google Calendar's API.

This document explains what credentials are required, how to obtain them from Google, and how to configure them inside Phinite.

![Google Calendar](/images/sampleimage.png)

## What this integration enables

Once configured, Phinite assistants can:

- Create and manage calendar events
- Check meeting availability
- Send calendar invites
- Update event details
- Query upcoming events

This integration is bidirectional and uses Google Calendar's official API v3.

## Required credentials

Phinite supports two authentication methods for Google Calendar:

### Authentication Method 1: Custom Form (Service Account JSON)

**Required Credentials:**

- Service Account JSON (required)

**Setup Steps:**

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create or select project
3. Enable Google Calendar API in APIs & Services > Library
4. Go to IAM & Admin > Service Accounts > Create Service Account
5. Create Key (JSON format) and download
6. In Phinite: Select Custom Form tab > Upload JSON file

### Authentication Method 2: OAuth2

- Login using your google user name and password. 
- Give permissions to the app and create connection

## Configure in Phinite

1. Log into your Phinite workspace at [app.phinite.ai/login](https://app.phinite.ai/login)
2. Navigate to Integrations
3. Select Google Calendar
4. Click + Add Configuration
5. Choose authentication method:
  - **Custom Form tab**: Upload JSON file
  - **OAuth2 tab**: Enter Client ID and Secret, then authorize
6. Enter the following:
  - Name of the connection: Google Calendar Production
7. Select the workspace assistants that should use this connection
8. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Google Calendar:

- **Create Event**: Schedule new calendar events
- **Update Event**: Modify existing event details
- **Delete Event**: Remove calendar events
- **Get Event**: Retrieve specific event information
- **List Events**: Query events within date ranges
- **Check Availability**: Verify free/busy status
- **Send Invite**: Email calendar invitations
- **Add Attendees**: Include participants in events
- **Set Reminders**: Configure event notifications
- **Create Recurring Event**: Set up repeating meetings
- **Move Event**: Transfer between calendars
- **Get Calendar List**: Retrieve available calendars
- **Share Calendar**: Grant access permissions
- **Set Event Status**: Mark events as confirmed/tentative
- **Add Event Location**: Include meeting venues

## Documentation & resources

- [Official Google Calendar Documentation](https://developers.google.com/calendar)
- [Google Calendar API Reference](https://developers.google.com/calendar/api/v3/reference)

## Notes

- Service accounts have domain-wide delegation capabilities
- Ensure proper calendar sharing permissions are set
- Rate limits apply to API calls (check Google's quota limits)
- Client Secrets are only visible at creation time (April 2025 change)

