---
title: Vue d’ensemble des modèles et dispositions
description: Cet article couvre les modèles et dispositions dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 12/12/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: adf1585e418ca2d09065db03de72cb1bbfb3e614
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844618"
---
# <a name="templates-and-layouts-overview"></a>Vue d’ensemble des modèles et dispositions


[!include [banner](includes/banner.md)]

Les modèles sont un élément fondamental du modèle de page Microsoft Dynamics 365 Commerce. Si votre objectif est d’optimiser le rendement et la cohérence des workflows de création de site, il est important que vous appreniez comment tirer parti des modèles pour votre site web. Les décisions anticipées sur la structure du modèle sont importantes, et peuvent considérablement affecter le coût et l’agilité des mises à jour quotidiennes, saisonnières, et à l’échelle de la marque. Les modèles bien structurés présentent d’autres avantages également. Par exemple, ils permettent d’améliorer les scores d’optimisation du moteur de recherche (SEO) à la taille du site et de réduire le nombre de bogues.

Pour bien commencer à utiliser des modèles vous devez comprendre les avantages fonctionnels des modèles et des dispositions, les différences entre eux, et la hiérarchie.

L’illustration suivante présente la hiérarchie du modèle de page derrière une page web affichée.

![Diagramme de modèle de page.](../commerce/media/page-model-diagram.png)

| Entité        | Fonction de base |
|---------------|----------------|
| Modèle      | Les modèles définissent les options de module et l’échafaudage de base pour un ensemble de dispositions et d’instances de page. |
| Disposition        | Les dispositions définissent la sélection et l’organisation finale des modules pour une page ou un ensemble de pages. |
| Instance de la page | Les instances de page définissent les données et le contenu des pages spécifiques. |

## <a name="templates"></a>Modèles

Les modèles sont en haut de la hiérarchie de modèle de page Dynamics 365 Commerce et représentent une étape antérieure importante pour la configuration du site. Conceptuellement, les modèles permettent de contrôler la cohérence dans une famille de dispositions enfants et de pages pour définir la structure de base et créer des options pour les workflows de création de disposition et de pages en aval. Les modèles peuvent contribuer à la simplification du processus de création avec des éléments gérés centralement et prédéfinis (tels que les en-têtes et les pieds de page) et à la création guidée des flux qui permettent de s’assurer que les choix de configuration du module sont conformes à la marque.

### <a name="controlling-consistency"></a>Contrôler la cohérence

Lorsque vous créez un modèle, la plus grande décision commerciale que vous devez prendre est le contrôle que le modèle doit avoir sur le processus de création de page. Un modèle qui laisse tout possible à un créateur en aval est le type le plus simple de modèle pour créer, mais il peut avoir des conséquences à long terme pour la maintenance des pages qui sont créées à partir de celui-ci. Un modèle bien écrit fournit des instructions et une expérience de création normalisées, mais il donne également aux auteurs suffisamment de flexibilité pour qu’ils puissent terminer leur tâche. Tous ces aspects dépendent du niveau de contrôle que le modèle applique.

Les modèles peuvent aider les créateurs de contenu à être plus efficaces et à respecter la marque des manières suivantes :

- Limitez les modules qui peuvent être utilisés dans une page.
- Suggérez des choix de module et de configuration par défaut.
- Faites explicitement certains choix de module et de configuration qui sont contrôlés au niveau du modèle. Ce processus est également appelé *verrouillage* d’un paramètre.

L’exemple suivant montre comment un modèle de base (modèle X) peut être configuré :

- Toutes les dispositions enfants du modèle X doivent avoir un conteneur d’en-tête, un conteneur du corps, et un conteneur de pied de page.
- Dans le modèle X, la configuration du conteneur d’en-tête est verrouillée et peut être modifiée que dans le modèle X lui-même. Toutes les dispositions et pages enfants sont toujours cette en-tête.
- Le conteneur du corps nécessite au moins un module et un maximum de dix modules. Ces modules sont définis par les dispositions et les pages en aval.
- Pour le conteneur du corps, les modules de bannière, de fonctionnalité et de carrousel sont disponibles.
- Un conteneur de pied de page est paramétré dans le modèle X, mais il peut être remplacé par les dispositions et les pages en aval.

Le modèle dans cet exemple définit une structure unique et un jeu d’options pour les auteurs de contenu en aval. Notez que certaines parties d’une page (dans ce cas, l’en-tête) sont entièrement définies et verrouillées dans le modèle, et ne peuvent pas être modifiées par les auteurs en aval. D’autres parties (dans ce cas, le corps) peuvent être définies par les auteurs en aval avec des instructions spécifiques (dans ce cas, un nombre minimal et un nombre maximal de modules de types spécifiques). Et d’autres parties (dans ce cas, le pied de page) sont définies dans le modèle mais peuvent être remplacées par les auteurs en aval.

Une étape initiale importante pour les administrateurs du site et de marque consiste à trouver l’équilibre entre la contrainte et la flexibilité des auteurs de disposition et de pages enfants. Lorsque des modèles sont utilisés, cet équilibre est totalement configurable. Il affecte si des éléments de page sont centralement mis à jour (verrouillés dans le modèle) ou laissés aux niveaux enfants individuels qui sont plus bas dans la hiérarchie de page.

Pour commencer à utiliser les modèles, voir [Utilisation des modèles](work-with-templates.md).

## <a name="layouts"></a>Dispositions

Les dispositions sont le niveau suivant dans la hiérarchie de modèle de page, sous les modèles. Alors qu’un modèle définit tous les modules autorisés pour une page, une disposition est une sélection et une organisation explicites des modules. Les pages sont le niveau suivant dans la hiérarchie de modèle de page, sous les dispositions. Elles définissent le contenu localisé pour les modules sélectionnés dans la disposition.

L’exemple suivant se base sur l’exemple de modèle dans la section précédente, et indique comment une disposition de base peut être configurée :

- Le modèle parent de la disposition requiert que le conteneur du corps ait entre un et dix modules. Ces modules peuvent être des modules de bannière, de fonctionnalité et de carrousel. Par conséquent, la disposition peut définir la sélection et l’organisation des modules suivants :

    - Le premier module dans le conteneur du corps est un module de bannière, et il est suivi par un module de bannière et deux modules de fonctionnalités.
    - Le premier module de fonctionnalité est aligné à gauche, et le second module de fonctionnalité est aligné à droite.

- Même si un pied de page par défaut est hérité du modèle parent, l’auteur du modèle a laissé le pied de page déverrouillé. Par conséquent, la disposition peut le remplacer en définissant un fragment différent de pied de page.

La disposition dans cet exemple définit la disposition finale des modules des pages enfants. Comme un modèle, une disposition peut définir les propriétés par défaut ou verrouillées du module qui seront toujours héritées par les pages enfants (par exemple, l’alignement des modules de fonctionnalité). Le contenu ou les données réelles pour chaque module dans la disposition est ensuite défini davantage défini dans la hiérarchie, dans chaque instance de page enfant. Une différence importante ici est que les dispositions ne contiennent pas directement le contenu localisable, alors que les pages enfants, oui. La principale fonctionnalité de la disposition est de définir l’organisation finale et la configuration par défaut des modules pour ses pages enfants.

Cette hiérarchie est puissante pour deux motifs. Premièrement, les dispositions qui partagent le même modèle parent sont traitées comme compatibles avec les scénarios de changement de disposition. Par conséquent, la disposition de la page peut être modifiée en une autre disposition de la même hiérarchie de modèle sans que le contenu de niveau de la page soit recréé. Vous pouvez profiter de cette capacité à exercer des mises à jour de conception saisonnières, expérimenter, ou effectuer une nouvelle configuration permanente du site. Deuxièmement, les dispositions sont un moyen de modifier centralement les éléments partagés pour un groupe de pages sans nécessiter de mises à jour dans les pages individuelles. Par exemple, si une catégorie de produit a 1 000 pages présentant la même disposition, les modules peuvent être réorganisés dans la disposition, et cette modification est immédiatement répercutée dans chacune des 1 000 pages enfants.

En comprenant cette hiérarchie, vous pouvez fournir une structure de site agile et efficace qui garantit une économie de coûts, qui est évolutive, et génère de meilleurs résultats à mesure que le site évolue dans le temps.

### <a name="preset-and-custom-layouts"></a>Dispositions prédéfinies et personnalisées

Les dispositions de votre site peuvent être *prédéfinies* ou *personnalisées* :

- Les **Dispositions prédéfinies** permettent un workflow de création de page dans lequel tous les modules sont déjà sélectionnés et organisés, seule la saisie de données est nécessaire. Cette approche peut aider à gagner du temps lorsque vous devez créer plusieurs de pages qui ont les mêmes besoins de disposition. Les dispositions prédéfinies ont des relation un-à-plusieurs avec leurs pages enfants. Par conséquent, une disposition prédéfinis unique peut être utilisée pour contrôler l’organisation du module pour des centaines ou des milliers de pages enfants.
- Les **Dispositions personnalisées** sont principalement des dispositions à usage unique intégrées dans une page. Elles ne sont pas exposées comme option lorsque d’autres nouvelles pages sont créées ou dans les scénarios de changement de disposition. L’avantage de cette approche est qu’un auteur peut expérimenter en créant une page qui utilise une disposition personnalisée. Ensuite, si l’auteur souhaite réutiliser la disposition pour d’autres pages, elle peut être facilement convertie en une disposition prédéfinie. La nouvelle disposition prédéfinie est alors exposée comme une option dans les workflows de création de page et dans les scénarios de changement de disposition pour les pages de la même hiérarchie de modèle. Inversement, les dispositions prédéfinies peuvent être branchées en dispositions personnalisées. Ainsi, un auteur peut désactiver une page de la disposition prédéfinie et créer une disposition personnalisée à usage unique. (Cette nouvelle disposition personnalisée est encore associée à des contraintes dans le modèle parent.)

Les dispositions prédéfinies et les dispositions personnalisés sont modifiées dans différentes parties du jeu d’outils de création. Comme les dispositions personnalisées n’ont aucune dépendance avec d’autres pages, elles sont modifiées directement dans l’éditeur de page. Dans ce cas, l’existence d’une disposition est la plupart du temps transparente pour l’utilisateur et est exposée uniquement dans les propriétés au niveau de la page et via les actions pour les options de disposition. Toutefois, comme les modifications des dispositions prédéfinies peuvent affecter la plupart des pages enfants, elles doivent être modifiées dans l’éditeur de disposition, dans lequel les actions de publication prennent en compte l’impact en aval complet dans les pages enfants.

Les illustrations suivantes affiche des scénarios de dispositions prédéfinies et personnalisées.

![Scénarios de dispositions prédéfinies et personnalisées.](../commerce/media/template-figure1.png)

Pour commencer à utiliser les dispositions prédéfinies, voir [Utiliser des dispositions prédéfinies](work-with-layouts.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Utiliser des modèles](work-with-templates.md)

[Utilisation des mises en page prédéfinies](work-with-layouts.md)

[Utilisation de groupes de publication](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]