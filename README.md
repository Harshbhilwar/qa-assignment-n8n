# n8n QA Assignment

## Workflow Overview

This workflow demonstrates API integration, data transformation, conditional logic, notification delivery, and error handling using n8n.

## APIs Used

### API 1: CoinGecko Markets API

Purpose:
Fetch cryptocurrency market data including coin name, symbol, current price, and market ranking.

### API 2: CoinGecko Coin Details API

Purpose:
Fetch additional details about Bitcoin to enrich the workflow data.

## Why These APIs Were Chosen

CoinGecko provides free and reliable cryptocurrency market data without requiring authentication, making it suitable for demonstrating API integration and workflow automation concepts.

## Transformation Logic

The workflow retrieves cryptocurrency market data and uses a JavaScript Code node to filter the response and keep only the top 5 cryptocurrency records.

```javascript
const coins = $input.all();
return coins.slice(0, 5);
```

## Workflow Steps

1. Schedule Trigger starts the workflow every hour.
2. HTTP Request fetches cryptocurrency market data from CoinGecko.
3. JavaScript Code node filters the response to the top 5 cryptocurrencies.
4. HTTP Request fetches additional Bitcoin details.
5. IF node checks whether Bitcoin's market_cap_rank equals 1.
6. If the condition evaluates TRUE, a Discord notification is sent.

## Conditional Logic

Condition:

```
market_cap_rank == 1
```

If Bitcoin is ranked #1, the workflow sends a notification to Discord.

## Error Handling

All HTTP Request nodes are configured with:

```
On Error → Continue (using error output)
```

This ensures the workflow does not fail silently when an external API is unavailable.

## Technologies Used

- n8n
- CoinGecko API
- JavaScript
- Discord Webhook

## Output

When the condition is satisfied, the workflow sends the following notification to Discord:

```
Bitcoin is currently ranked #1. Workflow executed successfully.
```

## Result

The workflow successfully retrieves cryptocurrency data, enriches it using a second API request, evaluates a condition, and sends a notification to Discord while maintaining proper error handling.


