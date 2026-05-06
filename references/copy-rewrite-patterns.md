# Copy rewrite patterns

Lookup table for common verbose UI copy and its tightened replacement. Apply by default unless context demands otherwise.

## Welcomes / scene-setting → delete

| Before | After |
|---|---|
| "Welcome to your profile! Here you can update your personal information." | *(delete)* |
| "This is your dashboard where you can see all your data." | *(delete)* |
| "Use the form below to..." | *(delete — the form is self-evident)* |
| "Click the button to..." | *(delete — buttons explain themselves via label)* |

## Form labels → tighten

| Before | After |
|---|---|
| "Please enter your first name" | Label `First name`, placeholder optional |
| "What is your email address?" | Label `Email` |
| "Phone number (optional)" | Label `Phone`, hint `Optional` |
| "Please select your country from the list below" | Label `Country` |
| "Type a password (must be at least 8 characters)" | Label `Password`, hint `8+ characters` |

## Buttons → verb of what happens

| Before | After |
|---|---|
| `Submit` | `Save` / `Send` / `Create` / `Pay` (whichever applies) |
| `OK` | `Confirm` only if generic; otherwise the actual verb |
| `Click here` | The verb of the action |
| `Save changes` | `Save` |
| `Continue` (when it submits a form) | `Save and continue` or just `Save` |
| `Yes, I want to delete this item` | `Delete` |
| `Cancel` (in a multi-step modal) | Keep `Cancel` — it's the standard escape |

## Empty states → explain + offer next step

| Before | After |
|---|---|
| "No results" | "No patients yet. Add your first patient." + primary CTA |
| "Empty" | "You haven't created any invoices. New invoice →" |
| Blank pane | Always show: icon + 1-line explanation + 1 CTA |

## Error messages → say what's wrong AND what to do

| Before | After |
|---|---|
| "Error" | "Couldn't save changes. Try again." + Retry button |
| "Invalid input" | "Email must contain @" |
| "Something went wrong" | "We couldn't load your appointments. Refresh, or contact support if it persists." |

## Loading states → never silent

| Before | After |
|---|---|
| Blank screen | Skeleton matching final layout |
| Generic spinner | Skeleton, or spinner + 1-line context: "Loading patients…" |
| Disabled button no feedback | `ButtonLoading` / spinner inside button |

## Headings / tabs → no duplication

| Before | After |
|---|---|
| Page H1: "Patient details" + tab "Patient details" | Tab says `Information` |
| H2: "Recent activity" + Card title: "Recent activity" | One of them, not both |

## Tone

- Drop "please" in UI labels — it's polite but adds reading load.
- Drop "you" / "your" in field labels — `Email` not `Your email`.
- Keep contractions — `Couldn't` not `Could not`. More human, fewer characters.
- Sentence case for labels and buttons. Title Case Looks Shouty.
