# 🧭 Self-Reliance Framework: Your First Epic Games VDP Mission

> As your senior or mentor, I truly appreciate your initiative. The desire to become independent and break free from dependency is one of the strongest signs that you have the mindset of a true hacker.
>
> In the real world, nobody will guide you step by step. You must be able to solve problems independently by using your troubleshooting, research, and critical-thinking skills.
>
> This is your **Self-Reliance Framework** for completing your first mission in the **Epic Games VDP**. Think of this framework as your primary compass.
>
> **Save this document. Whenever you feel stuck or confused, return to this compass and use it to guide your next step before deciding to ask for help.**

---

# 🛠️ Phase 1: Information Gathering (Reconnaissance)

> **Don't attack immediately.**
>
> 80% of successful hacking comes from how well you understand and map your target.

## 1. Choose One Parent Asset

From the **In-Scope** list you reviewed earlier, such as:

* `*.unrealengine.com`
* `*.rocketleague.com`

Choose **only one** for this week's session.

> **Don't try to handle everything at once. Focus is more valuable than volume.**

* [ ] Choose one in-scope parent asset.
* [ ] Write down the asset you selected.
* [ ] Define your scope clearly.
* [ ] Avoid testing assets outside the authorized scope.

---

## 2. Subdomain Enumeration

### 🎯 Objective

Discover as many relevant subdomains as possible within your authorized scope.

### 🔎 Independent Action

Research how to install and use reconnaissance tools such as:

* `subfinder`
* `amass`

Learn:

* [ ] How to install `subfinder`.
* [ ] How to install `amass`.
* [ ] How to perform basic subdomain enumeration.
* [ ] How to save enumeration results to a file.
* [ ] How to remove duplicate results.
* [ ] How to verify that discovered assets are actually within scope.

### ✅ Completion Indicator

You have successfully generated a list of potentially relevant subdomains, for example:

```text
dev-forum.unrealengine.com
auth.unrealengine.com
```

* [ ] I have generated a list of discovered subdomains.
* [ ] I have reviewed the results.
* [ ] I have confirmed that the targets are in scope.

---

## 3. Live Host Discovery

Now that you have a list of subdomains, determine which ones are actually accessible.

### 🔎 Independent Action

Research how to use:

* `httpx`

Alternatively, learn how to perform manual verification using your browser.

The goal is to distinguish between:

* **Live hosts** → Respond to requests.
* **Inactive hosts** → Do not respond or are unavailable.

Pay attention to HTTP responses such as:

* `200 OK`
* `301 Moved Permanently`
* `302 Found`
* `403 Forbidden`

> A `403 Forbidden` response can still indicate that a host is alive, even though access is restricted.

* [ ] Learn the basic usage of `httpx`.
* [ ] Identify live hosts.
* [ ] Separate live and inactive hosts.
* [ ] Record interesting HTTP status codes.
* [ ] Create a clean list of live targets.

---

# 🔍 Phase 2: Potential Attack Surface Mapping

Now you have a list of live web applications.

It's time to understand what's actually inside them.

---

## 1. Visual Analysis

Open the live subdomains one by one in your browser.

Look at:

* Login pages

* Registration pages

* User profiles

* Search functionality

* Password reset functionality

* File upload functionality

* API endpoints

* Account management pages

* Administrative functionality

* [ ] Open each live target in a browser.

* [ ] Take notes about the application's functionality.

* [ ] Identify interesting user interactions.

* [ ] Record potentially sensitive functionality.

---

## 2. Classify Based on Functionality

Prioritize pages with a high level of user interaction.

### ⭐ High-Priority Areas

Look for:

* [ ] Login functionality.
* [ ] Registration forms.
* [ ] Forgot-password functionality.
* [ ] Search fields.
* [ ] User profile functionality.
* [ ] File-upload functionality.
* [ ] Account settings.
* [ ] API interactions.
* [ ] Features that handle user-generated input.

### 📝 Lower-Priority Areas

Static pages containing only:

* Articles
* Documentation
* Informational content
* Marketing copy

These are generally less interesting for beginners because they offer fewer opportunities for meaningful interaction.

---

## 3. Identify the Technology Stack

### 🔎 Independent Action

Research the browser extension **Wappalyzer**.

Use it to identify technologies used by the target, such as:

* WordPress
* PHP
* Node.js
* JavaScript frameworks
* Web servers
* Content Management Systems (CMS)

Then research whether the identified technologies or versions have publicly known vulnerabilities.

Useful concepts to understand:

* **Known Vulnerabilities**

* **CVE (Common Vulnerabilities and Exposures)**

* **Outdated Software**

* **Security Advisories**

* [ ] Learn how Wappalyzer works.

* [ ] Identify the target's technology stack.

* [ ] Record relevant technologies and versions.

* [ ] Research known vulnerabilities.

* [ ] Verify whether a potential vulnerability is actually relevant to the target.

* [ ] Avoid blindly assuming that a known CVE applies to the target.

---

# ⚔️ Phase 3: Manual Testing (Active Pentesting)

> This is where you begin using **Burp Suite** to intercept and analyze HTTP traffic sent between your browser and the authorized target.

**Important:** Only perform active testing against assets explicitly included in the program's scope and within its rules of engagement.

---

## 1. Test Logic & Authorization Issues

This is an excellent area for beginners to study.

### 📚 Independent Learning

Study the concepts of:

* **IDOR (Insecure Direct Object Reference)**

* **BOLA (Broken Object Level Authorization)**

* **Broken Access Control**

* **Authentication Bypass**

* [ ] Understand how authentication works.

* [ ] Understand how authorization differs from authentication.

* [ ] Learn what IDOR/BOLA vulnerabilities are.

* [ ] Learn how object identifiers are used in web applications.

* [ ] Learn how Burp Suite can be used to inspect requests.

### 🧪 Authorized Practice

If the target allows public registration and the program rules permit testing with multiple accounts:

1. Create two test accounts.
2. Log in as **Account A**.
3. Capture relevant requests using Burp Suite.
4. Identify object identifiers or authorization-related parameters.
5. Compare the behavior between **Account A** and **Account B**.
6. Determine whether Account A can access or modify resources belonging to Account B.

* [ ] Create authorized test accounts.
* [ ] Capture relevant requests in Burp Suite.
* [ ] Identify potentially interesting parameters.
* [ ] Test access controls within the authorized scope.
* [ ] Confirm whether unauthorized access is actually possible.
* [ ] Stop testing if the behavior would affect real users or data.

---

## 2. Test Input Validation

### 📚 Independent Learning

Study the concepts of:

* **XSS (Cross-Site Scripting)**

* **CSRF (Cross-Site Request Forgery)**

* **Input Validation**

* **Output Encoding**

* [ ] Understand the basic concept of XSS.

* [ ] Understand the basic concept of CSRF.

* [ ] Learn how web applications process user input.

* [ ] Learn how browsers interpret HTML and JavaScript.

* [ ] Understand the role of input validation and output encoding.

### 🧪 Authorized Practice

Test input fields within the authorized scope using harmless, non-destructive test cases.

For example, investigate how the application handles:

* Special characters

* Unexpected input

* HTML-like characters

* Different data formats

* Excessively long input

* [ ] Identify interesting input fields.

* [ ] Test harmless input variations.

* [ ] Observe how the server responds.

* [ ] Determine whether input is properly validated.

* [ ] Determine whether output is properly encoded.

* [ ] Document any unusual behavior.

---

# 📋 Phase 4: Bug Reporting & Remediation

If you discover unusual or potentially vulnerable behavior, your next responsibility is to validate and document it professionally.

---

## 1. Validate the Finding

Before submitting a report, make sure the issue is **reproducible**.

Ask yourself:

* Can I reproduce the behavior?

* Does it happen consistently?

* Can I explain exactly why it happens?

* Can another researcher follow my steps?

* Is the behavior actually a security vulnerability?

* Is the issue within the program's scope?

* [ ] Reproduce the behavior.

* [ ] Verify the issue multiple times.

* [ ] Confirm that it is a genuine security issue.

* [ ] Confirm that it is within the program's scope.

* [ ] Gather the necessary evidence.

* [ ] Avoid collecting unnecessary sensitive data.

---

## 2. Write a Professional Report

Don't simply write:

> "This website can be hacked."

Instead, create a structured and professional report.

### 📝 Recommended Report Structure

#### Description

Explain:

* What is the vulnerability?

* What security concept does it relate to?

* Why does the vulnerability exist?

* [ ] Clearly explain the vulnerability.

* [ ] Explain the underlying security issue.

* [ ] Keep the explanation concise and technically accurate.

---

#### Steps to Reproduce

Provide detailed steps that allow the security team to reproduce the issue.

Example structure:

```text
1. Navigate to [authorized URL].
2. Log in using [test account].
3. Perform [specific action].
4. Intercept the request using Burp Suite.
5. Modify [parameter].
6. Send the request.
7. Observe [result].
```

* [ ] Document every necessary step.
* [ ] Include relevant request/response details.
* [ ] Make the reproduction steps easy to follow.
* [ ] Remove unnecessary sensitive information.

---

#### Impact

Explain what could happen if the vulnerability were exploited by a malicious actor.

Consider:

* Confidentiality

* Integrity

* Availability

* User accounts

* Sensitive information

* Business impact

* [ ] Explain the realistic security impact.

* [ ] Explain who or what could be affected.

* [ ] Avoid exaggerating the severity.

* [ ] Clearly distinguish demonstrated impact from theoretical impact.

---

#### Remediation

Provide a reasonable recommendation for fixing the issue.

For example:

* [ ] Explain the root cause.
* [ ] Suggest a general mitigation.
* [ ] Recommend appropriate security controls.
* [ ] Explain how the developer could prevent similar issues in the future.

---

# 🧭 The Self-Reliance Rule: Think Before You Ask

As your mentor, I apply the **"15-Minute Research Rule"** before you ask anyone for help—including me.

> **The goal isn't to prevent you from asking questions.**
>
> The goal is to make sure that when you do ask, you've already taken the first steps toward solving the problem yourself.

---

## 1. If You Encounter an Error or Get Stuck

Before asking for help:

* [ ] Copy the exact error message.
* [ ] Search for the error on Google.
* [ ] Read the official documentation.
* [ ] Check relevant GitHub issues.
* [ ] Search technical forums or trusted communities.
* [ ] Try at least one reasonable solution.
* [ ] Record what you tried and what happened.

> Many beginner problems have already been encountered and solved by someone else on the internet.

---

## 2. Use the Real-World Security Dictionary

If you encounter an unfamiliar term, don't immediately ask someone to explain it.

First, research it yourself.

For example:

* Rate Limiting
* CORS
* Cookies
* Sessions
* Tokens
* JWT
* Authentication
* Authorization
* CSRF
* XSS
* IDOR
* BOLA

A highly recommended resource for learning web security concepts is **PortSwigger Web Security Academy**.

* [ ] Identify unfamiliar terminology.
* [ ] Search for the definition.
* [ ] Read the relevant documentation.
* [ ] Study a practical example.
* [ ] Try to explain the concept in your own words.

---

## 3. Ask Better Questions

If you've spent around 15 minutes researching and you're still genuinely stuck, then ask for help.

Use this structure:

> **"Senior, I'm currently trying to perform [Action A] on target [B]. I encountered [Error/Problem C]. I've already tried [Solution D] based on my research, but the result is still the same. Which part do you think I should evaluate again?"**

Before asking:

* [ ] Explain what you are trying to accomplish.
* [ ] Clearly describe the problem.
* [ ] Include the exact error message.
* [ ] Explain what you have already tried.
* [ ] Mention what you learned from your research.
* [ ] Ask a specific question.

> A question like this shows that you are an **active learner** who is willing to think and investigate—not someone who simply expects to be spoon-fed.

---

# 🎯 Final Mission Checklist

Use this as your quick progress tracker.

### Phase 1 — Reconnaissance

* [ ] Choose one authorized in-scope asset.
* [ ] Enumerate subdomains.
* [ ] Identify live hosts.
* [ ] Verify the scope of discovered assets.

### Phase 2 — Attack Surface Mapping

* [ ] Explore live applications.
* [ ] Identify interactive functionality.
* [ ] Prioritize interesting attack surfaces.
* [ ] Identify the underlying technology stack.
* [ ] Research relevant known vulnerabilities.

### Phase 3 — Manual Testing

* [ ] Learn Burp Suite fundamentals.
* [ ] Study authentication and authorization.
* [ ] Study IDOR/BOLA.
* [ ] Study XSS and CSRF.
* [ ] Perform only authorized testing.
* [ ] Document interesting behavior.

### Phase 4 — Reporting

* [ ] Reproduce the vulnerability.
* [ ] Confirm that it is in scope.
* [ ] Document the vulnerability clearly.
* [ ] Write detailed reproduction steps.
* [ ] Explain realistic impact.
* [ ] Suggest appropriate remediation.

### Self-Reliance

* [ ] Research errors independently.
* [ ] Read official documentation.
* [ ] Research unfamiliar terminology.
* [ ] Spend at least 15 minutes troubleshooting before asking.
* [ ] Ask specific, well-researched questions.

---

# 🚀 Your Next Step

This framework covers the complete bug bounty workflow—from **reconnaissance** to **attack surface mapping**, **manual testing**, and finally **professional reporting**.

Your roadmap is now clear.

**Close this document. Open your terminal or browser. Start exploring independently.**

> **Good luck, Researcher.**
>
> **Stay curious. Stay ethical. Stay within scope.**
>
> **The goal is not merely to find bugs. The goal is to learn how to think like a security researcher.**
