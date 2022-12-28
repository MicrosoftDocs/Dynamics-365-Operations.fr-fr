---
title: Version préliminaire de Dynamics 365 Commerce 10.0.30 (novembre 2022)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Commerce 10.0.30.
author: josaw1
ms.date: 12/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: a449c7eff21c059555f9659ea932705858d26275
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831745"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>Version préliminaire de Dynamics 365 Commerce 10.0.30 (novembre 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire 10.0.30 de Microsoft Dynamics 365 Commerce. Cette version a un numéro de build de 10.0.1362 et est disponible selon le programme suivant :

- **Version préliminaire :** septembre 2022
- **Disponibilité générale de la version (mise à jour automatique) :** octobre 2022
- **Disponibilité générale de la version (mise à jour automatique) :** novembre 2022

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---------|------------------|----------------|--------------| 
| Support technique   | Chattez sur un site e-commerce à l’aide d’un bot Power Virtual Agents. | Cette fonctionnalité donnera aux utilisateurs du site de commerce électronique le choix d’utiliser un bot de conversation instantanée Power Virtual Agents pour les demandes d’assistance. | Activé par les administrateurs/décideurs pour les utilisateurs finaux |
| Aperçus  |  Diffusez des événements d’informations opérationnelles sur les points de vente (PDV) à votre compte Application Insights. | [Accéder aux journaux Application Insights](../dev-itpro/operational-insights.md#enable-diagnostic-events-in-application-insights)   |  IT Pro/developer opt-in   |
|  Paiements  | Prise en charge des commandes PayPal au-delà de la période d’autorisation de 29 jours. | La période d’autorisation maximale pour PayPal est de 29 jours, après quoi une nouvelle autorisation et un nouvel ID de commande doivent être générés. Comme alternative, PayPal offre une option où une commande PayPal peut être référencée comme une commande générale, permettant plusieurs autorisations et captures pour le même ID de commande, au lieu de générer une nouvelle autorisation et un nouvel ID de commande à 29 jours). | Lors de la configuration du connecteur de paiement PayPal dans Commerce headquarters, le champ **OrderIntent** a été ajouté et peut avoir deux valeurs :<p><p>- **Autoriser** : cette configuration est celle par défaut (si le champ est laissé vide, **Autoriser** agira par défaut). Configurer **OrderIntent** vers **Authorize** correspond à la valeur PayPal **processing_instruction** **NO_INSTRUCTION**. La commande sera autorisée auprès de PayPal et l’autorisation ne peut pas être modifiée lorsque cette valeur est utilisée.<p>- **Enregistrer** : quand la valeur **OrderIntent** est définie sur **Enregistrer**, cela correspond à la valeur PayPal **processing_instruction** de **ORDER_SAVED_EXPLICITLY**. Les références de commande sont enregistrées dans le service PayPal lorsque cette valeur est utilisée.  |
| Connexion au PDV  | [Activer les fonctionnalités de diagnostic en libre-service pour la connexion au point de vente](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Cette fonctionnalité fournit des fonctionnalités de diagnostic en libre-service dans les points de vente (PDV) et dans Commerce headquarters pour aider les employés et les responsables des magasins à identifier et à résoudre rapidement les causes profondes des problèmes de connexion au PDV.<p><p>- Les messages d’échec affichés sur l’écran de connexion au PDV ont été améliorés pour fournir des informations concrètes sur la cause profonde qui peuvent aider les employés du magasin qui utilisent le PDV à comprendre ce qui n’a pas fonctionné afin qu’ils puissent effectuer les actions nécessaires pour résoudre le problème.<p>- Une fonction **Tester la connexion** est disponible sur la page **Collaborateurs** dans Commerce headquarters afin que les responsables de magasin qui configurent les appareils de point de vente puissent simuler la connexion au point de vente. En cas d’échec de connexion, cette fonction fournit des guides de dépannage exploitables afin que les responsables puissent vérifier les configurations pertinentes, corriger les problèmes et valider les correctifs.  | Activé par défaut |


## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Dynamics 365 Finance 10.0.30 inclut des mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.30](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de la version 10.0.30, connectez-vous à Lifecycle Services (LCS) et consultez l’ [Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 et les clouds du secteur : plan de la vague 2 de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2022](/dynamics365-release-plan/2022wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-features"></a>Fonctions supprimées et déconseillées

Les [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](removed-deprecated-features-commerce.md) l’article décrivent les fonctionnalités qui ont été supprimées ou obsolètes pour Commerce.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l’article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
