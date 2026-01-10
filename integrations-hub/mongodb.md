---
title: "MongoDB"
description: "Document database CRUD operations and aggregations."
icon: "leaf"
---

## Overview

Phinite's MongoDB integration allows workspace assistants to perform CRUD operations, aggregations, indexing, and database management on MongoDB databases.

This document explains what credentials are required, how to configure MongoDB connection, and how to set up the integration inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Insert, update, and delete documents
- Query collections with filters
- Perform aggregation pipelines
- Create and manage indexes
- Handle database operations
- Monitor collection statistics

This integration is bidirectional and uses MongoDB's official drivers.

## Required credentials

Phinite uses 2 credentials for MongoDB:

- Connection String (required)
- Database Name (required)

These credentials are obtained from your MongoDB deployment. Phinite does not modify or replace MongoDB's authentication model.

## Setup steps

### Step 1: Get MongoDB Connection Details

For MongoDB Atlas:
1. Log into MongoDB Atlas
2. Go to your cluster
3. Click "Connect"
4. Choose "Connect your application"
5. Copy the connection string

For self-hosted MongoDB:
1. Use your MongoDB server connection string
2. Format: mongodb://username:password@host:port/database

### Step 2: Create Database User (Recommended)

1. In MongoDB Atlas or your MongoDB instance
2. Create a dedicated user for Phinite
3. Grant appropriate permissions:
   - readWrite for basic operations
   - dbAdmin for administrative tasks
4. Note the username and password

### Step 3: Whitelist IP Addresses (Atlas)

1. In MongoDB Atlas Network Access
2. Add your Phinite server IP addresses
3. Or allow access from anywhere (less secure)

### Step 4: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select MongoDB
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: MongoDB Production
   - Connection String: Your MongoDB connection string
   - Database Name: Target database name
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for MongoDB:

- Insert Document: Add single documents
- Insert Many Documents: Bulk document insertion
- Find Document: Query single documents
- Find Many Documents: Query multiple documents
- Update Document: Modify existing documents
- Delete Document: Remove documents
- Count Documents: Get document counts
- Aggregate Documents: Run aggregation pipelines
- Create Collection: Set up new collections
- List Collections: View database collections
- Drop Collection: Remove collections
- Create Index: Add database indexes
- List Indexes: View collection indexes
- Drop Index: Remove indexes
- Create Database: Set up new databases
- List Databases: View available databases
- Run Command: Execute database commands
- Get Collection Stats: Access collection statistics

## Documentation & resources

- Official MongoDB Documentation: `https://docs.mongodb.com/`
- MongoDB Drivers: `https://docs.mongodb.com/drivers/`
- MongoDB Atlas: `https://cloud.mongodb.com/`

## Notes

- Connection strings contain sensitive information
- Use strong passwords and IP whitelisting
- Monitor connection limits and performance
- Some operations require specific user permissions
- Aggregation pipelines can be resource-intensive
