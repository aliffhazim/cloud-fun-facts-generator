# API Gateway Plan

## Endpoint
GET /fact
  - Query param: witty (optional, boolean, default false)
  - Integration: Lambda proxy integration to getFunFact

## CORS
- Enable CORS for Amplify frontend origin
- Allow methods: GET, OPTIONS

## Stages
- dev → for testing during build
- prod → connected to Amplify frontend once stable

## Throttling (cost control)
- Rate limit: 5 requests/sec, burst 10
- Keeps this a $0.03 project even with public traffic
