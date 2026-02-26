# US-002: Access Source Details

## User Story
As a customer, I want to click on citation markers to view the source details so that I can verify the information myself.

## Acceptance Criteria
- Clicking a citation opens a source detail panel
- Source panel shows: source type, date, and brief description
- Panel can be closed easily

## Technical Specifications

### Frontend Components
- **SourceDetailPanel Component**: Modal or side panel displaying source information
- **Trigger**: Click event on CitationMarker
- **Close Mechanism**: X button, ESC key, click outside

### Panel Content Structure
```
- Source Title
- Source Type (e.g., Product Spec, Customer Review, Database)
- Publication/Update Date
- Brief Description (2-3 sentences)
- Link to full source (see US-003)
```

### Implementation Details
```
- Component: <SourceDetailPanel sourceId={id} isOpen={boolean} onClose={fn} />
- Animation: Slide-in from right (300ms)
- Overlay: Semi-transparent backdrop
- Z-index: 1000 (above main content)
```

### Data Requirements
- Source metadata API endpoint
- Cached source details for quick access
- Fallback content for missing data

### Testing Scenarios
1. Click citation marker opens panel
2. Panel displays all required fields
3. Close button/ESC/outside click closes panel
4. Multiple citations can be opened sequentially
5. Panel content loads within 200ms

### Accessibility Requirements
- Keyboard navigation support
- Screen reader announcements
- Focus trap within panel
- ARIA labels for all interactive elements