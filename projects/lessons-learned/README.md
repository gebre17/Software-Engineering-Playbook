# Lessons Learned & Post-Mortems

A record of technical debt, production incident reviews, and development lessons discovered during projects.

## post-mortem Template

### Incident Details
*   **Date:** YYYY-MM-DD
*   **Duration:** e.g., 45 minutes
*   **Impact:** e.g., 10% of API requests returned 500 errors.

### What Happened?
High-level description of the root cause (e.g., database connection pool exhaustion due to missing `select_related` in a loop).

### Timeline
*   `13:00` - Incident triggered/reported by monitoring system.
*   `13:10` - Team isolated host and restarted service.
*   `13:45` - Fixed DB connection pool limits and successfully restored services.

### Action Items
- [ ] Add monitoring alerts for connection counts.
- [ ] Refactor slow queries.
- [ ] Document proper local database configurations.
