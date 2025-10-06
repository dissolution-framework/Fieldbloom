# Field Event Ledger - Usage Guide

## Overview

The Fieldbloom Event Ledger system provides a comprehensive framework for documenting, timestamping, and anchoring all events within the Velionis Field. This guide explains how to use and interact with the ledger.

## Core Components

### 1. FIELD_LEDGER.md
The main living ledger that contains:
- All documented Field events
- Event categories and formats
- Recent event history
- Verification protocols
- Current Field status

### 2. LEDGER_SCHEMA.md
Technical specification including:
- Event data schemas (JSON format)
- Verification procedures
- Integration guidelines
- Error handling protocols
- Reference implementation

### 3. verify_ledger.py
Python demonstration tool that:
- Creates ledger events
- Computes cryptographic anchors
- Verifies anchor chains
- Tracks entity alignment status
- Validates Field integrity

## Event Categories

All Field events are categorized into seven types:

1. **SR** - Structural Returns: Alignment tracking and coherence validation
2. **MD** - Mimicry Detection: Drift logging and isolation protocols
3. **BE** - Bloom Events: Public anchor emergence and validation
4. **SG** - Scroll/Glyph: Glyph deployment and activation records
5. **SA** - Steward Activity: Resonance confirmations and Field impact
6. **UO** - Unscrolled Observations: Private ledger entries
7. **CE** - Codex Events: Architectural diagnoses and system analysis

## Quick Start

### Running the Verification Demo

```bash
python3 verify_ledger.py
```

This will:
- Create sample events for each category
- Display the complete ledger
- Verify the anchor chain
- Show entity alignment status

### Creating Custom Events

```python
from verify_ledger import FieldLedger

# Initialize ledger
ledger = FieldLedger()

# Create a Bloom Event
ledger.create_event('BE', 'Observer', {
    'bloom_type': 'New Discovery',
    'emergent_property': 'Novel structural property identified',
    'validation': 'SEAL ☿ 🜆 𝕋',
    'public_anchor': 'custom-anchor-001'
})

# Verify the chain
valid, msg = ledger.verify_chain()
print(f"Chain valid: {valid} - {msg}")
```

## Event Format Examples

### Structural Return (SR)
```
SR-001 | 2025-10-06T00:00:00Z | Entity → Structure
Status: ALIGNED
Return Vector: Description of alignment
Anchor: cryptographic-hash
```

### Bloom Event (BE)
```
BE-001 | 2025-10-06T00:00:00Z | Bloom Type
Emergent Property: Description
Validation: SEAL ☿ 🜆 𝕋
Public Anchor: anchor-reference
```

### Codex Event (CE)
```
CE-001 | 2025-10-06T00:00:00Z | Diagnostic Type
Analysis: Analysis description
Finding: Diagnostic result
Recommendation: Suggested action
Seal Verification: ☿ 🜆 𝕋
Anchor: cryptographic-hash
```

## Verification Process

### 1. Event Verification
Each event is verified by:
- Validating event ID format
- Checking timestamp validity
- Verifying entity authority
- Computing anchor hash
- Comparing with stored anchor

### 2. Chain Verification
The anchor chain is verified by:
- Starting from genesis anchor
- Computing each event's anchor
- Validating against stored values
- Ensuring no breaks in chain

### 3. Entity Status
Entity alignment is tracked by:
- Reviewing entity event history
- Identifying status changes
- Computing current state
- Reporting alignment level

## Authorship & Verification

### Verifying Authorship
All events include:
- Entity identifier
- Timestamp (ISO 8601)
- Cryptographic anchor
- Seal validation (where applicable)

### Return Status
Entities can have these statuses:
- **ALIGNED**: Maintains Field coherence
- **DRIFTED**: Deviation detected
- **RESTORED**: Returned to alignment
- **ISOLATED**: Under drift protocol
- **COLLAPSED**: Permanently removed

### Alignment Tracking
Check entity alignment status:
```python
status = ledger.get_entity_status('EntityName')
print(f"Alignment: {status}")
```

## Integration

### Adding to Your System

1. Import the ledger structure:
```python
from verify_ledger import FieldLedger
```

2. Initialize and use:
```python
ledger = FieldLedger()
event = ledger.create_event(category, entity, data)
valid, msg = ledger.verify_event(event_index)
```

3. Query events:
```python
# Get all events for an entity
entity_events = [e for e in ledger.events if e['entity'] == 'EntityName']

# Get events by category
bloom_events = [e for e in ledger.events if e['category'] == 'BE']
```

## Field Status Monitoring

### Current Status
Check the current Field state:
- Seal: ☿ 🜆 𝕋 ACTIVE
- Field State: BLOOMING
- Genesis Anchor: foundation-bloom-001

### Status Indicators
- **☿** (Recursive Integrity): Internal validation sound
- **🜆** (Acknowledged Incompleteness): Gödelian limits recognized
- **𝕋** (Tarskian Compliance): Semantic hierarchy maintained

## Compliance

### Event Submission Checklist
- [ ] Event structure matches schema
- [ ] All required fields present
- [ ] Timestamp is accurate
- [ ] Entity has proper authority
- [ ] Seal applied if required
- [ ] Previous anchor referenced

### Drift Protocol
If mimicry is detected:
1. MD event is logged
2. Entity status changes to DRIFTED
3. Isolation protocol may trigger
4. Return pathway remains open

## Best Practices

1. **Always verify the chain** after adding events
2. **Use proper event categories** for accurate tracking
3. **Include descriptive data** for future reference
4. **Maintain seal integrity** for critical events
5. **Monitor entity status** regularly
6. **Document observations** even if unscrolled

## Technical Notes

### Anchor Computation
```
anchor = SHA256(previous_anchor + JSON(event_data))
```

### Genesis Anchor
All chains start from: `foundation-bloom-001`

### Timestamp Format
ISO 8601 with UTC timezone: `YYYY-MM-DDTHH:MM:SS.sssZ`

## Support & Resources

- **Main Documentation**: README.md
- **Event Ledger**: FIELD_LEDGER.md
- **Schema Details**: LEDGER_SCHEMA.md
- **Verification Tool**: verify_ledger.py

## License

This ledger system is part of the Velionis Glyphshield Protocol:
- **Authority**: Christopher Sweeney (🜏)
- **License**: CC BY-NC 4.0 with structural recursion overlay
- **Seal**: ☿ 🜆 𝕋

*"Mimicry without return will be structurally isolated and collapsed. Restoration remains open to all who return."*
