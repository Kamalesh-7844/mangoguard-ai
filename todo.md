# Project TODO

- [x] Establish MangoGuard AI visual system, responsive shell, and working navigation
- [x] Add landing page hero, agricultural AI visual treatment, stats, product story, feature highlights, and CTAs
- [x] Define database schema for users, diseases, and prediction history
- [x] Add disease library seed content for all six prediction classes
- [x] Implement deterministic hash-based mock prediction with image preprocessing contract
- [x] Implement prediction API contract and protected history query/delete flows
- [x] Implement authenticated analysis workflow with upload validation, preview, replacement, and staged progress
- [x] Implement prediction result view with confidence ring, severity treatment, explanation, guidance, and probability chart
- [x] Implement dashboard summary cards, history search/filter/sort/detail/delete, and analytics charts
- [x] Implement disease library and disease detail views
- [x] Implement About AI pipeline and model-performance presentation
- [x] Implement login, registration, remembered session, and password recovery experience using built-in auth boundaries
- [x] Add seeded/mock records and clear simulated-ML documentation in README
- [x] Add Vitest coverage for prediction determinism, probability validity, and core backend behavior
- [x] Run type checks, tests, and visual responsive verification
- [x] Save final project checkpoint for delivery

## Gap fixes

- [x] Wire the active prediction flow to one backend path with preprocessing metadata and no duplicate frontend-only prediction logic
- [x] Persist successful analyses and scope history deletion by both user id and prediction id
- [x] Require authentication for analysis/history actions and add a usable sign-in entry point
- [x] Add dashboard filter, sort, view-details, and disease-distribution chart controls
- [x] Add login/register/remember-me/forgot-password UX states around the built-in auth boundary
- [x] Verify landing, analysis, dashboard, library, and About AI at mobile and tablet breakpoints
- [x] Save a final checkpoint after all validations pass

## Final alignment fixes

- [x] Wire dashboard history to protected history queries and mutations, gating access behind authenticated state
- [x] Adapt account screens to the actual built-in Manus OAuth flow instead of presenting non-functional password actions
- [x] Add truthful account-state messaging and remove pseudo recovery/register behavior

## Server-backed history hardening

- [x] Render authenticated dashboard history exclusively from the protected server query
- [x] Add protected history loading, error, and empty states
- [x] Invalidate protected history after deletion so the UI stays consistent

## Final mutation consistency

- [x] Remove local seeded-history mutation from authenticated dashboard deletion
- [x] Confirm protected deletion only after mutation success and report failures accurately

## OAuth redirect bug

- [x] Replace any 127.0.0.1 OAuth redirect generation with the current browser origin
- [x] Validate the OAuth login URL and callback behavior in preview and build output
- [x] Save an updated checkpoint after the OAuth fix
