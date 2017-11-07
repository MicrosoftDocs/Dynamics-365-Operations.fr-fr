---
title: "Mise à jour de document simple et de réévaluation de devise"
description: "Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 13ad43cc77731727525aae1edc4d405c166acbc1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a>Mise à jour de document simple et de réévaluation de devise

[!include[banner](../includes/banner.md)]


Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

Procédez comme suit lorsque vous effectuez la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

1.  Avant la mise à niveau vers Dynamics 365 for Operations, exécutez les processus de réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Définissez le champ **Méthode** sur **Date de facture**. Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises. Par conséquent, les transactions en cours sont évaluées dans leur devise comptable d'origine.
2.  Effectuez la mise à niveau vers Dynamics 365 for Operations, version 1611.
3.  Exécutez à nouveau la réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Cette fois, définissez le champ **Méthode** sur **Standard**. Une nouvelle transaction de réévaluation est créée d'après les taux de change actuels. Cette transaction enregistre les profits/pertes non réalisés et le compte général collectif approprié.





