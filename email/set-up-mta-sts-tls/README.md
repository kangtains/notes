# Set Up MTA-STS TLS Mail

In order to set up MTA-STS, first you need to create a ``TXT record`` on ``_mta-sts.your-domain`` to indicate that your domain supports MTA-STS:

```
_mta-sts.your-domain IN TXT "v=STSv1; id=12345678"
In the record value v=STSv1; id=12345678 above:
```

* the ``v`` tag must be ``STSv1``, the protocol literal;
* the ``id``` tag contains an alphanumeric string up to 32 alphanumerics long, used to track policy (see below) updates; it must uniquely identify a given instance of a policy, such that senders can determine when the policy has been updated by comparing to the id of a previously seen policy.

Simply click the green button as illustrated above to copy the record to the clipboard, then publish it in the DNS.

Next you need to create an MTA-STS policy as follows:

```
version: STSv1
mode: testing
mx: your-email-host
max_age: 86400
In the policy above:
```

* version must be ``STSv1``;
* mode can be ``enforce``, ``testing``, or ``none``:

**enforce mode**: the sending server must not deliver the message to a receiving host that fails MX matching or certificate validation or that does not support STARTTLS;

**testing mode**: the sending server delivers the message; if TLS reporting is implemented, the sending server also sends a TLS report to the specified email addresses indicating policy application failure, when the receiving host fails MX matching or certificate validation or does not support STARTTLS;

**none mode**: the sending server treats the policy domain as though it does not have any active policy;

* ``mx`` points to one of your MX hosts; multiple mx key/value pairs are possible;
* ``max_age`` is the max lifetime of the policy in seconds, 31557600 maximum.

Modify the ``mx`` value in the MTA-STS policy based on your own MX settings. For example, if your domain's MX record points to: ``your-email-server.com``, you need to update the policy to:

```
version: STSv1
mode: testing
mx: your-email-server.com
max_age: 86400
```

If your domain has multiple MX records, create multiple mx key/value pairs in the policy:

```
version: STSv1
mode: testing
mx: your-email-server.com
mx: another-email-server.com
max_age: 86400
```

Once the policy looks good, save it in a txt file ``mta-sts.txt`` somewhere on your computer.

Next we need to host the MTA-STS policy file so that it becomes accessible for all on the internet at:

```
https://mta-sts.your-domain/.well-known/mta-sts.txt
```

You need to take the following 2 steps:

create an mta-sts subdomain on your-domain in the DNS;

create a ``.well-known`` directory under your web root; then copy ``mta-sts.txt`` to ``.well-known/``.

Once this is done, ensure the MTA-STS policy file is accessible by navigating to the following url in your favorite browser:

```
https://mta-sts.your-domain/.well-known/mta-sts.txt
```