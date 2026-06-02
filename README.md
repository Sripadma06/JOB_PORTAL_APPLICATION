# Job Portal JSP/Servlet Project

This project scaffolds a two-sided job portal using `JSP + Servlet + JDBC + MySQL`.

## Modules

- Candidate flow: register, login, search/filter jobs, view details, apply with resume upload
- Recruiter flow: login, post jobs, view applications received for posted jobs
- Database design: `users`, `jobs`, `applications`, `skills`, `job_skills`

## Setup

1. Create the MySQL schema using `src/main/resources/database/schema.sql`.
2. Update DB settings with environment variables if needed:
   `JOB_PORTAL_DB_URL`
   `JOB_PORTAL_DB_USER`
   `JOB_PORTAL_DB_PASSWORD`
3. Build as a WAR with Maven and deploy to Tomcat 10+.

## Seed Admin

- Email: `admin@jobportal.com`
- Password hash is pre-seeded in SQL for the literal password: `admin123`

## Notes

- Resume upload is handled in `ApplyJobServlet` via Servlet `Part` API.
- Job filtering uses dynamic SQL with `PreparedStatement`.
- Skills are normalized through `skills` and `job_skills`.
