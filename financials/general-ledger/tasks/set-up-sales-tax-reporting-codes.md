--- 
title: "Paramétrer des codes déclaration de taxe"
description: "Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a40da4263e7e770ce84a269ceaf60a8ca3f5382a
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-sales-tax-reporting-codes"></a>Paramétrer des codes déclaration de taxe

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe. Ils sont utilisés dans les présentations d'états spécifiques à un pays, l'état des paiements de taxe par code imprime les montants de taxe pour une période de règlement résumée par code déclaration. Après avoir créé les codes déclaration de taxe, vous pouvez vous y référer dans les organisateurs de paramétrage d'état dans la page du code taxe. 

La société fictive DEMF sert d'exemple dans cet enregistrement.



1. Allez dans Taxe > Configuration > Taxe > Codes déclaration de taxe.
2. Cliquez sur Nouveau.
3. Sélectionnez la présentation d'état à laquelle appartient le code déclaration.
    * Cette structure est utilisée pour filtrer les codes taxes disponibles pour le code taxe. Chaque code taxe appartient à une période de règlement appartenant à une administration fiscale qui utilise une présentation d'état.  
4. Entrez un numéro de champ faisant référence à un champ dans une déclaration de taxe.
5. Dans le champ Texte d'état, entrez une description à afficher dans les états.
6. Dans le champ Brève description, entrez une description à des fins internes.
7. Cliquez sur Enregistrer.


