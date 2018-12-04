---
title: "Mise à niveau de journaux de documents simples et de réévaluations de devises"
description: "Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 343fa226e1cf9072696082e9ebf0a1629e553ae9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---

# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Mise à niveau de journaux de documents simples et de réévaluations de devises

[!include [banner](../includes/banner.md)]

Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

Procédez comme suit lorsque vous effectuez la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

1.  Avant la mise à niveau vers Dynamics 365 for Operations, exécutez les processus de réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Définissez le champ **Méthode** sur **Date de facture**. Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises. Par conséquent, les transactions en cours sont évaluées dans leur devise comptable d'origine.
2.  Effectuez la mise à niveau vers Dynamics 365 for Operations, version 1611.
3.  Exécutez à nouveau la réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Cette fois, définissez le champ **Méthode** sur **Standard**. Une nouvelle transaction de réévaluation est créée d'après les taux de change actuels. Cette transaction enregistre les profits/pertes non réalisés et le compte général collectif approprié.





