--- 
title: "Créer un ordre de fabrication"
description: "Cette procédure permet d'indiquer comment créer un ordre de fabrication."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 730adcea0ac59f683ecae8cbb62025bd7db75c55
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-production-order"></a>Créer un ordre de fabrication

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet d'indiquer comment créer un ordre de fabrication. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Il s'agit de la première des sept procédures expliquant le cycle de vie de l'ordre de fabrication.


## <a name="create-a-production-order"></a>Créer un ordre de fabrication
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
2. Cliquez sur Nouvel ordre de fabrication.
3. Entrez « D0001 » dans le champ Numéro d'article.
4. Entrez une date dans le champ Livraison.
    * La date de livraison indique à quel moment l'ordre de fabrication doit se terminer afin de livrer à temps. Cette date peut être utilisée dans le processus de planification. Vous pouvez par exemple planifier la commande rétrospectivement à partir de la date de livraison.  
5. Définir la Quantité sur « 20 ».
    * Remarque : Le champ Numéro de nomenclature affiche automatiquement le numéro de la nomenclature active pour l'article actuel, mais vous pouvez modifier la nomenclature pour l'ordre de fabrication en sélectionnant une nomenclature active dans la liste des versions de nomenclature approuvées.    Remarque : Le champ Numéro de gamme affiche automatiquement le numéro de la gamme active pour l'article actuel, mais vous pouvez modifier la gamme pour l'ordre de fabrication en sélectionnant une gamme active dans la liste des versions de gamme approuvées.  
6. Cliquez sur Créer.

## <a name="validate-the-production-order"></a>Valider l'ordre de fabrication
1. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Cliquez sur le lien du numéro de l'ordre de fabrication que vous venez de créer. Cela ouvre la page de détails de la commande.  
2. Cliquez sur Modifier.
3. Entrez une date dans le champ Livraison.
    * Vous pouvez par exemple modifier la date de livraison de l'ordre de fabrication.  
4. Cliquez sur Enregistrer.
5. Fermez la page.

## <a name="update-the-bom"></a>Mettre à jour la nomenclature
1. Cliquez sur Ordre de fabrication dans le volet Actions.
2. Cliquez sur Nomenclature.
    * Ouvrez la page Nomenclature pour valider les données de nomenclature copiées à partir des données par défaut lorsque l'ordre de fabrication a été créé. Dans cette procédure, vous devez mettre à jour la quantité d'une nomenclature.  
3. Cliquez sur Modifier.
4. Dans le champ Quantité, entrer un numéro.
    * La modification de la quantité de la ligne de nomenclature affecte l'estimation des coûts de la consommation de matières pour l'ordre de fabrication.  
5. Cliquez sur Enregistrer.
6. Fermez la page.

## <a name="update-the-production-route"></a>Mettre à jour la gamme de production
1. Cliquez sur Ordre de fabrication dans le volet Actions.
2. Cliquez sur Gamme
    * Ouvrez la page Gamme pour valider les données de la gamme de production copiées à partir des données par défaut lorsque la commande a été créée. Dans cette procédure, vous devez mettre à jour la quantité pour l'une des opérations de la gamme de production.  
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
4. Cliquez sur Modifier.
5. Dans le champ Qté à traiter , entrez un numéro.
    * Le fait de modifier le temps d'exécution affecte la consommation de gamme estimée et le coût de l'ordre de fabrication.  
6. Cliquez sur Enregistrer.
7. Fermez la page.


