
# 🚇 Metro-Ticket-Generating-System — ServiceNow

Automated, accessible, and fast metro ticket generation using **ServiceNow**, powered by dynamic **QR code** generation for contactless entry and exit.

![Platform](https://img.shields.io/badge/Platform-ServiceNow-2E7D32?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## 📌 Project Overview

Commuters currently rely on manual counters, third-party apps, or ticket vending machines that are often slow, inaccessible, or offline-dependent. This project re-imagines metro ticket booking as a **ServiceNow-powered digital service**, allowing users to book tickets through a request portal, receive instant confirmation, and validate travel via an auto-generated **QR code** — all backed by ServiceNow's workflow, automation, and data management capabilities.

---

## 🗂️ Table of Contents

- [Phase 1: Requirement Analysis & Planning](#phase-1-requirement-analysis--planning)
- [Phase 2: Backend Development & Configuration](#phase-2-backend-development--configuration)
- [Phase 3: UI/UX Development & Customization](#phase-3-uiux-development--customization)
- [Phase 4: Data Migration, Testing & Security](#phase-4-data-migration-testing--security)
- [Phase 5: Deployment, Documentation & Final Presentation](#phase-5-deployment-documentation--final-presentation)
- [Documentation Set](#-documentation-set)
- [Scalability & Future Roadmap](#-scalability--future-roadmap)
- [Conclusion](#-conclusion)


---

## Phase 1: Requirement Analysis & Planning

**Business Objectives**
- Eliminate manual/paper-based ticketing and long queue times.
- Provide a self-service digital booking channel accessible on web and mobile.
- Reduce ticket-counter operational load and human error.
- Enable real-time ticket validation via QR scanning at gates.

**Functional Scope**
- Source/destination station selection, fare calculation, and passenger count.
- Instant ticket generation with a unique QR code per booking.
- Booking history, cancellation, and refund workflow.
- Admin dashboard for fare management, station master data, and reporting.

**Stakeholder Mapping**
| Stakeholder | Role |
|---|---|
| Commuters (End Users) | Book tickets, scan QR at gates |
| Metro Operations Team | Manage stations, fares, and reports |
| ServiceNow Admin | Platform configuration, roles, ACLs |
| Station Staff | Handle exceptions, manual overrides |
| Project Sponsor | Approves scope, budget, and timelines |

**Execution Roadmap**
A phased delivery model — Planning → Backend → UI/UX → Testing & Security → Deployment — with milestone sign-offs at the end of each phase.

---

## Phase 2: Backend Development & Configuration

**Data Architecture**
- Custom tables: `Station Master`, `Fare Matrix`, `Ticket Booking`, `Passenger Details`, `Transaction Log`.
- Relationships built using reference fields (e.g., Ticket Booking → Station Master).

**Automation Logic**
- Flow Designer / Business Rules to auto-calculate fare based on station distance.
- Scheduled jobs for ticket expiry and auto-cancellation of unpaid bookings.
- Integration Hub / REST API for QR code generation and payment gateway callback handling.

**Business Rules**
- Auto-generate a unique Ticket ID and QR payload on record insert.
- Validate seat/quota and station pair before confirming a booking.
- Trigger notifications (Email/SMS) on booking confirmation and cancellation.

---

## Phase 3: UI/UX Development & Customization

**Interface Design**
- Service Portal widget for ticket booking with a clean, mobile-first layout.
- QR code rendered directly on the confirmation page and downloadable as PDF/image.

**Navigation Flow**
`Home → Select Station Pair → Choose Passengers → Fare Summary → Payment → QR Ticket Confirmation → My Bookings`

**Usability**
- Minimal-click booking flow (target: 3 steps to book).
- Accessible design (screen-reader labels, high-contrast theme, responsive layout).
- Multilingual support consideration for wider commuter accessibility.

---

## Phase 4: Data Migration, Testing & Security

**Data Handling**
- Migration of existing station, fare, and route master data into ServiceNow tables.
- Data validation scripts to check for duplicates and orphaned references.

**Access Control**
- Role-based ACLs: `metro_user`, `metro_admin`, `metro_staff`.
- Field-level security on fare configuration and passenger PII data.

**QA Testing**
- Unit testing of business rules and flows.
- UAT (User Acceptance Testing) with sample commuter scenarios.
- Load testing for peak-hour booking simulation.

**Data Integrity**
- Audit logging on all booking and cancellation transactions.
- Scheduled data reconciliation between bookings and payment records.

---

## Phase 5: Deployment, Documentation & Final Presentation

**Troubleshooting**
- Maintained an issue log with root-cause analysis for defects raised during UAT.
- Rollback plan defined for update set deployment failures.

**Adherence to Timelines**
- Delivered against the phase-wise roadmap with milestone checkpoints.

**Innovation**
- QR-based contactless validation, reducing physical ticket dependency.
- Automated fare computation removing manual fare-chart lookups.

---

## 📚 Documentation Set

| Document | Purpose |
|---|---|
| **Functional Overview** | Describes what the system does from a business/user perspective |
| **Technical Blueprint** | Details table schemas, flows, business rules, and integrations |
| **Setup Manual** | Step-by-step guide to install/configure the application in a ServiceNow instance |

---

## 🚀 Scalability & Future Roadmap

- Integration with UPI/payment gateways for real-time payment settlement.
- Mobile app wrapper using ServiceNow Mobile Studio.
- Integration with turnstile/QR scanner hardware via IoT/Integration Hub.
- Predictive analytics on ridership trends using Performance Analytics.
- Multi-city/multi-metro-line scalability with configurable fare zones.

---

## ✅ Conclusion

This project successfully demonstrates how the **ServiceNow platform** — typically used for enterprise IT service management — can be extended to build a **citizen-facing digital service** for metro ticket booking. By combining custom data models, automated business rules, a user-friendly Service Portal interface, and dynamic QR code generation, the solution delivers a faster, more accessible, and largely automated ticketing experience compared to traditional counter-based systems.



## 📄 License

This project is released under the [MIT License](LICENSE).
