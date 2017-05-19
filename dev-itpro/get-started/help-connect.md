---
title: "Connexion au système d&quot;aide"
description: "Cette rubrique décrit les composants du système Aide pour Microsoft Dynamics 365 for Operations, explique comment les connecter entre eux et résume la création de l&quot;aide personnalisée."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f9af4de5f15125569d8f3e78f36e6a2b9c2a089b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="connect-the-help-system"></a>Connexion au système d'aide

[!include[banner](../includes/banner.md)]


Cette rubrique décrit les composants du système d'aide Microsoft Dynamics 365 for Operations. Elle fournit une vue d'ensemble de la procédure de connexion de ces composants et une synthèse de la création de l'aide personnalisée. 

<a name="help-architecture"></a>Architecture de l'aide
-----------------

La figure suivante illustre les parties du système d'aide de Dynamics 365 for Operations. Le système d'aide intégré au produit extrait des articles du site Dynamics 365 for Operations sur https://docs.microsoft.com, ainsi que les guides de tâche enregistrés dans le Concepteur de processus d'entreprise de Lifecycle Services (LCS) de Microsoft Dynamics. 
**Remarque :** Les fonctionnalités indiquées dans le schéma avec un astérisque (\*) sont planifiées, mais ne sont pas encore disponibles. [![Architecture de l'aide](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Connexion au système d'aide
En utilisant le formulaire **Paramètres système**, les administrateurs système connectent les parties du système d'aide pour une implémentation. [![Écran Paramètres système avec les paramètres d'aide](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Sur la page **Paramètres système**, procédez comme suit :

> [!IMPORTANT]
> La première fois que vous ouvrez l'onglet **Aide**, vous devez vous connecter à Lifecycle Services. Veillez à cliquer sur le lien au milieu de l'écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur **OK** pour obtenir à la page **Paramètres système**.[![Se connecter à LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)

1.  Sélectionnez le projet Lifecycle Services auquel se connecter.
2.  Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.
3.  Sélectionnez l'ordre d'affichage des bibliothèques BPM. Cela déterminer l'ordre dans lequel les enregistrements de tâche des bibliothèques s'affichent dans le volet **Aide**.

Une fois ces étapes accomplies, vous pouvez ouvrir le volet **Aide** puis cliquer sur l'onglet **Guides de tâche**. Les guides de tâche qui s'appliquent à la page sur laquelle vous vous trouvez dans Dynamics 365 for Operations s'affichent. Si aucun guide de tâche n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche.

### <a name="showing-translated-task-guides"></a>Affichage des guides de tâches traduits

Les guides de tâches traduits ont été expédiés pour la première fois dans la Bibliothèque unifiée APQC de mai 2016 et la bibliothèque de mise en route. Dans Dynamics 365 for Operations, pour afficher l'aide du guide de tâche localisé, assurez-vous que vous êtes connecté à la bibliothèque de mai. La langue dans laquelle s'affiche un guide de tâche est contrôlée pour chaque utilisateur par les paramètres de langue sous **Options** &gt; **Préférences**. 

> [!NOTE]
> Bien que de nombreux guides des tâches aient été traduits, le client Dynamics 365 for Operations n’affiche pas les noms des guides des tâches traduits. De plus, seuls les guides des tâches qui ont été publiés en février 2016 sont disponibles pour la traduction dans la bibliothèque de mai à ce stade. Nous publierons une bibliothèque mise à jour avec des traductions supplémentaires.
> -   Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.
> -   Si un guide de tâche n'a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.

## <a name="creating-custom-help"></a>Création d'une aide personnalisée
Vous pouvez créer une aide personnalisée pour votre implémentation de Dynamics 365 for Operations en créant des enregistrements de tâche qui reflètent votre implémentation, et en les enregistrant dans une bibliothèque de processus d'entreprise LCS. Pour les partenaires, si vous faites d'une bibliothèque une bibliothèque d'entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients. Vous pouvez également faire une copie de la bibliothèque globale unifiée APQC, puis ouvrir votre copie, ouvrir des enregistrements de tâches à partit de celle-ci et enregistrer les enregistrements avec vos modifications. Pour plus d'informations, consultez [Création d'un enregistrement de tâche pour l'utiliser comme documentation ou formation](../user-interface/task-recorder.md).

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble de l'Aide](help-overview.md)

[Vue d'ensemble de l'enregistreur de tâches](../user-interface/task-recorder.md)

[Procédure de création d'un enregistrement de tâche à utiliser comme documentation ou formation](../user-interface/task-recorder-training-docs.md)





