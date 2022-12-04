
# Security_Magento

This section describes the different technologies used by magento to maintain
security of Magento . Moreover this section deals with
decription of different compliances of specific privacy legislation
followed by Magento.


## Documentation

Magento applies a Content Security policy (CSP). With this 
policy it provides an additional layer of security aginst different data injection attacks.
This common attack vector works by injecting malicious content that falsely claims to originate from the website.
Once this content is loaded it begins the tranfer of sensitive data.

In all this scenario , CSP is useful when it tells the browser to which resource source it should trust and which should be blocked.
Using carefully defined policies, CSP can restrict browser content to allow only whitelisted resources to appear.

CSP has two modes: 

```bash
  report-only
```

```bash
  restrict mode
```

#### Report-only
In report only mode which is by default mode in Magento.
It reports all the resources which violated the CSP.In this mode it does not enforce the compliance with CSP.
Once all the valid resources are whitelisted then Magento can apply or enforce CSP(restrict mode).

#### Restric mode
In restrict mode, the browser is instructed to enforce all content policies and limit publication to whitelisted resources

### Enhanced Password Management 

Magento has improved the hashing algorithms it uses to store
the passwords. Magento now uses the Argon2ID13 algorithms to store Password.
Argon2ID13 is an algorithm for storing password
- It resists the GPU cracking attacks
- Argon2i is optimized to resist side-channel attacks

#### Argon2i

Argon2 is a cryptographic algorithm that allows you to store your entries safely. 
It is dedicated to password encryption and doesn’t have any uses apart from that.
- Argon2d maximizes resistance to GPU cracking attacks
- Argon2i is optimized to resist side-channel attacks

#### Pictorial Description

![Process](https://devdocs.magento.com/common/images/archi_hash_upgrade_algorithm.png)

### Prevention from ClickJacking attacks
ClickJacking is a from of attack in which hackers display a dummy 
web page to users . This can cause users to unwittingly download malware,
visit malicious web pages, provide credentials 
or sensitive information, transfer money, or purchase products online.
Magento protects it users from ClickJacking by
adopting the mechanism of X-Frame Option.
X-Frame Options becomes the part of HTTP header and 
it directs the browser either to load the webpage in frame or not.

Further information can be read from here:
[Security Documentation of Magento](https://experienceleague.adobe.com/docs/commerce-operations/security-and-compliance/overview.html)


## Compliance 

Magento follows two Compliances 

- California Consumer Privacy Act (CCPA)

- General Data Protection Regulation (GDRP)

### CCPA 

The California Consumer Privacy Act is a state statute intended to enhance privacy rights and consumer protection for residents of California, United States.

You can read more about CCPA from here:

[CCPA docs](https://experienceleague.adobe.com/docs/commerce-operations/security-and-compliance/privacy/ccpa.html?lang=en)


### GDRP
The General Data Protection Regulation is a regulation in EU law on data protection and privacy in the European Union and the European Economic Area

[GDRP docs](https://experienceleague.adobe.com/docs/commerce-operations/security-and-compliance/privacy/gdpr.html?lang=en)
