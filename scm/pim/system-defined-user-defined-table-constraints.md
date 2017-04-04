---
title: "Contraintes de table définies par l&quot;utilisateur et par le système"
description: "Cet article décrit les deux types de contraintes de table pour des composants dans un modèle de configuration de produit - défini par l&quot;utilisateur et défini par le système. Les contraintes de table représentent des matrices des combinaisons d&quot;attributs autorisées dans lesquelles chaque ligne définit un ensemble de valeurs d&quot;attribut possibles."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: 510ee819e6bc69b72df767f6cfd284230baba729
ms.lasthandoff: 03/31/2017


---

# <a name="system-defined-and-user-defined-table-constraints"></a>Contraintes de table définies par l'utilisateur et par le système

Cet article décrit les deux types de contraintes de table pour des composants dans un modèle de configuration de produit - défini par l'utilisateur et défini par le système. Les contraintes de table représentent des matrices des combinaisons d'attributs autorisées dans lesquelles chaque ligne définit un ensemble de valeurs d'attribut possibles.

Les contraintes de table représentent les matrices des combinaisons d'attributs autorisées pour les composants d'un modèle de configuration de produit. Chaque ligne de la table définit un ensemble de valeurs d'attribut possibles. Il existe deux types de contraintes que vous pouvez déclarer dans un modèle de configuration de produit :

-   **Contrainte d'expression** – Créez une expression qui définit les relations entre les attributs pour s'assurer que seules les valeurs compatibles peuvent être sélectionnées lors de la configuration d'un produit.
-   **Contrainte de table** – Créez une table qui définit les combinaisons autorisées pour un ensemble spécifié d'attributs. Il existe deux types de contraintes de table : les contraintes de table définies par l'utilisateur et les contraintes de table définies par le système.

Cet article décrit les contraintes de table définies par l'utilisateur et par le système pour les composants d'un modèle de configuration de produit.

## <a name="user-defined-table-constraints"></a>Contraintes de table définies par l'utilisateur
Une contrainte de table définie par l'utilisateur est un type de matrice utilisé pour décrire les combinaisons de valeurs d'attribut définies par les types d'attributs. Par exemple, si vous produisez des haut-parleurs, vous pouvez inclure des colonnes pour les finitions du meuble et la grille avant dans la contrainte de table définie par l'utilisateur. Le type d'attribut pour les finitions du meuble a quatre valeurs, et le type d'attribut pour la grille avant a trois valeurs. Par conséquent, si les contraintes ne sont pas utilisées, il existe 4 × 3 = 12 combinaisons possibles. Toutefois, dans cet exemple, seules six combinaisons sont autorisées, comme indiqué dans le tableau suivant. Ces informations sont affichées sous l'onglet **Combinaisons autorisées** de la page **Modifier une contrainte de table**.

| Finitions du meuble | Grille avant |
|----------------|-------------|
| Noir          | Noir       |
| Noir          | Métal       |
| Chêne            | Noir       |
| Bois de rose       | Blanc       |
| Blanc          | Noir       |
| Blanc          | Blanc       |

Les contraintes de table définies par l'utilisateur sont définies par une entrée de table statique qui fonctionne de la même manière qu'une contrainte d'expression. Lorsque vous utilisez une contrainte de table définie par l'utilisateur, l'avantage est que les tables sont souvent plus facile à créer, à comprendre et à tenir à jour que de longues contraintes d'expression.

## <a name="system-defined-table-constraints"></a>Contraintes de table définies par le système
Une contrainte de table définie par le système crée une mise en correspondance dynamique entre un type d'attribut et un champ dans une table. Lorsqu'une contrainte de table définie par le système est incluse dans un modèle de configuration de produit, la mise en correspondance garantit que les données de la table s'affichent à la place des valeurs du type d'attribut. Le résultat crée une contrainte dynamique, car le contenu de la table peut être modifié, par exemple, par d'autres modules.  

Lorsque vous créez une contrainte de table définie par le système, sélectionnez une table, définissez éventuellement la requête à utiliser, puis associez les types d'attributs aux champs de la table sélectionnée. Les types de champs doivent faire correspondre aux types des types d'attributs.  

Avant qu'une contrainte de table puisse prendre effet sur un modèle de configuration de produit, la contrainte de table doit être incluse dans une contrainte de l'un des composants du modèle. La procédure est de créer une nouvelle contrainte, sélectionne le type de contrainte de table, puis sélectionnez la définition de contrainte de table à utiliser. Enfin, tous les champs de la contrainte de table doivent être mis en correspondance avec les attributs du modèle de configuration de produit.

<a name="see-also"></a>Voir également :
--------

[Concepts clés en matière de modèles de configuration du produit](product-configuration-models.md)


