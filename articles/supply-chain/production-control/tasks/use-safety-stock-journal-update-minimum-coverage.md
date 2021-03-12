---
title: Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale
description: Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0b0985169f7ffadbf97ed4f237c8ec11120cfc3e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980983"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Utiliser le journal du stock de sécurité pour mettre à jour la couverture minimale

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment calculer des propositions de couverture minimale basées sur des transactions historiques et comment mettre à jour la couverture d'article avec ces propositions. Cette opération est effectuée à l'aide du journal du stock de sécurité. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF. Cette tâche est destinée au responsable de production, pour aider à maintenir la couverture minimale.


## <a name="create-a-new-safety-stock-journal-name"></a>Créer un nouveau nom de journal de stock
1. Dans le **Volet de navigation**, allez dans **Planification > Paramétrage > Noms du journal du stock de sécurité**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, tapez « Matériel ».
4. Dans le champ **Description**, tapez « Matériel ».
5. Fermez la page.

## <a name="create-a-safety-stock-journal"></a>Créer un journal du stock de sécurité
1. Dans le **Volet de navigation**, allez dans **Planification > Planification > Exécuter > Calcul du stock de sécurité**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, saisissez ou sélectionnez une valeur. Choisissez le nom du journal de stock de sécurité que vous avez créé, par exemple, Matériel.  
4. Cliquez sur **Créer des lignes**.
5. Entrez une date dans le champ **Date de début**.  
6. Entrez une date dans le champ **Date de fin**.
7. Cliquez sur **OK**. Ceci créera des lignes pour les dimensions qui ont des mouvements de stock.  

## <a name="calculate-proposal"></a>Calculer la proposition
1. Cliquez sur **Calculer la proposition**.
2. Sélectionnez l'option **Utiliser la sortie moyenne pendant le délai**.
3. Définissez le **facteur de multiplication** sur « 10 ». Le facteur de multiplication est employé pour ajuster la proposition. Les données de démonstration ne contiennent que quelques transactions, vous devrez donc définir le facteur pour obtenir une proposition réaliste.  
4. Cliquez sur **OK**. Faites défiler vers le bas jusqu'à M0002 et M0003. Affichez la colonne **Quantité minimale calculée**.   

## <a name="update-minimum-quantity"></a>Mettre à jour la quantité minimale
1. Entrez un nombre dans le champ **Nouvelle quantité minimale**. Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée. Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée. Par exemple, vous pouvez entrer la quantité minimale calculée dans ce champ pour M0002 qui a l'entrepôt 12.  
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité. Par exemple, vous pouvez choisir M0002 qui a l'entrepôt 12.  
3. Entrez un nombre dans le champ **Nouvelle quantité minimale**. Mettre à jour la nouvelle quantité minimale pour correspondre à la valeur de la quantité minimale calculée. Si le minimum calculé est zéro, vous pouvez entrer la valeur future désirée.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Valider la nouvelle quantité minimale et contrôler le résultat
1. Cliquez sur **Valider**.
2. Cliquez sur **OK**.
3. Cliquez pour suivre le lien dans le champ **Numéro d'article**.
4. Cliquez pour suivre le lien dans le champ **Numéro d'article**.
5. Dans le **volet Actions**, cliquez sur Plan.
6. Cliquez sur **Couverture de l'article**. Notez que la **quantité minimale** a été mise à jour avec la nouvelle quantité minimale du journal du stock de sécurité.  

