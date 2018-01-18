---
title: "Créer une feuille de chargement"
description: "Cette rubrique décrit la procédure de création d'une feuille de chargement lors de l'utilisation des processus de gestion des entrepôts."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b274ff572d2be9a71b91d533023b95be98591e4f
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-bill-of-lading"></a>Créer une feuille de chargement

[!include[banner](../includes/banner.md)]


Cette rubrique décrit la procédure de création d'une feuille de chargement lors de l'utilisation des processus de gestion des entrepôts.  

Une feuille de chargement est un document juridique entre la société qui expédie les articles et le transporteur. Le document accompagne les articles expédiés, et sert de preuve d'expédition lorsque les articles sont livrés à la destination. Si vous utilisez la gestion des entrepôts, il existe deux manières de générer une feuille de chargement :

  -   Vous pouvez créer l'état manuellement, à l'aide de la page **Feuille de chargement**.
  -   Vous pouvez générer un état à partir de l'option **Atelier de planification des chargements**.

Si vous générez la feuille de chargement à partir de l'option **Atelier de planification des chargements**, le statut de chargement doit être **Expédié**. S'il y a plus d'une expédition dans le chargement, une feuille de chargement est créée pour chaque expédition. Une fois la feuille de chargement créée, vous pouvez y apporter des modifications dans la page **Feuille de chargement**.

## <a name="master-bill-of-lading"></a>Feuille de chargement principale
S'il existe plusieurs expéditions dans un chargement, vous pouvez créer une feuille de chargement principale. La mise en page et les informations sont les mêmes que sur une feuille de chargement, mais elle contient le récapitulatif du contenu de toutes les expéditions. Si l'option **Créer une feuille de chargement principale s'il existe plusieurs expéditions sur un chargement** est définie sur **Oui** sur la page **Paramètres de gestion de transport**, une feuille de chargement principale est générée automatiquement si vous créez une feuille de chargement à partir de **Atelier de planification des chargements**, et il y a plusieurs expéditions. Vous pouvez également obtenir la liste des feuilles de chargement en cliquant sur **Informations associées** &gt; **Feuille de chargement**. Si vous créez des feuilles de chargement manuellement, vous pouvez créer une feuille de chargement principale dans la page **Feuille de chargement**.




