# RapidDock privacy policy

Effective date: September 24, 2026

This policy covers RapidDock Integration for Microsoft Edge and its companion RapidDock Windows download manager, maintained by the GitHub account danielpiro. Their purpose is to transfer downloads and magnet links from the browser to the local download manager.

## Information accessed and used

The extension observes HTTP and HTTPS requests associated with browser tabs. It temporarily stores request URLs, request methods, timestamps, and available Cookie, Authorization, and User-Agent headers in local browser session storage. This request context is gathered before the extension knows which request will become a download, so it can include requests unrelated to a captured download. Cookies and authorization headers can contain sensitive sign-in credentials.

For a captured download, the extension passes the download URL, referring page URL, filename, and available recent request headers to the locally installed RapidDock application through native messaging. For a clicked magnet link, it passes the link and referring page URL to the application. It accesses hyperlink targets to handle magnet clicks; it does not extract page text, images, audio, or video, or record general typing or mouse movements.

The extension stores the automatic-capture preference and last capture error locally. It reads browser download information and pauses a captured download while the desktop application accepts it. After successful handoff, it cancels and erases that browser download entry. If handoff fails, it attempts to resume the browser download.

## Storage and retention

Request context is stored in browser session storage, not a RapidDock cloud service. Only context less than 60 seconds old is used for handoff. Cleanup runs periodically as requests arrive and when navigation completes; each cleanup removes entries older than 60 seconds and entries beyond the newest 512. Entries can remain until the next cleanup or the browser session ends. Context is also removed after a download handoff attempt.

The capture preference and last error persist in local extension storage until replaced or that storage is cleared. The desktop app stores transfer state locally so unfinished downloads can resume; this state can include URLs and request headers. Completing or removing a transfer removes it from the active queue, but does not securely erase backups or previously saved local files. Downloaded files are saved in Windows Downloads by default and remain until the user deletes them.

## Sharing and external connections

RapidDock has no analytics or advertising service. The publisher does not receive browsing history, download history, cookies, or authorization headers through a RapidDock-operated server. RapidDock does not sell user data, use it for advertising or unrelated purposes, or use it to assess creditworthiness or for lending.

The desktop app contacts the download servers selected by the user, including servers reached through redirects. These services receive the network requests needed to download the files, including the user's IP address and applicable request headers. Their privacy policies apply. Torrent downloads contact trackers and peers, which can see the user's IP address and torrent participation.

Desktop update checks contact GitHub. Optional saved repository credentials are encrypted for the current Windows account and excluded from portable distribution packages. Existing GitHub CLI credentials may also authorize updates. GitHub handles update requests, this policy page, and support interactions under its [privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). Edge handles extension installation and store updates separately.

## User controls

Turning off automatic capture stops automatic download handoff. In the current extension, it does not stop temporary request-context storage or magnet-link handling. Disable or remove the extension to stop all extension activity. Browser extension controls can restrict site access, which may prevent download handoff from working on restricted sites.

Users can remove queued transfers, clear saved update credentials, delete local application data, and uninstall the extension or desktop application. Downloaded files require separate deletion. Windows startup registration can be disabled in Windows Startup settings.

## Contact and changes

For privacy or support questions, [open an issue on the RapidDock support page](https://github.com/danielpiro/RapidDock-support/issues). Issues are public: do not include cookies, authorization headers, passwords, private download URLs, or other sensitive personal information.

Changes to these practices will be reflected in this policy and its effective date.
