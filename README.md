# QloApps-VUL
Vulnerability Summary
Vulnerability Type: Insecure Token Exposure in URL / Insecure Token Handling

Description
In QloApps v1.6.1, authentication tokens are exposed in URL query parameters. This token, used for user authentication, is included in the URL during redirection, creating a significant security risk. The token’s exposure in the URL may allow unauthorized access to sensitive areas of the application.

Impact
Unauthorized Access: Exposed tokens may grant unauthorized access to protected areas.
Session Hijacking: Tokens in URLs are vulnerable to interception during transmission.
Targeted Attacks: If usernames are also exposed, attackers can target specific accounts.
Affected Versions
QloApps v1.6.1

Steps to Reproduce
Access a URL within the application that redirects to a URL with an authentication token exposed in the query string.
Observe that the sensitive token is visible in the URL, creating a potential security risk.
