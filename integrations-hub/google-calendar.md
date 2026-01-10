---
title: "Google Calendar"
description: "Configure Google Calendar via service account to create, update, and query events."
icon: "calendar-days"
---

## Overview

Phinite’s Google Calendar integration enables assistants to manage events, check availability, and send invites using Google Calendar API v3.

<Frame>
  ![Google Calendar](/images/sampleimage.png)
</Frame>

## What this integration enables

- Create and manage calendar events
- Check free/busy availability
- Send invites and add attendees
- Update and move events
- List and query events by date range

## Required credentials

- Service Account JSON (required)

## Setup steps

### Step 1: Create Google Cloud Project
1. Go to Google Cloud Console: https://console.cloud.google.com/
2. Click Create Project or select existing project
3. Enter project name and click Create
4. Enable the Google Calendar API:
   - Go to APIs & Services > Library
   - Search for "Google Calendar API"
   - Click Enable

### Step 2: Create Service Account
1. In Google Cloud Console, go to IAM & Admin > Service Accounts
2. Click Create Service Account
3. Enter service account name and description
4. Click Create and Continue
5. Skip role assignment (click Continue)
6. Click Done

### Step 3: Generate Service Account Key
1. Click on the created service account
2. Go to Keys tab
3. Click Add Key > Create new key
4. Select JSON format
5. Click Create
6. Download the JSON file and keep it secure

### Step 4: Configure in Phinite
1. Log into your Phinite workspace: https://www.phinite.ai
2. Navigate to Integrations
3. Select Google Calendar
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Google Calendar Production
   - Credentials: Upload the JSON file or paste JSON content
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

<Tip>
  Ensure calendars are shared properly with the service account if you need access to non-owned calendars.
</Tip>

## Predefined tools

- Create Event
- Update Event
- Delete Event
- Get Event
- List Events
- Check Availability (free/busy)
- Send Invite
- Add Attendees
- Set Reminders
- Create Recurring Event
- Move Event
- Get Calendar List
- Share Calendar
- Set Event Status
- Add Event Location

## Documentation & resources

- Official: `https://developers.google.com/calendar`
- API Reference: `https://developers.google.com/calendar/api/v3/reference`


