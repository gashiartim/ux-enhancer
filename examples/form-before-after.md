# Example: Patient profile form refactor

A typical settings/profile form refactor. Shows the most common ux-enhancer transformations: deleting happy talk, tightening labels, surfacing the primary CTA, and using DS state primitives.

## Before

```tsx
export function PatientProfileForm({ patient }: { patient: Patient }) {
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);

  return (
    <div className="p-8">
      <h1 className="text-2xl font-bold mb-2">Welcome to your profile!</h1>
      <p className="text-gray-600 mb-6">
        On this page you can view and update your personal information.
        Please make sure all the fields are filled out correctly before
        clicking the submit button at the bottom of the form.
      </p>

      {error && <div className="text-red-500">{error}</div>}

      <form onSubmit={handleSubmit}>
        <label>Please enter your first name:</label>
        <input name="firstName" defaultValue={patient.firstName} />

        <label>Please enter your last name:</label>
        <input name="lastName" defaultValue={patient.lastName} />

        <label>What is your email address?</label>
        <input name="email" type="email" defaultValue={patient.email} />

        <label>Phone number (optional, but recommended):</label>
        <input name="phone" defaultValue={patient.phone} />

        {loading ? <Spinner /> : null}

        <button type="button">Cancel</button>
        <button type="submit">Submit changes</button>
      </form>
    </div>
  );
}
```

## After

```tsx
export function PatientProfileForm({ patient }: { patient: Patient }) {
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState<string | null>(null);

  return (
    <Card>
      <CardHeader>
        <Typography variant="h2">Profile</Typography>
      </CardHeader>

      <CardContent>
        {error && <FormErrorBanner>{error}</FormErrorBanner>}

        <form onSubmit={handleSubmit} className="space-y-4">
          <Field label="First name" name="firstName" defaultValue={patient.firstName} />
          <Field label="Last name"  name="lastName"  defaultValue={patient.lastName} />
          <Field label="Email"      name="email" type="email" defaultValue={patient.email} />
          <Field label="Phone"      name="phone" hint="Optional" defaultValue={patient.phone} />

          <div className="flex justify-end gap-2 pt-2">
            <Button variant="ghost" type="button">Cancel</Button>
            <ButtonLoading loading={loading} type="submit">Save</ButtonLoading>
          </div>
        </form>
      </CardContent>
    </Card>
  );
}
```

**UX Improvements:**

- Deleted happy-talk paragraph → users scan, they don't read intros (Krug: omit needless words).
- Compressed labels (`Please enter your first name` → `First name`) → reduces reading load.
- Replaced inline `<Spinner />` with `ButtonLoading` → loading state lives where the action is, not floating in the form.
- Replaced raw error `<div>` with `FormErrorBanner` → consistent error UX, semantic styling.
- Promoted `Save` (primary) over `Cancel` (ghost) → primary action is now visually distinct.
- Wrapped in `Card` + `Typography` → DS hierarchy instead of ad-hoc `text-2xl font-bold`.
- Renamed `Submit changes` → `Save` → button states the verb of what happens, not the form mechanic.
