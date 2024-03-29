---
title: États et cycle de vie des documents
description: Cet article décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: intro-internal
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 350b3236eec6ad6520025bf44b22f12366f1e266
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269914"
---
# <a name="document-states-and-lifecycle"></a>États et cycle de vie des documents

[!include [banner](includes/banner.md)]

Cet article décrit les différents états de document des éléments de page dans Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Description de l’état d’un document

L’article [Éléments de page](page-elements-overview.md) répertorie les différents types de système de gestion de contenu (CMS). Ces types de documents peuvent avoir plusieurs états dans l’outil de création. Les états de document permettent d’éviter des conflits de données et d’appliquer le contrôle des versions. Ils déterminent qui peut modifier les documents, quand les documents peuvent être modifiés, et quand des modifications peuvent être affichées par d’autres personnes.

Le tableau suivant indique les états de document possibles des éléments de page dans Commerce.

| État de document      | Action du générateur de site        | Description                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Extrait         | Sélectionnez **Modifier**.           | Le document applicable est extrait pour vous. Lorsqu’un document est défini à cet état, il ne peut pas être modifié par d’autres utilisateurs système authentifiés, et toute modification apportée au document est visible uniquement de vous. |
| Enregistré               | Sélectionnez **Enregistrer**.           | Les modifications qui ont été effectuées vers un document extrait sont enregistrées vers la base de données, mais le document n’est pas encore vérifié ou publié. Les modifications enregistrées ne sont pas visibles aux autres utilisateurs système authentifiés jusqu’à ce que l’auteur sélectionne **Terminer la modification**. Elles restent invisibles des utilisateurs externes jusqu’à ce que l’article soit publié. |
| Extraction ignorée | Sélectionnez **Ignorer les modifications**.  | Toutes les modifications apportées au document extrait sont ignorées et l’article revient à la dernière version archivée. |
| Enregistré          | Sélectionnez **Terminer la modification**. | Le document modifié est archivé. Toutes les modifications sont visibles pour les autres utilisateurs système authentifiés, et ces utilisateurs peuvent ensuite modifier le document. Chaque archivage crée un enregistrement de version du document dans l’historique de l’article. |
| Publiées           | Sélectionnez **Publier**.        | Le document est publié et les modifications sont transmises à votre site en direct et deviennent détectables par des utilisateurs externes. Les éléments ne peuvent être publiés que s’ils ont été archivés tout d’abord en sélectionnant **Terminer la modification**. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Manières d’ajouter du contenu](add-manage-content.md)

[Glossaire sur le modèle de page](page-elements-overview.md)

[Utilisation de groupes de publication](publish-groups.md)

[Activer et utiliser le partage intercanal](cross-channel-sharing.md)

[Utiliser des modules](work-with-modules.md)

[Utiliser des fragments](work-with-fragments.md)

[Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md)

[Personnaliser la navigation dans le site](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
