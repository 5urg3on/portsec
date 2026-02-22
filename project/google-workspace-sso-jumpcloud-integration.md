# Google Workspace SSO Integration with JumpCloud

Single Sign-On (SSO) implementation for Google Workspace using JumpCloud as SAML 2.0 Identity Provider.

## Overview

This project documents the configuration and deployment of SAML-based SSO for Google Workspace, enabling centralized authentication through JumpCloud Directory Platform.

## Features

- ✅ SAML 2.0 authentication
- ✅ Centralized user management
- ✅ Seamless Google Workspace access via JumpCloud portal
- ✅ Audit logging and monitoring

## Architecture

**Identity Provider (IdP):** JumpCloud  
**Service Provider (SP):** Google Workspace  
**Protocol:** SAML 2.0  

## Implementation

### Prerequisites
- Active JumpCloud account with admin access
- Google Workspace admin privileges
- Domain verification completed

### Configuration Steps

1. **JumpCloud Setup**
   - Add Google Workspace SSO application
   - Configure SAML settings
   - Set Entity ID to `google.com`
   - Generate X.509 certificate

2. **Google Workspace Setup**
   - Enable third-party SSO
   - Upload JumpCloud certificate
   - Configure sign-in/sign-out URLs
   - Map SAML attributes

3. **User Assignment**
   - Create user groups in JumpCloud
   - Assign users to Google Workspace SSO app
   - Test authentication flow

## Authentication Flow

1. User accesses JumpCloud User Portal
2. User clicks Google Workspace application
3. JumpCloud generates SAML assertion
4. User redirected to Google Workspace
5. Google validates SAML assertion
6. Access granted

## Security

- SAML 2.0 encryption
- Certificate-based validation
- Centralized access control
- Audit logging enabled

## Monitoring

Successful authentication log from Jumpcloud:
```json
{
  "error_message": "",
  "initiated_by": {
    "administrator": false,
    "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "type": "user",
    "username": "okrare.jerry"
  },
  "server_timestamp": "2026-02-22T01:00:52.203069748Z",
  "geoip": {
    "country_code": "US",
    "timezone": "America/New_York",
    "latitude": xx.xxxxx,
    "continent_code": "NA",
    "region_name": "Georgia",
    "longitude": -xx.xxxxx,
    "region_code": "GA"
  },
  "timestamp_source": "server",
  "sso_token_success": true,
  "target_resource": {
    "type": "APPLICATION"
  },
  "useragent": {
    "os_full": "Windows 10",
    "os": "Windows",
    "major": "143",
    "minor": "0",
    "os_major": "10",
    "os_version": "10",
    "name": "Firefox",
    "os_name": "Windows",
    "version": "143.0",
    "device": "Other"
  },
  "auth_context": {
    "auth_methods": {},
    "policies_applied": [
      {
        "metadata": {
          "resource_type": "APPLICATION",
          "action": "ALLOW"
        },
        "name": "Global Policy",
        "id": ""
      }
    ]
  },
  "mfa": false,
  "event_type": "sso_auth",
  "application": {
    "display_label": "Jauto Google Workspace",
    "sso_type": "saml",
    "name": "google",
    "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "sso_url": "https://sso.jumpcloud.com/saml2/jautogoogleworkspace"
  },
  "provider": "",
  "service": "sso",
  "organization": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "@version": "1",
  "client_ip": "x.x.x.x",
  "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "idp_initiated": true,
  "timestamp": "2026-02-22T01:00:52Z"
}
```
## Results

- ✅ Successful SSO deployment
- ✅ Zero authentication failures post-configuration
- ✅ Centralized identity management
- ✅ Improved security posture

## Technologies Used

- JumpCloud Directory Platform
- Google Workspace
- SAML 2.0
- X.509 Certificate Authentication

## License

Internal documentation for organizational use.
**Author:** Sylvester Baruch  
