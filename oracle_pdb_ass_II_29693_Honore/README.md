# Oracle PDB Management — Individual Assignment II

**Course:** Database Development with PL/SQL (INSY 8311)
**Student:** NGOGA Honore
**Student ID:** 29693
**Instructor:** Eric Maniraguha
**Submission Date:** September 22, 2026
**Repository link:**https://github.com/NGOGA-Honore/oracle_pdb_ass_II_29693_Honore.git
## Overview

This repository documents the completion of Individual Assignment II, covering
Oracle Pluggable Database (PDB) creation, management, deletion, and monitoring
via Oracle Enterprise Manager (OEM). All four required tasks were completed
individually using Oracle Database 21c Express Edition.

## Oracle Environment Used

- **Database:** Oracle Database 21c Express Edition (XE)
- **OS:** Windows
- **Tools:** Oracle SQL Developer, Oracle Enterprise Manager (OEM) Express
- **Container Database:** XE
- **HTTPS Port (OEM):** 5500

## Task Explanations

### Task 1 — Create a New Pluggable Database
Created pluggable database `HO_PDB_29693` from the PDB seed using
`CREATE PLUGGABLE DATABASE`, opened it, and saved its state so it persists
across restarts. Created user `honore_plsqlauca_29693` inside the PDB with
`CONNECT`, `RESOURCE`, and `DBA` privileges. This account will be reused for
future coursework.
📁 Evidence: [`Screenshots/pdb_creation/`](./Screenshots/pdb_creation)

### Task 2 — Create and Delete a PDB
Created a temporary pluggable database `HO_TO_DELETE_PDB_29693`, verified its
existence via `v$pdbs`, then closed and dropped it including its datafiles.
Re-queried `v$pdbs` to confirm it no longer exists.
📁 Evidence: [`Screenshots/pdb_deletion/`](./Screenshots/pdb_deletion)

### Task 3 — Oracle Enterprise Manager (OEM) Setup
Retrieved the OEM HTTPS port using `dbms_xdb_config.gethttpsport()`, accessed
OEM Express at `https://localhost:5500/em`, and logged in with the PDB user
created in Task 1. Confirmed the dashboard reflects the Oracle environment and
displays the logged-in username.
📁 Evidence: [`Screenshots/oem_dashboard/`](./Screenshots/oem_dashboard)

### Task 4 — Documentation & Reporting
This README and the organized repository structure constitute the
documentation deliverable for this assignment.

## Challenges Faced

- Initially connected to the database via the `XEPDB1` service name, which
  placed the session inside a PDB rather than the root container (`CDB$ROOT`).
  Resolved by running `ALTER SESSION SET CONTAINER = CDB$ROOT;` before
  creating new pluggable databases.
- Encountered an `ORA-01017: invalid username/password` error when first
  attempting to connect as `SYSDBA`. Resolved by verifying credentials and
  reconnecting with the correct SYS password and SYSDBA role.

## Academic Integrity Statement

I, NGOGA Honore, confirm that this assignment was completed individually
without copying from classmates, and that all screenshots and evidence
provided are my own work performed on my own Oracle environment.

## Submission Details

| Field | Value |
|---|---|
| Student Name | NGOGA Honore |
| Student ID | 29693 |
| PDB Name (Task 1) | HO_PDB_29693 |
| Username (Task 1) | honore_plsqlauca_29693 |
| Temporary PDB (Task 2) | HO_TO_DELETE_PDB_29693 |
| GitHub Repository | https://github.com/NGOGA-Honore/oracle_pdb_ass_II_29693_Honore |
| Submission Date | September 22, 2026 |