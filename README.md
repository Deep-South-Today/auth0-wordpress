# Auth0 Wordpress

## Overview
This is a modified version of the Auth0 plugin for wordpress forked from [auth0/wordpress](https://github.com/auth0/wordpress) for use on DST sites.

## Installation

1. Upload the plugin files to `/wp-content/plugins/auth0-wordpress/`
2. Activate the plugin through the 'Plugins' screen in WordPress
3. Configure the Application Configuration credentials in Auth0 > Options:
   * Client ID
   * Client Secret
   * Domain: **deep-south-today.us.auth0.com**
4. Save and update the rest of the settings below.

## Settings

1. Auth0 — Options
   * Enable Authentication - **Enabled**
   * Connection Matching - **Flexible**
   * Missing Users - **Deny Accesss**
   * Default Role - Guest Contributor
   * Allow Passwordless - **Disabled**

2. Auth0 — Advanced Options
   * Pair Sessions - **Disabled**
   * WordPress Login Fallback - **Disabled**
   * Custom Domain - **login.deepsouthtoday.org**
   * JWKS Caching - WP_Object_Cache
   * Device Storage Method - Encrypted Cookies
   * Session Expires - Default
   * Use Rolling Sessions - **Disabled**
   * Use Refresh Tokens - Disabled
   * Session Cookies > Require SSL - **Enabled**

## Setting up a new domain

1. Install [WPS Hide Login](https://wordpress.org/plugins/wps-hide-login/) and change the login URL to **login**
2. Contact Kinsta Support to exclude **/login** from caching
3. In Cloudflare, add the cache rule `(http.request.uri.path eq "/login")` to the domain
4. In the [Auth0 dashboard](https://auth0.com), add the new domain to
   * Allowed Callback URLs: `https://domain.org/login/`
   * Allowed Logout URLs: `https://*.domain.org`
     




