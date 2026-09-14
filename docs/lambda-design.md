# Lambda Function Design — getFunFact

## Trigger
API Gateway GET /fact

## Responsibilities
1. Query DynamoDB for a random fact (scan + random index, or a random-id GSI)
2. If `witty=true` query param is present, pass fact to Bedrock for rewrite
3. Return JSON: { "fact": string, "source": "dynamodb" | "bedrock" }

## Pseudocode (no implementation yet)
