---
title: Mettre à niveau les journaux de document simple et les réévaluations de devise
description: Cette rubrique décrit comment mettre à niveau les journaux de document simple et les réévaluations de devise.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fb4eca4933716105789d3bbc21dd374395211d1d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559519"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Mettre à niveau les journaux de document simple et les réévaluations de devise

[!include [banner](../includes/banner.md)]

Certaines organisations saisissent des journaux qui contiennent un N° document unique pour plusieurs clients ou fournisseurs, et elles exécutent le processus de réévaluation des comptes en devises de la comptabilité client ou de la comptabilité fournisseur. Cette rubrique décrit les étapes à suivre par ces organisations lorsqu’elles effectuent la mise à niveau vers Microsoft Dynamics 365 for Operations, version 1611.

Procédez comme suit lors de la mise à niveau vers la version 1611 de Microsoft Dynamics 365 for Operations.

1.  Avant la mise à niveau vers Finance and Operations, exécutez les processus de réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Définissez le champ **Méthode** sur **Date de facture**. Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises. Par conséquent, les transactions en cours sont évaluées dans leur devise comptable d’origine.
2.  Mettre à niveau vers version 1611.
3.  Exécutez à nouveau la réévaluation des comptes en devises pour la comptabilité fournisseur et la comptabilité client. Cette fois, définissez le champ **Méthode** sur **Standard**. Une nouvelle transaction de réévaluation est créée d’après les taux de change actuels. Cette transaction enregistre les profits/pertes non réalisés et le compte général collectif approprié.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]