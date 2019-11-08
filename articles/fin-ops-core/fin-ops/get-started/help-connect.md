---
title: Connexion au système d'aide
description: Cette rubrique décrit les composants du système d'aide pour les applications Finance and Operations, explique comment les connecter entre eux et résume la création de l'aide personnalisée.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 491024c9c3d6c7d20ef212e167ceab6abac8dac7
ms.sourcegitcommit: d554faca895609b8124bf2ea5aca5a55c407534a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2019
ms.locfileid: "2537853"
---
# <a name="connect-the-help-system"></a>Connexion au système d'aide

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les composants du système d'aide des applications Finance and Operations, par exemple Dynamics 365 Finance, Supply Chain Management, Retail et Talent. Elle fournit une vue d'ensemble de la procédure de connexion de ces composants et une synthèse de la création de l'aide personnalisée.

## <a name="help-architecture"></a>Architecture de l'aide

La figure suivante illustre les parties du système d'aide. Le système d'aide intégré au produit extrait des articles du site https://docs.microsoft.com, ainsi que les guides de tâche enregistrés dans le Concepteur de processus d'entreprise de Lifecycle Services (LCS).

> [!NOTE]
> Les fonctionnalités indiquées dans le schéma avec un astérisque (\*) sont planifiées, mais ne sont pas encore disponibles.

[![Architecture de l'aide](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Connexion au système d'aide

> [!NOTE]
> L'onglet **Guides de tâche** n'est pas disponible actuellement dans Dynamics 365 Talent ou Retail. Nous œuvrons actuellement pour activer cette fonctionnalité dans une future version. Les guides des tâches dans l'expérience Mise en route dans Talent restent disponibles pour couvrir les fonctionnalités de base. L'aide concernant la procédure est également disponible sur le site docs.microsoft.com pour Retail et Talent.

En utilisant le formulaire **Paramètres système**, les administrateurs système connectent les parties du système d'aide pour une implémentation.

[![Écran Paramètres système avec paramètres d'aide](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Sur la page **Paramètres système**, procédez comme suit :

> [!IMPORTANT]
> La première fois que vous ouvrez l'onglet **Aide**, vous devez vous connecter à Lifecycle Services. Veillez à cliquer sur le lien au milieu de l'écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur **OK** pour accéder à l'écran **Paramètres**.
>
> [![Se connecter à LCS](./media/connect-to-lcs-crop-1024x365.png "Se connecter à LCS")](./media/connect-to-lcs-crop.png)

1. Sélectionnez le projet Lifecycle Services auquel se connecter.
2. Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.
3. Sélectionnez l'ordre d'affichage des bibliothèques BPM. Cela déterminer l'ordre dans lequel les enregistrements de tâche des bibliothèques s'affichent dans le volet **Aide**.

À l'issue de ces étapes, vous pouvez ouvrir le volet **Aide**, puis cliquer sur l'onglet **Guides de tâches**. Vous obtenez désormais les guides de tâches qui s'appliquent à la page sur laquelle vous êtes actuellement dans les applications Finance and Operations. Si aucun guide de tâche n'est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche.

### <a name="showing-translated-task-guides"></a>Affichage des guides de tâches traduits

Les guides de tâches traduits ont été expédiés pour la première fois dans la Bibliothèque unifiée APQC de mai 2016 et la bibliothèque de mise en route. Dans les applications Finance and Operations, pour afficher l'aide du guide de tâche localisé, assurez-vous que vous êtes connecté à la bibliothèque de mai. La langue dans laquelle s'affiche un guide de tâche est contrôlée pour chaque utilisateur par les paramètres de langue sous **Options** &gt; **Préférences**.

> [!NOTE]
> Bien que de nombreux guides des tâches aient été traduits, le client n’affiche pas les noms des guides des tâches traduits. De plus, seuls les guides des tâches qui ont été publiés en février 2016 sont disponibles pour la traduction dans la bibliothèque de mai à ce stade. Nous publierons une bibliothèque mise à jour avec des traductions supplémentaires.
>
> - Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.
> - Si un guide de tâche n'a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.

## <a name="creating-custom-help"></a>Création d'une aide personnalisée

Vous pouvez utiliser des guides de tâche pour créer de l'aide personnalisée, ou connecter un site Web au volet d'aide.

### <a name="create-custom-help-with-task-guides"></a>Créer une aide personnalisée à l'aide des guides de tâches

Vous pouvez créer une aide personnalisée pour votre implémentation de Finance, Supply Chain Management, et pour Retail en créant des enregistrements de tâche qui reflètent votre implémentation, et en les enregistrant dans une bibliothèque de processus d'entreprise LCS. Vous ne pouvez pas créer de guides de tâche personnalisés pour Talent.

Pour les partenaires, si vous faites d'une bibliothèque une bibliothèque d'entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients. Vous pouvez également faire une copie de la bibliothèque globale unifiée APQC, puis ouvrir votre copie, ouvrir des enregistrements de tâches à partit de celle-ci et enregistrer les enregistrements avec vos modifications. Pour plus d'informations, consultez [Création d'un enregistrement de tâche pour l'utiliser comme documentation ou formation](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Connecter un site personnalisé

Microsoft a fourni un livre blanc et un exemple de code qui expliquent comment créer et connecter un site d'aide personnalisée au volet d'aide. Pour plus d'informations, voir :

- [Créer de l'aide personnalisée pour les applications Finance and Operations (livre blanc)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Référentiel GitHub d'aide personnalisée](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Ressources supplémentaires

[Aperçu de l'aide](help-overview.md)

[Vue d'ensemble de l'enregistreur de tâches](../../dev-itpro/user-interface/task-recorder.md)

[Procédure de création d'un enregistrement de tâche à utiliser comme documentation ou formation](../../dev-itpro/user-interface/task-recorder-training-docs.md)