---
title: Créer et tenir à jour un blocage du stock
description: Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock.
author: perlynne
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2485eaf31226b11106895074ae0ad95e561777b
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916597"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Créer et tenir à jour un blocage du stock

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment empêcher le stock physique disponible d'être réservée par d'autres documents sources sortants en utilisant le blocage du stock. Vous pouvez exécuter la procédure dans la société USMF fictive avec les valeurs d'exemple affichées. Vous devez posséder d'un article avec le stock physique disponible avant de commencer cette procédure.


## <a name="create-an-inventory-blocking"></a>Créer un blocage du stock
1. Dans le **volet de navigation**, accédez à **Modules > Gestion des stocks > Tâches périodiques > Blocage du stock**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, sélectionnez l'article que vous souhaitez choisir. Sélectionnez un numéro d'article avec le stock physique disponible à bloquer. Si vous utilisez USMF, vous pouvez sélectionner l'article M9201.  
5. Entrez un nombre dans le champ **Quantité**. Si vous utilisez l'article M9201, vous devez sélectionner inférieur à 200.
6. Développez le raccourci **Dimensions de stock**.
7. Dans le champ **Entrepôt**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Si vous utilisez l'article M9201, vous pouvez sélectionner l'entrepôt 51.  
9. Cliquez sur **Enregistrer**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Mettre à jour les conditions du blocage du stock
1. Dans le raccourci **Général**, entrez un nombre dans le champ **Quantité**. Mettez à jour le champ de quantité en stock pour refléter la quantité à bloquer.  
2. Entrez une date dans le champ **Date prévue**. Vous souhaitez peut-être indiquer à quel moment il est prévu que le stock bloqué devienne disponible pour réservation en affectant une date prévue. Si l'option Réceptions prévues est sélectionnée pour le blocage du stock, (elle l'est par défaut lorsque vous créez manuellement un blocage), cette date s'affiche sur la transaction attendue.  
3. Cliquez sur **Enregistrer**.

## <a name="remove-the-inventory-blocking"></a>Supprimer le blocage du stock
1. Dans le **volet Actions**, cliquez sur **Supprimer**.
2. Cliquez sur **Oui**.
3. Fermez la page.

