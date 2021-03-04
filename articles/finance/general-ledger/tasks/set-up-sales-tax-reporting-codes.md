---
title: Paramétrer des codes déclaration de taxe
description: Les codes déclaration de taxe font référence à un numéro de champ répertorié dans la déclaration de taxe.
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
ms.openlocfilehash: 362d30e56fe35b85d50bfa2df57364733b366fef
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646179"
---
# <a name="set-up-sales-tax-reporting-codes"></a>Paramétrer des codes déclaration de taxe

[!include [banner](../../includes/banner.md)]

Les codes déclaration de taxe font référence à un numéro de champ répertorié dans la déclaration de taxe. Ils sont utilisés sur des présentations de rapport spécifiques à un pays. Ils sont également utilisés sur l’état de déclaration de taxe par code. Ce rapport affiche les montants de la taxe pour une période de décompte récapitulée pour chaque code de déclaration. Après avoir créé les codes déclaration de taxe, vous pouvez vous y référer dans les organisateurs de paramétrage d’état sur la page **code taxe**. 

La société fictive DEMF sert d’exemple dans cet enregistrement.

1. Dans le **Volet de navigation**, accédez à **Taxes > Paramétrage > Taxe > Codes déclaration de taxe**.
2. Cliquez sur **Nouveau**.
3. Sélectionnez la présentation d’état à laquelle appartient le code déclaration. Cette structure est utilisée pour filtrer les codes taxes disponibles pour le code taxe. Chaque code taxe appartient à une période de règlement appartenant à une administration fiscale qui utilise une présentation d’état.  
4. Dans le champ **Code de déclaration**, entrez un numéro.
5. Dans le champ **Texte d’état**, entrez une description à afficher dans les états.
6. Dans le champ **Brève description**, entrez une description à des fins internes.
7. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]