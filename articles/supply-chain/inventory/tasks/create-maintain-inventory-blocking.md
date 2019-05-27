---
title: Créer et tenir à jour un blocage du stock
description: Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09789dc0b89f8bd36cca9b3e5be366bf17246243
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549769"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Créer et tenir à jour un blocage du stock

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock. Vous pouvez exécuter la procédure dans la société USMF fictive avec les valeurs d'exemple affichées. Vous devez posséder d'un article avec le stock physique disponible avant de commencer cette procédure.


## <a name="create-an-inventory-blocking"></a>Créer un blocage du stock
1. Allez dans Gestion des stocks > Tâches périodiques > Blocage du stock.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, sélectionnez l'article que vous souhaitez choisir. 
    * Sélectionnez un numéro d'article avec le stock physique disponible à bloquer. Si vous utilisez USMF, vous pouvez sélectionner l'article M9201.  
5. Dans le champ Quantité, entrer un numéro.
    * Si vous utilisez l'article M9201, vous devez sélectionner inférieur à 200.  
6. Activez ou désactivez l'extension de la section Dimensions de stock.
7. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Si vous utilisez l'article M9201, vous pouvez sélectionner l'entrepôt 51.  
9. Cliquez sur Enregistrer.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Mettre à jour les conditions du blocage du stock
1. Dans le champ Quantité, entrer un numéro.
    * Mettez à jour le champ de quantité en stock pour refléter la quantité à bloquer.  
2. Entrez une date dans le champ Date prévue.
    * Vous souhaitez peut-être indiquer à quel moment il est prévu que le stock bloqué devienne disponible pour réservation en affectant une date prévue. Si l'option Réceptions prévues est sélectionnée pour le blocage du stock, (elle l'est par défaut lorsque vous créez manuellement un blocage), cette date s'affiche sur la transaction attendue.  
3. Cliquez sur Enregistrer.

## <a name="remove-the-inventory-blocking"></a>Supprimer le blocage du stock
1. Cliquez sur Supprimer.
2. Cliquez sur Oui.
3. Fermez la page.

