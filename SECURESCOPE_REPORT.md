# SecureScope Security Report

Automated scan found **82** vulnerabilities across **0** files.

## Summary

| File | Issues | Highest Severity |
|------|--------|------------------|
| `Dockerfile` | 1 | HIGH |
| `config/db.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | HIGH |
| `docker-compose.yml` | 1 | MEDIUM |
| `docker-compose.yml` | 1 | MEDIUM |
| `models/index.js` | 1 | MEDIUM |
| `server.js` | 1 | LOW |
| `server.js` | 1 | MEDIUM |
| `server.js` | 1 | MEDIUM |
| `server.js` | 1 | MEDIUM |
| `server.js` | 1 | MEDIUM |
| `server.js` | 1 | MEDIUM |
| `server.js` | 1 | MEDIUM |
| `server.js` | 1 | MEDIUM |
| `views/app/products.ejs` | 1 | MEDIUM |
| `views/app/products.ejs` | 1 | MEDIUM |
| `views/app/products.ejs` | 1 | MEDIUM |
| `views/app/products.ejs` | 1 | MEDIUM |
| `views/app/products.ejs` | 1 | MEDIUM |
| `views/app/products.ejs` | 1 | MEDIUM |
| `core/authHandler.js` | 1 | MEDIUM |
| `core/authHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | MEDIUM |
| `Dockerfile` | 1 | CRITICAL |
| `Dockerfile` | 1 | CRITICAL |
| `startup.sh` | 1 | HIGH |
| `wait-for-it.sh` | 1 | CRITICAL |
| `wait-for-it.sh` | 1 | HIGH |
| `wait-for-it.sh` | 1 | HIGH |
| `wait-for-it.sh` | 1 | HIGH |
| `wait-for-it.sh` | 1 | HIGH |
| `wait-for-it.sh` | 1 | HIGH |
| `wait-for-it.sh` | 1 | CRITICAL |
| `wait-for-it.sh` | 1 | CRITICAL |
| `wait-for-it.sh` | 1 | CRITICAL |
| `wait-for-it.sh` | 1 | CRITICAL |
| `wait-for-it.sh` | 1 | CRITICAL |
| `wait-for-it.sh` | 1 | CRITICAL |
| `server.js` | 1 | CRITICAL |
| `entrypoint-dev.sh` | 1 | CRITICAL |
| `models/index.js` | 1 | HIGH |
| `models/index.js` | 1 | HIGH |
| `models/user.js` | 1 | MEDIUM |
| `core/authHandler.js` | 1 | HIGH |
| `core/authHandler.js` | 1 | HIGH |
| `core/authHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | CRITICAL |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | CRITICAL |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | HIGH |
| `core/appHandler.js` | 1 | MEDIUM |
| `core/appHandler.js` | 1 | HIGH |
| `core/passport.js` | 1 | HIGH |
| `core/passport.js` | 1 | CRITICAL |
| `core/passport.js` | 1 | HIGH |
| `routes/main.js` | 1 | MEDIUM |
| `routes/main.js` | 1 | HIGH |
| `routes/main.js` | 1 | HIGH |
| `routes/app.js` | 1 | HIGH |
| `routes/app.js` | 1 | HIGH |
| `routes/app.js` | 1 | HIGH |
| `config/vulns.js` | 1 | HIGH |
| `config/vulns.js` | 1 | HIGH |

## Details by File

### Other Findings

- **By not specifying a USER, a program in the container may run as 'root'. This is a security hazard. If an attacker can control a process running as root, they may have control over the container. Ensure that the last USER in a Dockerfile is a USER other than 'root'.** (HIGH) — `Dockerfile`
  By not specifying a USER, a program in the container may run as 'root'. This is a security hazard. If an attacker can control a process running as root, they may have control over the container. Ensur
- **If TLS is disabled on server side (Postgresql server), Sequelize establishes connection without TLS and no error will be thrown. To prevent MITN (Man In The Middle) attack, TLS must be enforce by Sequelize. Set "ssl: true" or define settings "ssl: {...}"** (MEDIUM) — `config/db.js`
  If TLS is disabled on server side (Postgresql server), Sequelize establishes connection without TLS and no error will be thrown. To prevent MITN (Man In The Middle) attack, TLS must be enforce by Sequ
- **Detected a sequelize statement that is tainted by user-input. This could lead to SQL injection if the variable is user-controlled and is not properly sanitized. In order to prevent SQL injection, it is recommended to use parameterized queries or prepared statements.** (HIGH) — `core/appHandler.js`
  Detected a sequelize statement that is tainted by user-input. This could lead to SQL injection if the variable is user-controlled and is not properly sanitized. In order to prevent SQL injection, it i
- **The application redirects to a URL specified by user-supplied input `req` that is not validated. This could redirect users to malicious locations. Consider using an allow-list approach to validate URLs, or warn users they are being redirected to a third-party website.** (MEDIUM) — `core/appHandler.js`
  The application redirects to a URL specified by user-supplied input `req` that is not validated. This could redirect users to malicious locations. Consider using an allow-list approach to validate URL
- **The following function call serialize.unserialize accepts user controlled data which can result in Remote Code Execution (RCE) through Object Deserialization. It is recommended to use secure data processing alternatives such as JSON.parse() and Buffer.from().** (MEDIUM) — `core/appHandler.js`
  The following function call serialize.unserialize accepts user controlled data which can result in Remote Code Execution (RCE) through Object Deserialization. It is recommended to use secure data proc
- **The libxml library processes user-input with the `noent` attribute is set to `true` which can lead to being vulnerable to XML External Entities (XXE) type attacks. It is recommended to set `noent` to `false` when using this feature to ensure you are protected.** (HIGH) — `core/appHandler.js`
  The libxml library processes user-input with the `noent` attribute is set to `true` which can lead to being vulnerable to XML External Entities (XXE) type attacks. It is recommended to set `noent` to 
- **Service 'mysql-db' allows for privilege escalation via setuid or setgid binaries. Add 'no-new-privileges:true' in 'security_opt' to prevent this.** (MEDIUM) — `docker-compose.yml`
  Service 'mysql-db' allows for privilege escalation via setuid or setgid binaries. Add 'no-new-privileges:true' in 'security_opt' to prevent this.
- **Service 'mysql-db' is running with a writable root filesystem. This may allow malicious applications to download and run additional payloads, or modify container files. If an application inside a container has to save something temporarily consider using a tmpfs. Add 'read_only: true' to this service to prevent this.** (MEDIUM) — `docker-compose.yml`
  Service 'mysql-db' is running with a writable root filesystem. This may allow malicious applications to download and run additional payloads, or modify container files. If an application inside a cont
- **Detected possible user input going into a `path.join` or `path.resolve` function. This could possibly lead to a path traversal vulnerability,  where the attacker can access arbitrary files stored in the file system. Instead, be sure to sanitize or validate user input first.** (MEDIUM) — `models/index.js`
  Detected possible user input going into a `path.join` or `path.resolve` function. This could possibly lead to a path traversal vulnerability,  where the attacker can access arbitrary files stored in t
- **A CSRF middleware was not detected in your express application. Ensure you are either using one such as `csurf` or `csrf` (see rule references) and/or you are properly doing CSRF validation in your routes with a token or cookies.** (LOW) — `server.js`
  A CSRF middleware was not detected in your express application. Ensure you are either using one such as `csurf` or `csrf` (see rule references) and/or you are properly doing CSRF validation in your ro
- **Don’t use the default session cookie name Using the default session cookie name can open your app to attacks. The security issue posed is similar to X-Powered-By: a potential attacker can use it to fingerprint the server and target attacks accordingly.** (MEDIUM) — `server.js`
  Don’t use the default session cookie name Using the default session cookie name can open your app to attacks. The security issue posed is similar to X-Powered-By: a potential attacker can use it to fi
- **Default session middleware settings: `domain` not set. It indicates the domain of the cookie; use it to compare against the domain of the server in which the URL is being requested. If they match, then check the path attribute next.** (MEDIUM) — `server.js`
  Default session middleware settings: `domain` not set. It indicates the domain of the cookie; use it to compare against the domain of the server in which the URL is being requested. If they match, the
- **Default session middleware settings: `expires` not set. Use it to set expiration date for persistent cookies.** (MEDIUM) — `server.js`
  Default session middleware settings: `expires` not set. Use it to set expiration date for persistent cookies.
- **Default session middleware settings: `httpOnly` not set. It ensures the cookie is sent only over HTTP(S), not client JavaScript, helping to protect against cross-site scripting attacks.** (MEDIUM) — `server.js`
  Default session middleware settings: `httpOnly` not set. It ensures the cookie is sent only over HTTP(S), not client JavaScript, helping to protect against cross-site scripting attacks.
- **Default session middleware settings: `path` not set. It indicates the path of the cookie; use it to compare against the request path. If this and domain match, then send the cookie in the request.** (MEDIUM) — `server.js`
  Default session middleware settings: `path` not set. It indicates the path of the cookie; use it to compare against the request path. If this and domain match, then send the cookie in the request.
- **Default session middleware settings: `secure` not set. It ensures the browser only sends the cookie over HTTPS.** (MEDIUM) — `server.js`
  Default session middleware settings: `secure` not set. It ensures the browser only sends the cookie over HTTPS.
- **A hard-coded credential was detected. It is not recommended to store credentials in source-code, as this risks secrets being leaked and used by either an internal or external malicious adversary. It is recommended to use environment variables to securely provide credentials or retrieve credentials from a secure vault or HSM (Hardware Security Module).** (MEDIUM) — `server.js`
  A hard-coded credential was detected. It is not recommended to store credentials in source-code, as this risks secrets being leaked and used by either an internal or external malicious adversary. It i
- **Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ... %>' to escape this data. If you need escaping, ensure no external data can reach this location.** (MEDIUM) — `views/app/products.ejs`
  Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ...
- **Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ... %>' to escape this data. If you need escaping, ensure no external data can reach this location.** (MEDIUM) — `views/app/products.ejs`
  Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ...
- **Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ... %>' to escape this data. If you need escaping, ensure no external data can reach this location.** (MEDIUM) — `views/app/products.ejs`
  Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ...
- **Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ... %>' to escape this data. If you need escaping, ensure no external data can reach this location.** (MEDIUM) — `views/app/products.ejs`
  Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ...
- **Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ... %>' to escape this data. If you need escaping, ensure no external data can reach this location.** (MEDIUM) — `views/app/products.ejs`
  Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ...
- **Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ... %>' to escape this data. If you need escaping, ensure no external data can reach this location.** (MEDIUM) — `views/app/products.ejs`
  Detected an explicit unescape in an EJS template, using '<%- ... %>' If external data can reach these locations, your application is exposed to a cross-site scripting (XSS) vulnerability. Use '<%= ...
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/authHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/authHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **Insecure Deserialization** (HIGH) — `core/appHandler.js`
  Data deserialization without safe loader may allow code execution.
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/appHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/appHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/appHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/appHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **Weak Cryptographic Algorithm** (MEDIUM) — `core/appHandler.js`
  A weak or deprecated cryptographic algorithm is used.
- **ML: Potential command injection** (CRITICAL) — `Dockerfile`
  ML classifier detected potential command injection (confidence: 0.90).
- **ML: Potential command injection** (CRITICAL) — `Dockerfile`
  ML classifier detected potential command injection (confidence: 0.97).
- **ML: Potential path traversal** (HIGH) — `startup.sh`
  ML classifier detected potential path traversal (confidence: 0.83).
- **ML: Potential SQL injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential sql injection (confidence: 0.79).
- **ML: Potential path traversal** (HIGH) — `wait-for-it.sh`
  ML classifier detected potential path traversal (confidence: 0.83).
- **ML: Potential path traversal** (HIGH) — `wait-for-it.sh`
  ML classifier detected potential path traversal (confidence: 0.74).
- **ML: Potential path traversal** (HIGH) — `wait-for-it.sh`
  ML classifier detected potential path traversal (confidence: 0.92).
- **ML: Potential command injection** (HIGH) — `wait-for-it.sh`
  ML classifier detected potential command injection (confidence: 0.74).
- **ML: Potential path traversal** (HIGH) — `wait-for-it.sh`
  ML classifier detected potential path traversal (confidence: 0.83).
- **ML: Potential command injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential command injection (confidence: 0.83).
- **ML: Potential command injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential command injection (confidence: 0.83).
- **ML: Potential command injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential command injection (confidence: 0.77).
- **ML: Potential command injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential command injection (confidence: 0.88).
- **ML: Potential SQL injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential sql injection (confidence: 0.97).
- **ML: Potential command injection** (CRITICAL) — `wait-for-it.sh`
  ML classifier detected potential command injection (confidence: 0.87).
- **ML: Potential command injection** (CRITICAL) — `server.js`
  ML classifier detected potential command injection (confidence: 0.97).
- **ML: Potential SQL injection** (CRITICAL) — `entrypoint-dev.sh`
  ML classifier detected potential sql injection (confidence: 0.93).
- **ML: Potential path traversal** (HIGH) — `models/index.js`
  ML classifier detected potential path traversal (confidence: 0.99).
- **ML: Potential cross-site scripting** (HIGH) — `models/index.js`
  ML classifier detected potential cross-site scripting (confidence: 0.93).
- **ML: Potential hardcoded secret** (MEDIUM) — `models/user.js`
  ML classifier detected potential hardcoded secret (confidence: 0.91).
- **ML: Potential path traversal** (HIGH) — `core/authHandler.js`
  ML classifier detected potential path traversal (confidence: 0.92).
- **ML: Potential path traversal** (HIGH) — `core/authHandler.js`
  ML classifier detected potential path traversal (confidence: 0.95).
- **ML: Potential path traversal** (HIGH) — `core/authHandler.js`
  ML classifier detected potential path traversal (confidence: 0.90).
- **ML: Potential cross-site scripting** (HIGH) — `core/appHandler.js`
  ML classifier detected potential cross-site scripting (confidence: 0.72).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.71).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.85).
- **ML: Potential command injection** (CRITICAL) — `core/appHandler.js`
  ML classifier detected potential command injection (confidence: 0.86).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.83).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.86).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.91).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.91).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.91).
- **ML: Potential SQL injection** (CRITICAL) — `core/appHandler.js`
  ML classifier detected potential sql injection (confidence: 0.89).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.91).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.91).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.96).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.85).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.87).
- **ML: Potential hardcoded secret** (MEDIUM) — `core/appHandler.js`
  ML classifier detected potential hardcoded secret (confidence: 0.73).
- **ML: Potential path traversal** (HIGH) — `core/appHandler.js`
  ML classifier detected potential path traversal (confidence: 0.99).
- **ML: Potential path traversal** (HIGH) — `core/passport.js`
  ML classifier detected potential path traversal (confidence: 0.94).
- **ML: Potential command injection** (CRITICAL) — `core/passport.js`
  ML classifier detected potential command injection (confidence: 0.77).
- **ML: Potential path traversal** (HIGH) — `core/passport.js`
  ML classifier detected potential path traversal (confidence: 0.73).
- **ML: Potential hardcoded secret** (MEDIUM) — `routes/main.js`
  ML classifier detected potential hardcoded secret (confidence: 0.81).
- **ML: Potential cross-site scripting** (HIGH) — `routes/main.js`
  ML classifier detected potential cross-site scripting (confidence: 0.83).
- **ML: Potential path traversal** (HIGH) — `routes/main.js`
  ML classifier detected potential path traversal (confidence: 0.89).
- **ML: Potential path traversal** (HIGH) — `routes/app.js`
  ML classifier detected potential path traversal (confidence: 0.86).
- **ML: Potential path traversal** (HIGH) — `routes/app.js`
  ML classifier detected potential path traversal (confidence: 0.86).
- **ML: Potential path traversal** (HIGH) — `routes/app.js`
  ML classifier detected potential path traversal (confidence: 0.90).
- **ML: Potential path traversal** (HIGH) — `config/vulns.js`
  ML classifier detected potential path traversal (confidence: 0.71).
- **ML: Potential command injection** (HIGH) — `config/vulns.js`
  ML classifier detected potential command injection (confidence: 0.74).
