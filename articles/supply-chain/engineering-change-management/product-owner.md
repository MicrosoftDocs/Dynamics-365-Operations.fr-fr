---
title: Propriétaires de produits
description: Cette rubrique fournit des informations sur la les propriétaires de produits. Un propriétaire de produit est un groupe d'utilisateurs qui sont responsables de produits spécifiques. Seuls les membres du groupe peuvent lancer ces produits. Le propriétaire du produit peut également être utilisé dans le workflow d'approbation.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4308020d66995d857e547be47216cb82caacf035
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4428337"
---
# <a name="product-owners"></a>Propriétaires de produits

[!include [banner](../includes/banner.md)]

Le propriétaire de produit est un groupe d'utilisateurs qui sont responsables de produits spécifiques. Lorsqu'un groupe de propriétaires de produit est affecté à un produit, seuls les membres de ce groupe peuvent valider le produit. Le propriétaire du produit peut également être utilisé dans le workflow d'approbation de la gestion des modifications d'ingénierie.

Les propriétaires de produit sont des paramètres globaux. Par conséquent, ils sont disponibles pour toutes les entité juridique.

## <a name="create-a-product-owner-group"></a>Créer un groupe de propriétaires de produit

Pour créer un groupe de propriétaires de produit et y ajouter des membres, procédez comme suit.

1. Aller à **Gestion des modifications d'ingénierie \> Configurer \> Propriétaires de produit**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Propriétaire de produit**, entrez un nom pour le groupe.
4. Dans le champ **Nom**, entrez une description du groupe.
5. Sur le raccourci **Membres**, ajoutez les nœuds de calcul qui doivent être membres du groupe.

## <a name="assign-a-product-owner-to-a-product"></a>Affecter un propriétaire de produits à un produit

Pour affecter un propriétaire de produit à un produit, procédez comme suit.

1. Ouvrez la page **Détails du produit** pour le produit ou le produit générique concerné.
1. Sur le raccourci **Général**, définissez le champ **Propriétaire du produit** sur le nom du groupe de propriétaires de produit concerné.

Lorsqu'un propriétaire de produit est affecté à un produit, seuls les membres du groupe de propriétaires de produit peuvent modifier le paramètre **Propriétaire du produit**.

Le propriétaire de produit est également visible sur la page **Produits lancés**.

## <a name="product-owners-and-product-releases"></a>Propriétaires de produits et versions de produits

Seuls les utilisateurs appartenant au groupe de propriétaires de produit d'un produit peuvent lancer ce produit. Cependant, il existe une exception lorsque le produit est un élément enfant et que son parent est libéré par le propriétaire du parent. En d'autres termes, si le produit fait partie de la nomenclature d'un autre produit, le système ne vérifie pas le propriétaire du produit de chaque article de la nomenclature. Il vérifie uniquement le propriétaire du produit de l'article parent.

Par exemple, le produit X est affecté au groupe de propriétaires de produits *Armoires design*. Le produit X fait également partie de la nomenclature du produit Y, qui est affectée au groupe de propriétaires de produits *Concevoir des haut-parleurs*. Si un utilisateur du groupe de propriétaires de produits *Concevoir des haut-parleurs* lance le produit Y et sa nomenclature, le produit X sera publié avec le produit Y.

## <a name="product-owners-and-approvals"></a>Propriétaires de produits et approbations

Étant donné que les propriétaires de produits savent si des modifications techniques spécifiques bénéficieront à leurs produits, il est souvent judicieux de les inclure dans le processus d'approbation de la gestion des modifications techniques. Vous pouvez mettre en œuvre cette approche en configurant les propriétaires de produit en tant que fournisseurs participants dans les workflows utilisés pour la gestion des modifications techniques. Le système attribuera ensuite des tâches d'approbation dans les workflows, en fonction des produits qui sont dans les demandes de modification technique et les ordres de modification technique. Pour plus d'informations, voir [Gérer modifications des produits techniques](engineering-change-management.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]