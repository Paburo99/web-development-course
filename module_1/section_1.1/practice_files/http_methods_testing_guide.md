# HTTP Methods Testing Guide
> *Hands-on practice for sub-section 1.1.3*

## 🎯 Purpose
This guide provides step-by-step instructions for testing different HTTP methods, analyzing status codes, and examining headers using browser DevTools and online APIs.

## 🛠️ Tools Required
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Browser Developer Tools (F12)
- Internet connection
- Text editor (optional)

## 📋 Testing Checklist

### ✅ HTTP Methods Practice

#### 1. **GET Request Testing**
**Target**: `https://jsonplaceholder.typicode.com/posts`

**Steps:**
1. Open DevTools (F12) → Network tab
2. Clear existing entries (🗑️ icon)
3. Navigate to the URL above
4. Click on the request in Network tab

**What to Observe:**
- [ ] Request method shows `GET`
- [ ] Status code is `200 OK`
- [ ] Response contains array of posts
- [ ] `Content-Type: application/json` header
- [ ] No request body

**Expected Result:**
```http
GET /posts HTTP/1.1
Host: jsonplaceholder.typicode.com
Status: 200 OK
Content-Type: application/json; charset=utf-8
```

#### 2. **POST Request Testing**
**Method**: Browser Console

**Steps:**
1. Open browser console (F12 → Console)
2. Clear Network tab
3. Paste and run this code:

```javascript
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'Test Post',
    body: 'This is a test post content',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
.then(response => {
  console.log(`Status: ${response.status} ${response.statusText}`);
  return response.json();
})
.then(json => console.log('Response:', json));
```

**What to Observe:**
- [ ] Request method shows `POST`
- [ ] Status code is `201 Created`
- [ ] Request has body with JSON data
- [ ] Response includes new ID (usually 101)
- [ ] `Content-Type` header in request

#### 3. **PUT Request Testing**

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PUT',
  body: JSON.stringify({
    id: 1,
    title: 'Updated Title',
    body: 'Updated content',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
.then(response => {
  console.log(`Status: ${response.status} ${response.statusText}`);
  return response.json();
})
.then(json => console.log('Updated:', json));
```

**What to Observe:**
- [ ] Request method shows `PUT`
- [ ] Status code is `200 OK`
- [ ] Complete resource replacement
- [ ] Response shows updated data

#### 4. **PATCH Request Testing**

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PATCH',
  body: JSON.stringify({
    title: 'Only Title Changed'
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
.then(response => {
  console.log(`Status: ${response.status} ${response.statusText}`);
  return response.json();
})
.then(json => console.log('Patched:', json));
```

**What to Observe:**
- [ ] Request method shows `PATCH`
- [ ] Status code is `200 OK`
- [ ] Only specified field updated
- [ ] Smaller request body than PUT

#### 5. **DELETE Request Testing**

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'DELETE',
})
.then(response => {
  console.log(`Status: ${response.status} ${response.statusText}`);
  console.log('Resource deleted');
});
```

**What to Observe:**
- [ ] Request method shows `DELETE`
- [ ] Status code is `200 OK`
- [ ] Usually no response body
- [ ] No request body needed

---

### ✅ Status Code Analysis

#### Test Different Status Codes
**Target**: `https://httpbin.org/status/{code}`

**Practice Steps:**
1. Test each status code by visiting the URL
2. Observe the response in DevTools Network tab

**Status Codes to Test:**

| URL | Expected Status | Meaning | Notes |
|-----|----------------|---------|-------|
| `httpbin.org/status/200` | 200 OK | Success | Normal successful response |
| `httpbin.org/status/201` | 201 Created | Resource Created | Used after POST success |
| `httpbin.org/status/204` | 204 No Content | Success, No Body | Common for DELETE |
| `httpbin.org/status/301` | 301 Moved Permanently | Permanent Redirect | Check Location header |
| `httpbin.org/status/302` | 302 Found | Temporary Redirect | Check Location header |
| `httpbin.org/status/304` | 304 Not Modified | Cached Version OK | Browser cache related |
| `httpbin.org/status/400` | 400 Bad Request | Client Error | Invalid request |
| `httpbin.org/status/401` | 401 Unauthorized | Authentication Required | Need to log in |
| `httpbin.org/status/403` | 403 Forbidden | Access Denied | Insufficient permissions |
| `httpbin.org/status/404` | 404 Not Found | Resource Missing | URL doesn't exist |
| `httpbin.org/status/405` | 405 Method Not Allowed | Wrong HTTP Method | Check allowed methods |
| `httpbin.org/status/429` | 429 Too Many Requests | Rate Limited | Try again later |
| `httpbin.org/status/500` | 500 Internal Server Error | Server Problem | Server-side error |
| `httpbin.org/status/502` | 502 Bad Gateway | Proxy Error | Upstream server issue |
| `httpbin.org/status/503` | 503 Service Unavailable | Server Down | Temporary unavailability |

**For Each Test, Record:**
- [ ] Status code number
- [ ] Status text description
- [ ] Browser behavior (error page, redirect, etc.)
- [ ] Any special headers (Location, Retry-After, etc.)

---

### ✅ Headers Deep Dive

#### Request Headers Analysis
**Target**: Any major website (e.g., github.com, stackoverflow.com)

**Steps:**
1. Open DevTools → Network tab
2. Clear entries and navigate to site
3. Click on main document request
4. Examine Request Headers section

**Headers to Find and Document:**

| Header | Purpose | Example Value | Notes |
|--------|---------|---------------|-------|
| `Host` | Target server | `github.com` | Required in HTTP/1.1 |
| `User-Agent` | Browser identification | `Mozilla/5.0...` | Identifies your browser |
| `Accept` | Accepted content types | `text/html,application/xhtml+xml` | What browser can handle |
| `Accept-Language` | Language preferences | `en-US,en;q=0.9` | User's language settings |
| `Accept-Encoding` | Compression support | `gzip, deflate, br` | Compression algorithms |
| `Cookie` | Stored cookies | `sessionid=abc123` | Authentication/state |
| `Referer` | Previous page | `https://google.com/` | Where you came from |
| `Cache-Control` | Caching preferences | `no-cache` | How to handle caching |

#### Response Headers Analysis

**Headers to Find and Document:**

| Header | Purpose | Example Value | Notes |
|--------|---------|---------------|-------|
| `Content-Type` | Response format | `text/html; charset=utf-8` | What you're receiving |
| `Content-Length` | Response size | `12345` | Size in bytes |
| `Server` | Server software | `nginx/1.18.0` | What server is running |
| `Date` | Response timestamp | `Mon, 23 Oct 2023 15:30:45 GMT` | When response was sent |
| `Cache-Control` | Caching rules | `public, max-age=3600` | How long to cache |
| `ETag` | Version identifier | `"abc123"` | For cache validation |
| `Set-Cookie` | Set browser cookies | `sessionid=xyz; HttpOnly` | Server setting cookies |
| `Location` | Redirect target | `https://example.com/new` | For 3xx redirects |
| `Access-Control-Allow-Origin` | CORS policy | `*` or specific domain | Cross-origin permissions |

---

## 🔧 Advanced Exercises

### Exercise 1: API Error Handling
**Goal**: Understand different error responses

**Steps:**
1. Try to access non-existent resource: `https://jsonplaceholder.typicode.com/posts/999999`
2. Try invalid JSON in POST request
3. Try unsupported method on endpoint

**Record:** Status codes, error messages, response structure

### Exercise 2: Header Manipulation
**Goal**: See how headers affect responses

**Test these fetch requests:**

```javascript
// Test Accept header
fetch('https://httpbin.org/json', {
  headers: { 'Accept': 'application/xml' }
});

// Test User-Agent
fetch('https://httpbin.org/user-agent', {
  headers: { 'User-Agent': 'MyCustomBot/1.0' }
});

// Test custom headers
fetch('https://httpbin.org/headers', {
  headers: { 'X-Custom-Header': 'test-value' }
});
```

### Exercise 3: Cache Behavior
**Goal**: Understand caching headers

**Steps:**
1. Visit any major website twice
2. Compare first vs second request
3. Look for `304 Not Modified` responses
4. Check `If-Modified-Since` and `ETag` headers

---

## 📊 Results Documentation Template

**Date:** ___________  
**Browser:** ___________  
**Testing Session:** HTTP Methods & Status Codes

### GET Request Results
- Status Code: ___________
- Response Time: ___________
- Key Headers Found: ___________

### POST Request Results
- Status Code: ___________
- Response Time: ___________
- Response Body: ___________

### Error Code Analysis
- Most Common 4xx Error: ___________
- Server Error Encountered: ___________
- Redirect Status Observed: ___________

### Header Insights
- Security Headers Found: ___________
- Caching Headers Present: ___________
- Custom Headers Discovered: ___________

### Troubleshooting Notes
- Issues Encountered: ___________
- Solutions Applied: ___________
- Learning Points: ___________

---

## 🎯 Success Criteria

You've successfully completed this practice when you can:
- [ ] Identify HTTP methods in DevTools Network tab
- [ ] Explain status codes you encounter
- [ ] Analyze request/response headers
- [ ] Use browser console for API testing
- [ ] Troubleshoot common HTTP issues
- [ ] Understand caching behavior from headers

## 🔗 Quick Reference Links
- [MDN HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- [HTTP Status Codes](https://httpstatuses.com/)
- [JSONPlaceholder API](https://jsonplaceholder.typicode.com/)
- [HTTPBin Testing Service](https://httpbin.org/)

**Time Investment:** 90-120 minutes  
**Difficulty:** Intermediate  
**Prerequisites:** Basic browser usage, Developer Tools familiarity 