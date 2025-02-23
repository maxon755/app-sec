## Task 1. The difference between SAST and DAST activities

**SAST** (static application security testing) - the reviewing software source code to identify sources of vulnerabilities. Could be done ether manually or with static analysis tools.

**DAST** (static application security testing) - non-functional application testing process to identify security weaknesses and vulnerabilities.

|                               | SAST        | DAST       |
| ----------------------------- | ----------- | ---------- |
| SDLC stage                    | development | deployment |
| visibility                    | white-box   | black-box  |
| language specific             | yes         | no         |
| can be automated              | yes         | yes        |
| can cover 100% of source code | yes         | no         |
| can harm application          | no          | yes        |
|                               |             |            |

## Task 2. Testing for Cookies Attributes
The testing for Cookies Attributes means:
- Reviewing the current Cookies configuration.
- Locking down Cookies attributes (Secure, HttpOnly, etc) and limiting their attack surface as much as possible while still meeting application needs.

## Task 3. How to prevent Software and Data Integrity Failures
To Software and Data Integrity Failures the following measure can be performed:
- Use digital signatures or similar mechanisms to verify the software or data is from the expected source and has not been altered.

- Ensure libraries and dependencies, such as npm or Maven, are consuming trusted repositories. If you have a higher risk profile, consider hosting an internal known-good repository that's vetted.

- Ensure that a software supply chain security tool, such as OWASP Dependency Check or OWASP CycloneDX, is used to verify that components do not contain known vulnerabilities

- Ensure that there is a review process for code and configuration changes to minimize the chance that malicious code or configuration could be introduced into your software pipeline.

- Ensure that your CI/CD pipeline has proper segregation, configuration, and access control to ensure the integrity of the code flowing through the build and deploy processes.

- Ensure that unsigned or unencrypted serialized data is not sent to untrusted clients without some form of integrity check or digital signature to detect tampering or replay of the serialized data.
