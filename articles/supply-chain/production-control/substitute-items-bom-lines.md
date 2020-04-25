---
title: Remplacement des matériaux lors de la fabrication
description: Cette rubrique décrit comment remplacer des matériaux durant le processus de production.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 70171
ms.assetid: ce3b11ef-550e-49b7-8942-2607c2ec3c5c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b7ee4bbb832fc21d52ff30b7acc8e6a5fd3aece
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212455"
---
# <a name="material-substitution-in-manufacturing"></a>Remplacement des matériaux lors de la fabrication

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment remplacer des matériaux durant le processus de production. 

Il existe trois méthodes pour remplacer les matériaux lors du processus de production :

-   Par date, lorsqu'un matériau est remplacé par un autre après une date spécifique
-   Durant la planification, lorsqu'un matériau contenu dans une formule est remplacé par un autre, car il est épuisé
-   Durant la production, lorsqu'un matériau est en rupture de stock imprévue et remplacé par un autre

## <a name="substituting-material-by-date"></a>Remplacement d'un matériau par date
Prenons le scénario suivant : une machine qu'une société fabrique contient un composant qui sortira du catalogue du fournisseur dans deux mois. À compter de la date d'expiration, le fournisseur proposera un nouveau composant qui pourra remplacer l'ancien. Les dates de début et de fin de validité peuvent être paramétrées sur les lignes de nomenclature. Pour cet exemple, vous paramétrez l'expiration de l'ancien composant en entrant la date d'expiration dans le champ **Date de fin**. Puis, dans la nomenclature, vous paramétrez le nouveau composant de remplacement de manière à qu'il soit valide à compter du jour suivant l'expiration de l'ancien composant. Pour ce faire, entrez la date de début dans le **Date de début**.

## <a name="substituting-material-by-planning"></a>Remplacement d'un matériau par planification
Vous pouvez remplacer les matériaux durant la planification uniquement lorsque vous utilisez des formules, pas lorsque vous utilisez une nomenclature. Imaginez le scénario suivant : une société de fabrication de produits alimentaires crée une sauce à partir d'une formule contenant 20 ingrédients. Un ingrédient de la formule peut être remplacé par l'un des deux autres ingrédients. Toutefois, étant donné que ces deux ingrédients sont plus chers que l'ingrédient par défaut, le remplacement n'est possible que si l'ingrédient par défaut est épuisé. Le matériau pouvant être remplacé est appelé A, tandis que les deux matériaux de remplacement sont appelés B et C. Le remplacement des matériaux par planification est contrôlé par les champs **Planifier le groupe** et **Priorité** des lignes de formule. Pour cet exemple, vous créez des lignes de formule pour les trois matériaux et les associez au même groupe de plans. Dans le paramétrage, la ligne de formule du matériau A a la priorité la plus élevée (nombre le plus bas), la ligne de formule du matériau C a la priorité la plus faible et la ligne de formule du matériau B a une priorité comprise entre la priorité des deux autres lignes. En cas de demande de l'article fini, la planification détermine d'abord si la demande pour le matériau A peut être couverte. Si la demande ne peut pas être couverte, la planification examine les matériaux B et C, dans l'ordre de priorité. Si le matériau B est disponible, il est utilisé une fois qu'un lot de commandes prévisionnel est confirmé pour la formule. Si aucun des matériaux n'est disponible, la planification crée un ordre prévisionnel pour le matériau A. **Remarque :** lorsque vous paramétrez des lignes de formule dans un groupe de plans, vous devez spécifier une quantité uniquement pour le matériau ayant la priorité la plus élevée. Cette quantité est utilisée pour calculer la demande pour l'ensemble des matériaux du plan, même ceux ayant la priorité la plus faible. Vous ne pouvez pas spécifier plusieurs quantités pour les articles à faible priorité du groupe de plans.

## <a name="substituting-material-during-production"></a>Remplacement d'un matériau durant la production
Imaginez le scénario suivant : une plaque métallique est requise pour une opération de soudure. Durant l'opération, un magasinier informe l'opérateur que la plaque est en rupture de stock. Toutefois, il est décidé que la plaque peut être remplacée par une plaque légèrement plus épaisse. Ainsi, l'opération peut être finalisée. Le matériau peut être ajouté à la nomenclature pour un ordre de fabrication en cours. Si l'ordre de fabrication a le statut **Commencé**, les utilisateurs sont invités à réévaluer l'ordre lorsqu'ils ajoutent un nouvel article à la nomenclature de production. Une fois le matériau ajouté, de nouveaux prélèvements peuvent être créés pour le nouvel article. Il n'est pas nécessaire d'ajouter le nouveau matériau à la nomenclature de production. Vous pouvez l'ajouter directement aux prélèvements de production. Ensuite, lorsque les prélèvements sont validés, le système ajoute le matériau à la nomenclature de production.



