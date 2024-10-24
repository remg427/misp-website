---
title: MISP 2.4.136 released (Cerebrate project integration)
date: 2021-01-18
layout: post
banner: /img/blog/galaxy2.0/4.jpeg
---

# MISP 2.4.136 released

Though we're rather late with the release notes, we did have some goodies to share for the winter festivities, bundled neatly into the [2.4.136 release](https://github.com/MISP/MISP/releases/tag/v2.4.136).

Apart from the usual bug fixes and usability improvements, we've also added some new features to play with.

# First integration with Cerebrate

[Cerebrate](https://github.com/cerebrate-project) is an up and coming tool we're developing as part of the [MeliCERTes project](https://ec.europa.eu/digital-single-market/en/news/open-platforms-collaborate-cyber-threats), aiming to ease the management of both larger sharing communities as well as a set of local tools. The tool is self-hosted and can be used to maintain information on organisations and individuals that we interact with along with sharing group metadata. We also want to use this to make the harmonisation of MISP related organisation metadata information between instances of an organisation or a community (such as UUIDs, public keys, meta-information, etc).

In addition it will also act as an orchestration platform, easing the interconnections between organisations for both MISP and other tools.

In this first iteration, we can use a Cerebrate instance as a lookup repository for organisation metadata in MISP, using a familiar preview/pull mechanism that we're used to in MISP.

We also welcome contributions to that project, especially since the internals are aligned more and more with MISP and will act as the foundation for the next major MISP rework. For more information visit the [Cerebrate on github](https://github.com/cerebrate-project)

# A host of quality of life improvements for the sharing groups

The larger our communities grow, the more it becomes important to be able to quickly and accurately find the information that we're after in our sharing group repositories. Thanks to the tireless work of @JakubOnderka, we can now filter sharing groups, find events associated to a sharing group and more.

# Even though testing is doubting, doubt is the origin of wisdom

A new test suite was added by @JakubOnderka to enrich the CI suite with a set of tests aiming to detect potential security / ACL flaws in the system.

# Installer improvements

The [MISP installer](https://misp.github.io/MISP/INSTALL.ubuntu2004/) has been significantly improved especially concerning the installation of the misp-modules and various refactoring to improve the capability of replaying the install process.

# Release management

Finally a notice on a change we have made to our release management, we will from here on rely on an additional branch for development to ensure that half-baked features don't make their way to the 2.4 branch. Until now the recommendation was to stick to tagged releases for stability and to just track the 2.4 branch for the quickest bug fixes.

This lead to both options having downsides (should I miss out on a potential bug fix or risk running non-finalised features in my system?).

With the current approach, all new development will go on the "develop" branch, which we purely recommend to be used by developers, the 2.4 branch will see the features merged from develop just prior to a release after the testing and readying the release is completed. Once that is done, the usual tagging of a new version will occur.

This allows us to still include hotfixes and urgent bugfixes on 2.4, without muddying the water with potentially risky new developments, as such we encourage all users to track the HEAD of the 2.4 branch from here on.

# Acknowledgement

We would like to thank all the [contributors](/contributors), reporters and users who have helped us in the past months to improve MISP and information sharing at large. This release includes multiple updates in [misp-objects](/objects.html), [misp-taxonomies](/taxonomies.html) and [misp-galaxy](/galaxy.html)
.

As always, a detailed and [complete changelog is available](/Changelog.txt) with all the fixes, changes and improvements.

