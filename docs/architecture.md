# Architecture Plan

## Data Flow
User clicks button (frontend) → API Gateway (REST endpoint) → Lambda (fetch/generate fact) → DynamoDB (fact source) → Bedrock (optional, rewrites fact wittily) → response returned → Amplify frontend renders it

## Diagram (text form for now)
[User Browser] 
    → [Amplify Hosted Frontend]
        → [API Gateway: GET /fact]
            → [Lambda: getFunFact]
                → [DynamoDB: FunFacts table]
                → [Bedrock: rewrite prompt] (optional path)
            ← JSON response { "fact": "..." }
    ← Rendered on page

## Design Decisions
- REST over WebSocket → simpler for a single button-click use case
- DynamoDB over hardcoded array → lets facts be added without redeploying Lambda
- Bedrock is optional/toggled → keeps base cost near $0, GenAI calls only on demand

## Open Questions
- Single table vs categorized facts (AWS / security / general cloud)?
- Cache Bedrock responses to avoid repeat cost on same fact?
