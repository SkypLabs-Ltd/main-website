+++
title="Google Authenticator is not your friend"
date=2023-04-27

[taxonomies]
categories = ["News"]
tags = ["2FA", "MFA", "Security", "Privacy"]
+++
The Google Authenticator mobile application has been around for more than a
decade, allowing to generate [Time-based One Time Passwords (TOTP)][totp]
locally on platforms such as Android and iOS. A few days ago, an update was
released adding a couple of new features, including the possibility to
synchronise your TOTP secrets with Google.

<!-- more -->

## Even more data sent to Google

The synchronisation feature has been under the spotlight recently, as [it has
been proven that the TOTP secrets are not sent end-to-end encrypted (E2EE) to
Google][mysk-twitter-post]. This poses both security and privacy issues, as
Google would know the list of all your online accounts for which you have
enabled TOTP [Two-Factor Authentication (2FA)][mfa], giving them another
opportunity to produce an even more complete picture of your online activities,
but it also increases the number of threats to your digital life as your TOTP
secrets can be stolen if either your Google account or Google's infrastructure
is compromised.

## Our recommendation

Two criteria should be prioritised when choosing an online service for storing
and processing sensitive data, and they can be expressed as the form of the
following questions: is the data sent end-to-end encrypted before leaving your
device and is the software processing your data open-source?

E2EE increases significantly your privacy and security, as the online services
you send data to won't be able to spy on you, nor any potential attacker
exploiting a security breach in those online services. Additionally, if the
software sending your data is open-source, it means it can be audited by
security experts, guaranteeing the absence of security flaws and backdoors.

[ente Authenticator][ente-auth] ticks the boxes by providing a way to
synchronise your TOTP secrets easily while protecting your accounts and
respecting your privacy. Their [implementation of E2EE has been
audited][ente-security-audit] by [Cure53][cure53] and [Symbolic
Software][symbolic-software], and "together they have certified that ente's
architecture is sound and that \[their\] implementation across all clients is
cryptographically accurate". As of today, this service is free of charge.

## Conclusion

As explained earlier in this post, using the synchronisation feature of Google
Authenticator poses security and privacy issues, and is therefore discouraged.
We recommend people use user-respecting software like ente Authenticator or
equivalent.

 [cure53]: https://cure53.de/ "Cure53"
 [ente-auth]: https://ente.io/blog/auth/ "ente Authenticator"
 [ente-security-audit]: https://ente.io/blog/cryptography-audit/ "ente security audit"
 [mysk-twitter-post]: https://twitter.com/mysk_co/status/1651021165727477763 "Twitter post from Mysk about Google Authenticator leaking TOTP secrets"
 [symbolic-software]: https://symbolic.software/ "Symbolic Software"
 [totp]: https://en.wikipedia.org/wiki/Time-based_One-time_Password "TOTP - Wikipedia"
 [mfa]: https://en.wikipedia.org/wiki/Multi-factor_authentication "MFA - Wikipedia"
