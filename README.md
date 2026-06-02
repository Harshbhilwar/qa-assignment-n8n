# n8n QA Assignment

## Workflow Overview

This workflow demonstrates:

- Schedule Trigger
- API Integration using CoinGecko
- JavaScript Data Processing
- Conditional Logic
- Discord Notification
- Error Handling

## Workflow Steps

1. Schedule Trigger starts workflow.
2. HTTP Request fetches cryptocurrency market data.
3. JavaScript node selects top 5 coins.
4. HTTP Request fetches Bitcoin details.
5. IF node checks if Bitcoin rank equals 1.
6. Discord webhook sends notification.

## Error Handling

HTTP nodes are configured with:

Continue On Error

to ensure workflow execution continues even when external API failures occur.

## Technologies Used

- n8n
- CoinGecko API
- Discord Webhook
- JavaScript

## Result

Workflow successfully sends Discord notification when Bitcoin is ranked #1.