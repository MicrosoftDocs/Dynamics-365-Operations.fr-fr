---
title: Gérer les changements de formules et de leurs composants
description: Cette rubrique décrit comment gérer les formules et gérer les changements des données principales de la fabrication de processus.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d25ddfc992d49c9a3c24d03cb0c71d68f7aa21fa
ms.sourcegitcommit: 908a85987b604a7782407da70fb70ef75c07989f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2021
ms.locfileid: "6641102"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Gérer les changements de formules et de leurs composants

[!include [banner](../includes/banner.md)]

Si vous utilisez les capacités de fabrication par processus de Microsoft Dynamics 365 Supply Chain Management, vous pouvez également utiliser les capacités de gestion de formules associées pour gérer les changements suivants :

- **Formule et éléments de planification :** gérez les changements de composants dans les formules et leurs coproduits et sous-produits.
- **Coproduits et sous-produits :** modifiez les quantités et autres informations des coproduits et sous-produits dans une formule.
- **Articles de poids variable :** gérez les changements des articles de poids variable.

## <a name="turn-on-this-feature-in-your-system"></a>Activer cette fonctionnalité dans votre système

Pour utiliser cette capacité, procédez comme suit :

1. Activez la fonctionnalité *Gestion des modifications d’ingénierie* et sa clé de configuration, comme décrit dans [Présentation de la gestion des modifications d’ingénierie](product-engineering-overview.md). Comme mentionné dans cette rubrique, assurez-vous d’activer également la clé de licence **Gestion des modifications pour la fabrication par processus**, qui est imbriquée sous la clé de licence **Gestion des modifications d’ingénierie**.
1. Activez la fonctionnalité *Gérer les changements de formules et de leurs composants* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="feature-naming-conventions"></a>Conventions d’affectation de noms de fonctionnalités

Dans l’interface utilisateur (IU) et la documentation de Supply Chain Management, la fonctionnalité de gestion des modifications est généralement appelée *gestion des modifications d’ingénierie*, et les produits gérables sont généralement appelés *produits d’ingénierie*. Bien que cette terminologie ne soit pas généralement associée à la gestion des formules pour la fabrication par processus, vous devez considérer la gestion des modifications d’ingénierie comme une simple gestion des modifications et vous devez considérer les produits d’ingénierie comme des produits avec version.

## <a name="work-with-formula-change-management-features"></a>Utiliser les fonctionnalités de gestion des changements de formules

La liste suivante résume la manière dont les fonctionnalités de gestion des modifications d’ingénierie s’appliquent à la gestion des formules. Elle fournit également des liens vers d’autres informations. Étant donné que la gestion des changements de formules tire parti des fonctionnalités de gestion des modifications d’ingénierie, vous devez apprendre comment la gestion des modifications d'ingénierie fonctionne en général, afin de pouvoir l’utiliser pour gérer vos formules et leurs composants.

- **Gestion centralisée des données du produit** : configurez une organisation qui, via un processus de lancement géré, garantit que des données précises et pertinentes sur le produit sont disponibles pour les utilisateurs dans toute l’entreprise. Pour plus d’informations, consultez [Sociétés d’ingénierie et règles de propriété des données](engineering-org-data-ownership-rules.md).
- **Contrôle de version du produit** : suivez les changements de produits par le biais des versions du produit et contrôlez le produit à toutes les étapes de la chaîne d’approvisionnement. De cette façon, vous pouvez suivre les changements de vos formulations. Pour plus d’informations, voir [Versions d’ingénierie et catégories de produits d’ingénierie](engineering-versions-product-category.md).
- **Gestion du cycle de vie du produit** : gérez la visibilité des données du produit dans toute l’organisation et contrôlez la disponibilité des versions du produit à chaque étape de la chaîne d’approvisionnement. Vous avez un contrôle détaillé sur la date à laquelle une version du produit peut être utilisée dans des processus métier spécifiques, et vous pouvez créer vos propres états du cycle de vie en fonction des besoins de votre entreprise. Pour plus d’informations, voir [États du cycle de vie du produit et transactions](product-lifecycle-state-transactions.md).
- **Gestion des changements de formules**: les utilisateurs de votre organisation peuvent demander des changements de formules. Utilisez les ordres de changement pour évaluer et documenter l’impact des changements proposés. Ajoutez des flux de travail pour gérer le processus de changement et le lancement de nouvelles versions du produit et de sa formule. Pour plus d’informations, voir [Gérer modifications des produits techniques](engineering-change-management.md).
- **Contrôle de la disponibilité** : utilisez les vérifications du système et le guide de l’utilisateur (questionnaires et listes de contrôle) pour vous assurer que toutes les données requises du produit sont entièrement saisies avant le lancement du produit. Pour plus d’informations, voir [Disponibilité du produit](product-readiness.md).
- **Fonctionnalité de lancement de produit améliorée** : lancez des versions entièrement définies d’un produit et de sa formule depuis une organisation (entité juridique) vers d’autres entités juridiques. Vous pouvez même décider si les informations sur le produit doivent être révisées ou modifiées avant le lancement. Pour plus d’informations, voir [Lancement de structures de produit](release-product-structure.md).

Notez que la plupart des rubriques liées à la liste précédente fournissent des exemples basés sur les nomenclatures. Cependant, les formules fonctionnent de la même manière. Voici quelques concepts supplémentaires qu’il est utile de connaître lorsque vous utilisez la gestion des changements (ou uniquement la gestion des changements de formules) pour gérer les formules et les nomenclatures :

- Pour chaque [catégorie d’ingénierie du produit](engineering-versions-product-category.md), vous pouvez spécifier le type de production (nomenclature, formule ou élément de planification). Vous pouvez également spécifier si la prise en charge du poids variable est nécessaire pour les produits qui utilisent cette catégorie.
- Les coproduits et les sous-produits ne sont pas des produits d’ingénierie. Par conséquent, ils ne sont pas versionnés. Si vous devez les modifiez, créez simplement un nouveau produit. Cette approche facilite la maintenance.
- Vous pouvez gérer les articles finis qui sont des nomenclatures et qui ont des éléments de formule enfants. La fonctionnalité fonctionnera pour toute combinaison de nomenclatures contenant des formules et/ou de formules contenant des nomenclatures.
