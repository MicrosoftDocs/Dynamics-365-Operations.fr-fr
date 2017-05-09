---
title: "Mise à niveau du N° document unique et de la réévaluation des comptes en devises pour Microsoft Dynamics 365 for Operations, version 1611"
description: "Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu&quot;elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Mise à niveau du N° document unique et de la réévaluation des comptes en devises pour Microsoft Dynamics 365 for Operations, version 1611

Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu'elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

Procédez comme suit lorsque vous effectuez la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

1.  Avant la mise à niveau vers Dynamics 365 for Operations, exécutez les processus de réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Définissez le champ **Méthode** sur **Date de facture**. Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises. Par conséquent, les transactions en cours sont évaluées dans leur devise comptable d'origine.
2.  Effectuez la mise à niveau vers Dynamics 365 for Operations, version 1611.
3.  Exécutez à nouveau la réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Cette fois, définissez le champ **Méthode** sur **Standard**. Une nouvelle transaction de réévaluation est créée d'après les taux de change actuels. Cette transaction enregistre les profits/pertes non réalisés et le compte général collectif approprié.



