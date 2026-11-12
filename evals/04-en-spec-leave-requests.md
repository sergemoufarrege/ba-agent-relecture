# Functional Specification — Leave Request Module

Version 0.4 — Northwind Logistics Ltd (Manchester, UK) — HR Systems team

## 1. Scope

This module lets employees request annual leave and sick leave, and lets managers and HR approve them.

In scope: leave requests, approval workflow, leave balance calculation, notifications.
Out of scope: payroll calculation (handled by the PayPoint system).

## 2. Actors

- Employee: submits leave requests through the HR portal.
- Line manager: approves or rejects requests from their team.
- HR officer: manages exceptions and long absences.
- PayPoint: payroll system that receives approved absences.

## 3. Business rules

- **BR-01**: An employee cannot request leave for dates in the past, except sick leave.
- **BR-02**: Annual leave requests of up to 5 consecutive days are approved by the line manager.
- **BR-03**: Annual leave requests of more than 3 consecutive days must be approved by an HR officer.
- **BR-04**: Leave balance is accrued monthly at 2.08 days per month for full-time employees.
- **BR-05**: Part-time employees accrue leave pro rata, as defined in BR-11.
- **BR-06**: Sick leave of more than 7 calendar days requires a fit note uploaded by the employee.
- **BR-07**: A request cannot be submitted if the employee's remaining balance is insufficient.

Requests should be processed in a timely manner.

## 4. Data model

**LEAVE_REQUEST**

| Field | Type | Mandatory |
|---|---|---|
| request_id | UUID | Yes |
| employee_id | UUID | Yes |
| leave_type | | Yes |
| start_date | Date | Yes |
| end_date | Date | Yes |
| days_requested | Decimal (4,1) | Yes |
| status | List: DRAFT, SUBMITTED, APPROVED, CANCELLED | Yes |
| rejection_reason | Text (500) | No |

## 5. Workflow

1. The employee creates a request (status DRAFT).
2. The employee submits the request (status SUBMITTED).
3. The request is reviewed (status PENDING_REVIEW).
4. The request is approved (status APPROVED) or rejected (status REJECTED).
5. Approved absences are sent to PayPoint.

## 6. Functional requirements

- **FR-01**: The employee can create, save as draft and submit a leave request.
- **FR-02**: The employee can see their remaining leave balance before submitting.
- **FR-03**: The line manager sees a list of pending requests for their team.
- **FR-04**: The approver can approve or reject a request, with a reason for rejection.
- **FR-05**: The employee is kept informed of their request.
- **FR-06**: HR can view all absences across the company.
