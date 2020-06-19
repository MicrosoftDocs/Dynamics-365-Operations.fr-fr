---
title: Terminaux de paiement dédiés et invites pour une imprimante et un tiroir-caisse
description: Cette rubrique fournit des informations sur la possibilité d'avoir un terminal de paiement dédié et d'inviter l'utilisateur à sélectionner un tiroir-caisse et une imprimante de reçus.
author: rubendel
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: tonyafehr
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 4035817fb534477eb4146ff712a92d6e29ce2db2
ms.sourcegitcommit: 4db8c30c2f26af1896938dd3ece3756577374ecb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3416604"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Terminaux de paiement dédiés et invites pour une imprimante et un tiroir-caisse

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur la possibilité d'avoir un terminal de paiement dédié et d'inviter l'utilisateur à sélectionner un tiroir-caisse et une imprimante de reçus.

## <a name="overview"></a>Vue d’ensemble

Les distributeurs modernes recherchent des moyens de simplifier l'expérience de paiement en magasin. Les nouvelles tendances de paiement sans papier utilisant des moyens électroniques contribuent non seulement à fluidifier l'expérience d'achat, mais réduisent également la nécessité de disposer d'une gamme complète de périphériques pour chaque employé du magasin.

Microsoft Dynamics 365 Commerce adopte ces tendances en rendant possible un scénario dans lequel un terminal de point de vente (PDV) a un terminal de paiement dédié qui lui est affecté en permanence, mais ne possède pas sa propre imprimante de reçus ni son propre tiroir-caisse. Lorsque les collaborateurs doivent imprimer un reçu ou réceptionner un paiement en espèces, ils sont invités à sélectionner une station matérielle sur laquelle ces périphériques sont configurés.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Inscrire | Entité utilisée pour configurer une instance d'une caisse enregistreuse de PDV. |
| Périphérique | Représentation de l'instance physique d'une caisse enregistreuse de PDV et de l'application MPOS qui lui est affectée. |
| Station matérielle dédiée | Logique métier de station matérielle qui est intégrée dans les applications Modern POS pour Windows ou Modern POS pour Android. |
| Port d'ouverture de tiroir-caisse (d/k) | Méthode classique pour connecter un tiroir-caisse à une imprimante de reçus. |
| Périphériques réseau | Prise en charge intégrée des terminaux de paiement, des imprimantes de reçus et des tiroirs-caisse compatibles réseau. |

## <a name="supported-pos-clients-and-devices"></a>Clients et appareils de PDV pris en charge

La fonctionnalité décrite dans cette rubrique est prise en charge par les clients de PDV Modern POS pour Windows et Modern POS pour Android.

Cette fonctionnalité prend en charge les terminaux de paiement et les imprimantes de reçus compatibles réseau. Vous pouvez prendre en charge le tiroir-caisse en connectant celui-ci à l'imprimante de reçus compatible réseau via le port d/k.

La prise en charge prête à l'emploi de cette fonctionnalité est assurée par le [Connecteur de paiement Dynamics 365 pour Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). Cependant, d'autres connecteurs de paiement peuvent être pris en charge via le kit de développement logiciel (SDK) Commerce pour les paiements. Les imprimantes de reçus prises en charge incluent les imprimantes de reçus compatibles réseau de Star Micronics et Epson.

Pour configurer les imprimantes de reçus Star Micronics, utilisez l'utilitaire Star Micronics Printer Utility pour configurer le périphérique afin qu'il puisse être utilisé sur le réseau. Cet utilitaire fournira également l'adresse IP de l'appareil.

Pour configurer les imprimantes de reçus Epson, utilisez l'utilitaire Epson ePOS-Print pour configurer le périphérique afin qu'il utilise les protocoles réseau.

Pour plus d'informations sur la configuration des périphériques réseau, consultez [Vue d'ensemble de la prise en charge des périphériques réseau](https://go.microsoft.com/fwlink/?linkid=2129965).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Configurer un terminal de paiement dédié et une invite pour une imprimante et un tiroir-caisse

### <a name="set-up-hardware-profiles"></a>Paramétrage de profils matériels

Vous devez avoir deux types de profil matériel. Le premier est affecté à la caisse enregistreuse. Le deuxième est affecté à une station matérielle au niveau du magasin et est utilisé pour regrouper logiquement les imprimantes de reçus et les tiroirs-caisses en réseau.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Configurer un profil matériel pour la caisse enregistreuse

Pour configurer le profil matériel affecté à la caisse enregistreuse, procédez comme suit.

1. Dans Dynamics 365 Commerce, recherchez **Profil matériel**.
2. Sélectionnez **Nouveau**.
3. Attribuez un numéro de profil matériel, puis entrez une description. Ce profil matériel sera affecté à la caisse enregistreuse elle-même. Par conséquent, une description telle que **Dédié au secours** suffira.
4. Dans les raccourcis des différents types d'appareils, configurez les types d'appareils suivants.

    | Périphérique | Type | Nom du périphérique | Détails supplémentaires |
    |---|---|---|---|
    | Imprimante | Secours | **Epson** ou **Star** | Le nom d'appareil est sensible à la casse. L'**ID du profil de reçu** doit être le même que l'**ID du profil de reçu** qui est mappé sur l'imprimante réseau configurée dans le profil matériel affecté à la station matérielle au niveau du canal. |
    | Tiroir-caisse | Secours | **Epson** ou **Star** | Le nom d'appareil est sensible à la casse. Définissez l'option **Utiliser les équipes de travail partagées** sur **Oui**. |
    | Service TEF | Adyen | Non applicable | Pour plus d'informations sur la configuration du connecteur de paiement Adyen prêt à l'emploi, voir [Connecteur de paiement Dynamics 365 pour Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3). D'autres connecteurs de paiement peuvent être pris en charge via le [kit de développement logiciel (SDK) Commerce pour les paiements](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/end-to-end-payment-extension). |
    | Clavier d'identification personnelle | Réseau | **MicrosoftAdyenDeviceV001** | Aucun(e). |

5. Dans Dynamics 365 Commerce, recherchez **Caisses enregistreuses**.
6. Sélectionnez une caisse enregistreuse en sélectionnant son numéro, puis sélectionnez **Modifier**.
7. Attribuez le profil matériel que vous venez de créer à la caisse enregistreuse qui doit utiliser un terminal de paiement dédié. Le périphérique mappé à cette caisse enregistreuse doit utiliser l'application Modern POS pour Windows ou l'application Modern POS pour Android.
8. Sélectionnez **Enregistrer**.
9. Dans le volet Actions, sous l'onglet **Caisses enregistreuses**, sélectionnez **Configurer les adresses IP**.
10. Dans le raccourci **Clavier d'identification personnelle**, entrez l'adresse IP du terminal de paiement. Pour plus d'informations sur la façon d'obtenir l'adresse IP du terminal de paiement à l'aide du connecteur Adyen, voir [Connecteur de paiement Dynamics 365 pour Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3).
11. Sélectionnez **Enregistrer**.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>Configurer un profil matériel pour l'imprimante de reçus et le tiroir-caisse

Pour configurer le profil matériel utilisé pour regrouper l'imprimante de reçus et le tiroir-caisse réseau, procédez comme suit.

1. Dans Dynamics 365 Commerce, recherchez **Profil matériel**.
2. Sélectionnez **Nouveau**.
3. Attribuez un numéro de profil matériel, puis entrez une description. Ce profil matériel sera utilisé pour regrouper l'imprimante de reçus et le tiroir-caisse. Par conséquent, une description telle que **Imprimante réseau et tiroir-caisse** suffira.
4. Dans les raccourcis des différents types d'appareils, configurez les types d'appareils suivants.

    | Périphérique | Type | Description | Détails supplémentaires |
    |---|---|---|---|
    | Imprimante | Réseau | **Epson** ou **Star** | Le nom d'appareil est sensible à la casse. L'**ID du profil de reçu** doit être le même que l'**ID du profil de reçu** qui est mappé sur l'imprimante configurée dans le profil matériel affecté à la caisse enregistreuse. |
    | Tiroir-caisse | Secours | **Epson** ou **Star** | Le nom d'appareil est sensible à la casse. Définissez l'option **Utiliser les équipes de travail partagées** sur **Oui**. |

5. Sélectionnez **Enregistrer**.

### <a name="set-up-hardware-stations"></a>Configurer des postes matériels

Vous devez disposer de deux postes matériels. Le premier sera mappé sur la caisse enregistreuse. Le deuxième sera sélectionné selon les besoins, chaque fois qu'un reçu devra être imprimé ou qu'un tiroir-caisse devra être ouvert.

#### <a name="register-a-hardware-station"></a>Enregistrer une station matérielle

1. Dans Dynamics 365 Commerce, recherchez **Tous les magasins**.
2. Sélectionnez un magasin en sélectionnant ses valeurs **ID canal de vente au détail**, puis sélectionnez **Modifier**.
3. Dans le raccourci **Postes matériels**, sélectionnez **Ajouter**.
4. Définissez le **Type de station matérielle** sur **Dédié**.
5. Entrez une description, mais ne définissez aucune autre valeur pour cette station matérielle. Cette station matérielle sera utilisée à tout moment pour la caisse enregistreuse. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>Configurer une station matérielle pour l'imprimante de reçus et le tiroir-caisse

1. Dans Dynamics 365 Commerce, recherchez **Tous les magasins**.
2. Sélectionnez un magasin en sélectionnant ses valeurs **ID canal de vente au détail**, puis sélectionnez **Modifier**.
3. Dans le raccourci **Postes matériels**, sélectionnez **Ajouter**.
4. Définissez le **Type de station matérielle** sur **Dédié**.
5. Entrez une description. Cette station matérielle sera utilisée pour l'imprimante de reçus et le tiroir-caisse.
6. Dans le champ **Profil matériel**, sélectionnez le profil matériel que vous avez créé précédemment pour l'imprimante de reçus et le tiroir-caisse.
7. Sélectionnez **Enregistrer**.
8. Tandis que la station matérielle pour l'imprimante de reçus et le tiroir-caisse est toujours sélectionnée, sélectionnez **Configurer les adresses IP**.
9. Obtenez l'adresse IP de l'imprimante et saisissez-la comme adresse IP pour l'imprimante de reçus et le tiroir-caisse.
10. Sélectionnez **Enregistrer**.
11. Recherchez **Programmes de distribution**.
12. Sélectionnez le programme de distribution **1090**, puis sélectionnez **Exécuter maintenant**.
13. Sélectionnez le programme de distribution **1070**, puis sélectionnez **Exécuter maintenant**.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>Configurer le système pour demander la sélection de l'imprimante de reçus et du tiroir-caisse selon les besoins

1. Dans un client de PDV pris en charge, fermez l'équipe de travail en cours, s'il y en a une d'ouverte.
2. Connectez-vous, puis sélectionnez **Opérations de tiroir sans rapport avec le tiroir-caisse**.
3. Utilisez l'opération **Gérer les stations matérielles** pour activer une station matérielle.
4. Sélectionnez la station matérielle que vous avez créée pour la caisse enregistreuse pour la rendre active.
5. Déconnectez-vous du PDV, reconnectez-vous, puis ouvrez une équipe de travail.

Le terminal de paiement affecté au profil matériel sera désormais toujours actif et vous recevrez une invite si une imprimante de reçus ou un tiroir-caisse est requis.

De nombreux commerçants qui ont demandé cette fonctionnalité souhaitent réduire les déchets en fournissant des reçus par e-mail et en encourageant les paiements électroniques. Selon la configuration du PDV, les collaborateurs du magasin sont invités à sélectionner une imprimante de reçus ou un tiroir-caisse uniquement lorsqu'un client souhaite un reçu physique ou souhaite payer en espèces.

Les collaborateurs du magasin sont invités à sélectionner une station matérielle une seule fois par transaction, sauf si un reçu doit être imprimé et que le paiement est effectué en espèces, mais le profil matériel qui a été sélectionné à l'origine n'inclut pas les deux appareils. Dans ce cas, le collaborateur du magasin sera à nouveau invité à sélectionner une station matérielle pouvant être utilisée pour mener à bien la transaction.

## <a name="related-articles"></a>Articles connexes

- [Paramétrer une application POS Hybrid sur Android et iOS](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp)
- [Connecteur de paiement Dynamics 365 pour Adyen](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)
- [Vue d'ensemble de la prise en charge des périphériques réseau](https://go.microsoft.com/fwlink/?linkid=2129965)
