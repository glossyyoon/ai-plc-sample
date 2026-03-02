# User Story 2: Policy Information with Citation

## Story Description
**As a** customer  
**I want** to receive policy information (returns, shipping) with source attribution  
**So that** I know the information is official and current

## Acceptance Criteria
- AI retrieves policy information from policy document repository
- Response includes citation (e.g., "[Return Policy - Updated Jan 2026]")
- Policy information is accurate and matches official documentation
- System retrieves current policy version

## Technical Specifications

### Document Repository Integration
- **Repository Type**: Document management system (DMS)
- **Supported Policy Types**: Returns, Shipping, Warranty, Privacy
- **Version Control**: Track policy versions with timestamps

### Data Model
```
PolicyDocument {
  id: string
  type: enum (RETURN, SHIPPING, WARRANTY, PRIVACY)
  content: string
  version: string
  lastUpdated: timestamp
  effectiveDate: timestamp
}
```

### Citation Format
- Format: "[{PolicyType} - Updated {Month Year}]"
- Example: "[Return Policy - Updated Jan 2026]"
- Include version number in metadata

### Retrieval Logic
- Always fetch latest version by effectiveDate
- Cache policy documents for 1 hour
- Invalidate cache on policy updates

### Error Handling
- Policy not found: Escalate to human agent
- Multiple versions: Use most recent effective version
- Outdated cache: Force refresh from source

## Testing Requirements
- Verify correct policy version retrieval
- Test citation format accuracy
- Validate content matches official documentation
- Test cache invalidation on policy updates