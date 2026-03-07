Meta Ads Performance Intelligence Framework






A structured Meta Ads analytics and optimization framework built using Looker Studio and SQL-based KPI modeling.

This project demonstrates how paid media data can be transformed into decision-ready insights through funnel analysis, performance scoring, and campaign optimization metrics.

🚀 Project Overview

Most Meta Ads dashboards simply display metrics.

This framework focuses on decision intelligence by transforming raw advertising data into actionable signals such as:

Budget allocation signals

Creative fatigue detection

Funnel bottleneck identification

Lead efficiency scoring

Campaign and ad set ranking

Instead of static reporting, the goal is to build a performance intelligence system that helps marketing teams scale winning campaigns and fix underperforming ones.

📊 Dashboard Overview
![Dashboard Overview](main/dashboard_overview.png)
The executive dashboard provides a high-level view of campaign performance including:

Total Spend

Impressions

Clicks

Leads

Cost per Lead

Conversion Rate

This allows marketing teams and decision-makers to quickly assess overall campaign efficiency.

📊 Core Capabilities
1️⃣ End-to-End Performance Overview

Track key acquisition metrics in a unified performance summary:

Spend

CPM

CPC

CPL

Total Leads

Conversion Rate

These KPIs provide a clear overview of how efficiently the advertising budget is being used.

2️⃣ Full-Funnel Visualization

The framework models the complete acquisition funnel:

Impressions → Clicks → Landing Page Views → Leads

This helps identify where users drop off in the funnel and where optimization should be applied.

Campaign Performance

3️⃣ Lead Performance Scoring

Campaigns and ad sets are ranked based on performance efficiency metrics such as:

Cost per Lead

Conversion Rate

Spend Efficiency

Performance Index

This allows marketers to easily identify top-performing campaigns and prioritize scaling them.

4️⃣ Creative Fatigue Detection

The framework identifies potential creative fatigue based on performance trends including:

Declining CTR

Increasing CPC

Reduced engagement

Ad sets are classified into categories such as:

Healthy

At Risk

Fatigued

This enables proactive creative refresh strategies.

5️⃣ Top vs Bottom Ad Set Analysis

The dashboard highlights performance distribution across campaigns and ad sets.

This allows marketers to quickly identify:

High-performing audience segments

Underperforming campaigns

Budget reallocation opportunities

Funnel Analysis

The funnel analysis provides visibility into conversion performance across acquisition stages, allowing teams to identify bottlenecks between:

Traffic generation

Landing page engagement

Lead capture

🏗 Architecture

The framework follows a modern analytics architecture:

Meta Ads API
     ↓
Data Collection Layer
     ↓
Data Warehouse (BigQuery)
     ↓
SQL Transformation Layer
     ↓
KPI Modeling & Funnel Analysis
     ↓
Looker Studio Dashboard
Data Source

Meta Ads API

Transformation Layer

KPI normalization

Funnel modeling

Performance scoring logic

Visualization Layer

Looker Studio dashboards

🧮 Example SQL Model

Example query used to generate campaign performance metrics.

SELECT
  campaign_name,
  SUM(spend) AS total_spend,
  SUM(impressions) AS impressions,
  SUM(clicks) AS clicks,
  SUM(leads) AS leads,
  SAFE_DIVIDE(SUM(clicks), SUM(impressions)) AS ctr,
  SAFE_DIVIDE(SUM(leads), SUM(clicks)) AS conversion_rate,
  SAFE_DIVIDE(SUM(spend), SUM(leads)) AS cost_per_lead
FROM meta_ads_campaign_data
GROUP BY campaign_name
ORDER BY total_spend DESC;

This transformation layer converts raw ad performance data into analysis-ready metrics used by the dashboard.

📷 Dashboard Screenshots

All dashboard screenshots can be found in the /screenshots directory.

They illustrate:

Performance overview

Campaign ranking

Funnel visualization

Conversion metrics

🧠 Design Philosophy

The objective of this framework is not just reporting.

The objective is structured decision-making that directly impacts:

Budget allocation

Creative rotation

Funnel optimization

Campaign scaling

By focusing on performance signals instead of raw metrics, marketing teams can make faster and more effective optimization decisions.

🏢 Built By

YDA Labs

Performance Analytics
Revenue Intelligence
Automation Systems
