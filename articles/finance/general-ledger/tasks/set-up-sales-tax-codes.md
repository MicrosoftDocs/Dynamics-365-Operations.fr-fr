---
title: Paramétrer des codes taxe
description: Cet article explique comment paramétrer des codes taxe dans Dynamics 365 Finance.
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b12133583f40cc17cb85f6dbd86697592af25caf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858466"
---
# <a name="set-up-sales-tax-codes"></a>Paramétrer des codes taxe

[!include [banner](../../includes/banner.md)]

Cet article explique comment paramétrer des codes taxe. Les codes taxe sont créés pour chaque taxe indirecte ou responsabilité que l’entité juridique est obligée de calculer, de collecter et de payer à l’administration fiscale.

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

    Dans le raccourci **Calcul**, dans le champ **Origine**, si **Montant par unité** est sélectionné, la valeur sera multipliée par la quantité de la transaction pour calculer le montant de la taxe.  Si le code taxe n’est pas une taxe basée sur des unités, la valeur est un pourcentage appliqué sur le code d’origine pour cette taxe pour calculer le montant de la taxe.     

11. Cliquez sur **Enregistrer**.
12. Fermez la page.
13. Cliquez sur **Enregistrer**.

Depuis Microsoft Microsoft Dynamics 365 Finance version 10.0.22, si vous utilisez le [Service fiscal](../../localizations/global-tax-calcuation-service-overview.md), et que la fonction [**Prise en charge de plusieurs numéros d’immatriculation à la TVA**](../../localizations/emea-multiple-vat-registration-numbers.md) est activée dans l’espace de travail **Gestion des fonctionnalités**, vous pouvez utiliser le champ **Type de taxe** pour spécifier le type de code TVA. Les valeurs disponibles sont les suivantes :

- TVA standard
- TVA réduite
- 0 % de TVA
- Accise
- Autre

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
