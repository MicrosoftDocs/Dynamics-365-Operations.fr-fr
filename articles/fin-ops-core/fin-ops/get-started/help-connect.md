---
title: Configurer l’expérience d’aide pour les applications de finances et d’opérations
description: Cet article fournit des informations sur les composants du système d’aide pour certaines applications Microsoft Dynamics 365.
author: edupont04
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: edupont
ms.search.region: Global
ms.author: edupont
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.form: SystemParameters
ms.openlocfilehash: 2c45a203303181c7ea23e20f8fa1bdce1c827aa2
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462222"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>Configurer l’expérience d’aide pour les applications de finances et d’opérations

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Dans cet article, vous trouverez un aperçu des composants du système d’aide pour des applications de finances et d’opérations, telles que Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management Dynamics 365 Commerce et Dynamics 365 Human Resources. L’article explique également comment connecter ces composants et fournit un résumé du processus de création d’une aide personnalisée.

## <a name="help-architecture"></a>Architecture de l’aide

Les applications de finances et d’opérations incluent des aperçus conceptuels et d’autres rubriques qui sont publiés sur le site [Microsoft Dynamics 365 documentation](/dynamics365/). Ce contenu est ensuite accessible à partir du volet **Aide** du produit. La figure suivante illustre les parties du système d’aide.

[![Architecture de l’aide.](./media/help-architecture.png)](./media/help-architecture.png)

Le système d’aide intégré au produit extrait des articles Microsoft Docs et d’autres sites Web connectés. Il extrait également des guides de tâche stockés dans le Concepteur de processus d’entreprise (BPM) dans Microsoft Dynamics Lifecycle Services (LCS).

## <a name="adding-task-guides"></a>Ajout de guides de tâche

> [!NOTE]
> L’onglet **Guides de tâche** n’est pas disponible actuellement dans Human Resources ou Commerce. <!--We are currently working to enable this functionality in a future release.--> Toutefois, les guides de tâche dans l’expérience Mise en route dans Human Resources restent disponibles pour couvrir les fonctionnalités de base. Pour Human Resources et Commerce, l’aide est disponible sur le site [Documentation Microsoft Dynamics 365](/dynamics365/).

Sur la page **Paramètres système**, les administrateurs système peuvent configurer l’accès aux bibliothèques de guides de tâches pertinentes pour une implémentation.

> [!NOTE]
> - Pour configurer l’aide, vous devez vous connecter avec un compte dans le même client que celui dans lequel l’application est déployée.
> - Il n’est pas possible de connecter une bibliothèque LCS depuis une instance de l’application s’exécutant sur un disque dur virtuel (VHD) local.

[![Écran Paramètres système avec paramètres d’aide.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Pour configurer des guides de tâche pour une solution, procédez comme suit sur la page **Paramètres système**.

> [!IMPORTANT]
> La première fois que vous ouvrez l’onglet **Aide**, vous devez vous connecter à Lifecycle Services. Veillez à cliquer sur le lien au milieu de l’écran, attendez la connexion, fermez la boîte de dialogue, puis cliquez sur **OK** pour accéder à l’écran **Paramètres système**.
>
> [![Se connecter à LCS](./media/connect-to-lcs-crop-1024x365.png "Connectez-vous à LCS.")](./media/connect-to-lcs-crop.png)

1. Sélectionnez le projet Lifecycle Services auquel se connecter.
2. Sélectionnez les bibliothèques BPM (dans le projet sélectionné) à partir desquelles récupérer les enregistrements de tâche.
3. Sélectionnez l’ordre d’affichage des bibliothèques BPM. L’ordre d’affichage définit l’ordre dans lequel les enregistrements de tâche des bibliothèques s’affichent dans le volet **Aide**.

À l’issue de ces étapes, vous pouvez ouvrir le volet **Aide**, puis sélectionnez l’onglet **Guides de tâches**. Vous obtenez désormais les guides de tâches qui s’appliquent à la page sur laquelle vous êtes actuellement dans les applications de finances et d’opérations. Si aucun guide de tâche n’est trouvé, vous pouvez entrer des mots clés pour affiner votre recherche.

### <a name="showing-translated-task-guides"></a>Affichage des guides de tâches traduits

Les guides de tâche traduits ont été lancés pour la première fois dans la Bibliothèque unifiée APQC de mai 2016 et la bibliothèque de mise en route. Pour afficher l’aide du guide de tâche localisé, assurez-vous que la solution Dynamics 365 est connectée à la bibliothèque de mai 2016. Les utilisateurs peuvent modifier la langue dans laquelle s’affiche un guide de tâche en modifiant les paramètres de langue sous **Options** &gt; **Préférences**.

> [!NOTE]
> Bien que de nombreux guides des tâches aient été traduits, le client n’affiche pas les noms traduits. De plus, dans la bibliothèque de mai 2016, les traductions sont disponibles uniquement pour les guides des tâches qui ont été publiés en février 2016. Microsoft va publier une bibliothèque mise à jour qui inclut des traductions supplémentaires.
>
> - Si un guide de tâche a été traduit, lorsque vous ouvrez ce guide de tâche, tout le texte du guide de tâche s’affiche dans la langue sélectionnée.
> - Si un guide de tâche n’a pas encore été traduit, lorsque vous ouvrez ce guide de tâche, une partie du texte (texte des commandes) s’affiche dans la langue sélectionnée.

## <a name="adding-custom-help"></a>Ajout d’une aide personnalisée

Vous pouvez utiliser des guides de tâche pour créer une aide personnalisée, ou connecter un site Web au volet **Aide**.

### <a name="create-custom-help-by-using-task-guides"></a>Créer une aide personnalisée à l’aide des guides de tâche

Vous pouvez créer une aide personnalisée pour les applications prises en charge en créant des enregistrements de tâche qui reflètent votre implémentation, et en les enregistrant dans une bibliothèque de processus d’entreprise LCS. Vous ne pouvez pas créer de guides de tâches personnalisés pour Human Resources.

Si vous êtes un partenaire et que vous faites d’une bibliothèque une bibliothèque d’entreprise et la comprenez dans une solution, elle sera à la disposition de vos clients. Vous pouvez également faire une copie de la bibliothèque unifiée APQC, puis ouvrir des enregistrements de tâches dans la copie, les modifier et enregistrer vos modifications. Pour plus d’informations, voir [Ressources de l’enregistreur de tâches](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Connexion à un site d’aide personnalisé

Les applications de finances et d’opérations sont rarement utilisées dans leur forme prête à l’emploi. Au lieu de cela, la solution est personnalisée et étendue pour répondre aux besoins de l’organisation. Vous pouvez également personnaliser et étendre l’expérience d’aide. Par exemple, vous pouvez ajouter une aide personnalisée au volet **Aide** du produit.

Microsoft a fourni une boîte à outils pour vous aider à déployer et à connecter l’aide personnalisée du volet **Aide**. Pour plus d’informations sur la façon de configurer une solution d’aide personnalisée connectée au volet **Aide**, voir [Vue d’ensemble de l’aide personnalisée](../../dev-itpro/help/custom-help-overview.md).

Si vous souhaitez collaborer avec Microsoft sur des outils et de processus de personnalisation de l’aide, remplissez le formulaire à l’adresse [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Voir également :

[Système d’aide](help-overview.md)  
[Vue d’ensemble de l’aide personnalisée](../../dev-itpro/help/custom-help-overview.md)  
[Ressources de l’enregistreur de tâches](../../dev-itpro/user-interface/task-recorder.md)  
[Créer une documentation ou une formation à l’aide de l’enregistreur de tâches](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Référentiel GitHub d’aide personnalisée](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
