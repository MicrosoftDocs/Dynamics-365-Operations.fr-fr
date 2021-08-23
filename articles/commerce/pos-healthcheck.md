---
title: Contrôle sanitaire des périphériques et services de PDV
description: Cette rubrique fournit une vue d’ensemble de l’opération de contrôle d’intégrité dans le point de vente (PDV).
author: rubendel
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 89f926af540ff7c7a57824419edb295ab3b78ee8b22684cb14a0ab6f3436bb01
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715380"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Contrôle sanitaire des périphériques et services de PDV

[!include [banner](includes/banner.md)]

Cette rubrique décrit le contrôle d’intégrité dans le point de vente (PDV).

## <a name="overview"></a>Vue d’ensemble

Les magasins de détail peuvent être des environnements complexes où de nombreuses applications et appareils sont utilisés. Au fur et à mesure que les opérations se développent, il peut devenir difficile de garantir le bon déroulement des opérations, en raison de dépendances, par exemple, de périphériques qui peuvent tomber en panne ou se débrancher accidentellement au cours d’une journée. La résolution des problèmes liés aux appareils et services peut être coûteuse pour les grands commerçants et tout aussi frustrant pour les petites opérations.

Les version 10.0.10 et ultérieures de Microsoft Dynamics 365 Commerce incluent un contrôle d’intégrité qui peut aider à éviter une partie de ce coût et de la frustration. Cette opération fournit une méthode pour tester les périphériques directement à partir du point de vente en dehors des opérations normales. Par conséquent, il peut aider les détaillants à détecter les problèmes avant qu’ils ne surviennent.

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Périphériques | Tout appareil que l’application de PDV utilise pour faciliter les transactions et autres opérations dans le magasin. Les exemples incluent les tiroirs-caisses, les lecteurs de codes à barres et les terminaux de paiement. |
| Service | Dans cette rubrique, un service est une application auxiliaire dont l’application de PDV dépend pour effectuer des transactions et des opérations quotidiennes. Les exemples incluent des applications qui contribuent aux calculs de taxes ou d’expédition. |

## <a name="health-check-operation"></a>Opération de contrôle d’intégrité

L’opération de contrôle d’intégrité est l’opération 717 sur la page **Opérations PDV** dans Commerce Headquarters. Elle peut être utilisée lorsque le PDV est en mode sans tiroir. Cependant, une station matérielle doit être active.

Par défaut, le contrôle d’intégrité teste uniquement les périphériques configurés dans le profil matériel pour la station matérielle actuellement active pour un registre. Si un registre utilise plusieurs stations matérielles au cours d’une journée, pour effectuer des contrôles d’intégrité pour chacune d’entre elles, il doit se connecter à une station matérielle à la fois. Il n’y a pas de contrôle d’intégrité au niveau du magasin. Cependant, il est possible que ce type de contrôle puisse être effectué via l’extensibilité de Commerce Server.

### <a name="out-of-box-health-checks"></a>Contrôles d’intégrité prêts à l’emploi

| Type | Connexion | Détails |
|---|---|---|
| Imprimante | OPOS | Ce contrôle teste la liaison et l’incorporation d’objets de base pour les fonctions de PDV (OPOS). Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> |
| Affichage de ligne | OPOS | Ce contrôle teste les fonctions OPOS de base. Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> |
| Affichage double | Windows | Ce contrôle garantit que le système d’exploitation détecte un deuxième affichage Windows. | 
| LBM | OPOS | Ce contrôle teste les fonctions OPOS de base. Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> |
| Créateur | OPOS | Ce contrôle teste les fonctions OPOS de base. Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> | 
| Scanneur | OPOS | Ce contrôle teste les fonctions OPOS de base. Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> | 
| Echelle | OPOS | Ce contrôle teste les fonctions OPOS de base. Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> |
| Clavier d’identification personnelle | OPOS | Ce contrôle teste les fonctions OPOS de base. Voici quelques exemples :<ul><li>Ouvrir : **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Fermer :**DeviceEnabled=False** &gt;**ReleaseDevice** &gt; **Close**</li></ul> |
| Terminal de paiement | SDK Paiements | Ce contrôle teste les fonctions de terminal de paiement de base fournies par le kit de développement logiciel Paiements. <ul><li>Verrouiller</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Clôture</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Utilisation de l’opération de contrôle d’intégrité dans le PDV

Lorsque l’opération de contrôle de l’intégrité est lancée dans le PDV, un volet à droite répertorie les périphériques configurés et affiche le statut de chaque périphérique. Pour effectuer un contrôle d’intégrité pour un seul appareil, sélectionnez l’appareil, puis sélectionnez **Test sélectionné**. Pour effectuer un contrôle d’intégrité pour tous les appareils, sélectionnez **Tout tester**. La fonction **Tout tester** teste tous les appareils, un à la fois, et met à jour le statut de chaque appareil dans la colonne **Statut**.

La colonne **Dernier contrôle** indique la dernière fois que le contrôle d’intégrité a été effectué pour chaque appareil.

Si le contrôle de l’intégrité pour un appareil réussit (c’est-à-dire, si aucune erreur ne survient), le statut de l’appareil sera **OK**. Si le contrôle d’intégrité échoue, le statut indique qu’il y a eu une erreur. Dans ce cas, le volet de droite fournit des détails liés à l’erreur ou demande à l’utilisateur de contacter l’administrateur système.

Certains appareils, tels que le verrouillage du clavier OPOS, ne disposent pas de tests de vérification d’intégrité prêts à l’emploi. Si aucun test de contrôle de l’intégrité n’est détecté pour un appareil utilisé, le statut sera **Non pris en charge**.

### <a name="extending-health-checks"></a>Extension des contrôles d’intégrité

Les tests de vérification d’intégrité prêts à l’emploi sont configurés pour fournir des messages conviviaux pour les erreurs typiques. Cependant, tous les scénarios ne sont pas couverts. Grâce à l’extensibilité, les commerçants peuvent mapper des messages conviviaux sur des erreurs qui pourraient être spécifiques à leur environnement.

Des contrôles d’intégrité personnalisés peuvent également être créés pour tester les périphériques qui ne sont pas pris en charge immédiatement, ou pour tester tous les services dont dépend le point de vente.

## <a name="related-articles"></a>Articles connexes

[Déclencheurs et impression de Modern POS (MPOS)](dev-itpro/pos-trigger-printing.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]