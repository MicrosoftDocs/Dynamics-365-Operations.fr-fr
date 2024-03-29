---
title: Transférer une immobilisation
description: Ce Guide de tâche transfèrera les informations financières pour un registre d’immobilisation provenant d’un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c8428467d6e12b6d6af9023980b8cf8738d9294
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727003"
---
# <a name="transfer-a-fixed-asset"></a>Transférer une immobilisation

[!include [banner](../../includes/banner.md)]

Ce Guide de tâche transfèrera les informations financières pour un registre d’immobilisation provenant d’un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières.  

1. Dans le volet de navigation, accédez à **Modules > Immobilisations > Immobilisations > Immobilisations**.
2. Dans la liste, recherchez et sélectionnez l’immobilisation à transférer.
3. Dans le volet Actions, cliquez sur **Immobilisation**.
4. Cliquez sur **Transférer des immobilisations**.
5. Entrez une date dans le champ **Date de transfert**.
6. Entrez des commentaires pour décrire le transfert.
    
    Cette liste répertorie tous les registres pour l’immobilisation.  
7. Marquez les registres à transférer vers le nouvel ensemble de dimensions financières.
    * Cette liste répertorie les valeurs de dimension financière existantes pour le registre sélectionné.  
    * Sélectionnez la dimension financière que vous souhaitez mettre à jour pour le registre d’immobilisation sélectionné.  
8. Dans le champ **Dimension financière**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Définissez d’autres valeurs de dimension financière, le cas échéant.  
    * Toutes les valeurs de dimension financière sont modifiées lorsqu’un transfert a lieu, même si une valeur a été entrée ou est laissée vide. Par exemple, si vous avez entré une valeur pour BusinessUnit et laissé les dimensions financières pour CostCenter et Département vides. Si votre structure de compte avait autorisé les valeurs vides pour CostCenter et Département, suite au transfert, chaque modèle de valeur aurait eu la nouvelle valeur pour BusinessUnit et une valeur vide pour CostCenter et Département.  
9. Cliquez sur **Mettre à jour**.
    * Vous pouvez prévisualiser les modifications avant de finaliser le transfert.  
    * Réexaminez les résultats avant de transférer les registres d’immobilisation.  
10. Cliquez sur **Transférer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
