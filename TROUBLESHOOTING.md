# 🔧 Web Development Troubleshooting Guide

> *Quick solutions to common web development problems*

## 🆘 Quick Reference

### 📞 Emergency Fixes
- **Page won't load?** → Check console for errors (F12)
- **Styles not applying?** → Clear browser cache (Ctrl+F5)
- **JavaScript broken?** → Look for syntax errors in console
- **Can't install packages?** → Clear npm cache (`npm cache clean --force`)
- **Git not working?** → Check if you're in the right directory

---

## 🌐 Browser & HTML Issues

### HTML Not Displaying Correctly

**Problem:** HTML page shows raw code or doesn't render properly
```
Solutions:
✅ Ensure file has .html extension
✅ Check for unclosed tags (<div> needs </div>)
✅ Validate HTML using W3C Validator
✅ Check file encoding (should be UTF-8)
```

**Problem:** Links not working
```
Solutions:
✅ Check file paths (relative vs absolute)
✅ Ensure target files exist
✅ Check case sensitivity (important on Linux/Mac)
✅ Use forward slashes (/) not backslashes (\)
```

**Problem:** Images not showing
```
Solutions:
✅ Verify image file exists and path is correct
✅ Check image file extension (.jpg, .png, .gif, .svg)
✅ Try different image formats
✅ Check if image is too large (>10MB can cause issues)
```

### Form Issues

**Problem:** Form not submitting
```
Solutions:
✅ Check <form> has action and method attributes
✅ Ensure submit button is inside <form> tag
✅ Check for JavaScript errors preventing submission
✅ Verify server endpoint is working
```

---

## 🎨 CSS Styling Issues

### Styles Not Applying

**Problem:** CSS changes don't appear
```
Solutions:
✅ Hard refresh browser (Ctrl+F5 or Cmd+Shift+R)
✅ Check CSS file is linked correctly in HTML
✅ Verify CSS selector specificity
✅ Look for typos in property names
✅ Check for missing semicolons
```

**Problem:** Layout broken or overlapping elements
```
Solutions:
✅ Use browser dev tools to inspect elements
✅ Check for float issues (consider flexbox/grid)
✅ Verify box-sizing is set correctly
✅ Look for position absolute/fixed conflicts
✅ Check z-index values
```

**Problem:** Responsive design not working
```
Solutions:
✅ Add viewport meta tag: <meta name="viewport" content="width=device-width, initial-scale=1">
✅ Use relative units (%, em, rem, vw, vh)
✅ Test media queries with dev tools
✅ Check min-width vs max-width in media queries
```

### Flexbox/Grid Issues

**Problem:** Flexbox not working as expected
```
Solutions:
✅ Ensure parent has display: flex
✅ Check flex-direction (row is default)
✅ Use justify-content for main axis alignment
✅ Use align-items for cross axis alignment
✅ Consider flex-wrap for overflow
```

**Problem:** CSS Grid layout broken
```
Solutions:
✅ Verify display: grid on container
✅ Define grid-template-columns/rows
✅ Check grid-area names match
✅ Use browser grid inspector tools
```

---

## 💻 JavaScript Errors

### Common JavaScript Issues

**Problem:** "Script not loading" or "Function not defined"
```
Solutions:
✅ Check script src path is correct
✅ Ensure script loads before being called
✅ Move scripts to bottom of <body> or use defer/async
✅ Check browser console for 404 errors
```

**Problem:** Variables undefined or null errors
```
Solutions:
✅ Check variable spelling and case sensitivity
✅ Ensure variables are declared before use
✅ Use let/const instead of var
✅ Check if DOM elements exist before accessing
```

**Problem:** Event handlers not working
```
Solutions:
✅ Ensure DOM is loaded (use DOMContentLoaded)
✅ Check element selectors are correct
✅ Verify event names (click, not onClick)
✅ Use addEventListener instead of inline handlers
```

### AJAX/Fetch Issues

**Problem:** API calls failing
```
Solutions:
✅ Check network tab in dev tools
✅ Verify API endpoint URL is correct
✅ Check CORS policy (cross-origin requests)
✅ Ensure proper HTTP methods (GET, POST, etc.)
✅ Check request headers and body format
```

**Problem:** JSON parsing errors
```
Solutions:
✅ Validate JSON format using JSON validator
✅ Check response content-type header
✅ Handle errors with try/catch blocks
✅ Log raw response before parsing
```

---

## 🛠️ Development Tools Issues

### VS Code Problems

**Problem:** Extensions not working
```
Solutions:
✅ Restart VS Code
✅ Update extensions to latest versions
✅ Disable conflicting extensions
✅ Check extension compatibility with VS Code version
```

**Problem:** Live Server not working
```
Solutions:
✅ Right-click HTML file and select "Open with Live Server"
✅ Check if port 5500 is blocked by firewall
✅ Try different port in Live Server settings
✅ Ensure HTML file is in workspace folder
```

### Browser Developer Tools

**Problem:** Dev tools not showing accurate info
```
Solutions:
✅ Clear browser cache and hard reload
✅ Disable browser extensions temporarily
✅ Try incognito/private browsing mode
✅ Update browser to latest version
```

---

## 📦 Node.js & NPM Issues

### Installation Problems

**Problem:** `npm install` fails
```
Solutions:
✅ Clear npm cache: npm cache clean --force
✅ Delete node_modules and package-lock.json, then reinstall
✅ Check Node.js version compatibility
✅ Try using yarn instead of npm
✅ Check internet connection and npm registry
```

**Problem:** Permission errors (EACCES)
```
Solutions:
✅ Use npm config to set different global directory
✅ Don't use sudo with npm (security risk)
✅ On Windows, run terminal as administrator
✅ Check file/folder permissions
```

**Problem:** Module not found errors
```
Solutions:
✅ Ensure package is installed: npm list package-name
✅ Check import/require syntax
✅ Verify package name spelling
✅ Check if package is dev dependency vs regular dependency
✅ Restart development server after installing
```

### Package.json Issues

**Problem:** Scripts not running
```
Solutions:
✅ Check script syntax in package.json
✅ Ensure referenced files exist
✅ Use npm run script-name (not npm script-name)
✅ Check for typos in script names
```

---

## 🔗 Git & Version Control

### Common Git Issues

**Problem:** "fatal: not a git repository"
```
Solutions:
✅ Initialize repository: git init
✅ Check if you're in correct directory
✅ Clone repository if working with existing project
```

**Problem:** Merge conflicts
```
Solutions:
✅ Open conflicted files and resolve manually
✅ Look for <<<<<<< ======= >>>>>>> markers
✅ Choose which changes to keep
✅ Remove conflict markers
✅ Commit resolved changes
```

**Problem:** Can't push to GitHub
```
Solutions:
✅ Check if remote origin is set correctly
✅ Ensure you have push permissions
✅ Use personal access token instead of password
✅ Check if branch is up to date (pull first)
```

### GitHub Issues

**Problem:** Repository not updating
```
Solutions:
✅ Check if changes are committed locally
✅ Push changes: git push origin main
✅ Refresh GitHub page
✅ Check if pushing to correct branch
```

---

## 🚀 Deployment Issues

### GitHub Pages

**Problem:** Site not deploying to GitHub Pages
```
Solutions:
✅ Enable GitHub Pages in repository settings
✅ Ensure index.html is in root directory
✅ Check if repository is public
✅ Wait 5-10 minutes for changes to propagate
✅ Check GitHub Pages build status
```

**Problem:** CSS/JS not loading on deployed site
```
Solutions:
✅ Use relative paths (not absolute paths)
✅ Check case sensitivity in file names
✅ Ensure all files are committed and pushed
✅ Clear browser cache
```

### Netlify/Vercel Issues

**Problem:** Build failing
```
Solutions:
✅ Check build logs for specific errors
✅ Ensure all dependencies are in package.json
✅ Check Node.js version compatibility
✅ Verify build command is correct
✅ Check environment variables are set
```

---

## 🌍 Cross-Browser Compatibility

### Browser-Specific Issues

**Problem:** Site works in Chrome but not Safari/Firefox
```
Solutions:
✅ Check for vendor prefixes (-webkit-, -moz-, -ms-)
✅ Use CSS autoprefixer
✅ Test with browserslist compatibility
✅ Avoid browser-specific features
✅ Use polyfills for newer JavaScript features
```

**Problem:** Mobile layout broken
```
Solutions:
✅ Add viewport meta tag
✅ Test on actual devices, not just browser tools
✅ Check touch event compatibility
✅ Ensure buttons/links are large enough for touch
✅ Test on different screen sizes
```

---

## 📱 Performance Issues

### Slow Loading Pages

**Problem:** Website loads slowly
```
Solutions:
✅ Optimize images (compress, use WebP format)
✅ Minify CSS and JavaScript
✅ Use CDN for libraries
✅ Enable browser caching
✅ Reduce HTTP requests
✅ Use lazy loading for images
```

**Problem:** JavaScript execution slow
```
Solutions:
✅ Use browser profiler to identify bottlenecks
✅ Avoid unnecessary DOM queries
✅ Use event delegation
✅ Debounce/throttle expensive operations
✅ Consider using Web Workers for heavy computations
```

---

## 🔍 Debugging Techniques

### General Debugging Process

1. **Identify the Problem**
   - What exactly is not working?
   - When did it start happening?
   - What changed recently?

2. **Check Browser Console**
   - Press F12 to open developer tools
   - Look for error messages in Console tab
   - Check Network tab for failed requests

3. **Use Console.log()**
   - Add console.log() statements to track variables
   - Check if functions are being called
   - Verify data flow through your application

4. **Test in Isolation**
   - Create minimal test case
   - Remove unnecessary code
   - Test one feature at a time

5. **Use Browser Dev Tools**
   - Inspect element styles
   - Debug JavaScript step by step
   - Monitor network requests
   - Check application storage

### Debugging Tools

- **Browser Dev Tools** (F12)
- **VS Code Debugger** (Built-in)
- **React Developer Tools** (Browser Extension)
- **Vue.js DevTools** (Browser Extension)
- **Lighthouse** (Performance Auditing)

---

## 📚 Getting Additional Help

### Before Asking for Help

1. **Search for the Error**
   - Google the exact error message
   - Check Stack Overflow
   - Look at MDN documentation

2. **Create Minimal Example**
   - Remove unnecessary code
   - Create CodePen or JSFiddle demo
   - List exact steps to reproduce

3. **Document What You've Tried**
   - List attempted solutions
   - Include relevant code snippets
   - Specify browser and versions

### Where to Get Help

- **[Stack Overflow](https://stackoverflow.com/)** - Programming Q&A
- **[MDN Web Docs](https://developer.mozilla.org/)** - Comprehensive documentation
- **[CSS-Tricks](https://css-tricks.com/)** - CSS solutions and guides
- **[JavaScript.info](https://javascript.info/)** - Modern JavaScript tutorial
- **[Can I Use](https://caniuse.com/)** - Browser compatibility tables
- **[GitHub Issues](https://github.com/)** - Framework/library specific issues

### Community Resources

- **[Reddit r/webdev](https://reddit.com/r/webdev)** - Web development community
- **[Discord Communities](https://discord.gg/)** - Real-time help
- **[Dev.to](https://dev.to/)** - Developer community and tutorials

---

## ⚡ Emergency Checklist

When everything breaks, try these in order:

1. **🔄 Hard refresh browser** (Ctrl+F5)
2. **🗑️ Clear browser cache** completely
3. **👀 Check browser console** for errors
4. **🔧 Restart development server**
5. **📂 Check file paths** and names
6. **💾 Ensure all files are saved**
7. **🌐 Test in different browser**
8. **📱 Try incognito/private mode**
9. **🔌 Restart VS Code** and reopening project
10. **💻 Restart computer** (last resort)

---

**Remember:** Every developer faces these issues. The key is systematic debugging and patience! 🚀

**Need more help?** 
- Check the [Study Guide](./STUDY_GUIDE.md) for learning strategies.
- Our [Navigation Guide](NAVIGATION.md) for quick links to specific topics.
- The complete [Curriculum](./README.md) for additional resources. 
