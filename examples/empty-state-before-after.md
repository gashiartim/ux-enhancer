# Example: Empty state refactor

Empty states are one of the easiest places to fail Krug's "no dead ends" rule. A blank pane or a bare "No results" tells the user nothing about *why* it's empty or *what to do next*.

## Before

```tsx
export function AppointmentsList({ appointments }: Props) {
  if (appointments.length === 0) {
    return <p>No appointments.</p>;
  }

  return (
    <ul>
      {appointments.map((a) => <AppointmentRow key={a.id} appointment={a} />)}
    </ul>
  );
}
```

## After

```tsx
export function AppointmentsList({ appointments }: Props) {
  if (appointments.length === 0) {
    return (
      <PageState
        variant="empty"
        title="No appointments yet"
        description="Schedule your first appointment to start tracking visits."
        action={<Button onClick={openNewAppointment}>New appointment</Button>}
      />
    );
  }

  return (
    <ul className="divide-y">
      {appointments.map((a) => <AppointmentRow key={a.id} appointment={a} />)}
    </ul>
  );
}
```

**UX Improvements:**

- Replaced bare `No appointments.` with `PageState` → empty state now explains *why* and offers a clear next action (Krug: no dead ends).
- Surfaced the primary CTA inline → user doesn't have to hunt the rest of the page for "+New".
- Used DS `PageState` instead of inline `<p>` → consistent across the app, accessible by default.
