# US-005: Handle Missing Evidence

## User Story
As a customer, I want to receive a clear message when the AI cannot find supporting evidence so that I understand the limitation.

## Acceptance Criteria
- AI indicates when evidence is unavailable
- Response suggests alternative ways to get information
- No fabricated citations are shown

## Technical Specifications

### Detection Logic
- **Threshold**: If retrieval confidence < 0.6, trigger missing evidence flow
- **Validation**: Verify at least one high-quality source exists
- **Fallback**: Provide helpful alternative actions

### Response Templates
```
1. No Sources Found:
   "I couldn't find specific information about [topic] in our product database. 
    You might want to: [alternatives]"

2. Low Confidence Sources:
   "I found limited information about [topic]. For the most accurate details, 
    I recommend: [alternatives]"

3. Partial Information:
   "I can provide some information about [topic], but for complete details: 
    [alternatives]"
```

### Alternative Suggestions
- Contact customer support
- Check product manual/documentation
- Visit specific product page
- Search broader category
- Refine query with more details

### Implementation Details
```
- Component: <MissingEvidenceMessage alternatives={array} />
- Confidence Threshold: 0.6 (configurable)
- Logging: Track all missing evidence cases
- User Feedback: Option to report unhelpful responses
```

### Data Requirements
- Confidence scores from retrieval system
- Alternative action templates
- Support contact information
- Related resource links

### Testing Scenarios
1. Query with no matching sources shows message
2. Low-confidence results trigger appropriate response
3. Alternatives are relevant and actionable
4. No hallucinated citations appear
5. User can provide feedback on response

### Quality Assurance
- Never generate citations without sources
- Always provide actionable alternatives
- Log cases for continuous improvement
- Monitor user satisfaction with fallback responses