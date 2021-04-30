---
title: Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 83798af9c39ae8845125026903741882356d8845
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909327"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Nouveautés ou modifications dans Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Supply Chain Management 10.0.6. Cette version a un numéro de build de 10.0.234. Bien que la date de disponibilité générale soit en novembre, les nouvelles fonctionnalités sont disponibles pour une sortie anticipée en octobre. Pour plus d’informations sur la version 10.0.6, voir [Ressources supplémentaires](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Entité de données Modèles V2 de configuration du produit

Une deuxième version de l’entité « Modèles de configuration du produit » est publiée (appelée « Modèles V2 de configuration du produit »). Le modèle par défaut « Modèles de configuration du produit 418 » doit également utiliser la nouvelle entité de données « Modèles V2 de configuration du produit » dans les modèles de l’infrastructure d’importation/d’exportation. Le modèle ne sera pas mis à jour automatiquement, vous devrez donc charger manuellement le modèle par défaut. L’entité V2 exporte une ligne en tant que fichier séparé dans une pièce jointe au lieu de l’intégrer, ce qui résout les limitations de taille de l’entité V1. 
 
Que devez-vous faire pour effectuer ce changement ?
-    L’entité V1 étant obsolète, vous devez commencer la migration de V1 vers V2. Si vous utilisez le modèle « Modèles de configuration de produit 418 », vous pouvez cliquer sur le bouton « Charger les modèles par défaut » et recharger le modèle « 418 - Modèles de configuration de produit »
-    Si vous devez conserver la compatibilité avec les systèmes existants, vous pouvez pour l’instant continuer à utiliser le modèle existant et l’entité (obsolète) V1 jusqu’à ce que vous déplaciez vos intégrations vers le nouveau modèle. 

## <a name="feature-management-enhancements"></a>Améliorations apportées à la gestion de la fonctionnalité
La gestion de la fonctionnalité vous permet désormais d’activer toutes les nouvelles fonctionnalités par défaut, de demander une confirmation pour activer une fonctionnalité et d’activer toutes les fonctionnalités qui n’ont pas déjà été activées. 


## <a name="purchase-agreement-responsible-party"></a>Partie responsable du contrat d’achat
Vous avez maintenant la possibilité de définir les parties responsables principales et secondaires sur le formulaire de classification des accords d’achat et les accords d’achat qui en résultent.  Cela permet à l’utilisateur d’accéder à qui supervise les accords.

## <a name="rfq-link-on-the-purchase-order-line"></a>Lien de l’appel d’offre sur la ligne de la commande fournisseur
Vous pouvez ajouter un lien de référence à partir des lignes de commande d’achat vers les lignes d’appels d’offres correspondantes dont elles sont issues, ce qui permet à l’utilisateur de recevoir facilement la demande d’appel d’offre.

## <a name="additional-resources"></a>Ressources supplémentaires

### <a name="bug-fixes"></a>Correctifs de bogue
Pour plus d’informations sur les correctifs de bogues inclus dans chacune des mises à jour qui font partie de 10.0.6, connectez-vous à Lifecycle Services (LCS) et consultez l’[Article de la base de connaissances](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Update 30 de la plateforme
Microsoft Dynamics 365 Supply Chain Management 10.0.6 inclut Platform update 30. Pour en savoir plus sur Platform update 30, consultez [Nouveautés ou modifications de Platform update 30](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365 : vague 2 du plan de publication 2019
Vous souhaitez connaître les fonctionnalités à venir et récemment publiées dans nos applications ou notre plateforme d’entreprise ?

Consultez [Dynamics 365 : vague 2 du plan de publication 2019](/dynamics365-release-plan/2019wave2/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, dans un document unique que vous pouvez utiliser pour la planification.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Fonctionnalités de Supply Chain Management supprimées et obsolètes

La rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) décrit les fonctionnalités qui ont été, ou qui doivent être supprimées ou déconseillées pour Supply Chain Management.

- Une fonction *supprimée* n’est plus disponible dans le produit.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Avant que toute fonctionnalité ne soit supprimée du produit, l’avis d’obsolescence sera annoncé dans la rubrique [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mois avant le retrait.

Pour les dernières modifications qui n’affectent que le temps de compilation, mais qui sont compatibles d’un point de vue binaire avec les environnements sandbox et de production, le temps d’obsolescence sera inférieur à 12 mois. Ce sont généralement des mises à jour fonctionnelles qui doivent être apportées au compilateur.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]