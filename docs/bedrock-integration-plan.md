# Bedrock Integration Plan

## Goal
Take a plain fact from DynamoDB and rewrite it in a witty, conversational tone.

## Model
- Start with a lightweight Bedrock text model (cost-efficient for short rewrites)

## Prompt Design (draft)
"Rewrite the following cloud computing fact in a witty, conversational tone. 
Keep it under 2 sentences. Do not add facts that aren't in the original.
Fact: {factText}"

## Cost Control
- Only called when witty=true is passed
- Short max_tokens (~80) since output is 1-2 sentences
- Optional: cache rewritten versions back into DynamoDB so the same fact isn't re-generated twice
