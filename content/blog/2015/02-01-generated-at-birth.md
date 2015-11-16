Title:  Generated at Birth
Date:   2015-02-01 02:00:00
Author: Alex Kersten
---

Imagine a system that houses your most important data and through which you
make your most vital fiscal decisions. A platform via which you can borrow
against credit, relinquish power of attorney, receive government benefits, and
command financial accounts. Surely such a platform would be routinely audited
for security - a single compromise of user credentials would prove devastating
to the unfortunate victims. Surely users would be held to the utmost
standards of password hygiene, with complexity enforcement and mandatory
two-factor authentication. Surely, if such a system existed and were
its security measured by the yardstick, an impregnable utopia the
goalposts, we'd at least be in the red zone.

You'd better grab your napkins, because we're way back in the nosebleeds. In
a different stadium.

Astute readers may have noticed that at least the functional description of
our hypothetical platform does reflect a real system in the US - we have a
central identity system through which we can perform all of the
aforementioned tasks and more. The only trouble is the way we authenticate
our identity with this platform. Or, more specifically, the fact that *we
can't*.

> **Developer A:** Hey, I just committed the finishing touches for our new
online banking login portal. Tell me what you think, yeah?

> **Dev B:** This looks great and all, but where's the password field? I can
only type in my username.

> **Dev A:** Your username _is_ the password!

Of course, I'm talking about social security numbers. We entrust our
reputation to the enduring secrecy of a 9-digit number. A 9-digit number
whose keyspace is continuously shrinking[^1], whose components can be
predicted[^2], and whose secrecy for millions of individuals has been
obliterated countless times over by accidental release[^3] and compromise of
completely auxiliary services[^4].

Clearly, the system is fundamentally flawed. Let's go back to the drawing
board and look at the problem we're trying to solve. We need a way to provide
a proof of identify iff we truly are the person identified by that identity.
That is, we need a system where simply having a signature from a person
cannot be used to generate more signatures or signatures in a different
context.

Sound familiar? It should, because this is a solved problem. In fact, it has
been solved so many times that there is an entire field of mathematics
devoted to it. We're talking about [public-key cryptography](http://en
.wikipedia.org/wiki/Public-key_cryptography). Let's take this for a spin.

Imagine that, at birth, you are generated[^5] a keypair.

That concept is powerful enough to be its own paragraph. Take your keypair
and sign revocable subkeys with it. Use a subkey to sign whatever dreadful
contract your local monopolistic ISP cooks up. When you're done with their
service, revoke the key by signing a dated revocation notice with it, and
whatever credit authority is responsible for computing your credit score will
not honor credit adjustments after a key has been revoked[^6]. In contrast to
the present-day system where myriad people have had their credit destroyed
by false accusations of unreturned equipment or breach of contract.

An individual can be identified by their signature, and they now have complete
control over their identity. A secret number that is thousands of bytes long
is a lot harder to lose than a 9-digit number that you give away.


[^1]: [SSN Death Master File](http://ssdmf.info/)
[^2]: [SSN prefixes by state](http://www.ssa.gov/employer/stateweb.htm). By the way, [SSN randomization](http://www.ssa.gov/employer/randomization.html)  is about as useful as trying to extend the longevity of the IPv4 address space, and is also not relevant to you (unless you were born after June 2011)
[^3]: [SSNs released premortem](http://cancelthesefunerals.com/)
[^4]: Why does my ISP need to know my SSN?
[^5]: Through some secure air-gapped hardware RNG, offloaded onto read-only time-locked media, and entrusted to your guardian until you are of-age to make independent decisions
[^6]: Clearly, revoking a key in this way would signify the end of the contract, in breach or naturally (but either way provably)
