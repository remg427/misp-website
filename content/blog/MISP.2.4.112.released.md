---
title: MISP 2.4.112 released (aka summer fixes and improvement)
date: 2019-08-01
layout: post
banner: /img/blog/vuln.png
---

# MISP 2.4.112 released

A new version of MISP ([2.4.112](https://github.com/MISP/MISP/tree/v2.4.112)) has been released with a host of API fixes, improvements and a security fix.

## Improvements

- [sync] Event index cleaned up, total count of listed events added as X-Result-Count header
- [sync] Previewing a remote instance now passes pagination rules in the request instead of fetching the full data-set and paginating in memory. This also include a fix to issues with empty preview pages. Massive performance boost when previewing a remote instance. This requires the remote side to be the same version or newer.
- [API] New parameters added to attributes/restSearch to include additional context, fixes #4935, fixes #4940, affects MISP/PyMISP#415.

  - includeSightings: include sightings for all attributes returned
  - includeCorrelations: include the correlations to other attributes (includes a light-weight event object with each attribute)
- [cli] Added cleanCaches command.
- [API] Disable background processing on-demand via URL parameters.
- [API] Disable DB logging completely, fixes #4921.
- [API] IncludeContext now includes the additional event fields in the attributes/restSearch results (in JSON format).
- [data model] New attribute type weakness (CWS) added
- [alerting] Block the alerting of events based on the date field as an alternative to the timestamp, fixes #4937.
- [warning-list] Speedup improvement in the CIDR lookup.
- [UI] Add a quick button for the event attribute toolbar for the showing of related tags.
- [restClient] Do not override query body if url hasn't changed.
- [feed-metadata] Panels Tracker feed added.
- [eventGraph:search] Usage of chosen instead of bootstrap with non- stripped label.

## Bugs fixed

Many bugs fixed based on the extensive PyMISP test cases in addition to manual reviews. All fixes are documented in the [changelog](/Changelog.txt).

## CVE-2019-14286 fixed

[CVE-2019-14286](https://cve.circl.lu/cve/CVE-2019-14286) has been fixed. In app/webroot/js/event-graph.js in MISP 2.4.111, a stored XSS vulnerability exists in the event-graph view when a user toggles the event graph view. A malicious MISP event must be crafted in order to trigger the vulnerability. This vulnerability has been fixed in MISP 2.4.112. We strongly encourage everyone to update as soon as possible. Thanks to David Heise who reported the vulnerability.

## misp-modules

[misp-modules](https://misp.github.io/misp-modules/) have been improved with new modules especially with a new advanced CVE module which includes the ability to import CVEs along with their associated weaknesses and attack techniques (as you can see in the screenshot). The documentation has been also improved (thanks to all the contributors who helped us on the documentation).

[MISP galaxies](/galaxy.html), [MISP object templates](/objects.html) and [MISP warning-lists](https://github.com/MISP/misp-warninglists/) have been updated to the latest version. MISP galaxy has been updated to include the July edition of the MITRE ATT&CK model.

We would like to thank all the [contributors](/contributors), reporters and users who have helped us in the past months to improve MISP and information sharing at large.

As always, a detailed and [complete changelog is available](/Changelog.txt) with all the fixes, changes and improvements.

