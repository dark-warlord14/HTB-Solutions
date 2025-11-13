# Challenge Title: Templated

- Category: Web
- Difficulty: EASY
- Link: https://app.hackthebox.com/challenges/Templated

## Challenge Description

Can you exploit this simple mistake?

![Hack The Box Challenge Screenshot](image1.png)

---

## 1. Vulnerability Summary

The application is vulnerable to Server-Side Template Injection (SSTI) due to improper handling of user-supplied input within a Jinja2 template. The initial reconnaissance revealed that the application is powered by Flask/Jinja2, strongly indicating an SSTI path.

![Powered by Flask/Jinja2](image2.png)

## 2. Solution

### 2.1. Initial SSTI Detection

- **Payload:** `{{ 7*7 }}`
- **Expected Output:** `49`
- **Observation:** The application successfully processed the Jinja2 syntax, returning `49`, which confirmed the SSTI vulnerability.

![SSTI Confirmed with 7*7](image3.png)

### 2.2. Exploiting for Remote Code Execution (RCE)

![Exploitation Step 1](image4.png)
![Exploitation Step 2](image5.png)
![Flag Obtained](image6.png)

## 3. Flag

- `adminHTB{t3mpl4t3s_4r3_m0r3_p0w3rfu1_th4n_u_th1nk!}`

## 4. Tools Used & References

### Tools Used

- `Burp Suite`
