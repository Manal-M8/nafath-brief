skeleton: NAFATH-V4

overview:

the six core disciplines of software, mobile, data, networking, artificial intelligence, and cybersecurity work together harmoniously to
form the current digital infrastructure. core software engineering architectures power mobile computing applications, which serve as primary nodes 
generating massive, continuous streams of real-time data. this data is transmitted across advanced cloud and edge networking infrastructures to eliminate latency.
once centralized or routed at the edge, the data fuels complex ai and machine learning models, enabling systems to perform predictive analytics and
intelligent automation. cutting across this entire pipeline, cybersecurity frameworks act as a multi-layered shield, leveraging ai-driven anomaly detection to 
safeguard network protocols, protect data privacy, and secure application integrity. together, these fields form an interconnected, self-optimizing ecosystem where
network connectivity, cognitive intelligence, and data security are seamlessly unified.

research:

##software

the twelve-factor app technique requires that secrets and configuration be kept solely in environment variables. they should never be in the code
because hardcoding secrets compromises security by exposing private credentials in version control repositories. decoupling them allows for
smooth cross-environment deployment (development, staging, and production) without changing code logic or necessitating an application rebuild, 
while maintaining the codebase's full open-sourceability.

resource: the twelve-factor app methodology - https://www.pyyne.com/post/the-twelve-factor-app-methodology

##ai

adversarial attacks on machine learning systems are categorized primarily into poisoning and evasion attacks, differing strictly by 
the targeted lifecycle phase. poisoning attacks strike during the training phase by injecting malicious data to corrupt the model's foundational 
learning process. conversely, evasion attacks target the inference phase, where attackers subtly manipulate test inputs to deceive a fully trained model 
into making incorrect predictions without altering its architecture.

resource: evasion adversarial attacks remain impractical against ml-based network intrusion detection systems, especially dynamic ones - https://arxiv.org/html/2306.05494v5 

##mobile

the owasp mobile application security verification standard (masvs) is a comprehensive framework establishing baseline security requirements for
mobile applications. it is used as a benchmark to verify mobile security by structuring assessments into architectural and threat-model categories 
(such as data storage, cryptography, and network communication). developers and auditors utilize its standardized security levels to conduct code reviews, 
vulnerability assessments, and penetration testing, ensuring robust defenses against reverse-engineering and data leakage.

resource: evaluating mobile banking application security posture using the owasp’s masvs framework - https://dl.acm.org/doi/abs/10.1145/3588001.3609367

research:

##networking

bgp route hijacking occurs when a malicious autonomous system (as) falsely advertises ip prefixes, steering global traffic to its network
via longest prefix matching. rpki mitigates this by utilizing cryptographically signed route origin authorizations (roas) to drop unauthorized announcements.
however, rpki does not protect against as-path manipulation; if an attacker falsifies the path while preserving the legitimate origin as, 
the invalid route is still accepted.

resource: rpki for beginners: how to secure your ip blocks from bgp hijacking -https://ipbnb.com/blog/rpki-bgp-hijacking-prevention#what-is-rpki 

##cybersecurity

log4shell was a critical remote code execution vulnerability in apache's log4j logging utility. it was rated a maximum 10.0 severity score
because it allowed unauthenticated attackers to execute arbitrary code simply by submitting a malicious string via jndi lookups. 
the security flaw was fixed by disabling jndi message lookups by default in log4j 2.15.0 and completely removing the vulnerable jndi ldap lookup functionality 
in version 2.16.0.

resource: log4shell rce vulnerability- https://digital.nhs.uk/cyber-alerts/2021/cc-3989 

##data

a software bill of materials (sbom) is a structured inventory listing all components, libraries, and dependencies within a software product.
to ensure transparency and supply chain security, it must contain seven minimum data fields: supplier name, component name, version of the component,
other unique identifiers, dependency relationship, author of sbom data, and timestamp. this metadata allows organization tracking of vulnerabilities.

resource: what is a software bill of materials (sbom) - https://www.ibm.com/think/topics/sbom 

analysis:

##misconception 

many mobile developers believe that securing an application only requires transport-layer encryption (https/tls). they falsely assume standard os sandboxing, like android storage parameters or ios data protection, fully immunizes local assets against runtime interception.

##correct version

local storage is highly susceptible to root extraction, reverse-engineering, and physical memory dumps. relying solely on platform isolation fails when devices are jailbroken or compromised by exploits; thus, application-layer encryption backed by hardware keychains (android keystore/ios keychain) is mandatory.

##open question

i would verify how to use automated tools to quickly scan mobile apps for hidden security flaws. additionally, i plan to learn how developers protect apps
from modern hacking tools that try to steal data from device memory, ensuring my application keeps user information completely safe.


resource:  masvs-storage: storage - https://mas.owasp.org/masvs/05-masvs-storage/ 

