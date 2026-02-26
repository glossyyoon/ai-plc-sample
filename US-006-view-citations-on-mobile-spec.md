# US-006: View Citations on Mobile

## User Story
As a mobile customer, I want to easily view citations without cluttering my screen so that I can verify information on any device.

## Acceptance Criteria
- Citations are readable on mobile screens
- Source panel is mobile-optimized
- No horizontal scrolling required

## Technical Specifications

### Responsive Design
- **Breakpoints**: 
  - Mobile: < 768px
  - Tablet: 768px - 1024px
  - Desktop: > 1024px
- **Citation Display**: Smaller font on mobile, same functionality
- **Panel Behavior**: Full-screen modal on mobile, side panel on desktop

### Mobile-Specific Components
```
- MobileCitationMarker: Touch-optimized (44x44px touch target)
- MobileSourcePanel: Full-screen overlay with slide-up animation
- MobileSourceLink: Large, thumb-friendly buttons
```

### Implementation Details
```
Mobile Panel:
- Position: Fixed, bottom: 0, height: 90vh
- Animation: Slide up from bottom (250ms)
- Close: Swipe down gesture + close button
- Content: Scrollable with momentum

Citation Markers:
- Font-size: 0.8em (mobile), 0.85em (desktop)
- Touch target: Minimum 44x44px
- Spacing: 8px padding around marker
```

### Layout Considerations
- Single column layout on mobile
- Larger tap targets (minimum 44x44px)
- Readable font sizes (minimum 16px body text)
- Adequate spacing between interactive elements
- No horizontal overflow

### Testing Scenarios
1. Citations readable on iPhone SE (smallest screen)
2. Source panel opens smoothly on mobile
3. No horizontal scrolling on any screen size
4. Touch targets meet accessibility standards
5. Swipe gestures work reliably
6. Panel content scrolls without issues

### Performance Requirements
- Touch response: < 100ms
- Animation: 60fps
- Panel load: < 200ms
- Smooth scrolling on all devices

### Accessibility
- Minimum font size: 16px
- Touch target size: 44x44px
- High contrast ratios
- Support for zoom up to 200%
- Screen reader compatibility",
  "message": "Add US-006: View Citations on Mobile specification",
  "branch": "main"
}