# OTT & Movie Streaming Engagement Analysis

## Business Problem
The product and content analytics team at an Indian OTT streaming platform wants to understand what drives viewer engagement and total watch time across movies, web series, and live streams. By identifying how technical factors (such as buffering events), content length, and subscription plans influence session watch duration, managers can reduce viewer drop-off and improve subscription retention.

## Key Questions
1. What does `Watch_Duration_Mins` look like overall (average, spread, and distribution)?
2. Do `Content_Runtime_Mins` and `Buffering_Events` affect `Watch_Duration_Mins`?
3. Does `Watch_Duration_Mins` differ by `Subscription_Tier`, `Content_Type`, `Device_Type`, and `City`?
4. Which records need attention? (Sessions classified as **"Low Engagement / Drop-Off Risk"** where `Watch_Duration_Mins` is **under 30 minutes**.)

## Data Dictionary

| Column Name | Data Type | Meaning | Valid Values or Valid Range |
| :--- | :--- | :--- | :--- |
| `Session_ID` | String | Unique identifier for each streaming session | `OTT1001` to `OTT1250` |
| `Stream_Date` | Date | Date when the streaming session occurred | `2024-11-21` to `2026-11-20` (`YYYY-MM-DD`) |
| `City` | Category | Indian metro city of the viewer | `Mumbai`, `Delhi`, `Bengaluru`, `Hyderabad`, `Pune` |
| `Subscription_Tier` | Category | Viewer's active OTT plan | `Mobile`, `Basic`, `Standard`, `Premium` |
| `Content_Type` | Category | Format of content streamed | `Movie`, `Web Series`, `Documentary`, `Live Sports` |
| `Device_Type` | Category | Device used to stream the content | `Smartphone`, `Smart TV`, `Laptop`, `Tablet` |
| `User_Age` | Integer | Age of the registered viewer in years | `18` to `60` |
| `Content_Runtime_Mins` | Integer | Total runtime of the selected title in minutes | `45` to `180` |
| `Buffering_Events` | Integer | Number of playback stalls/buffering interruptions | `0` to `8` |
| `Trailer_Clicks` | Integer | Number of trailers clicked before starting playback | `0` to `10` |
| `Watch_Duration_Mins` | Float | **Main Outcome:** Total minutes watched in the session | `5.0` to `180.0` |

## Project Steps
1. **Load & Inspect:** Loaded raw data (`255` rows, `11` columns) and checked data types, summary statistics, missing values, and duplicates.
2. **Data Cleaning:** Removed duplicate rows, standardized inconsistent category text, handled missing values, and fixed out-of-range numeric values.
3. **Feature Engineering:** Created `Completion_Rate_Pct`, `Engagement_Status`, and `Age_Group`.
4. **Exploratory Analysis & Visualization:** Answered the four business questions using summary tables and saved visualizations to `images/`.