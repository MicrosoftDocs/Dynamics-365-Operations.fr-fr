---
title: Paramétrer des codes taxe
description: Cette rubrique explique comment paramétrer des codes taxe dans Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f6df5ed3fc49b537845e7d418d4953c0faee5f3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994538"
---
# <a name="set-up-sales-tax-codes"></a>Paramétrer des codes taxe

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer des codes taxe. Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l’entité juridique est obligée de calculer, de collecter et de payer à l’administration fiscale.

La société fictive USMF est citée en exemple dans cette tâche.

1. Allez dans **Volet de navigation > Taxes > Taxes indirectes > Taxe > Codes taxe**.
2. Sélectionnez **Nouveau**.
3. Tapez une valeur dans le champ **Code taxe**.
4. Tapez une valeur dans le champ **Nom**.
5. Sélectionnez une **Période de règlement** en ouvrant la liste déroulante pour spécifier l’administration fiscale et les intervalles auxquels cette taxe doit être déclarée et payée.
6. Sélectionnez un **Groupe de validation dans la comptabilité** pour spécifier les comptes principaux pour valider la taxe dans la comptabilité.
7. Développez le raccourci **Calcul**. Plusieurs champs contrôlent la manière dont les montants de taxe sont calculés. Renseignez ces champs si nécessaire.  
8. Dans le **Volet Actions** en haut de l’interface, sélectionnez **Code taxe**.
9. Sélectionnez **Valeurs**.
10. Entrez la valeur pour ce code taxe dans la colonne **valeur**.
    - Dans le raccourci **Calcul**, dans le champ Origine, si Montant par unité est sélectionné, la valeur sera multipliée par la quantité de la transaction pour calculer le montant de la taxe.  Si le code taxe n’est pas une taxe basée sur des unités, la valeur est un pourcentage appliqué sur le code d’origine pour cette taxe pour calculer le montant de la taxe.     
11. Sélectionnez **Enregistrer**.
12. Fermez la page.
13. Sélectionnez **Enregistrer**.

