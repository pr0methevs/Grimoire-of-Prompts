# A.S.P.E.C.C.T

- Audience: The people (or system) who will receive the output. Include demographics, expertise level, and key goals.

- Scope: The boundaries of the task – what the model should cover and what to leave out.

- Problem: The specific issue, question, or objective the prompt is meant to address.

- Example: A concrete instance or prior output that shows the desired format or style.

- Context: Background information, situation, or domain knowledge that frames the problem.

- Constraints: Rules, limits, or requirements the model must obey (e.g., word count, style guidelines).

- Tone: The desired voice, formality, or attitude of the output.


#### A.S.P.E.C.C.T Prompt Example

**Audience**  
You are a senior software engineer (Java 21 + Spring Boot 3, Angular 19) with 8+ years of full‑stack experience.  
The output will be read by your teammates who are comfortable with clean‑architecture principles and TypeScript.

**Scope**  
Design a **“User Invitation”** feature that allows an admin to invite users via email.  
The backend should expose a REST endpoint `/api/invitations` and the Angular front‑end should provide a form component `InviteUserComponent`.  
You only need to provide:  
1. A high‑level architecture diagram (text‑only).  
2. Key Java classes/interfaces (service, controller, DTO).  
3. Key Angular component template and service snippets.  
4. Brief unit‑test strategy.

**Problem**  
Admins need to invite new users securely while:
- ensuring email uniqueness,
- generating a one‑time token that expires in 48 hrs,
- sending a well‑formatted invitation email,
- providing a frontend that validates the email client‑side and shows meaningful error messages.

**Example**  
> **Java DTO**  
> ```java
> public record InviteRequest(String email, String role) {}
> ```  
> **Angular template snippet**  
> ```html
> <input type="email" [(ngModel)]="email" required />
> ```

**Context**  
- The application already uses Spring Security with JWT.
- Email service is provided via a third‑party API (SendGrid).
- The front‑end uses Angular Material.

**Constraints**  
- Java version 21, Spring Boot 3.0.  
- Angular 19, TypeScript 5.0.  
- No external state‑management library (use `BehaviorSubject` only).  
- The token generation must use `java.util.UUID` and be stored in a JPA entity `Invitation`.  
- All code must compile without warnings.

**Tone**  
Clear, concise, and professional.  
Use bullet points where appropriate.  
Use mermaid diagrams to show flow and relationship where appropriate.
Include brief comments to explain non‑obvious choices.

---

**Prompt to the LLM**

> *"Act as the senior engineer described above and deliver the architecture diagram, Java and Angular code snippets, and test strategy as specified in the scope. Keep the output concise, use markdown, and adhere strictly to the constraints."*