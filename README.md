# E-commerce Conversion Funnel Analysis

## Project Overview

This project analyzes an e-commerce conversion funnel from initial visits through product views, add-to-cart actions, and completed purchases.

The objective is to identify where users drop out of the funnel, calculate conversion rates between stages, identify potential bottlenecks, and present the results through an interactive Power BI dashboard.

## Funnel Stages

The analysis follows four stages:

1. Visits
2. Product Views
3. Add to Cart
4. Purchases

## Tools Used

- Microsoft Excel
- Power BI
- DAX
- GitHub

## Dataset

The dataset contains e-commerce funnel activity with information including:

- Date
- Traffic Source
- Device
- Visits
- Product Views
- Add to Cart
- Purchases
- Conversion rates

The dataset was cleaned before analysis by removing duplicate records, removing a blank row, and replacing missing Traffic Source and Device values with `Unknown`.

The final dataset contains **600 records**.

## Key Performance Indicators

| KPI | Result |
|---|---:|
| Total Visits | 218,971 |
| Total Product Views | 149,537 |
| Total Add to Cart | 44,358 |
| Total Purchases | 20,074 |
| Overall Purchase Conversion Rate | 9.17% |

## Funnel Conversion Analysis

| Funnel Stage | Conversion Rate |
|---|---:|
| Visit → Product View | 68.29% |
| Product View → Add to Cart | 29.66% |
| Add to Cart → Purchase | 45.25% |

## Funnel Drop-off Analysis

| Funnel Stage | Drop-off Rate |
|---|---:|
| Visit → Product View | 31.71% |
| Product View → Add to Cart | 70.34% |
| Add to Cart → Purchase | 54.75% |

The Product View → Add to Cart stage has the largest drop-off in the analyzed dataset.

## Dashboard Features

The Power BI dashboard includes:

- Total Visits KPI
- Total Product Views KPI
- Total Add to Cart KPI
- Total Purchases KPI
- Overall Purchase Conversion Rate
- E-commerce Conversion Funnel
- Funnel Drop-off Rate
- Purchases by Traffic Source
- Purchases by Device
- Users by Funnel Stage
- Traffic Source slicer
- Device slicer
- Date slicer

The slicers allow users to interactively analyze funnel performance across different traffic sources, devices, and dates.

## DAX Measures

### Overall Purchase Conversion

```DAX
Overall Purchase Conversion % =
DIVIDE(
    SUM('Raw_Funnel_Data'[Purchases]),
    SUM('Raw_Funnel_Data'[Visits]),
    0
)
