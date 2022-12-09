---
title: Vue d’ensemble de Dynamics 365 Payment Connector pour Adyen
description: Cet article donne une vue d’ensemble du connecteur de paiement Microsoft Dynamics 365 pour Adyen.
author: rassadi
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.openlocfilehash: 58d88e023b73ce19331bd6f54644a62d8f6f35af
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812084"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Vue d’ensemble de Dynamics 365 Payment Connector pour Adyen

[!include [banner](../includes/banner.md)]

Cet article donne une vue d’ensemble du connecteur de paiement Microsoft Dynamics 365 pour Adyen et inclut une liste complète des fonctions et fonctionnalités prises en charge. Les articles connexes couvrent l’inscription à Adyen, la configuration du connecteur, les questions fréquemment posées et des conseils de dépannage pour certains problèmes courants.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Connecteur de paiement | Une extension qui facilite la communication entre Microsoft Dynamics 365 Commerce (et les composants associés) et un service de paiement. Le connecteur décrit dans cet article a été implémenté à l’aide du kit de développement logiciel (SDK) de paiement standard. |
| Avec carte | Fait référence à des transactions de paiement où une carte physique est présentée et utilisée dans un connecteur de terminal de paiement qui est connecté à Dynamics 365 POS. |
| Sans carte | Fait référence aux transactions de paiement où une carte physique n’est pas présente, comme les scénarios de commerce électronique ou de centre d’appels. Dans ces scénarios, les informations associées au paiement sont entrées manuellement, soit dans un site Web de e-commerce, soit dans un flux de centre d’appels, ou dans le terminal de paiement ou du PDV. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Fonctions, fonctionnalités, versions et terminaux pris en charge

Le connecteur de paiement Dynamics 365 pour Adyen prêt à l’emploi utilise le kit de développement logiciel de paiement standard. Par conséquent, il ne dispose pas de fonctionnalités spéciales qui ne sont pas également disponibles pour les autres connecteurs de paiement.

### <a name="supported-versions"></a>Versions prises en charge

#### <a name="microsoft-dynamics-365-supported-versions"></a>Version prises en charge de Microsoft Dynamics 365
Le connecteur de paiement propriétaire et prêt à l’emploi de Dynamics 365 pour Adyen est pris en charge dans Microsoft Dynamics 365 Finance version 8.1.3 (janvier 2019) ou version ultérieure, et dans Microsoft Dynamics 365 Retail version 8.1.3 ou ultérieure. Cependant, les tiers peuvent toujours développer d’autres connecteurs de paiement pour Adyen pour les versions antérieures de Microsoft Dynamics 365.

#### <a name="supported-adyen-firmware-versions"></a>Versions du microprogramme Adyen prises en charge

La liste ci-dessous décrit les versions minimales et maximales du microprogramme Adyen prises en charge pour chaque version de Microsoft Dynamics 365 Retail POS.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Dynamics 365 Retail POS version 10.0.25
| Version minimale du microprogramme Adyen | Version maximale du microprogramme Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Dynamics 365 Retail POS version 10.0.26
| Version minimale du microprogramme Adyen | Version maximale du microprogramme Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Dynamics 365 Retail POS version 10.0.27
| Version minimale du microprogramme Adyen | Version maximale du microprogramme Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Dynamics 365 Retail POS version 10.0.28
| Version minimale du microprogramme Adyen | Version maximale du microprogramme Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Dynamics 365 Retail POS version 10.0.29
| Version minimale du microprogramme Adyen | Version maximale du microprogramme Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Dynamics 365 Retail POS version 10.0.30
| Version minimale du microprogramme Adyen | Version maximale du microprogramme Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> Adyen peut publier des mises à jour de versions mineures après que Microsoft a testé la version majeure. Tant qu’une version majeure est prise en charge, il est acceptable d’avoir des mises à jour de version mineure dans la même version majeure. Ces mises à jour sont généralement des correctifs très ciblés qui n’exigent pas de nouveau test complet, tant que la même version majeure du microprogramme a déjà été testée. Les mises à jour ne doivent pas dépasser la version maximale du microprogramme Adyen indiquée dans la documentation. 
>
> La migration d’une version de microprogramme Adyen antérieure à la version 53 vers la version 53 nécessite l’article de la base de connaissances **4577957** concernant les PDV pour les mises à jour mensuelles de Commerce, versions 10.0.11 à 10.0.14. Si l’une de ces versions est en cours d’utilisation et n’inclut pas le correctif, après la mise à niveau, le terminal de paiement n’autorisera que les paiements via NFC. L’application du correctif au PDV résout ce problème. Si la version du PDV est antérieure à la version 10.0.11, déposez une demande de support en notant qu’un correctif pour l’article de la base de connaissances **4577957** est requis pour un MPOS hors service.
> 
> Pour les versions 59p7 à 62p9 du microprogramme Adyen, l’opération **décaissement de carte cadeau** demande la saisie du code PIN par deux fois dans les scénarios où la carte-cadeau est saisie manuellement. Ce problème ne se produit pas lorsque la carte cadeau est glissée dans le lecteur. Adyen étudie le problème. 

### <a name="supported-payment-terminals"></a>Terminaux de paiement pris en charge
Le connecteur de paiement Dynamics 365 pour Adyen tire parti de l’[API Adyen Payment Terminal](https://www.adyen.com/blog/introducing-the-terminal-api) indépendante des appareils. Elle prend en charge tous les terminaux de paiement pris en charge par cette interface de programmation d’application (API). Pour une liste complète des terminaux de paiement pris en charge, consultez la page [Terminaux de point de vente Adyen](https://www.adyen.com/pos-payments/terminals).

La vidéo suivante décrit les capacités du terminal de paiement Android Adyen Castles SE1.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bKeM]

### <a name="supported-payment-instruments"></a>Instruments de paiement pris en charge

#### <a name="supported-debit-and-credit-cards"></a>Cartes de crédit prises en charge

| Marque | Variante | Carte présente | Commerce électronique | Centre d’appels |
|---|---|:-:|:-:|:-:|
| MasterCard | Crédit | ✔ | ✔ | ✔ |
| MasterCard | Débit | ✔ | ✔ | ✔ |
| MasterCard | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| MasterCard | Apple Pay | ✔ |  |  |
| MasterCard | Samsung Pay | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maestro Samsung Pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VISA | Crédit | ✔ | ✔ | ✔ |
| VISA | Débit | ✔ | ✔ | ✔ |
| VISA | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| VISA | Android Pay | ✔ |  |  |
| VISA | Apple Pay | ✔ |  |  |
| VISA | Samsung Pay | ✔ |  |  |
| VISA | VISA Checkout | ✔ | ✔ | ✔ |
| VISA | VISA Dankort | ✔ | ✔ | ✔ |
| VISA | VISA Hipotecario | ✔ | ✔ | ✔ |
| VISA | Carte VISA Aravia | ✔ | ✔ | ✔ |
| AMEX | Crédit | ✔ | ✔ | ✔ |
| AMEX | Débit | ✔ | ✔ | ✔ |
| AMEX | Android Pay | ✔ |  |  |
| AMEX | Apple Pay | ✔ |  |  |
| AMEX | Samsung Pay | ✔ |  |  |
| AMEX | AMEX Commercial | ✔ | ✔ | ✔ |
| AMEX | AMEX Consumer | ✔ | ✔ | ✔ |
| AMEX | AMEX Corporate | ✔ | ✔ | ✔ |
| AMEX | AMEX Small Business | ✔ | ✔ | ✔ |
| Discover | Standard | ✔ | ✔ | ✔ |
| Discover | Android Pay | ✔ |  |  |
| Discover | Apple Pay | ✔ |  |  |
| Discover | Samsung Pay | ✔ |  |  |
| Diners | Standard | ✔ | ✔ | ✔ |
| Dineromail | Standard | ✔ | ✔ | ✔ |
| JCB | Standard | ✔ | ✔ | ✔ |
| Union Pay\* | Standard | ✔ |  |  |
| Interac Debit\* | Standard | ✔ |  |  |

\*Les jetons de carte récurrents Interac et Union Pay ne sont pas fournis par Adyen, ils ne peuvent donc pas être pris en charge pour les transactions sans carte.

#### <a name="supported-gift-cards"></a>Cartes cadeaux prises en charge
| Scheme | Carte présente | Carte absente |
|---|:-:|---|
| Givex | ✔ | ✔ |
| SVS | ✔ | ✔ |

Pour prendre en charge ces programmes de cartes cadeaux externes via le connecteur de paiement Dynamics 365 pour Adyen, vous devez effectuer des étapes supplémentaires. Pour plus d’informations, voir [Prise en charge des cartes cadeaux externes ](/dynamics365/unified-operations/retail/dev-itpro/gift-card).

#### <a name="supported-wallets"></a>Portefeuilles pris en charge

| Scheme | Carte présente | Carte absente |
|---|---|---|
| Alipay | Cette prise en charge sera ajoutée dans une prochaine version. | N° |
| WeChat | Cette prise en charge sera ajoutée dans une prochaine version. | N° |

#### <a name="supported-card-present-input-methods"></a>Méthodes de saisie avec carte prises en charge
| Méthode de saisie | Prise en charge | Notes |
|---|:-:|---|
| Insertion de carte | ✔ | |
| Passage de carte | ✔ | |
| Contact sur l’écran | ✔ | |
| Saisie manuelle via l’interface utilisateur du point de vente. |  | Non pris en charge pour le moment |
| Saisie manuelle via le terminal de paiement. | ✔ | Prend en charge la saisie manuelle des cartes de crédit et des cartes cadeaux avec saisie du code PIN. | 


#### <a name="supported-card-present-countries"></a>Pays pris en charge avec carte

Les pays suivants disposent de composants Commerce et de la prise en charge des cartes par Adyen. Pour connaître la disponibilité internationale actuelle de Commerce, visitez la [Page de disponibilité internationale](/dynamics365/get-started/availability).

| Pays | Prise en charge |
| --- | :-: |
| Australie | ✔ |
| Autriche | ✔ |
| Belgique | ✔ |
| Canada | ✔ |
| République tchèque | ✔ |
| Danemark | ✔ |
| Estonie | ✔ |
| Finlande | ✔ |
| France | ✔ |
| Allemagne | ✔ |
| R.A.S. de Hong Kong | ✔ |
| Hongrie | ✔ |
| Islande | ✔ |
| Irlande | ✔ |
| Italie | ✔ |
| Japon | Version future |
| Lettonie | ✔ |
| Lituanie | ✔ |
| Malaisie | ✔ |
| Pays-Bas | ✔ |
| Nouvelle-Zélande | ✔ |
| Norvège | ✔ |
| Pologne | ✔ |
| Singapour | ✔ |
| Suisse | ✔ |
| Espagne | ✔ |
| Suède | ✔ |
| Suisse | ✔ |
| Royaume-Uni | ✔ |
| Etats-Unis | ✔ |
| Brésil | Version future |

#### <a name="supported-card-not-present-countries"></a>Pays pris en charge sans carte

Les pays suivants sont pris en charge par Adyen pour les transactions sans carte. [Contactez Adyen](https://www.adyen.com/contact/sales) pour plus de détails sur la prise en charge dans un pays spécifique. Pour connaître la disponibilité internationale actuelle de Commerce, visitez la [Page de disponibilité internationale](/dynamics365/get-started/availability).

| Pays | 
| --- |
| Argentine |
| Arménie |
| Australie |
| Autriche |
| Royaume de Bahreïn |
| Belgique |
| Brésil |
| Bulgarie |
| Canada |
| Chili |
| Chine |
| Colombie |
| Croatie |
| Chypre |
| République tchèque  |
| Danemark |
| Égypte |
| Estonie |
| Finlande |
| France |
| Georgia |
| Allemagne |
| Gibraltar |
| Grèce |
| Guernesey |
| R.A.S. de Hong Kong |
| Hongrie |
| Islande |
| Inde |
| Indonésie |
| Irlande |
| Île de Man |
| Israël |
| Italie |
| Japon |
| Jersey |
| Corée |
| Koweït |
| Lettonie |
| Lituanie |
| Luxembourg |
| Malaisie |
| Malte |
| Mexique |
| Maroc |
| Pays-Bas |
| Nouvelle-Zélande |
| Norvège |
| Pérou |
| Pologne |
| Portugal |
| Qatar |
| Roumanie |
| Arabie saoudite |
| Serbie |
| Singapour |
| Slovaquie |
| Slovénie |
| Afrique du Sud |
| Espagne |
| Suède |
| Suisse |
| Taïwan |
| Tanzanie |
| Thaïlande |
| Turquie |
| Émirats arabes unis (EAU) |
| Royaume-Uni |
| États-Unis d’Amérique, y compris Porto Rico  |

#### <a name="supported-dynamics-365-payment-features"></a>Fonctionnalités de paiement Dynamics 365 prises en charge

Le tableau suivant présente l’ensemble des fonctionnalités prises en charge par le connecteur de paiement Dynamics 365 pour Adyen. Ces fonctionnalités utilisent des améliorations qui ont été introduites dans le kit de développement logiciel Paiements et certains composants en décembre 2018. Elles ne sont pas exclusives au connecteur de paiement Dynamics 365 pour Adyen. Pour plus d’informations sur l’utilisation de ces améliorations pour un autre connecteur de paiement, consultez [Créer une intégration de paiement de bout en bout pour un terminal de paiement](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Scheme | Carte présente | Carte absente |
|---|:-:|:-:|
| [Décaisser le solde d’une carte cadeau](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Protection contre les paiements en double](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Émission de jetons omnicanaux | ✔ | ✔ |
| Remboursements associés | ✔<br>(À partir de la version 10.0.1) | ✔<br>(À partir de la version 10.0.1) |
| [Enregistrer les paiements en ligne](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(À partir de la version 10.0.2) | 
| [Cartes cadeaux externes pour les centres d’appel et le e-commerce](./gift-card.md) | ✔<br>(À partir de la version 10.0.10) | 
| [Redirection des paiements SCA](../adyen_redirect.md) | | ✔<br>(À partir de la version 10.0.12) |
| [Terminaux de paiement dédiés et invites pour une imprimante et un tiroir-caisse](../pos-multi-hws.md) | ✔<br>(À partir de la version 10.0.12) | |
| [Prise en charge des pourboires au niveau du kit de développement logiciel via le connecteur Adyen](tipping.md) | ✔<br>(À partir de la version 10.0.14) | |
| [Capture incrémentielle pour la facturation des commandes](incremental-capture.md) |  | ✔<br>(À partir de la version 10.0.18) |
| [Paiements par portefeuille](../wallets.md) |  | ✔<br>(À partir de la version 10.0.20) |
| [Google Pay avec Adyen](google-pay-adyen.md) |  | ✔<br>(À partir de la version 10.0.27) |

## <a name="next-steps"></a>Étapes suivantes

Pour plus d’informations sur l’inscription et la configuration du connecteur de paiement Dynamics 365 pour Adyen, voir [Configuration du connecteur de paiement Dynamics 365 pour Adyen](adyen-connector-setup.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer Dynamics 365 Payment Connector pour Adyen](adyen-connector-setup.md)

[FAQ de Dynamics 365 Payment Connector pour Adyen](adyen-connector-faq.md)

[Résoudre les problèmes avec Dynamics 365 Payment Connector pour Adyen](adyen-connector-troubleshoot.md)

[FAQ Paiements](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
