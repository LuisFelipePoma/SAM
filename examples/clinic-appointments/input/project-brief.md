# Clinic Appointments - Project Brief

## 1. Problema De Negocio

A private clinic chain manages patient appointments through phone calls, spreadsheets and isolated calendars. This causes double-bookings, missed appointments, slow rescheduling and poor visibility for clinic managers.

## 2. Objetivo Del Sistema

Create a web system for patients, receptionists and doctors to schedule, reschedule, cancel and monitor medical appointments across clinics.

## 3. Alcance Inicial / MVP

Included:

- Patient registration and login.
- Search doctor availability by specialty, location and date.
- Book, reschedule and cancel appointments.
- Receptionist appointment management.
- Doctor daily schedule view.
- Email/SMS notification request to an external provider.

Out of initial scope:

- Payments.
- Electronic medical records.
- Insurance authorization.
- Telemedicine video calls.

## 4. Stakeholders

| Stakeholder | Interest |
| --- | --- |
| Patients | Book appointments quickly and receive reminders. |
| Receptionists | Manage schedules without double-booking. |
| Doctors | See an accurate daily schedule. |
| Clinic managers | Monitor appointment volume and no-shows. |
| IT operations | Deploy and monitor the system with low support effort. |

## 5. Funcionalidades Principales

- CA-1: Register and log in.
- CA-2: Search availability.
- CA-3: Book appointment.
- CA-4: Reschedule/cancel appointment.
- CA-5: Receptionist manages doctor calendars.
- CA-6: Doctor views daily schedule.
- CA-7: Send notification request.

## 6. Atributos De Calidad Esperados

- Consistency: avoid double-booking.
- Availability: booking must remain available during business hours.
- Performance: availability search must be fast.
- Security/privacy: protect patient personal data.
- Modifiability: support future payment and telemedicine modules.
- Monitorability: track booking failures and notification failures.

## 7. Restricciones

- Web app for desktop and mobile browsers.
- MVP in 10 weeks.
- Existing clinic identity provider is not available; email/password login is acceptable for MVP.
- SMS/email delivery must use an external provider.
- Cloud deployment is preferred.
- Small team: 2 backend, 1 frontend, 1 QA.

## 8. Contexto Actual

Each clinic has different scheduling practices. Doctor availability changes frequently. Managers need consolidated appointment visibility but do not need medical record data in MVP.

## 9. Ambientes Y Operacion

- Development: local.
- QA: cloud test environment.
- Production: cloud production environment.
- Basic monitoring and error alerts are required.

## 10. Prioridades Del Cliente

Highest priority:

- Prevent double-booking.
- Book appointments quickly.
- Protect patient data.
- Ship MVP in 10 weeks.
