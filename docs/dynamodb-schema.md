# DynamoDB Schema — FunFacts Table

## Table: FunFacts
| Attribute | Type | Notes |
|---|---|---|
| factId | String (PK) | UUID per fact |
| text | String | The fun fact itself |
| category | String | e.g. "aws", "security", "general" |
| createdAt | String | ISO timestamp |

## Access Pattern
- Random fact retrieval → Scan with random offset (small table, acceptable cost) 
  OR maintain a numeric `factId` and generate a random int in Lambda
- Category filter (future) → GSI on `category`

## Seed Data (draft, ~5 starter facts)
1. AWS Lambda can run for a max of 15 minutes per invocation.
2. The first cloud computing term appeared in the 1990s, referencing the internet as a "cloud" in network diagrams.
3. Amazon S3 was launched in 2006 as one of AWS's first public services.
4. A single DynamoDB table can handle millions of requests per second at scale.
5. AWS has over 30 geographic regions worldwide as of the mid-2020s.
