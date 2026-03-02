# User Story 4: Multiple Source Citations

## Story Description
**As a** customer  
**I want** responses that combine information from multiple sources to show all references  
**So that** I understand the complete basis for the AI's answer

## Acceptance Criteria
- AI can cite multiple sources in a single response
- Each citation is distinguishable and traceable
- Response clearly indicates which information comes from which source
- Maximum of 3 citations per response for simplicity

## Technical Specifications

### Citation Management
- **Maximum Citations**: 3 per response
- **Citation Format**: Numbered references [1], [2], [3]
- **Inline Attribution**: Place citation immediately after relevant sentence

### Response Structure
```
Response {
  text: string
  citations: Citation[]
  citationMap: Map<sentenceId, citationId[]>
}

Citation {
  id: number (1-3)
  sourceType: string
  sourceName: string
  lastUpdated: timestamp
  excerpt: string (optional)
}
```

### Attribution Logic
- Map each sentence/claim to source citation(s)
- Place citation number at end of sentence
- Multiple citations: [1][2] format
- Deduplicate identical sources

### Citation Prioritization (when > 3 sources)
1. Most recent information
2. Official/authoritative sources
3. Most relevant to query

### Display Format
**Example Response:**
"Our return policy allows returns within 30 days [1]. Shipping is free for orders over $50 [2]. Premium members get extended return windows [1][3]."

**Citations:**
[1] Return Policy - Updated Jan 2026
[2] Shipping Policy - Updated Dec 2025
[3] Membership Benefits - Updated Feb 2026

## Testing Requirements
- Test responses with 1, 2, and 3 citations
- Verify correct sentence-to-citation mapping
- Test citation deduplication logic
- Validate prioritization when > 3 sources available
- Test readability with multiple citations