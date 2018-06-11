+++
date = "2015-12-2T14:10:00+03:00"
draft = false
title = "How does KeyGuardAPI work?"
weight = 6
+++

<i class="fas fa-key"></i> For signature operations in DLT nodes/applications a private key is normally used locally to sign a message.

<i class="fas fa-hdd"></i> HSMs transfer the private key handling from the application server to a dedicated secure hardware device.

<i class="far fa-comments"></i> For an application to use an HSM it calls an API with credentials and a message payload for the key on the HSM to sign.

<i class="fas fa-exclamation-triangle"></i> If an application is compromised the private key can be forced to sign messages chosen by the attacker.

<i class="fas fa-user-secret"></i> The attacker can perform a time consuming chosen-plaintext attack to reveal the private keys.

<i class="fas fa-user-secret"></i> But it is much easier to send the HSM a payload to sign that gives the attacker all of the funds secured by your keys...

<i class="fas fa-shield-alt"></i> _KeyGuardAPI sits in between the application and the HSM and firewalls each signature request to the HSM._

<i class="fas fa-ban"></i> If the request does not fit the configured validation requirements it is rejected and does not reach your HSM.

<i class="fas fa-medkit"></i> Once messages are signed by the HSM they are sanitized again to ensure safe data is returned to the application.

<i class="fas fa-user-ninja"></i> This prevents even the most determined hackers from gaining unintended access to your private keys.

<i class="fas fa-exclamation-circle"></i> _**safeSig <.io> never has unencrypted access to your private keys**_
