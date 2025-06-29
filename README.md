# HTTP Status Codes Reference 📋

A comprehensive reference guide for all HTTP status codes. Perfect for developers, students, and anyone working with web APIs.

## Table of Contents
- [1xx Informational](#1xx-informational)
- [2xx Success](#2xx-success)
- [3xx Redirection](#3xx-redirection)
- [4xx Client Error](#4xx-client-error)
- [5xx Server Error](#5xx-server-error)
- [Quick Reference](#quick-reference)

---

## 1xx Informational
*The request was received, continuing process*

| Code | Status | Description |
|------|--------|-------------|
| 100 | Continue | Server has received request headers, client should send request body |
| 101 | Switching Protocols | Server is switching protocols as requested by client |
| 102 | Processing | Server has accepted request but processing is not complete |
| 103 | Early Hints | Server is sending some response headers before final response |

---

## 2xx Success
*The action was successfully received, understood, and accepted*

| Code | Status | Description |
|------|--------|-------------|
| 200 | OK | Standard response for successful HTTP requests |
| 201 | Created | Request has been fulfilled, new resource created |
| 202 | Accepted | Request accepted for processing, but not completed |
| 203 | Non-Authoritative Information | Request successful, but response is from cached copy |
| 204 | No Content | Request successful, but no content to return |
| 205 | Reset Content | Request successful, client should reset document view |
| 206 | Partial Content | Server is delivering only part of resource due to range header |
| 207 | Multi-Status | Multiple status codes for multiple independent operations |
| 208 | Already Reported | Members of DAV binding already enumerated |
| 226 | IM Used | Server has fulfilled GET request, response is instance-manipulations |

---

## 3xx Redirection
*Further action must be taken in order to complete the request*

| Code | Status | Description |
|------|--------|-------------|
| 300 | Multiple Choices | Multiple options for resource, client must choose |
| 301 | Moved Permanently | Resource permanently moved to new URL |
| 302 | Found | Resource temporarily moved to different URL |
| 303 | See Other | Response to request can be found under different URL |
| 304 | Not Modified | Resource has not been modified since last request |
| 305 | Use Proxy | Requested resource must be accessed through proxy |
| 307 | Temporary Redirect | Request should be repeated with another URL |
| 308 | Permanent Redirect | Request and future requests should use different URL |

---

## 4xx Client Error
*The request contains bad syntax or cannot be fulfilled*

| Code | Status | Description |
|------|--------|-------------|
| 400 | Bad Request | Server cannot process request due to client error |
| 401 | Unauthorized | Authentication required to access resource |
| 402 | Payment Required | Reserved for future use |
| 403 | Forbidden | Server understood request but refuses to authorize |
| 404 | Not Found | Requested resource could not be found |
| 405 | Method Not Allowed | Request method not supported for resource |
| 406 | Not Acceptable | Requested resource cannot generate acceptable content |
| 407 | Proxy Authentication Required | Client must authenticate with proxy |
| 408 | Request Timeout | Server timed out waiting for request |
| 409 | Conflict | Request conflicts with current state of resource |
| 410 | Gone | Resource no longer available and will not be available again |
| 411 | Length Required | Request did not specify length of content |
| 412 | Precondition Failed | Server does not meet request preconditions |
| 413 | Payload Too Large | Request entity is larger than server can process |
| 414 | URI Too Long | URI provided was too long for server to process |
| 415 | Unsupported Media Type | Request entity has unsupported media type |
| 416 | Range Not Satisfiable | Client requested portion of file server cannot supply |
| 417 | Expectation Failed | Server cannot meet requirements of Expect header |
| 418 | I'm a teapot | Server refuses to brew coffee because it's a teapot |
| 421 | Misdirected Request | Request directed at server unable to produce response |
| 422 | Unprocessable Entity | Request well-formed but unable to be processed |
| 423 | Locked | Resource being accessed is locked |
| 424 | Failed Dependency | Request failed due to failure of previous request |
| 425 | Too Early | Server unwilling to process request that might be replayed |
| 426 | Upgrade Required | Client should switch to different protocol |
| 428 | Precondition Required | Origin server requires request to be conditional |
| 429 | Too Many Requests | User has sent too many requests in given time |
| 431 | Request Header Fields Too Large | Server unwilling to process request with large headers |
| 451 | Unavailable For Legal Reasons | Resource unavailable due to legal reasons |

---

## 5xx Server Error
*The server failed to fulfill an apparently valid request*

| Code | Status | Description |
|------|--------|-------------|
| 500 | Internal Server Error | Generic error message for unexpected server condition |
| 501 | Not Implemented | Server does not support functionality required to fulfill request |
| 502 | Bad Gateway | Server received invalid response from upstream server |
| 503 | Service Unavailable | Server currently unavailable (overloaded or maintenance) |
| 504 | Gateway Timeout | Server did not receive timely response from upstream server |
| 505 | HTTP Version Not Supported | Server does not support HTTP protocol version |
| 506 | Variant Also Negotiates | Server has internal configuration error |
| 507 | Insufficient Storage | Server unable to store representation needed to complete request |
| 508 | Loop Detected | Server detected infinite loop while processing request |
| 510 | Not Extended | Further extensions to request are required |
| 511 | Network Authentication Required | Client needs to authenticate to gain network access |

---

## Quick Reference

### Most Common Status Codes

**Success:**
- `200 OK` - Everything worked perfectly
- `201 Created` - New resource was created
- `204 No Content` - Success, but nothing to return

**Client Errors:**
- `400 Bad Request` - Invalid request syntax
- `401 Unauthorized` - Authentication required
- `403 Forbidden` - Access denied
- `404 Not Found` - Resource doesn't exist
- `429 Too Many Requests` - Rate limit exceeded

**Server Errors:**
- `500 Internal Server Error` - Something went wrong on server
- `502 Bad Gateway` - Invalid response from upstream
- `503 Service Unavailable` - Server temporarily unavailable

### Status Code Categories
- **1xx**: Informational responses
- **2xx**: Success responses
- **3xx**: Redirection messages
- **4xx**: Client error responses
- **5xx**: Server error responses

---

## Usage Examples

### RESTful API Design
```
GET /users/123
→ 200 OK (user found)
→ 404 Not Found (user doesn't exist)

POST /users
→ 201 Created (user created successfully)
→ 400 Bad Request (invalid data)

PUT /users/123
→ 200 OK (user updated)
→ 404 Not Found (user doesn't exist)

DELETE /users/123
→ 204 No Content (user deleted)
→ 404 Not Found (user doesn't exist)
```

### Authentication Flow
```
GET /protected-resource
→ 401 Unauthorized (no token provided)

POST /login
→ 200 OK (credentials valid)
→ 401 Unauthorized (invalid credentials)

GET /protected-resource (with valid token)
→ 200 OK (access granted)
→ 403 Forbidden (token valid but insufficient permissions)
```

---

## Contributing

Found an error or want to add more examples? Feel free to:
1. Fork this repository
2. Create your feature branch
3. Submit a pull request

## Resources

- [MDN HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- [RFC 7231 - HTTP/1.1 Semantics](https://tools.ietf.org/html/rfc7231)
- [IANA HTTP Status Code Registry](https://www.iana.org/assignments/http-status-codes/)

---

## License

This reference guide is available under the MIT License. Feel free to use it in your projects!

---

**Made with ❤️ by [Pratik Shikhaliya](https://github.com/pratik-shikhaliya) — who’s memorized 418 because he is a teapot.**

*Remember: Every status has a story.*
