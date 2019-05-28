---
title: Paramétrer des codes taxe
description: Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l'entité juridique est obligée de calculer, de collecter et de payer à l'administration fiscale.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f29442c2ef2e3d0008a74298fda218e4cbd93f8e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571581"
---
# <a name="set-up-sales-tax-codes"></a>Paramétrer des codes taxe

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l'entité juridique est obligée de calculer, de collecter et de payer à l'administration fiscale.

La société fictive USMF est citée en exemple dans cette tâche.



1. Accédez à Taxes > Taxes indirectes > Taxe > Codes taxe.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Code taxe.
4. Tapez une valeur dans le champ Nom.
5. Sélectionnez une période de règlement pour spécifier l'administration fiscale et les intervalles auxquels cette taxe doit être déclarée et payée.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Sélectionnez un groupe de validation dans la comptabilité pour spécifier les comptes principaux pour valider la taxe dans la comptabilité.
8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
10. Développez l'organisateur Calcul.
    * L'organisateur Calcul a plusieurs champs qui contrôlent la manière dont les montants de taxe sont calculés.  
11. Dans le volet Actions, cliquez sur le code Taxe.
12. Cliquez sur Valeurs.
13. Dans la liste, marquez la ligne sélectionnée.
14. Entrez la valeur de ce code taxe.
    * Dans l'organisateur Calcul, dans le champ Origine, si Montant par unité est sélectionné, la valeur sera multipliée par la quantité de la transaction pour calculer le montant de la taxe.  Si le code taxe n'est pas une taxe basée sur des unités, la valeur est un pourcentage appliqué sur le code d'origine pour cette taxe pour calculer le montant de la taxe.     
15. Cliquez sur Enregistrer.
16. Fermez la page.
17. Cliquez sur Enregistrer.

