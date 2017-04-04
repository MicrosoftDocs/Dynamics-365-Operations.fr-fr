---
title: "Document simple et mise à niveau de réévaluation de la devise pour Microsoft Dynamics 365 pour la version 1611 d&quot;opérations"
description: "Certaines organisations entrent les journaux qui contiennent un document unique ayant plus d&quot;un client ou fournisseur, ces processus exécute également Ventes ou Achats réévaluation des comptes en devises. Cette rubrique décrit les tâches à ces organisations doivent suivre lorsqu&quot;elles mise à niveau vers Microsoft Dynamics 365 pour la version 1611 d&quot;opérations."
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

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Document simple et mise à niveau de réévaluation de la devise pour Microsoft Dynamics 365 pour la version 1611 d'opérations

Certaines organisations entrent les journaux qui contiennent un document unique ayant plus d'un client ou fournisseur, ces processus exécute également Ventes ou Achats réévaluation des comptes en devises. Cette rubrique décrit les tâches à ces organisations doivent suivre lorsqu'elles mise à niveau vers Microsoft Dynamics 365 pour la version 1611 d'opérations.

Procédez comme suit lors de la mise à niveau vers Microsoft Dynamics 365 pour la version 1611 d'opérations.

1.  Avant la mise à niveau vers Dynamics 365 pour les opérations, exécutez les processus de réévaluation des comptes en devises pour Ventes et Achats. Définissez ** méthode ** le champ ** date de facture **. Une transaction de réévaluation qui contrepasse la dernière réévaluation des comptes en devises. Par conséquent, les transactions en cours sont évaluées à leur devise comptable d'origine.
2.  Mise à niveau vers Dynamics 365 pour la version 1611 d'opérations.
3.  Exécutez les ventes et la réévaluation des comptes en devises Achats traite de nouveau. Ce temps, définit ** méthode ** le champ ** standard **. Une nouvelle transaction de réévaluation basé sur les taux de change actuels. Cette transaction enregistre les profits non réalisés/pertes et le compte général approprié de synthèse.



