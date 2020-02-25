---
title: États et cycle de vie des documents
description: Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b4f1c462f734b2d58843308f0f877fe18a4d9af7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002979"
---
# <a name="document-states-and-lifecycle"></a>États et cycle de vie des documents


[!include [banner](includes/banner.md)]

Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Description de l'état d'un document

La rubrique [Éléments de page](page-elements-overview.md) répertorie les différents types de système de gestion de contenu (CMS). Ces types de documents peuvent avoir plusieurs états dans l'outil de création. Les états de document permettent d'éviter des conflits de données et d'appliquer le contrôle des versions. Ils déterminent qui peut modifier les documents, quand les documents peuvent être modifiés, et quand des modifications peuvent être affichées par d'autres personnes.

Le tableau suivant indique les états de document possibles des éléments de page dans Commerce.

| État de document | Description |
|---|---|
| Extrait | Lorsqu'un article CMS est extrait vers vous, il ne peut pas être modifié par un autre utilisateur du système authentifié. Vous êtes le seul utilisateur à pouvoir afficher les modifications apportées. |
| Archivé | Lorsqu'un article CMS est archivé, toutes les modifications sont visibles pour d'autres utilisateurs du système authentifiés, et ils peuvent ensuite extraire l'article et le modifier. Chaque archivage crée un enregistrement de version du document dans l'historique de l'article. |
| Publiées | Lorsqu'un article CMS est publié, il est transmis à votre site en direct et devient découvrable sur Internet par les utilisateurs externes non authentifiés. Les articles peuvent être transmis uniquement s'ils ont été archivés. |
| Enregistré | Les modifications apportées à un article extrait par CMS peut être enregistré dans CMS avant que l'article soit archivé ou publié. Ces modifications enregistrées ne sont pas visibles pour d'autres utilisateurs du système authentifiés tant que l'article n'est pas archivé. Elles restent invisibles des utilisateurs externes jusqu'à ce que l'article soit publié. |
| Extraction ignorée | Lorsqu'un article extrait par CMS est ignoré, toutes les modifications enregistrées sont supprimées, et l'article revient à la version qui a été récemment archivée. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Manières d'ajouter du contenu](add-manage-content.md)

[Glossaire sur le modèle de page](page-elements-overview.md)

[Utilisation de groupes de publication](publish-groups.md)

[Utiliser des modules](work-with-modules.md)

[Utiliser des fragments](work-with-fragments.md)

[Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md)

[Personnaliser la navigation dans le site](customize-site-navigation.md)
