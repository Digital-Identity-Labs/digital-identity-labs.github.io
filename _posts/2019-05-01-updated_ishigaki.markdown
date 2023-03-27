---
layout: post
title:  "Ishagaki Update: 0.4.5"
date:   2019-05-01 21:20:00
categories: software
header_image: 39371663884_c29cf054ae_w.jpg
author: Pete Birkinshaw
tags:
  - docker
  - shibboleth
---

We've released a minor update to [Ishigaki](https://github.com/Digital-Identity-Labs/ishigaki), our Docker image for the Shibboleth IdP.

The Jetty project released Jetty 9.4.18, a minor update, a few days ago, and today The 
Shibboleth Consortium released a minor update to the Shibboleth IdP (3.4.4), so
it's time for a new release of Ishigaki: 0.4.5.

Jetty has had [quite a few bugfixes since 9.4.15](https://github.com/eclipse/jetty.project/releases), including fixes for a directory
traversal security flaw. The Shibboleth IdP has [a few fixes and an
alternative LDAP driver](https://wiki.shibboleth.net/confluence/display/IDP30/ReleaseNotes#ReleaseNotes-3.4.4(May1,2019)) that may be needed when using LDAP with recent 
versions of Java.

  * [Ishigaki source code and docs](https://github.com/Digital-Identity-Labs/ishigaki)
  * [Ishigaki Docker image](https://cloud.docker.com/u/digitalidentity/repository/docker/digitalidentity/ishigaki)
