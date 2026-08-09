# Unauthenticated Access to Sensitive Academic and Personnel Data

**Severity:** Critical
**Discovery Date:** 2026-08-06
**Status:** Unresolved

A web-based academic/administrative dashboard was found accessible without an authenticated session, exposing sensitive student and faculty/staff information through an authentication/access-control failure.

## Report

- [vulnerability_report.md](vulnerability_report.md)

## Evidence

- [evidence/evidence_01_staff_fields.png](evidence/evidence_01_staff_fields.png) — Faculty/staff identity and employment-related fields.
- [evidence/evidence_02_staff_contact_fields.png](evidence/evidence_02_staff_contact_fields.png) — Sensitive staff/contact-related fields.
- [evidence/evidence_03_student_fields.png](evidence/evidence_03_student_fields.png) — Student identity and academic-related fields.

## Disclosure Notice

Sensitive target-identifying information and personal records have intentionally been withheld because the issue remains unresolved. This repository documents the security issue and the categories of exposed information without increasing risk to affected individuals.
