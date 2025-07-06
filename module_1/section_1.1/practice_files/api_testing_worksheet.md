# API Testing Worksheet
> *Practice exercises for HTTP methods, status codes, and headers*

## 🎯 Objective
Practice identifying and using HTTP methods, interpreting status codes, and analyzing headers through hands-on API testing.

## 🛠️ Setup
1. Open browser DevTools (F12)
2. Go to Network tab
3. Keep DevTools open during all exercises

---

## Exercise 1: HTTP Methods Practice

### GET Request Analysis
**URL:** `https://jsonplaceholder.typicode.com/users`

**Your Task:**
1. Navigate to the URL above
2. Find the request in Network tab
3. Fill out the information below

**Results:**
- HTTP Method: ___________
- Status Code: ___________
- Response Time: ___________ms
- Content-Type: ___________
- Response Body Type: ___________

### POST Request Testing
**Copy this code into browser console:**

```javascript
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'My Test Post',
    body: 'Testing POST method',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
.then(response => console.log('Status:', response.status))
.then(() => console.log('Check Network tab for details'));
```

**Results:**
- HTTP Method: ___________
- Status Code: ___________
- Request Body Size: ___________
- Response includes ID: ___________

---

## Exercise 2: Status Code Investigation

**Test each URL and record the status code:**

| URL | Status Code | Status Text | Notes |
|-----|-------------|-------------|-------|
| `httpbin.org/status/200` | _______ | _______ | _______ |
| `httpbin.org/status/404` | _______ | _______ | _______ |
| `httpbin.org/status/500` | _______ | _______ | _______ |
| `httpbin.org/status/301` | _______ | _______ | _______ |
| `httpbin.org/status/401` | _______ | _______ | _______ |

**Questions:**
1. Which status codes indicate success? ___________
2. Which indicate client errors? ___________
3. Which indicate server errors? ___________

---

## Exercise 3: Headers Analysis

**Visit:** `https://httpbin.org/headers`

**Find these request headers:**
- Host: ___________
- User-Agent: ___________
- Accept: ___________
- Accept-Language: ___________

**Response headers to find:**
- Content-Type: ___________
- Server: ___________
- Date: ___________

---

## Exercise 4: Real-World API

**Visit any major website (GitHub, Stack Overflow, etc.)**

**Document:**
1. Main document request method: ___________
2. Number of total requests: ___________
3. Largest response size: ___________
4. Any 404 errors found: ___________
5. Security headers present (list): ___________

---

## ✅ Completion Checklist

- [ ] Successfully identified different HTTP methods
- [ ] Recognized various status codes and their meanings
- [ ] Analyzed request and response headers
- [ ] Used browser console for API testing
- [ ] Explored real-world website network activity

## 📝 Reflection Questions

1. When would you use POST vs PUT vs PATCH?
2. What's the difference between 401 and 403 status codes?
3. Why are headers important for web communication?
4. How could understanding these concepts help in debugging web applications?

**Time to Complete:** 45-60 minutes 