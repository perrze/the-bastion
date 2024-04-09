============
groupCreate
============

Usage       : --osh groupCreate --group GROUP --owner ACCOUNT --algo ed25519 [--encrypted] [--no-key]
=====================================================================================================

Description : creates group GROUP on the bastion with ACCOUNT as the owner
Params      :

    --group       Group name to create

    --owner       Preexisting bastion account to assign as owner (can be you)

    --encrypted   Add a passphrase to the key. Beware that you'll have to enter it for each use.
                  Do NOT add the passphrase after this option, you'll be prompted interactively for it.

    --algo        Specifies the algo of the key, either rsa, ecdsa or ed25519.
    --size        Specifies the size of the key to be generated.
                  For RSA, choose between 2048 and 8192 (4096 is good).
                  For ECDSA, choose either 256, 384 or 521.
                  For ED25519, size is always 256.

    --no-key      Don't generate an egress SSH key at all for this group

With the policy and SSH version on this bastion,
the following algorithms are supported: RSA ECDSA ED25519

algo    size  strength   speed    compatibility
------- ----  ---------- -------- -----------------------
RSA     4096  good       slow     works everywhere
ECDSA    521  strong     fast     debian7+ (OpenSSH 5.7+)
ED25519  256  verystrong veryfast debian8+ (OpenSSH 6.5+)
