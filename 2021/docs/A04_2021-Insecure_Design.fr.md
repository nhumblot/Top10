# A04:2021 – Conception non sécurisée   ![icon](assets/TOP_10_Icons_Final_Insecure_Design.png){: style="height:80px;width:80px" align="right"}

## Facteurs

| CWEs associées | Taux d'incidence max | Taux d'incidence moyen | Exploitation pondérée moyenne | Impact pondéré moyen | Couverture max | Couverture moyenne | Nombre total d'occurrences | Nombre total de CVEs |
|:--------------:|:--------------------:|:----------------------:|:-----------------------------:|:--------------------:|:--------------:|:------------------:|:--------------------------:|:--------------------:|
|       40       |       24,19 %        |         3,00 %         |             6,46              |         6,78         |    77,25 %     |      42,51 %       |          262 407           |        2 691         |

## Aperçu

Une nouvelle catégorie pour 2021, l'accent est mis sur les risques liés aux failles de conception et d'architecture, avec un appel à l'augmentation du recours aux modèles de menaces, aux modèles et principes de conceptions sécurisés et aux architectures de référence. En tant que communauté, nous devons ajouter des contrôles en amont du développement, ces phases sont vitales pour une conception sécurisée. Les *Common Weakness Enumerations* (CWE) notables incluses sont *CWE-209: Generation of Error Message Containing Sensitive Information*, *CWE-256: Unprotected Storage of Credentials*, *CWE-501: Trust Boundary Violation* et *CWE-522: Insufficiently Protected Credentials*.

## Description

Conception non sécurisée est une vaste catégorie représentant différentes insuffisances, exprimées par « contrôles de conception manquants ou inefficaces ». La conception non sécurisée n'est pas la source de toutes les autres catégories de risques du Top 10. Il existe une différence entre une conception non sécurisée et une implémentation non sécurisée. Nous différencions les défauts de conception et les défauts d'implémentation pour une raison, ils ont des causes racines et des mesures correctives différentes. Une conception sécurisée peut toujours présenter des défauts d'implémentations conduisant à des vulnérabilités pouvant être exploitées. Une conception non sécurisée ne peut pas être corrigée par une implémentation parfaite car, par définition, les contrôles de sécurité nécessaires n'ont jamais été créés pour se défendre contre des attaques spécifiques. L'un des facteurs qui contribuent à la conception non sécurisée est le manque de profilage des risques commerciaux inhérent au logiciel ou au système en cours de développement, et donc l'incapacité à déterminer le niveau de sécurité requis.

### Gestion des exigences et des ressources

Recueillez et négociez les exigences métier pour une application avec les équipes fonctionnelles, y compris les exigences de sécurité concernant la confidentialité, l'intégrité, la disponibilité et l'authenticité de l'ensemble des données et de la logique métier attendue. Prenez compte du degré d'exposition de votre application et si vous avez besoin de séparer les tenants (en plus du contrôle d'accès). Rassemblez les exigences techniques, y compris les exigences de sécurité fonctionnelles et non fonctionnelles. Planifiez et négociez le budget couvrant l'ensemble de la conception, de la construction, des tests et de l'exploitation, y compris les activités de sécurité.

### Conception sécurisée

La conception sécurisée est une culture et une méthodologie qui évalue en permanence les menaces et garanti que le code est conçu et testé de manière robuste pour empêcher les méthodes d'attaques connues. La modélisation des menaces doit être intégrée aux sessions de *refinement* (ou activités similaires) et rechercher des changements dans les flux de données et le contrôle d'accès. Dans les *user stories*, déterminez le cas passant et les états d'échecs, assurez-vous qu'ils sont bien compris et acceptés par les parties responsables et impactées. Analysez les hypothèses et les conditions pour les cas passants et en échecs, assurez-vous qu'ils sont toujours exacts et souhaités. Déterminez comment valider les hypothèses et mettez en place les conditions nécessaires pour un comportement approprié. Assurez-vous que les résultats sont documentés dans la *user story*. Apprenez de vos erreurs, incitez et faites la promotion des améliorations. La conception sécurisée n'est ni un module complémentaire, ni un outil que vous pouvez ajouter au logiciel.

### Cycle de développement sécurisé

Un logiciel sécurisé nécessite un cycle de vie de développement sécurisé, une méthode de conception sécurisée, une voie pavée, une bibliothèque de composants sécurisés, des outils et une modélisation des menaces. Faites appel à vos spécialistes de la sécurité tout au long du projet et de la maintenance de votre logiciel. Essayez de tirer parti de l'[OWASP Software Assurance Maturity Model (SAMM)](https://owaspsamm.org) pour vous aider à structurer vos efforts de développement sécurisé.

## How to Prevent

-   Establish and use a secure development lifecycle with AppSec
    professionals to help evaluate and design security and
    privacy-related controls

-   Establish and use a library of secure design patterns or paved road
    ready to use components

-   Use threat modeling for critical authentication, access control,
    business logic, and key flows

-   Integrate security language and controls into user stories

-   Integrate plausibility checks at each tier of your application
    (from frontend to backend)

-   Write unit and integration tests to validate that all critical flows 
    are resistant to the threat model. Compile use-cases *and* misuse-cases
    for each tier of your application.

-   Segregate tier layers on the system and network layers depending on the
    exposure and protection needs

-   Segregate tenants robustly by design throughout all tiers

-   Limit resource consumption by user or service

## Example Attack Scenarios

**Scenario #1:** A credential recovery workflow might include “questions
and answers,” which is prohibited by NIST 800-63b, the OWASP ASVS, and
the OWASP Top 10. Questions and answers cannot be trusted as evidence of
identity as more than one person can know the answers, which is why they
are prohibited. Such code should be removed and replaced with a more
secure design.

**Scenario #2:** A cinema chain allows group booking discounts and has a
maximum of fifteen attendees before requiring a deposit. Attackers could
threat model this flow and test if they could book six hundred seats and
all cinemas at once in a few requests, causing a massive loss of income.

**Scenario #3:** A retail chain’s e-commerce website does not have
protection against bots run by scalpers buying high-end video cards to
resell auction websites. This creates terrible publicity for the video
card makers and retail chain owners and enduring bad blood with
enthusiasts who cannot obtain these cards at any price. Careful anti-bot
design and domain logic rules, such as purchases made within a few
seconds of availability, might identify inauthentic purchases and
rejected such transactions.

## References

-   [OWASP Cheat Sheet: Secure Design Principles](Coming Soon)

-   [OWASP SAMM: Design:Security Architecture](https://owaspsamm.org/model/design/security-architecture/)

-   [OWASP SAMM: Design:Threat Assessment](https://owaspsamm.org/model/design/threat-assessment/) 

-   [NIST – Guidelines on Minimum Standards for Developer Verification of Software](https://www.nist.gov/publications/guidelines-minimum-standards-developer-verification-software)

-   [The Threat Modeling Manifesto](https://threatmodelingmanifesto.org)

-   [Awesome Threat Modeling](https://github.com/hysnsec/awesome-threat-modelling)

## List of Mapped CWEs

[CWE-73 External Control of File Name or Path](https://cwe.mitre.org/data/definitions/73.html)

[CWE-183 Permissive List of Allowed Inputs](https://cwe.mitre.org/data/definitions/183.html)

[CWE-209 Generation of Error Message Containing Sensitive Information](https://cwe.mitre.org/data/definitions/209.html)

[CWE-213 Exposure of Sensitive Information Due to Incompatible Policies](https://cwe.mitre.org/data/definitions/213.html)

[CWE-235 Improper Handling of Extra Parameters](https://cwe.mitre.org/data/definitions/235.html)

[CWE-256 Unprotected Storage of Credentials](https://cwe.mitre.org/data/definitions/256.html)

[CWE-257 Storing Passwords in a Recoverable Format](https://cwe.mitre.org/data/definitions/257.html)

[CWE-266 Incorrect Privilege Assignment](https://cwe.mitre.org/data/definitions/266.html)

[CWE-269 Improper Privilege Management](https://cwe.mitre.org/data/definitions/269.html)

[CWE-280 Improper Handling of Insufficient Permissions or Privileges](https://cwe.mitre.org/data/definitions/280.html)

[CWE-311 Missing Encryption of Sensitive Data](https://cwe.mitre.org/data/definitions/311.html)

[CWE-312 Cleartext Storage of Sensitive Information](https://cwe.mitre.org/data/definitions/312.html)

[CWE-313 Cleartext Storage in a File or on Disk](https://cwe.mitre.org/data/definitions/313.html)

[CWE-316 Cleartext Storage of Sensitive Information in Memory](https://cwe.mitre.org/data/definitions/316.html)

[CWE-419 Unprotected Primary Channel](https://cwe.mitre.org/data/definitions/419.html)

[CWE-430 Deployment of Wrong Handler](https://cwe.mitre.org/data/definitions/430.html)

[CWE-434 Unrestricted Upload of File with Dangerous Type](https://cwe.mitre.org/data/definitions/434.html)

[CWE-444 Inconsistent Interpretation of HTTP Requests ('HTTP Request Smuggling')](https://cwe.mitre.org/data/definitions/444.html)

[CWE-451 User Interface (UI) Misrepresentation of Critical Information](https://cwe.mitre.org/data/definitions/451.html)

[CWE-472 External Control of Assumed-Immutable Web Parameter](https://cwe.mitre.org/data/definitions/472.html)

[CWE-501 Trust Boundary Violation](https://cwe.mitre.org/data/definitions/501.html)

[CWE-522 Insufficiently Protected Credentials](https://cwe.mitre.org/data/definitions/522.html)

[CWE-525 Use of Web Browser Cache Containing Sensitive Information](https://cwe.mitre.org/data/definitions/525.html)

[CWE-539 Use of Persistent Cookies Containing Sensitive Information](https://cwe.mitre.org/data/definitions/539.html)

[CWE-579 J2EE Bad Practices: Non-serializable Object Stored in Session](https://cwe.mitre.org/data/definitions/579.html)

[CWE-598 Use of GET Request Method With Sensitive Query Strings](https://cwe.mitre.org/data/definitions/598.html)

[CWE-602 Client-Side Enforcement of Server-Side Security](https://cwe.mitre.org/data/definitions/602.html)

[CWE-642 External Control of Critical State Data](https://cwe.mitre.org/data/definitions/642.html)

[CWE-646 Reliance on File Name or Extension of Externally-Supplied File](https://cwe.mitre.org/data/definitions/646.html)

[CWE-650 Trusting HTTP Permission Methods on the Server Side](https://cwe.mitre.org/data/definitions/650.html)

[CWE-653 Insufficient Compartmentalization](https://cwe.mitre.org/data/definitions/653.html)

[CWE-656 Reliance on Security Through Obscurity](https://cwe.mitre.org/data/definitions/656.html)

[CWE-657 Violation of Secure Design Principles](https://cwe.mitre.org/data/definitions/657.html)

[CWE-799 Improper Control of Interaction Frequency](https://cwe.mitre.org/data/definitions/799.html)

[CWE-807 Reliance on Untrusted Inputs in a Security Decision](https://cwe.mitre.org/data/definitions/807.html)

[CWE-840 Business Logic Errors](https://cwe.mitre.org/data/definitions/840.html)

[CWE-841 Improper Enforcement of Behavioral Workflow](https://cwe.mitre.org/data/definitions/841.html)

[CWE-927 Use of Implicit Intent for Sensitive Communication](https://cwe.mitre.org/data/definitions/927.html)

[CWE-1021 Improper Restriction of Rendered UI Layers or Frames](https://cwe.mitre.org/data/definitions/1021.html)

[CWE-1173 Improper Use of Validation Framework](https://cwe.mitre.org/data/definitions/1173.html)
