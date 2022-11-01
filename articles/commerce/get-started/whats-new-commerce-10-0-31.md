---
title: Version préliminaire de Dynamics 365 Commerce 10.0.31 (février 2023)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Commerce 10.0.31.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 05ccd9794ffeba6a09d6fec0a57ffad2b59707ad
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709857"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>Version préliminaire de Dynamics 365 Commerce 10.0.31 (février 2023)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article répertorie les fonctionnalités qui sont nouvelles ou ont été modifiées dans la version préliminaire 10.0.31 de Microsoft Dynamics 365 Commerce. Cette version a un numéro de build de 10.0.1406 et est disponible selon le programme suivant :

- **Version préliminaire de la version :** octobre 2022
- **Disponibilité générale de la version (auto-mise à jour) :** janvier 2023
- **Disponibilité générale de la version (mise à jour automatique) :** février 2023

## <a name="features-included-in-this-release"></a>Fonctionnalités incluses dans cette version

Le tableau suivant répertorie les fonctionnalités incluses dans cette version. Il se peut que nous mettions à jour de cet article pour inclure des fonctionnalités intégrées à la version après la publication d’origine de cet article.

| Fonctionnalités | Fonction | Plus d’informations | Activé par |
|---|---|---|---|
| Codes d'erreur | Commerce a introduit des références d’erreur standardisées à inclure dans les erreurs de paiement des canaux en ligne qui sont présentées aux acheteurs en ligne.| [Codes d’erreur du module de paiement](../checkout-module-error-codes.md)  | Activé par défaut |
| Paiements | [Activer Apple Pay avec le connecteur de paiement Dynamics 365 pour Adyen](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | Les clients du commerce électronique peuvent utiliser Apple Pay sur les pages de panier et de paiement lorsqu’ils utilisent des appareils ou des navigateurs pris en charge. | Acceptation des développeurs |
| Paiements  |  Commerce a ajouté la possibilité de limiter la façon dont les utilisateurs interagissent avec les jetons de paiement récurrents dans l’interface utilisateur de Commerce headquarters. Les formulaires de paiement, tels que la page **Commande client du centre d’appels**, n’affichent plus le jeton de paiement récurrent précédemment utilisé par un client pour une utilisation dans une nouvelle transaction. Seule une « carte enregistrée » déterminée entrée dans l’écran **Paiements des clients** de Commerce, ou avec l’accord d’un client lors du paiement via une commande client, sera présentée aux utilisateurs du centre d’appels ou de Commerce headquarters lors du traitement d’un paiement pour une nouvelle transaction. | [Limiter l’utilisation des jetons de paiement](../dev-itpro/limit-token-usage.md)  |  Gestion des fonctions<p>*Restreindre l’utilisation du jeton de paiement au contexte de la commande*  |
| PDV | [Créer des commandes fournisseur à partir d’un PDV](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  Amélioration de l’opération de stock entrant dans l’application PDV pour permettre aux utilisateurs de créer, de modifier et de confirmer des demandes de commande fournisseur. |  Gestion des fonctions<p>*Possibilité de créer une demande de commande fournisseur dans le PDV*   |



## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="platform-updates-for-finance-and-operations-apps"></a>Mises à jour de plateforme pour les applications de finances et d’opérations

Microsoft Dynamics 365 Commerce 10.0.31 inclut les mises à jour de plateforme. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.31 (février 2023)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Correctifs de bogue

Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de la version 10.0.31, connectez-vous à Microsoft Dynamics Lifecycle Services et consultez l’[article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 et les clouds du secteur : plan de la vague 2 de lancement 2022

Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 et les clouds du secteur : plan de la 2e vague de lancement 2022](/dynamics365-release-plan/2022wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-commerce-features"></a>Fonctionnalités de Commerce supprimées et déconseillées

Les [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](removed-deprecated-features-commerce.md) l’article décrivent les fonctionnalités qui ont été supprimées ou obsolètes pour Commerce.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans l'article [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 mois avant le retrait.


Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
