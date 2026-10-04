# FusionTech Troubleshooting

## Application Does Not Start

Check:

1. Node.js is installed and supported by the project.
2. Dependencies are installed.
3. The package manager completed without errors.
4. Local environment configuration is valid.
5. The development command from the private source repository is being used.

If dependency installation fails, remove the local dependency directory and lockfile only when appropriate, then reinstall using the project's documented package manager.

## Blank Page

Possible causes include:

- JavaScript runtime error
- Invalid environment configuration
- Build failure
- Incorrect deployment path
- Client-side routing configuration

Check the browser developer console first.

## Nested Routes Return 404 After Deployment

This commonly occurs when the hosting platform does not know that the application is a single-page application.

Configure the hosting platform to route unknown application paths to the frontend entry point.

## Contact Form Appears to Submit but No Email Arrives

Check:

1. Email integration configuration
2. Sender/recipient configuration
3. Provider dashboard logs
4. Spam/junk folders
5. Browser console errors
6. Network requests
7. Provider sending limits

A successful frontend interaction does not necessarily mean the external email provider accepted or delivered the message.

## AI Features Are Unavailable

Check:

- Whether the optional AI service is running
- Whether the configured service URL is reachable
- Whether the selected model is available
- Browser/network errors
- Local machine resource constraints

AI features should fail gracefully without preventing normal service browsing.

## Arabic Layout Looks Incorrect

Check:

- Current language selection
- Direction state
- Mixed Arabic/Latin content
- Fixed-width components
- Icon alignment
- Form field direction
- Responsive breakpoints

Test both short and long Arabic strings.

## Service Data Is Missing

For the demonstration architecture, browser-side data can be affected by:

- Clearing site data
- Switching browsers
- Private/incognito browsing
- Browser profile changes
- Storage restrictions

If persistent shared data is required, use a backend database rather than browser-only persistence.

## Admin Changes Do Not Persist

Verify that:

1. Browser storage is available.
2. The browser has not blocked site storage.
3. The application is running under the expected origin.
4. No runtime exception interrupted the save operation.

For production, authoritative CMS persistence should be handled server-side.

## Build Succeeds but Production Behaves Differently

Compare:

- Environment configuration
- Base path
- SPA routing
- Browser security policies
- External integration URLs
- HTTPS configuration
- Production build output

## General Diagnostic Strategy

When investigating an issue:

1. Reproduce the problem.
2. Check browser console errors.
3. Check network requests.
4. Identify whether the problem is UI, state, persistence, or integration related.
5. Test the affected feature without optional integrations.
6. Verify configuration.
7. Reproduce in a clean browser session.
8. Document the root cause and fix.

Avoid publishing credentials, tokens, private URLs, or other sensitive diagnostics in public issue reports.
