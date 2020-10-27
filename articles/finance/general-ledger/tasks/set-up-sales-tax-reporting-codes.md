---
title: Paramétrer des codes déclaration de taxe
description: Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c18f4fb0db31a959647bb10d2b99d940646676e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976791"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Paramétrer des codes déclaration de taxe

[!include [banner](../../includes/banner.md)]

Les codes déclaration de taxe font référence à un numéro de champ dans la déclaration de taxe. Ils sont utilisés dans les présentations d'états spécifiques à un pays, l'état des paiements de taxe par code imprime les montants de taxe pour une période de règlement résumée par code déclaration. Après avoir créé les codes déclaration de taxe, vous pouvez vous y référer dans les organisateurs de paramétrage d'état dans la page du code taxe. 

La société fictive DEMF sert d'exemple dans cet enregistrement.

1. Dans le **Volet de navigation**, accédez à **Taxes > Paramétrage > Taxe > Codes déclaration de taxe**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez la présentation d'état à laquelle appartient le code déclaration. Cette structure est utilisée pour filtrer les codes taxes disponibles pour le code taxe. Chaque code taxe appartient à une période de règlement appartenant à une administration fiscale qui utilise une présentation d'état.  
4. Dans le champ **Code de déclaration**, entrez un numéro.
5. Dans le champ **Texte d'état**, entrez une description à afficher dans les états.
6. Dans le champ **Brève description**, entrez une description à des fins internes.
7. Cliquez sur **Enregistrer**.

