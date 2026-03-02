# User Story 3: View Citation Details

## Story Description
**As a** customer  
**I want** to see more details about where information came from  
**So that** I can verify accuracy if needed

## Acceptance Criteria
- Citation is clickable/expandable in the UI
- Expanded view shows source type and last updated date
- User can access this without leaving the conversation
- Works on both mobile and desktop

## Technical Specifications

### UI Components
- **Citation Badge**: Clickable inline element
- **Expansion Panel**: Modal or inline expansion
- **Responsive Design**: Mobile-first approach

### Citation Metadata
```
CitationMetadata {
  sourceId: string
  sourceType: enum (PRODUCT_DB, POLICY_DOC, KNOWLEDGE_BASE)
  sourceName: string
  lastUpdated: timestamp
  url: string (optional)
  confidence: float
}
```

### Interaction Design
- **Desktop**: Hover tooltip + click for full details
- **Mobile**: Tap to expand inline
- **Keyboard Navigation**: Tab-accessible, Enter to expand

### Display Information
- Source type (e.g., "Product Database", "Policy Document")
- Last updated date (formatted: "Updated Jan 15, 2026")
- Document/record ID (if applicable)
- Direct link to source (if available)

### Performance Requirements
- Metadata loads instantly (pre-fetched with response)
- No additional API calls on citation click
- Smooth animation (< 300ms)

## Testing Requirements
- Cross-browser compatibility testing
- Mobile responsiveness tests (iOS/Android)
- Accessibility testing (WCAG 2.1 AA)
- Keyboard navigation testing
- Touch interaction testing",
  "message": "Add User Story 3: View Citation Details spec",
  "branch": "main"
}