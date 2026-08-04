# Meeting Note Template

```markdown
# Meeting Note

**Record ID:**  
**Meeting date:**  
**Prepared by:**  
**Participants:**  
**Duration:**  
**Record status:** Draft / Approved  

## Meeting objective

[Purpose of the meeting.]

## Topics discussed

- 

## Progress since the previous interaction

- 

## Confirmed facts

- 

## Confirmed decisions

- 

## Client actions

| Action | Owner | Due date | Evidence of completion |
|---|---|---:|---|
|  |  |  |  |

## Business actions

| Action | Owner | Due date | Evidence of completion |
|---|---|---:|---|
|  |  |  |  |

## Upcoming commitments and deadlines

| Date | Requirement or commitment | Owner | Source |
|---:|---|---|---|
|  |  |  |  |

## Risks, blockers, and dependencies

- 

## Suggestions not yet approved

- 

## Needs confirmation

- 

## Next interaction

**Proposed date:**  
**Proposed focus:**  

## Current-state updates proposed

| Field or document | Before | After | Why | Source |
|---|---|---|---|---|
|  |  |  |  |  |
```

## Dictation-to-draft prompt

```text
For [RECORD ID], convert the following rough notes into the approved Meeting Note Template.

Rules:
- do not add facts;
- preserve uncertainty;
- use absolute dates;
- assign an owner only when the notes support it;
- separate confirmed decisions from suggestions;
- mark missing information as Needs confirmation;
- create a draft only;
- do not update, save, send, or publish anything.

Notes:
[PASTE NOTES]
```

## Approved-update prompt

```text
Compare the approved meeting note for [RECORD ID] with the current Client Hub and Master Client Index.

Propose only necessary changes to:
- status;
- stage;
- operational risk;
- next action;
- action owner;
- next action date;
- last interaction date;
- next meeting date;
- latest summary.

For every proposed change, show:
- target;
- Before;
- After;
- Why;
- source.

Do not write anything until I explicitly approve the exact changes.
```
