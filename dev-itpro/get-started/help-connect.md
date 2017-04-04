---
title: "Connexion au système d&quot;aide"
description: "Cette rubrique décrit les composants du système Aide pour Microsoft Dynamics 365 for Operations, explique comment les connecter entre eux et résume la création de l&quot;aide personnalisée."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>Connexion au système d'aide

Cette rubrique décrit les composants du système d'aide de Microsoft Dynamics 365 pour les opérations. Il fournit une vue d'ensemble de la procédure de connexion ces composants et une synthèse de la création de l'aide personnalisée. 

<a name="help-architecture"></a>Architecture de l'aide
-----------------

L'illustration suivante présente les parties de Dynamics 365 du système d'aide d'opérations. Le système d'aide de produit en extrait des articles de Dynamics 365 pour le site d'opérations sur https://docs.microsoft.com, ainsi que la tâche guide enregistré dans le modeleur de processus entreprise aux Lifecycle Services (LCS). 
** Remarque : ** Les fonctions répertoriées dans le diagramme avec un astérisque (\*) sont organisées, mais n'étant pas encore disponibles. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Connecter le système d'aide
Utilisation ** des paramètres système ** la page, les administrateurs système lient les pièces du système d'aide pour une implémentation. [écran Paramètres système![avec les paramètres d'aide (]. /media/system-parameters_ops-1024x437.png)](. /media/system-parameters_ops.png) Sous ** des paramètres système ** la page, procédez comme suit :

1.  ** Important : ** La première fois que vous ouvrez ** aide ** l'onglet, vous devez vous connecter aux Lifecycle Services. Veillez à cliquer sur le lien au milieu de l'écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur ** effectué correctement ** pour obtenir ** des paramètres système ** à la page. [! Se connecter au [] (lettres de crédit. /media/connect-to-lcs-crop-1024x365.png « Se connectent au crédit »)](. /media/connect-to-lcs-crop.png)
2.  Sélectionnez le projet Lifecycle Services auquel se connecter.
3.  Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.
4.  Sélectionnez l'ordre d'affichage des bibliothèques BPM. Cela déterminer l'ordre dans lequel les enregistrements de tâche des bibliothèques s'affichent dans le volet **Aide**.

Une fois ces étapes accomplies, vous pouvez ouvrir le volet **Aide** puis cliquer sur l'onglet **Guides de tâche**. Les guides de tâche qui s'appliquent à la page sur laquelle vous vous trouvez dans Dynamics 365 for Operations s'affichent. Si aucun guide de tâche n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche.

### <a name="showing-translated-task-guides"></a>Affichage des guides de tâches traduits

Les guides traduits des tâches ont été expédiés la première fois dans la bibliothèque unifiée par APQC de mai 2016, et l'obtention a commencé la bibliothèque. Dans Dynamics 365 for Operations, pour afficher l'aide du guide de tâche localisé, assurez-vous que vous êtes connecté à la bibliothèque de mai. Langue qui un Guide de tâche apparaît dans est contrôlée pour chaque utilisateur par les paramètres de langue sous ** des options ** &gt; ** des préférences **. **Remarque :** bien que de nombreux guides des tâches aient été traduits, le client Dynamics 365 for Operations n’affiche pas les noms des guides des tâches traduits. En outre, seuls les guides d'emploi qui ont été lancés en février 2016 sont disponibles dans la traduction dans la bibliothèque de mai. Nous publierons une bibliothèque mise à jour avec des traductions supplémentaires.

-   Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.
-   Si un guide de tâche n'a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.

## <a name="creating-custom-help"></a>Création d'une aide personnalisée
Vous pouvez créer une aide personnalisée pour votre implémentation de Dynamics 365 for Operations en créant des enregistrements de tâche qui reflètent votre implémentation, et en les enregistrant dans une bibliothèque de processus d'entreprise LCS. Pour les partenaires, si vous faites d'une bibliothèque une bibliothèque d'entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients. Vous pouvez également faire une copie de la bibliothèque globale unifiée APQC, puis ouvrir votre copie, ouvrir des enregistrements de tâches à partit de celle-ci et enregistrer les enregistrements avec vos modifications. Pour plus d'informations, voir [comment créer une tâche de journalisation à utiliser comme documentation ou Formation (]. /user-interface/task-recorder.md).

<a name="see-also"></a>Voir également :
--------

[Help overview](help-overview.md)

[Vue d'ensemble de l'enregistreur de tâches (]. /user-interface/task-recorder.md)

[Procédure de création d'un enregistrement de tâche à utiliser comme documentation ou formation](../user-interface/task-recorder-training-docs.md)

[Créer de nouvelles bibliothèques de formation pour Dynamics 365 pour les opérations à l'intérieur de Lifecycle Services à l'aide de l'enregistreur de tâches (lien externe)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


