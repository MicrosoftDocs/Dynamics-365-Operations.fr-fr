---
title: Promouvoir une variante et terminer une expérience
description: Cette rubrique décrit comment promouvoir une variante réussie et réaliser une expérience dans Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930192"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promouvoir une variante et terminer une expérience

Cette rubrique décrit comment promouvoir la variante qui a produit les meilleurs résultats dans votre expérience et comment terminer le test. Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce. Les étapes supplémentaires sont traitées dans d'autres rubriques.

[ ![Expérimentation parcours utilisateur - Examiner et terminer](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Après avoir [réalisé votre expérience](experimentation-run-monitor.md) et collecté suffisamment de données pour déterminer la variante que vous souhaitez utiliser sur votre site en ligne, vous allez promouvoir la variante et terminer l'expérience.

## <a name="promote-a-variation"></a>Promouvoir une variante
Utilisez les données et les analyses liées à l'expérience dans le service tiers pour décider quelle variante a produit les meilleurs résultats. Procédez comme suit pour remplacer le contenu actuel sur le site en ligne par la variante la plus performante afin qu'elle soit disponible pour tous les utilisateurs de votre site web. 

1. Accédez à l'onglet **Expériences** dans le générateur de site et sélectionnez l'expérience.
1. Sélectionner **Terminer l'expérience** sur la barre du haut.
1. Dans le menu de la boîte de dialogue **Terminer l'expérience**, sélectionnez **Examiner les données de l'expérience**. Le service tiers s'ouvre et vous permet de valider les métriques et de déterminer la variante la plus performante.
1. Dans le menu de la boîte de dialogue **Terminer l'expérience** du générateur de site, sélectionnez la variante la plus performante, puis sélectionnez **Suivant**.
1. Ouvrez le service tiers et arrêtez l'expérience.
1. Dans le générateur de site, sélectionnez **Terminer** pour remplacer la page d'origine en ligne et publier la variante la plus performante afin qu'elle soit disponible pour tous les utilisateurs de votre site web. 

> [!NOTE]
> Si vous choisissez de conserver la page en ligne actuelle et de ne pas publier de variante, sélectionnez **Republier la page d'origine**.

## <a name="delete-your-experiment"></a>Supprimer votre expérience
Bien qu'il ne soit pas nécessaire de supprimer une expérience terminée dans Commerce, vous pouvez choisir de la supprimer pour économiser de l'espace ou nettoyer votre espace de travail. Pour supprimer une expérience, procédez comme suit.

1. Accédez à l'onglet **Expériences** dans le générateur de site et sélectionnez l'expérience. 
    > [!NOTE]
    > Si l'expérience est toujours active, arrêtez-la dans le service tiers avant de continuer.
1. Sélectionnez **Annuler la publication** dans la barre de commandes pour supprimer le contenu de la variante du site en ligne.
1. Sélectionnez **Supprimer** dans la barre de commandes pour supprimer l'expérience.

## <a name="previous-step"></a>Étape précédente
[Exécuter et surveiller une expérience](experimentation-run-monitor.md)
