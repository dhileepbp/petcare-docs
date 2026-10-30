# PetCare Pro User Guide

This guide explains how to set up and run a pet care business in PetCare Pro. It is written against the **DoggyVille** workspace and follows the order in which you should configure a new business: first what you sell (services), then where you sell it (branches), then who does the work (roles, employees, schedules), and finally day-to-day operations (customers, bookings, tasks).

Every chapter shows the real screen, with **numbered red callouts** that match the numbered list under each screenshot.

## Start here: recommended setup order

Follow these steps in order. Each step lists what it depends on.

| Step | Do this | Chapter | Why this order |
|------|---------|---------|----------------|
| 1 | Sign in and learn the layout | [1. Getting started](01-getting-started.md) | |
| 2 | Review workspace settings and feature flags | [14. Settings](14-settings.md) | Feature flags decide which modules appear in the sidebar |
| 3 | Create the **services** you offer | [2. Services](02-services.md) | Branches and employees refer to services |
| 4 | Create **roles** and set their access | [4. Roles & permissions](04-roles-permissions.md) | Employees must have a role |
| 5 | Create **branches**, assign services, set hours, capacity and prices | [3. Branches](03-branches.md) | Employees must belong to a branch |
| 6 | Add **employees**, then map them to services | [5. Employees](05-employees.md) | Needs at least one branch and one role |
| 7 | Set **schedules** (shifts) for each employee | [6. Schedules](06-schedules.md) | Needs employees and branches |
| 8 | Define **task templates** for each service | [10. Tasks & operations](10-tasks-operations.md) | Tasks hang off services |
| 9 | Add **customers and pets** | [8. Customers & pets](08-customers-pets.md) | Bookings need a customer and a pet |
| 10 | Take **bookings** | [9. Bookings](09-bookings.md) | Needs everything above |

## All chapters

1. [Getting started: sign in and navigation](01-getting-started.md)
2. [Services](02-services.md)
3. [Branches: locations, service assignment, capacity, pricing](03-branches.md)
4. [Roles & permissions](04-roles-permissions.md)
5. [Employees: add, roles, service assignments](05-employees.md)
6. [Schedules: shifts, weekly template, default schedule](06-schedules.md)
7. [Dashboard](07-dashboard.md)
8. [Customers & pets](08-customers-pets.md)
9. [Bookings, calendar, and daycare & boarding](09-bookings.md)
10. [Tasks, activities, and the dispatch board](10-tasks-operations.md)
11. [Inventory](11-inventory.md) *(text only: module is switched off in this workspace)*
12. [Memberships, subscriptions, and coupons](12-memberships.md)
13. [Communication and reports](13-communication-reports.md) *(text only: modules are switched off in this workspace)*
14. [Settings, feature flags, labels, vaccine types](14-settings.md)
15. [Timesheets](15-timesheets.md)

## How to read the screenshots

- A red outline with a **numbered badge** marks an element. The number matches the list below that screenshot.
- Required fields are marked with a red `*`. Every form also shows **"* Fields are required"** at the top.
- Forms were filled with sample values only to show how they look, and then closed without saving. **One exception:** during an early capture run, two test services named *Premium Grooming* were saved by mistake. They were removed from the Services list afterwards (the app's delete only hides a record, so two hidden rows remain in the database). A read-only check after the final runs showed 3 services, 1 branch, 8 roles, and 2 employees, matching the starting state.
- The sample records you see (customer `c1`, pet `pet1`, employees `worker1` and `staff1`) are test data that already existed in the DoggyVille workspace.
- Amounts are in Indian rupees (₹).

## What is and is not covered by screenshots

| Status | Chapters |
|--------|----------|
| Screens captured from the running app | Chapters 1-10, 12, 14, and the team view in 15 |
| Written from the application's source code, no screenshot | Inventory (11), Communication and Reports (13), Monthly Overview, the second and third steps of the New Booking wizard, the Assign service dialog, pet vaccinations, task approval, service execution |

The reason: Inventory, Communication, and Reports are switched **off** for DoggyVille (see [Feature flags](14-settings.md#feature-flags)), and the app redirects away from them. Where a section is based on source code, it says so at the top.

## Known quirks in the current build

These were noticed while capturing. They are described where they apply, and are listed here so you can raise them with your administrator or developer.

- The **delete confirmation for a service** says the service "will be permanently removed", but the application only hides it (a soft delete).
- The **Booking Calendar** opened on Thursday 29 October 2026 while the Dashboard and Daycare & Boarding pages showed Friday 30 October 2026.
- For the admin account used in the screenshots, the sidebar shows **My Timesheet** and **Monthly Overview**, while the product code defines a single **Timesheet** link for admins.
- The older **Create Booking dialog** labels the amount field in dollars (`Amount ($)`), while the rest of the product uses rupees.

## Re-creating the screenshots

The screenshots are produced by scripts built on Stagehand v4, in `tools/doc-capture/`. See [tools/doc-capture/README.md](../../tools/doc-capture/README.md).
