# PASTA Worksheet — Sneaker Company App

| Stage | Description |
|---|---|
| **I. Define business and security objectives** | - The app should connect buyers and sellers and allow easy account management.<br>- Users must be able to make quick and secure payments through multiple options.<br>- The system must protect user data and ensure privacy during all transactions. |
| **II. Define the technical scope** | Focused on the API as the main gateway. Any vulnerability here could put sensitive data at risk. Securing it helps keep other components (SQL, PKI) safe. |
| **III. Decompose application** | [PASTA data flow diagram](https://docs.google.com/presentation/d/1Y6R0NBqz9mSUOpBY6NtS4aa-sk6cHsGDYhoqS0CrMm4/edit?usp=sharing) |
| **IV. Threat analysis** | **Internal Threat:** Insider misuse — privileged employee accesses/modifies customer data or transaction records without authorization.<br>**External Threat:** Phishing attack leading to unauthorized access — attacker steals user credentials to access accounts.<br>**Detection:** Monitor system logs and unusual access patterns. |
| **V. Vulnerability analysis** | - Broken access control / excessive privileges<br>- Injection (e.g., SQL injection) / poor input validation |
| **VI. Attack modeling** | - SQL Injection — Lack of prepared statements → attacker reads/modifies DB.<br>- Session hijacking — Weak login credentials / stolen tokens → attacker takes over account and accesses data. |
| **VII. Risk analysis and impact** | - Prepared statements / Parameterized queries<br>- Strong login credentials + MFA (Multi-Factor Authentication)<br>- Audit logs & monitoring<br>- Input validation / Data sanitization |
