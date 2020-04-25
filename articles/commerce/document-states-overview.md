---
title: États et cycle de vie des documents
description: Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: 4a00f1c363e5ecb0e3e64637a8f487c48df2df72
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261511"
---
# <a name="document-states-and-lifecycle"></a>États et cycle de vie des documents


[!include [banner](includes/banner.md)]

Cette rubrique décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Description de l'état d'un document

La rubrique [Éléments de page](page-elements-overview.md) répertorie les différents types de système de gestion de contenu (CMS). Ces types de documents peuvent avoir plusieurs états dans l'outil de création. Les états de document permettent d'éviter des conflits de données et d'appliquer le contrôle des versions. Ils déterminent qui peut modifier les documents, quand les documents peuvent être modifiés, et quand des modifications peuvent être affichées par d'autres personnes.

Le tableau suivant indique les états de document possibles des éléments de page dans Commerce.

| État de document      | Action du générateur de site        | Description                                                   |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Extrait         | Sélectionnez **Modifier**.           | Le document applicable est extrait pour vous. Lorsqu'un document est défini à cet état, il ne peut pas être modifié par d'autres utilisateurs système authentifiés, et toute modification apportée au document est visible uniquement de vous. |
| Enregistré               | Sélectionnez **Enregistrer**.           | Les modifications qui ont été effectuées vers un document extrait sont enregistrées vers la base de données, mais le document n'est pas encore vérifié ou publié. Les modifications enregistrées ne sont pas visibles aux autres utilisateurs système authentifiés jusqu'à ce que l'auteur sélectionne **Terminer la modification**. Elles restent invisibles des utilisateurs externes jusqu'à ce que l'article soit publié. |
| Extraction ignorée | Sélectionnez **Ignorer les modifications**.  | Toutes les modifications apportées au document extrait sont ignorées et l'article revient à la dernière version archivée. |
| Enregistré          | Sélectionnez **Terminer la modification**. | Le document modifié est archivé. Toutes les modifications sont visibles pour les autres utilisateurs système authentifiés, et ces utilisateurs peuvent ensuite modifier le document. Chaque archivage crée un enregistrement de version du document dans l'historique de l'article. |
| Publiées           | Sélectionnez **Publier**.        | Le document est publié et les modifications sont transmises à votre site en direct et deviennent détectables par des utilisateurs externes. Les éléments ne peuvent être publiés que s'ils ont été archivés tout d'abord en sélectionnant **Terminer la modification**. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Manières d'ajouter du contenu](add-manage-content.md)

[Glossaire sur le modèle de page](page-elements-overview.md)

[Utilisation de groupes de publication](publish-groups.md)

[Utiliser des modules](work-with-modules.md)

[Utiliser des fragments](work-with-fragments.md)

[Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md)

[Personnaliser la navigation dans le site](customize-site-navigation.md)
