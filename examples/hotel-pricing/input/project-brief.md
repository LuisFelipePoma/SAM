# Hotel Pricing System - Project Brief

## 1. Problema De Negocio

AD&D Hotels needs to replace a legacy pricing system that has reliability, performance, availability and maintainability issues. These issues have caused financial losses and make modernization harder.

## 2. Objetivo Del Sistema

Create a new Hotel Pricing System that lets authorized users manage hotel prices, calculate derived rates, publish prices to external systems and serve price queries reliably.

## 3. Alcance Inicial / MVP

Included:

- Login and authorization.
- Change prices for hotels and dates.
- Query prices through UI/API.
- Manage hotels and rates.
- Publish accepted prices to the Channel Management System.

Out of initial scope:

- Full replacement of every external system.
- Non-REST query protocols in the MVP.
- Advanced revenue-management optimization.

## 4. Stakeholders

| Stakeholder | Interest |
| --- | --- |
| Sales managers | Change prices quickly and safely. |
| Commercial representatives | Query and manage prices for authorized hotels. |
| Administrators | Manage hotels, rates and user permissions. |
| Operators | Monitor publication and system reliability. |
| External systems | Consume current prices. |
| Internal stakeholders | See an MVP in 2 months and release in 6 months. |

## 5. Funcionalidades Principales

- HPS-1: Log In.
- HPS-2: Change Prices.
- HPS-3: Query Prices.
- HPS-4: Manage Hotels.
- HPS-5: Manage Rates.
- HPS-6: Manage Users.

## 6. Atributos De Calidad Esperados

- Performance for price publication.
- Reliability for accepted price changes and CMS delivery.
- Availability for price queries.
- Scalability for query volume growth.
- Security for identity and authorization.
- Modifiability for future protocols.
- Deployability across environments.
- Monitorability for publication operations.
- Testability without real external systems.

## 7. Restricciones

- Browser-based UI across common platforms/devices.
- Managed cloud identity service and cloud hosting.
- Code hosted on the company's Git platform.
- MVP demo in 2 months and initial release in 6 months.
- Initial external integration through REST APIs.
- Cloud-native approach preferred.
- Team knowledge favors Java and Angular.

## 8. Contexto Actual

The company has multiple systems around hotel operations and commercial analysis. Existing integrations use REST/SOAP request-response endpoints and shared database integration anti-patterns. Enterprise architecture principles now require a more decoupled model.

## 9. Ambientes Y Operacion

- Development: local developer machines.
- Integration: cloud environment with mocks for unavailable systems.
- Staging: cloud environment connected to test versions of external systems.
- Production: real operation.

## 10. Prioridades Del Cliente

Highest priority:

- HPS-2 Change Prices.
- HPS-3 Query Prices.
- HPS-4 Manage Hotels.
- QA-1 Performance.
- QA-2 Reliability.
- QA-3 Availability.
- QA-4 Scalability.
- QA-5 Security.
