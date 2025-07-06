# Network Analysis Practice Worksheet

## Exercise 1: DNS Resolution Tracking

Use this worksheet to record your DNS resolution findings:

### Target Domains
| Domain | IP Address | Port | Protocol | Notes |
|--------|------------|------|----------|-------|
| github.com |  |  |  |  |
| stackoverflow.com |  |  |  |  |
| mozilla.org |  |  |  |  |
| your-choice.com |  |  |  |  |

### Questions to Answer
1. Which domains redirected to other domains?
2. Which domains had multiple IP addresses?
3. Which domains used HTTPS by default?
4. Did any domains show geographical differences in IP addresses?

## Exercise 2: HTTP Request Headers Analysis

### Request Headers Checklist
Record the following headers from your httpbin.org request:

- [ ] User-Agent: `_________________________________`
- [ ] Accept: `_________________________________`
- [ ] Accept-Language: `_________________________________`
- [ ] Accept-Encoding: `_________________________________`
- [ ] Host: `_________________________________`

### Response Headers Checklist
- [ ] Status Code: `_________________________________`
- [ ] Content-Type: `_________________________________`
- [ ] Server: `_________________________________`
- [ ] Date: `_________________________________`
- [ ] Content-Length: `_________________________________`

## Exercise 3: Error Analysis

### Error Types Encountered
| Error | URL Tested | Status Code | Error Message | Cause |
|-------|------------|-------------|---------------|-------|
| DNS Error |  |  |  |  |
| 404 Error |  |  |  |  |
| Connection Error |  |  |  |  |

### Troubleshooting Notes
Write your observations about each error type and how to identify them.

## Exercise 4: Network Timeline Analysis

### Performance Metrics
Use DevTools to measure:
- DNS Resolution Time: _____ ms
- TCP Connection Time: _____ ms
- TLS Handshake Time: _____ ms (for HTTPS)
- Time to First Byte: _____ ms
- Total Load Time: _____ ms

### Reflection Questions
1. Which step took the longest time?
2. How does HTTPS compare to HTTP in terms of setup time?
3. What factors might affect these timings? 