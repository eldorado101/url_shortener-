Peepso URL Shortener (Admin Only)
Version: 1.4

Author: Dakota

Description: A secure, admin-only URL shortener with analytics for WordPress.

Table of Contents

Installation

Features

Usage

Technical Notes

Troubleshooting

Credits

Installation

Upload the Plugin:

Upload the peepso-url-shortener folder to the wp-content/plugins/ directory.
Alternatively, install via WordPress Admin → Plugins → Add New → Upload.

Activate the Plugin:

Go to Plugins > Installed Plugins and activate Peepso URL Shortener (Admin Only).

Flush Rewrite Rules:

Visit Settings > Permalinks and click Save Changes to enable short URL routing.

Features

Admin-only Access: Only users with manage_options capability (Administrators by default) can manage URLs.

Short URL Creation:
Generate unique short codes for any URL.
Short URLs are accessible via yourdomain.com/s/shortcode.

Analytics:
Track clicks and last clicked time for each URL.

Secure Design:
Uses nonces to prevent CSRF attacks.
Sanitizes all user inputs.

Edit/Delete URLs:
Modify or remove existing URLs via the admin interface.

Permanent Redirects:
Uses 301 redirects for SEO-friendliness.

Usage
1. Access the Admin Page

Go to URL Shortener in the WordPress admin menu.

2. Add a New URL

Enter a valid URL in the Add New URL form.

Click Shorten to generate a short code.

3. Manage URLs

Edit: Click Edit to modify a URL’s destination.

Delete: Click Delete to remove a URL (confirm with nonce).

4. View Analytics

The Existing URLs table shows:
Short code, long URL, creation date, click count, and last clicked time.
Direct links to test short URLs.

Technical Notes
Database Structure

Table Name: wp_peepso_short_urls (prefix depends on your WordPress setup).

Columns:
id: Unique ID.
short_code: Unique short code (e.g., abc123).
long_url: The original URL.
created_at: Timestamp of URL creation.
clicks: Number of clicks.
last_clicked: Last time the URL was accessed.

Rewrite Rules

Short URLs are routed via the rewrite rule ^s/([^/]*)/?.

Security

Nonces: Used in all forms and delete links to prevent CSRF.

Capabilities: Only users with manage_options can access the admin page.

Input Sanitization: Uses esc_url(), absint(), and $wpdb->prepare() for SQL queries.

Troubleshooting

Short URLs Not Working?

Ensure rewrite rules are flushed (Settings > Permalinks).
Check the uninstall.php file exists if reinstalling.

Error: "Security Check Failed"

Caused by expired/invalid nonces. Refresh the page and try again.

Database Issues?

Deactivate/reactivate the plugin to recreate the database table.

Credits

Built using WordPress core classes:
WP_List_Table for admin table styling.
$wpdb for database interactions.

Inspired by best practices for WordPress plugin security and performance.

License: GPLv2 or later (WordPress license).

Support: For issues or feedback, contact dakota@contentsocial.net

