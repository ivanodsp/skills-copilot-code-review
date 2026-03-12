---
applyTo: "src/backend/**/*.py,src/*.py"
---

# Backend-Specific Guidelines

## Scope
These instructions apply to backend Python files in `src/backend/` and backend entrypoints in `src/`.

## API and Routing
- Define HTTP endpoints in `src/backend/routers/`.
- Keep route handlers thin and move reusable logic to helper functions or service-style modules.
- Use clear request and response models when applicable.

## Data and Persistence
- Centralize database access patterns in `src/backend/database.py` or dedicated backend modules.
- Avoid hardcoded data in route handlers when it should come from the data layer.
- Keep sample or seed data clearly separated from runtime logic.

## Error Handling and Validation
- Validate incoming data and return explicit, user-safe error messages.
- Prefer explicit exception handling over silent failures.
- Do not expose stack traces, secrets, or internal implementation details in API responses.

## Security
- Sanitize and validate user input.
- Prevent leaking sensitive data in logs and responses.
- Prefer configuration from environment variables or secure config sources.

## Code Quality
- Reduce duplication and keep naming consistent.
- Prioritize readability and maintainability over premature optimization.
- If a hot path is used frequently, optimize with measured changes.

## Frontend Compatibility
- When changing API contracts, confirm expected behavior with frontend usage in `src/static/`.
- Call out breaking changes clearly in pull requests.
