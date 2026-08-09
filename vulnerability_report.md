# Unauthenticated Access to Sensitive Academic and Personnel Data

**Severity:** Critical
**Discovery Date:** 2026-08-06
**Status:** Unresolved
**Researcher Identity:** Withheld

## Executive Summary

A web-based academic/administrative dashboard was discovered to be accessible without an authenticated session. The exposed functionality provides access to sensitive student and faculty/staff information.

The application also discloses required parameter names when expected parameters are omitted. Supplying the required parameter(s) allows the relevant dashboard functionality to render. This constitutes an authentication/access-control failure that permits unauthenticated access to sensitive data.

## Data Exposed

### Faculty / Staff Information

Observed fields include:

- Full name
- English name
- Faculty
- Faculty group
- Academic/scientific degree
- Employment/job status
- Gender
- Age
- Date of birth
- National ID
- User code
- Email address
- Mobile number
- Sector
- Geographic distribution
- Appointment year
- Last login

### Student Information

Observed fields include:

- Student name
- Faculty
- Faculty code
- Student number
- Gender
- Nationality
- Country code
- Governorate code
- Study method
- Enrollment year
- Record/year information
- Graduation status
- Sector
- Geographic distribution

Fields above are described as observed fields; not every record necessarily contains every field.

## Impact

The dashboard interface appeared to represent approximately:

- 295,000 students
- 14,000 faculty/staff members

These figures were observed in the dashboard interface and were not independently verified as database counts.

Unauthenticated exposure of fields such as National ID, email address, mobile number, student number, user code, date of birth, academic information, and employment information creates a critical privacy and security impact. The exposed functionality was also observed to support data download/export; the details of this capability are intentionally not described.

## Reproduction

1. Access the affected dashboard without an authenticated session.
2. No normal login requirement is enforced.
3. Omitting required parameters causes the application to disclose the missing parameter name(s).
4. Supplying the required parameter(s) allows the relevant dashboard functionality to render.
5. Sensitive data fields become accessible.

> The exact target, URL, endpoint, parameters, requests, and extraction procedures are intentionally withheld because the vulnerability remains unresolved.

## Evidence

Three screenshots are referenced as evidence demonstrating the exposed data-field structure. No personal records visible in the screenshots are reproduced in this report.

| # | File | Description |
|---|------|-------------|
| 1 | `evidence/evidence_01_staff_fields.png` | Faculty/staff identity and employment-related fields. |
| 2 | `evidence/evidence_02_staff_contact_fields.png` | Sensitive staff/contact-related fields. |
| 3 | `evidence/evidence_03_student_fields.png` | Student identity and academic-related fields. |

## Security Classification

- **Vulnerability:** Missing Authentication / Broken Access Control
- **Impact:** Sensitive Personal and Academic Data Exposure
- **Attack Complexity:** Low
- **Privileges Required:** None Observed
- **User Interaction:** None Observed

## Remediation

- Require server-side authentication for all dashboard endpoints.
- Enforce authorization on every API, table, chart, filter, export, and download operation.
- Prevent direct access through manually supplied parameters.
- Remove verbose parameter disclosure from production errors.
- Review related APIs/endpoints for the same authorization weakness.
- Audit access logs for unauthorized access.
- Minimize sensitive fields returned to clients and exports.
- Add automated authorization tests for all sensitive endpoints.

## Disclosure Note

This public report intentionally excludes the target identity, exact URLs, parameters, personal records, exported datasets, and bulk-download procedures because the vulnerability remains unresolved. The purpose of this repository is to document the security issue and demonstrate the categories of exposed information without increasing risk to affected individuals.
