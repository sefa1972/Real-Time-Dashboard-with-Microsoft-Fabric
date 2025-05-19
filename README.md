# Real-Time Dashboard with Microsoft Fabric - Lab Guide

## Overview
This lab demonstrates how to create a real-time dashboard in Microsoft Fabric using Eventhouse, Eventstream, and KQL queries to visualize streaming bicycle rental data.

## Prerequisites
- Microsoft Fabric tenant
- Web browser access

## Lab Architecture
```
Eventstream (Bicycle Data) → Eventhouse (KQL Database) → Real-Time Dashboard
```

## Key Steps

### 1. Environment Setup
1. Create Fabric workspace with capacity
2. Create Eventhouse with KQL database
3. Set up Eventstream with sample bicycle data

### 2. Data Pipeline Configuration
```kql
// Sample data ingestion to Eventhouse
bikes
| where ingestion_time() between (ago(30min)..now())
| summarize latest_observation = arg_max(ingestion_time(), *) by Neighbourhood
```

### 3. Dashboard Creation
1. Create new Real-Time Dashboard
2. Add visualization tiles:
   - **Bar chart**: Bikes and empty docks by neighborhood
   - **Map**: Bike locations with capacity indicators
3. Configure base query for efficient data reuse

### 4. Advanced Features
- Add neighborhood filter parameter
- Create multiple dashboard pages
- Configure auto-refresh (30min interval)
- Share dashboard with collaborators

## Key Features Demonstrated
- Real-time data streaming with Eventhouse
- KQL query optimization
- Interactive dashboard visualizations
- Parameter-based filtering
- Multi-page dashboard design
- Collaboration features

## Clean Up
1. Navigate to workspace settings
2. Select "Remove this workspace"

# 👤 Author: Sefa Öztürk

BT Stajyeri | Azure Veri Mühendisi devam ediyor

📇 LinkedIn: https://www.linkedin.com/in/sefa-ozturk1972

