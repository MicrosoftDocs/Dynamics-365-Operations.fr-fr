---
title: Planification avec accords commerciaux d'achat
description: Cette rubrique décrit comment l'optimisation de la planification peut trouver le fournisseur et/ou le délai de livraison pour un ordre planifié, en fonction du meilleur prix ou du meilleur délai de livraison trouvé dans les accords commerciaux d'achat.
author: ChristianRytt
manager: tfehr
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: b302c5ace34a11a53a98c733b59633a11a463bfa
ms.sourcegitcommit: 3fa1e8583003a90ba486f757c3826b139e1b3f73
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2020
ms.locfileid: "3421529"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Planification avec accords commerciaux d'achat

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment l'optimisation de la planification peut trouver le fournisseur et/ou le délai de livraison pour un ordre planifié, en fonction du meilleur prix ou du meilleur délai de livraison trouvé parmi tous les accords commerciaux d'achat qui ont été passés pour un produit donné.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>Activer la fonctionnalité Accords commerciaux d'achat pour l'optimisation de la planification

Avant de pouvoir utiliser cette fonctionnalité, vous devez l'activer sur votre système. Les administrateurs peuvent utiliser l'espace de travail [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Planification*
- **Nom de la fonctionnalité :** *Accords commerciaux d'achat pour l'optimisation de la planification*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Préparer le système pour évaluer les accords commerciaux d'achat lors de la planification

Procédez comme suit pour configurer votre système en vue d'appliquer l'optimisation de la panification permettant d'évaluer les accords commerciaux d'achat.

1. Accédez à **Planification \> Paramétrage \> Paramètres de planification**. Dans l'onglet **Ordres prévisionnels**, dans la section **Fournisseur**, définissez les valeurs suivantes :

    - **Rechercher un accord commercial** – Définissez cette option sur **Oui** pour inclure les accords commerciaux d'achat dans la planification.
    - **Critère de recherche** – Sélectionnez le facteur auquel vous souhaitez donner la priorité pour chaque accord commercial d'achat : **Délai minimum** ou **Prix unitaire minimal**.

1. Accédez à **Approvisionnements \> Paramétrage \> Prix et remises \> Activation des prix/remises**,et assurez-vous que l'option **Fournisseur** est définie sur **Oui**.
1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Groupes de dimensions et de variantes \> Groupes de dimensions de stockage** et sélectionnez un groupe de dimensions de stockage qui s'applique aux produits pour lesquels la planification doit évaluer les accords commerciaux d'achat. Assurez-vous que chaque dimension de stockage pertinente de ce groupe est cochée dans la colonne **Prix d'achat**. Répétez cette étape pour tous les autres groupes de dimensions de stockage pertinents.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Préparer un produit lancé pour évaluer les accords commerciaux d'achat lors de la planification

Une fois votre système préparé comme décrit dans la section précédente, vous devez procéder comme suit pour vous assurer que chaque produit que vous souhaitez utiliser avec cette fonctionnalité est correctement configuré.

1. Accédez à **Gestion d'informations sur les produits \> Produits \> Produits lancés** et ouvrez un produit cible.
1. Dans le raccourci **Achat**, assurez-vous qu'aucun fournisseur n'est affecté dans le champ **Fournisseur**.
1. Dans le volet Actions, sous l'onglet **Plan**, dans le groupe **Couverture**, cliquez sur **Couverture de l'article** pour ouvrir la page **Couverture de l'article** pour le produit sélectionné. Vérifiez les paramètres suivants :

    - Dans l'onglet **Général**, vous pouvez configurer des remplacements de fournisseurs. Si vous souhaitez que l'optimisation de la planification utilise les accords commerciaux d'achat pour sélectionner un fournisseur, vous devez empêcher les remplacements de fournisseur en désactivant la case à cocher **Utiliser des paramètres spécifiques**.
    - Dans l'onglet **Délai**, vous pouvez configurer des remplacements de délais. i vous souhaitez que l'optimisation de la planification utilise les accords commerciaux d'achat pour sélectionner les délais, vous devez empêcher les remplacements de délais. Décochez la case correspondant à chaque type de délai que vous souhaitez sélectionner à l'aide des accords commerciaux d'achat (**Achat**, **Production** et/ou **Transfert**).

1. Fermez la page **Couverture de l'article** pour revenir à la page des détails du produit sélectionné.
1. Dans le volet Actions, dans l'onglet **Plan**, dans le groupe **Prévision**, sélectionnez **Prévision d'approvisionnement** pour ouvrir la page **Prévision d'approvisionnement**. Assurez-vous qu'aucune ligne affichée ici n'a de valeur dans la colonne **Compte fournisseur**.
1. Fermez la page **Prévision d'approvisionnement** pour revenir à la page des détails du produit sélectionné.
1. Dans le volet Actions, dans l'onglet **Achat**, dans le groupe **Accords commerciaux**, sélectionnez **Afficher les accords commerciaux**. Assurez-vous que tous les accords commerciaux d'achat pertinents sont répertoriés. Assurez-vous également que l'option **Ignorer le délai** est définie sur **Non** pour chaque accord pour lequel vous souhaitez que l'optimisation de la planification utilise le délai spécifié pour cet accord.
1. Dans le volet Actions, sous l'onglet **Plan**, dans le groupe **Paramètres de la commande**, sélectionnez **Paramètres de commande par défaut** pour ouvrir la page **Paramètres de commande par défaut** pour le produit sélectionné. Dans le raccourci **Commande fournisseur**, regardez la valeur du champ **Délai d'achat**. Si aucun remplacement de délai de couverture de l'article n'est défini, l'optimisation de la planification utilisera cette valeur lors de la sélection des accords commerciaux où l'option **Ignorer le délai** est définie sur **Oui**. Par conséquent, vous devez ajuster cette valeur selon vos besoins.
1. Répétez cette procédure pour chaque produit concerné.

> [!NOTE]
> La devise sur la ligne de l'accord d'achat doit correspondre à la devise du fournisseur sélectionné. La planification n'inclura que les informations des lignes de l'accord commercial d'achat où la devise correspond à la devise du fournisseur.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Exemples de la façon dont l'optimisation de la planification trouve le fournisseur et les délais

Le tableau suivant fournit des exemples qui montrent comment les différents paramètres d'un produit lancé et ses accords commerciaux d'achat associés affectent les valeurs trouvées pour la commande fournisseur prévisionnelle résultante. Les valeurs en **gras** des deux colonnes les plus à droite sont les valeurs sélectionnées par l'optimisation de la planification. Les valeurs en ***gras italique*** des autres colonnes sont les paramètres qui ont produit les valeurs résultantes pour chaque ligne.

| Produit lancé : Fournisseur | Paramètres de commande par défaut : Délai | Couverture de l'article : Remplacer le fournisseur | Couverture de l'article : Remplacer le délai | Accord commercial : Fournisseur | Accord commercial : Délai | Accord commercial : Ignorer le délai | Fournisseur résultant | Délai résultant |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001*** | ***1*** | N° | N° | US003 | 3 | N° | **US001** | **1** |
| US001 | 1 | ***Oui : US002*** | ***Oui : 2*** | US003 | 3 | N° | **US002** | **2** |
| *(Vide)* | 1 | N° | N° | ***US003*** | ***3*** | N° | **US003** | **3** |
| *(Vide)* | ***1*** | N° | N° | ***US003*** | 3 | Oui | **US003** | **1** |
| *(Vide)* | ***1*** | ***Oui : US002*** | N° | US003 | 3 | N° | **US002** | **1** |
| *(Vide)* | ***1*** | ***Oui : US002*** | N° | US003 | 3 | N° | **US002** | **1** |
| *(Vide)* | 1 | N° | Oui : 2 | ***US003*** | ***3*** | N° | **US003** | **3** |
| *(Vide)* | 1 | N° | ***Oui : 2*** | ***US003*** | 3 | Oui | **US003** | **2** |

## <a name="additional-resources"></a>Ressources supplémentaires

[Contrats d'achat](../../procurement/purchase-agreements.md)
