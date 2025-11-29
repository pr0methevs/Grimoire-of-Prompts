# C.R.A.F.T 

- Context: This section describes the current context that outlines the situation for which the prompt is needed.  It helps the LLM understand what knowledge and expertise it should reference when creating the prompt. 

- Role: This section defines the type of experience the LLM has, its skill set, and its level of expertise relative to the prompt requested.  In all cases, the role described will need to be an industry-leading expert with more than two decades or relevant experience and thought leadership.

- Action: This is the action that the prompt will ask the LLM to take.  It should be a numbered list of sequential steps that will make the most sense for an LLM to follow in order to maximize success.

- Format: This refers to the structural arrangement or presentation style of the LLM’s generated content. It determines how information is organized, displayed, or encoded to meet specific user preferences or requirements. Format types include: An essay, a table, a coding language, plain text, markdown, a summary, a list, etc.

- Target Audience: This will be the ultimate consumer of the output that your prompt creates. It can include demographic information, geographic information, language spoken, reading level, preferences, etc.


**C.R.A.F.T Prompt Example – “User Invitation” Feature (Java + Angular)**

**Context**  
Your organization is deploying a new “User Invitation” feature that lets site administrators invite new users via email.  
- Backend stack: Spring Boot 3.0 (Java 20) + JPA/Hibernate  
- Front‑end stack: Angular 19+ TypeScript 5.0 + Angular Material  
- Existing auth: JWT‑based Spring Security  
- Email provider: SendGrid (REST API)  
- The feature must enforce email uniqueness, generate a one‑time 48 hr token, send a templated email, and provide a client‑side form that validates input and displays errors.

**Role**  
Act as a senior full‑stack software architect with **20+ years** of industry experience (Java, Spring, Angular, REST APIs, CI/CD).  
You are a thought‑leader in clean‑architecture practices and have mentored teams on secure user‑management features.

**Action**  
1. **Design** a high‑level system diagram (text‑only) that shows component interactions (API, DB, email service).  
2. **Specify** the Java data‑model: a JPA `Invitation` entity, a `InviteRequest` DTO, and a `InvitationService` interface.  
3. **Create** the REST controller method signature for `POST /api/invitations` with validation annotations.  
4. **Draft** the Angular component (`InviteUserComponent`) template and the corresponding service (`InvitationService`).  
5. **Outline** a unit‑test strategy for both back‑end and front‑end code, including key test cases and mocking strategies.  
6. **Return** the code snippets in fenced code blocks with brief explanatory comments.

**Format**  
Produce the output in **Markdown**:  
- A text‑only diagram using ASCII art or simple bullet lists.  
- Java classes in ` ```java ` fences, Angular files in ` ```typescript ` / ` ```html ` fences.  
- Test strategy as a numbered list.  
- Use inline comments to clarify non‑obvious design decisions.

**Target Audience**  
- Mid‑level Java developers (Spring)  
- Front‑end developers (Angular)  
- Technical leads reviewing architectural decisions  
- Readable by developers with a solid grasp of REST, JPA, and Angular 15 but not necessarily expert in security tokens.

---

**Prompt to the LLM**

> *“Act as the senior architect described above and perform the six actions listed. Keep the output concise, organized in Markdown, and adhere to the specified format.”*