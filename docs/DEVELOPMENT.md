# FusionTech Development Guide

## Development Philosophy

FusionTech is organized around a maintainable frontend architecture with reusable components, shared application services, and optional external integrations.

The source repository is private, so this public document focuses on development principles rather than exposing repository-specific internals.

## Technology Stack

Core technologies include:

- React 19
- TypeScript
- Vite
- React Router
- Tailwind CSS
- Recharts
- Lucide React

Additional capabilities use browser APIs and optional external integrations.

## Recommended Workflow

### 1. Prepare the Environment

Install a current Node.js LTS release and a package manager supported by the private source project.

### 2. Configure Environment Values

Development integrations may require environment-specific configuration for services such as email or AI.

Never commit real credentials.

Use local development configuration and provide safe example values where documentation is needed.

### 3. Run the Development Server

Use the package scripts defined by the private source repository to start the development environment.

The exact command may change as the project evolves and is therefore intentionally not duplicated in this public documentation.

### 4. Develop by Feature

A typical workflow is:

1. Identify the feature boundary.
2. Reuse shared components where possible.
3. Keep business logic outside presentation components when practical.
4. Add localization for both supported languages.
5. Verify both left-to-right and right-to-left layouts.
6. Test mobile and desktop layouts.
7. Validate optional integrations independently.
8. Review accessibility and error states.

## TypeScript Practices

Prefer:

- Explicit domain types
- Narrow interfaces
- Reusable types
- Avoiding unnecessary `any`
- Predictable async error handling
- Small focused modules

## UI Practices

New UI should consider:

- Responsive behavior
- Keyboard navigation
- Semantic HTML
- Focus states
- Loading states
- Empty states
- Error states
- Arabic RTL behavior
- Theme compatibility

## Localization

Any new user-facing string should be added to the localization system rather than hard-coded into a page.

When adding Arabic content, verify:

- Text direction
- Alignment
- Icon placement
- Spacing
- Form controls
- Mixed Arabic/Latin text
- Numeric presentation

## Integration Development

External integrations should fail gracefully.

For example, if an optional AI service is unavailable, core browsing and service-management functionality should remain understandable and usable where possible.

## Quality Checklist

Before considering a feature complete:

- [ ] TypeScript checks pass
- [ ] Public pages work
- [ ] Administrative workflows work
- [ ] English is tested
- [ ] Arabic is tested
- [ ] RTL layout is tested
- [ ] Mobile layout is tested
- [ ] Error states are handled
- [ ] No credentials are committed
- [ ] No sensitive configuration is exposed
- [ ] Production security assumptions are documented
