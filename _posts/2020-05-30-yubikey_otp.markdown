---
layout: post
title:  "YubikeyOTP, a classic Yubikey OTP Library For Elixir"
date:   2020-05-30 10:45:00
categories: software
header_image: YubiKey-5C-inserted-on-desk-composite-cropped-1.png
author: Pete Birkinshaw
---

We've recently released a new open source Elixir library called YubikeyOTP. It's available on
 [Github](https://github.com/Digital-Identity-Labs/yubikey_otp) and via [Hex.pm](https://hex.pm/packages/yubikey_otp) under
 the MIT license.

YubikeyOTP will take the One Time Password (OTP) emitted by a Yubikey and send it to a validation service - by
 default, the one run by Yubico. You can use it in a web application to add two-factor authentication (2FA) but it can
 also be used in any other application that allows users to type input.

In case you're not familiar with Yubikeys, they are small plastic USB devices with a single button that provide one or
more ways to authenticate. They're very useful as an extra layer of login security. Their original authentication method
 was to generate and type (they behave as USB keyboards) unique, verifiable passwords that can be checked by a remote
 service. Ten years ago "hardware tokens" used as a second factor were usually hard to purchase, expensive and awkward
 to use. The Yubikey changed that.

This might seem an odd time to support the original Yubikey format when recent Yubikeys are capable of the new,
[unphishable](https://fidoalliance.org/wp-content/uploads/05-GDasher-Becoming-Unphishable.pdf) and non-proprietary
[WebAuthn](https://webauthn.guide/) protocol, but we've done it for a few reasons:

* There are lots of Yubikeys already sold and in use that do not support WebAuthn. They can still be useful - it's
 better to use "classic" OTP than not use a second factor
* The unchanging username/deviceid part of the OTP is potentially a privacy issue when used on public websites, but can be
  useful for organisations wanting to clearly associate Yubikeys with particular users. It's very easy to grant users
  access using their deviceID and it's important that access control be simple to maintain.
* We have a customers using them, and also use them ourselves. I'm not going to tell people to go away and buy new
 Yubikeys when they've already got something useful.
* Yubico have said they will continue to support their OTP protocol (although cheaper Yubikeys will only use WebAuthn)

We plan to support the new, open standard WebAuthn protocol too, and if you have a recent Yubikey you're probably
 much better off using that method of authenticating if you can. There seems to be decent support for WebAuthn in Java, Ruby and Elixir packages already
 so we're unlikely to be creating our own code for this.

Our YubikeyOTP library is currently an early version and hasn't been used in production yet. If you spot any bugs or
 missing features please let us know!


