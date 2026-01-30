# Product Feedback: Databricks Apps Deployment Friction

**Date:** 2026-01-30  
**App:** `stock-analysis-app` (Streamlit)  
**App ID:** `34f08d16-cbe5-4551-8230-5b1f1951ac00`  
**Workspace:** `dbc-c61e0601-2052.cloud.databricks.com`

---

## Executive Summary

Successfully deployed a Streamlit app to Databricks Apps after extensive troubleshooting. The deployment process had significant friction points that could be improved to make the experience seamless for users.

**Time to Resolution:** ~4 hours  
**Issues Encountered:** 8 major friction points  
**Root Causes:** Port configuration mismatch, unclear error messages, missing documentation

---

## Deployment Journey

### What Worked ✅
- App creation via CLI
- Source code upload
- Streamlit framework support
- OAuth authentication flow
- Permissions system (once understood)

### What Didn't Work ❌
- Port configuration discovery
- Error message clarity
- Environment variable visibility
- Health check requirements
- Permission requirements clarity
- Gateway routing diagnostics

---

## Friction Points & Recommendations

### 1. Port Configuration Discovery

**Issue:**
- No clear documentation on which port to use
- Tried ports: 8501 (Streamlit default), 8080 (documented), 9000 (worked partially), finally 8000 (correct)
- Port 8080 was "already in use" (reserved by platform)
- Environment variables showed `PORT=8000` but this wasn't discoverable until deep troubleshooting

**Impact:**
- 3+ hours of trial and error
- Multiple failed deployments
- Confusion about which port is correct

**Recommendations:**

1. **Document Port Requirements Clearly:**
   - Add to Databricks Apps documentation: "Apps must use port 8000 (set via `--server.port 8000`)"
   - Include in `app.yaml` examples
   - Add port validation during deployment

2. **Show Environment Variables in UI:**
   - Display environment variables (including `PORT`, `DATABRICKS_APP_PORT`) in app details page
   - Make this visible before deployment, not just after
   - Add "Environment" tab showing all runtime env vars

3. **Port Validation:**
   - Validate port in `app.yaml` during deployment
   - If port doesn't match `PORT` env var, show clear error: "Port mismatch: app.yaml uses 8501 but environment expects 8000"
   - Auto-suggest fix: "Update app.yaml to use port 8000"

4. **Better Error Messages:**
   - When gateway can't route: "Gateway cannot reach app on port 8501. Expected port: 8000 (from DATABRICKS_APP_PORT)"
   - When port conflict: "Port 8080 is reserved by Databricks platform. Use port 8000 instead."

---

### 2. Error Message Clarity

**Issue:**
- "502 Bad Gateway" with no context
- "App Not Available" with no explanation
- No indication of what to check or fix
- Errors didn't point to root cause (port mismatch, permissions, etc.)

**Impact:**
- Required extensive debugging
- Multiple support documents created
- User confusion about what's wrong

**Recommendations:**

1. **Contextual Error Messages:**
   - Instead of "502 Bad Gateway": "Gateway cannot connect to app container. Check: (1) App is running, (2) Port matches PORT env var (8000), (3) Health check endpoint responds"
   - Instead of "App Not Available": "User lacks 'Use' permission. Grant 'Use' permission in App → Permissions tab"

2. **Error Codes with Documentation:**
   - Add error codes: `APPS_502_PORT_MISMATCH`, `APPS_403_NO_USE_PERMISSION`
   - Link to troubleshooting docs for each error code
   - Provide "Quick Fix" button in UI for common errors

3. **Diagnostic Information:**
   - Show gateway routing status in app details
   - Display health check results
   - Show last successful connection time

---

### 3. Environment Variable Visibility

**Issue:**
- Environment variables not visible until app is running
- `PORT=8000` and `DATABRICKS_APP_PORT=8000` were key but hidden
- No way to see what port gateway expects before deployment

**Impact:**
- Had to deploy multiple times to discover correct port
- Couldn't validate configuration before deployment

**Recommendations:**

1. **Pre-Deployment Environment Preview:**
   - Show environment variables that will be set before deployment
   - Display in "Deploy" dialog: "App will run with: PORT=8000, DATABRICKS_APP_PORT=8000"
   - Allow editing env vars before deployment

2. **Environment Tab Enhancement:**
   - Make environment variables easily accessible
   - Show both user-set and platform-set variables
   - Highlight which variables are required vs optional

3. **Configuration Validation:**
   - Validate `app.yaml` against environment variables before deployment
   - Warn if port mismatch detected
   - Suggest corrections automatically

---

### 4. Health Check Requirements

**Issue:**
- No documentation on health check requirements
- Unclear if health checks are performed
- No way to see health check status or failures
- Streamlit doesn't have built-in health endpoint

**Impact:**
- Uncertainty about why routing fails
- No way to diagnose health check issues

**Recommendations:**

1. **Document Health Check Behavior:**
   - Explain if/when health checks are performed
   - Document expected endpoint (`/health`, `/`, etc.)
   - Document expected response format
   - Document timeout settings

2. **Health Check Status in UI:**
   - Show health check status in app details
   - Display last health check time and result
   - Show health check logs if available

3. **Health Check for Streamlit:**
   - Provide guidance for Streamlit apps (which don't have `/health` by default)
   - Or: Make health checks optional for Streamlit apps
   - Or: Auto-detect Streamlit and use root endpoint for health

---

### 5. Permission Requirements Clarity

**Issue:**
- "App Not Available" error didn't explain it's a permission issue
- Unclear difference between "Can Manage" and "Can Use"
- No guidance on which permission is needed for what action
- Permission errors not clearly explained

**Impact:**
- Had to grant permissions through trial and error
- Unclear why app wasn't accessible despite being "RUNNING"

**Recommendations:**

1. **Clear Permission Error Messages:**
   - "App Not Available: User lacks 'Use' permission. Grant 'Use' permission in App → Permissions tab"
   - Link directly to Permissions tab
   - Show which users/groups have which permissions

2. **Permission Guidance:**
   - Tooltip explaining: "Can Manage = deploy/update app, Can Use = access running app"
   - Show recommended permissions for common scenarios
   - Auto-suggest granting "Use" permission when app is deployed but not accessible

3. **Permission Inheritance:**
   - Clearly show inherited permissions
   - Explain inheritance chain
   - Make it easy to override inherited permissions if needed

---

### 6. Gateway Routing Diagnostics

**Issue:**
- No visibility into gateway routing status
- No way to see if gateway knows about the app
- No way to test gateway → container connectivity
- 502 errors with no diagnostic information

**Impact:**
- Had to guess what was wrong
- Extensive troubleshooting required
- No way to verify routing configuration

**Recommendations:**

1. **Gateway Status Dashboard:**
   - Show gateway routing status in app details
   - Display: "Gateway → Container: Connected" or "Failed"
   - Show routing table entry status
   - Display port mapping: "Gateway routes to: port 8000"

2. **Diagnostic Tools:**
   - "Test Connection" button to verify gateway → container
   - "View Gateway Logs" for routing issues
   - Network connectivity test from gateway to container

3. **Routing Information:**
   - Show which port gateway expects
   - Display health check results
   - Show last successful routing time

---

### 7. CLI Permission Issues

**Issue:**
- CLI deployment failed with unclear permission error
- Error: "User is not authorized" but didn't explain what permission is needed
- No way to check CLI user permissions
- Had to use UI as workaround

**Impact:**
- CLI workflow broken
- Had to switch to UI deployment
- Inconsistent experience

**Recommendations:**

1. **Clear Permission Errors:**
   - "User lacks CAN_MANAGE permission. Grant in App → Permissions tab"
   - Show which user needs which permission
   - Link to permissions page

2. **Permission Check Command:**
   - `databricks apps check-permissions <app-name>` to see what user can do
   - Show required vs current permissions
   - Suggest how to get missing permissions

3. **Service Principal Support:**
   - Better support for service principal deployments
   - Clear documentation on SP permissions needed
   - Auto-grant permissions to app creator

---

### 8. Documentation Gaps

**Issue:**
- Port requirements not clearly documented
- No troubleshooting guide for common errors
- Environment variables not explained
- Health check requirements unclear
- Permission model not well documented

**Impact:**
- Had to discover everything through trial and error
- Created extensive troubleshooting docs ourselves
- Wasted time on issues that should be documented

**Recommendations:**

1. **Comprehensive Getting Started Guide:**
   - Step-by-step guide with all requirements
   - Clear port configuration section
   - Environment variables explained
   - Common frameworks (Streamlit, Dash) with examples

2. **Troubleshooting Guide:**
   - Common errors and solutions
   - Error code reference
   - Diagnostic checklist
   - "Quick Fix" guides for common issues

3. **Framework-Specific Guides:**
   - Streamlit deployment guide
   - Dash deployment guide
   - Port requirements per framework
   - Health check requirements per framework

4. **API/CLI Documentation:**
   - Complete CLI command reference
   - Permission requirements per command
   - Example workflows
   - Error handling guide

---

## Specific Technical Issues

### Port Configuration

**Current State:**
- Environment sets `PORT=8000`, `DATABRICKS_APP_PORT=8000`
- Documentation shows port 8080 in examples
- Port 8080 is reserved by platform
- No validation of port mismatch

**Recommended Fix:**
1. Standardize on port 8000 for all apps
2. Update all documentation examples
3. Add port validation in deployment
4. Show expected port in UI before deployment

### Health Checks

**Current State:**
- Unclear if health checks are performed
- No documentation on health check behavior
- Streamlit apps don't have `/health` endpoint by default

**Recommended Fix:**
1. Document health check behavior
2. Make health checks optional for Streamlit (or use root endpoint)
3. Show health check status in UI
4. Provide health check endpoint examples

### Error Messages

**Current State:**
- Generic errors: "502 Bad Gateway", "App Not Available"
- No context or actionable guidance

**Recommended Fix:**
1. Contextual error messages with root cause
2. Actionable suggestions ("Grant Use permission", "Change port to 8000")
3. Links to relevant documentation
4. Error codes for programmatic handling

---

## User Experience Improvements

### Pre-Deployment Validation

**Add validation before deployment:**
- Port matches environment variables
- Required environment variables set
- Health check endpoint available (if required)
- Permissions configured
- Show preview of configuration

### Deployment Wizard

**Create guided deployment:**
- Step 1: Select framework (Streamlit, Dash, etc.)
- Step 2: Configure port (auto-suggest 8000)
- Step 3: Set environment variables
- Step 4: Configure permissions
- Step 5: Review and deploy

### Post-Deployment Diagnostics

**Add diagnostic dashboard:**
- App status: Running/Stopped/Error
- Gateway status: Connected/Failed
- Health check: Passing/Failing
- Last request: Timestamp
- Error log: Recent errors

---

## Quick Wins (Easy to Implement)

1. **Add port validation** - Check port matches `PORT` env var
2. **Show environment variables** - Display in app details page
3. **Better error messages** - Add context to 502 and "App Not Available"
4. **Document port 8000** - Update all examples
5. **Permission tooltips** - Explain "Can Manage" vs "Can Use"

---

## Medium-Term Improvements

1. **Pre-deployment validation** - Check config before deploy
2. **Gateway status dashboard** - Show routing status
3. **Health check UI** - Display health check results
4. **Diagnostic tools** - Test connection, view logs
5. **Deployment wizard** - Guided setup process

---

## Long-Term Enhancements

1. **Auto-configuration** - Detect framework and auto-configure
2. **Smart error recovery** - Auto-suggest and apply fixes
3. **Health check auto-setup** - Add health endpoints automatically
4. **Permission auto-grant** - Grant necessary permissions automatically
5. **Self-healing** - Auto-restart, auto-reconfigure on errors

---

## Success Metrics

**Current Experience:**
- Time to first working app: ~4 hours
- Issues encountered: 8 major friction points
- Documentation searches: 10+
- Support interactions: Multiple

**Target Experience:**
- Time to first working app: <15 minutes
- Issues encountered: 0-1 minor issues
- Documentation searches: 1-2
- Support interactions: 0

---

## Conclusion

The Databricks Apps platform is functional but has significant friction in the deployment process. The main issues are:

1. **Port configuration** - Unclear which port to use, no validation
2. **Error messages** - Generic errors without context or guidance
3. **Documentation** - Missing critical information (ports, health checks, permissions)
4. **Diagnostics** - No visibility into gateway routing, health checks, or environment

**Priority Recommendations:**
1. Document port 8000 requirement clearly
2. Add port validation with helpful error messages
3. Show environment variables in UI
4. Improve error messages with actionable guidance
5. Create comprehensive troubleshooting guide

With these improvements, the deployment experience would be significantly smoother and users could deploy apps in minutes rather than hours.

---

## Appendix: Technical Details

### Environment Variables Discovered

```json
{
  "PORT": "8000",
  "DATABRICKS_APP_PORT": "8000",
  "STREAMLIT_SERVER_PORT": "8000",
  "DATABRICKS_APP_NAME": "stock-analysis-app",
  "DATABRICKS_APP_URL": "https://stock-analysis-app-7474660070162674.aws.databricksapps.com",
  "DATABRICKS_HOST": "dbc-c61e0601-2052.cloud.databricks.com",
  "DATABRICKS_WORKSPACE_ID": "7474660070162674",
  "DATABRICKS_CLIENT_ID": "34f08d16-cbe5-4551-8230-5b1f1951ac00"
}
```

### Ports Tested

| Port | Result | Reason |
|------|--------|--------|
| 8501 | ❌ 502 Bad Gateway | Gateway expects different port |
| 8080 | ❌ Port in use | Reserved by Databricks platform |
| 9000 | ⚠️ Partial (HTTP 200 curl, 502 browser) | Wrong port, but worked for some requests |
| 8000 | ✅ **WORKS** | Matches environment variables |

### Error Messages Encountered

1. "502 Bad Gateway" - Gateway routing failure
2. "App Not Available" - Permission issue (missing "Use" permission)
3. "Port 8080 is already in use" - Port conflict
4. "User is not authorized" - CLI permission issue
5. "403 Forbidden" on `/.auth/callback` - OAuth callback blocked

### Permissions Required

- **CAN_MANAGE**: Deploy, update, delete app
- **CAN_USE**: Access running app (critical for users!)

---

**Contact:** For questions about this feedback, please reach out to the app creator.

