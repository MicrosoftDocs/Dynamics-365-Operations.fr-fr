---
title: Catalogues d'approvisionnement
description: "Cet article décrit, à un niveau supérieur, comment les acheteurs peuvent paramétrer et tenir à jour les catalogues d'approvisionnement. Des catalogues d'approvisionnement définissent les articles et les services que les employés de la société peuvent commander pour un usage interne."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 15767a54da25c293bb3d6d5e0a14e7e05a7d730b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="procurement-catalogs"></a>Catalogues d'approvisionnement

[!include[banner](../includes/banner.md)]


Cet article décrit, à un niveau supérieur, comment les acheteurs peuvent paramétrer et tenir à jour les catalogues d'approvisionnement. Des catalogues d'approvisionnement définissent les articles et les services que les employés de la société peuvent commander pour un usage interne.

Les acheteurs peuvent créer et mettre à jour les catalogues des articles et services pouvant être achetés pour un usage interne dans une organisation. Une fois les catalogues paramétrés, les employés de la société peuvent créer des demandes d'achat pour effectuer des commandes à partir de ceux-ci. Les catalogues permettent d'appliquer des stratégies d'achat afin de s'assurer que les employés commandent uniquement les articles et les services autorisés pour leur entité juridique acheteuse. Lorsque vous créez un catalogue d'approvisionnement, vous devez prendre en compte les tâches suivantes :

-   Configurez votre hiérarchie des catégories d'approvisionnement avant de créer le catalogue.
-   Déterminez les produits que vos employés peuvent commander. Vous pouvez afficher ou masquer des produits spécifiques dans un nœud de catalogue, ou vous pouvez afficher ou masquer tous les produits d'un nœud.
-   Déterminez le nombre de catalogues d'approvisionnement dont vous avez besoin. L'accès au catalogue d'approvisionnement est déterminé par la règle de stratégie de catalogue configurée pour l'entité juridique et la section auxquelles l'employé est affecté.

Plusieurs facteurs déterminent les produits que les employés peuvent commander et les catégories d'approvisionnement qu'ils peuvent utiliser en créant des demandes d'achat :

-   La règle de stratégie d'accès à la catégorie de la stratégie d'achat détermine les catégories d'approvisionnement disponibles dans la demande d'achat. Si aucune règle n'est définie, toutes les catégories d'approvisionnement sont disponibles.
-   Les employés peuvent commander un produit uniquement s'il figure dans le catalogue d'approvisionnement actif pour votre organisation, et s'il est présent dans un nœud activé et non masqué. Le produit doit également figurer dans une catégorie auquel un employé spécifique a accès en fonction de la règle de stratégie d'accès à la catégorie.
-   La règle de stratégie de catalogue spécifie le catalogue utilisé. Si aucune règle de stratégie de catalogue n'est définie, la règle d'accès à la catégorie détermine les produits qu'un employé peut commander dans la demande.

## <a name="prerequisites"></a>Logiciels requis
Le tableau suivant décrit les tâches devant être effectuées avant qu'un acheteur puisse créer un catalogue d'approvisionnement.

| Tâche                                                | Rôle               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Paramétrez une hiérarchie des catégories d'approvisionnement.            | Gestionnaire des achats | Les hiérarchies des catégories d'approvisionnement classent les articles ou les transactions à des fins d'analyse et de génération d'états. Elles permettent aux sociétés de gérer stratégiquement les catégories, les produits, les fournisseurs et d'autres facteurs d'approvisionnement à partir d'un emplacement centralisé. Une hiérarchie des catégories d'approvisionnement est définie pour l'ensemble de l'organisation. Le catalogue est basé sur la hiérarchie des catégories d'approvisionnement : les catégories de la hiérarchie deviennent des nœuds dans le catalogue. Les fournisseurs et les produits sont inclus dans votre catalogue. |
| Ajoutez des fournisseurs et des produits à des catégories d'approvisionnement. | Gestionnaire des achats | Lorsque la hiérarchie des catégories d'approvisionnement est créée pour votre organisation, chaque catégorie d'approvisionnement peut être associée à des fournisseurs et des produits spécifiques. Ces associations sont copiées automatiquement dans le catalogue.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Paramétrage d'un catalogue
Une fois les conditions préalables remplies, vous pouvez paramétrer des catalogues. Vous pouvez créer un catalogue utilisé par l'ensemble de votre organisation ou plusieurs catalogues utilisés par les différentes divisions de votre organisation. Si vous créez un catalogue pour l'ensemble de votre organisation, l'accès au catalogue est contrôlé par vos règles de stratégie d'achat.  

Le catalogue définit les produits disponibles lorsque des demandes d'achat sont créées, mais vous pouvez utiliser les règles de stratégie d'accès à la catégorie pour appliquer des restrictions supplémentaires. Comme les nœuds d'un catalogue sont des catégories d'approvisionnement, ils peuvent être supprimés par une règle de stratégie d'accès à la catégorie. Dans ce cas, les produits de cette catégorie ne peuvent pas être utilisés par les employés dans les demandes. Vous définissez des règles de stratégie d'accès à la catégorie dans la page **Stratégies d'achat**. Le tableau suivant décrit les tâches que vous devez effectuer pour paramétrer un catalogue.

| Tâche                                                   | Rôle             | Description                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Permet de créer un catalogue.                                  | Acheteurs | Lorsque vous créez un catalogue, vous spécifiez un nom et une description pour celui-ci. Vous définissez également si le catalogue est mis à jour manuellement ou automatiquement, et spécifiez le propriétaire du catalogue.                                                                                                                                      |
| Contrôlez si les produits sont disponibles dans le catalogue. | Acheteurs | Comme les produits sont hérités des catégories d'approvisionnement, ils apparaissent tous dans les nœuds de catalogue appropriés. Vous pouvez contrôler si tous les produits d'un nœud sont masqués ou affichés lorsque le catalogue est utilisé dans une demande d'achat. Vous pouvez également contrôler si les produits individuels d'un nœud sont masqués ou affichés. |
| Publiez le catalogue.                                   | Acheteurs | Avant qu'un catalogue puisse être utilisé par les employés dans une demande, vous devez définir une règle de stratégie pour le catalogue, définir l'état du catalogue sur **Actif** et publier le catalogue. Vous pouvez désactiver les catalogues auxquels vous ne souhaitez plus que vos utilisateurs accèdent.                                              |

Les mises à jour sont publiées automatiquement ou manuellement, selon l'option sélectionnée pour le catalogue dans le champ **Type de mise à jour par défaut** de la page **Catalogues**. Les types de mises à jour par défaut suivants sont disponibles pour les catalogues :

-   **Dynamique** – Le catalogue est automatiquement mis à jour à chaque modification.
-   **Statique** – Les catalogues doivent être mis à jour manuellement.
-   **Les deux** – Si le catalogue inclut des catégories de produits dont le type de mise à jour par défaut est **Statique**, il doit être mis à jour manuellement lors de la mise à jour de ces catégories. Si le catalogue inclut des catégories de produits dont le type de mise à jour par défaut est **Dynamique**, il est automatiquement mis à jour à chaque modification.


<a name="see-also"></a>Voir également :
--------

[Paramétrage d'une hiérarchie des catégories d'approvisionnement (Guide de tâche)](http://ax.help.dynamics.com/en/wiki/set-up-a-procurement-category-hierarchy/)




