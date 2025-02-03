# CVE Request: Insecure Token Exposure in QloApps v1.6.1

## Vulnerability Summary
- **Vulnerability Type:** Insecure Token Exposure in URL  
- **Affected Product:** QloApps v1.6.1  
- **Severity:** High  

## Description
QloApps v1.6.1 exposes authentication tokens in URLs during redirection, posing a significant security risk. When users access the admin panel or other protected areas, the application appends sensitive authentication tokens directly to the URL.

### Security Risks:
- **Stored in browser history:** Tokens may be retained and exposed on shared or compromised devices.  
- **Logged in web servers and proxies:** Full URLs, including tokens, may be stored in logs, potentially accessible by unauthorized entities.  
- **Intercepted in unsecured connections:** Without HTTPS enforcement, attackers can sniff network traffic and hijack sessions.  
- **Leaked through referrer headers:** Tokens in URLs may be sent to third-party sites when users navigate away from the application.  

This vulnerability increases the risk of **unauthorized access**, **session hijacking**, and **privilege escalation**, potentially allowing attackers to compromise the admin panel.

## Impact
- Unauthorized access to administrative functions.  
- Session hijacking leading to account takeovers.  
- Increased risk of targeted attacks if additional user identifiers are exposed.  

## Steps to Reproduce
1. Access the URL: `http://localhost/admin/index.php?controller`.  
2. Observe that the application redirects to a URL containing a sensitive authentication token:  
http://localhost/admin/index.php?controller=AdminLogin&token=6e47735650164e22315756daa6199fee

3. The token is visible in the URL and can be intercepted, logged, or manipulated.  

## Recommended Mitigations
- Store authentication tokens securely (e.g., in HTTP-only cookies or headers instead of URLs).  
- Implement session expiration and token invalidation mechanisms.  
- Enforce HTTPS to prevent token interception.  
- Avoid including sensitive information in referrer headers.  

---

### **3. Commit and Push**
- Scroll down and click **Commit new file**.  
- This will save the file in your repository.  

### **4. Share the Report**  
- You can share your GitHub repository link in security forums, on CVE request platforms, or with the QloApps team for responsible disclosure.  

Let me know if you need any help with GitHub commands or formatting!
