---
title: Contrôler l’accès aux contrats d’achat dans le secteur public
description: Vous pouvez vous assurer que seuls les départements approuvés peuvent accéder à un contrat d’achat.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementFinDimensionAccess_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eb5223d4c16d577ce1c65b140514f4956d6d7304
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968234"
---
# <a name="control-access-to-purchase-agreements-in-the-public-sector"></a>Contrôler l’accès aux contrats d’achat dans le secteur public

[!include [banner](../../includes/banner.md)]

Vous pouvez vous assurer que seuls les départements approuvés peuvent accéder à un contrat d’achat. Vous pouvez également limiter le montant que chaque département peut dépenser dans le cadre du contrat d’achat. Pour ce faire, la structure de compte et les dimensions financières pour l’accès au département doivent être définies dans l’écran Paramètres de la comptabilité fournisseur. Cette procédure a été créée pour les organisations du secteur public français, en utilisant les données de la société fictive PSUS dans la partition du secteur public.

1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Contrats d’achat.
2. Dans la liste, sélectionnez le contrat d’achat auquel vous souhaitez contrôler l’accès.
3. Dans le volet Action, cliquez sur Contrat d’achat.
4. Cliquez sur Accès du département.
5. Cliquez sur Nouveau.
6. Cliquez sur le bouton de liste déroulante pour ouvrir la recherche dans le champ Département.
7. Dans la liste, sélectionnez la dimension financière pour un département qui a accès à ce contrat d’achat.
8. Dans le champ Montant autorisé, entrez le montant total que ce département est autorisé à débloquer dans le cadre de ce contrat d’achat.
    * Ajoutez des départements supplémentaires jusqu’à ce que tous les départements autorisés aient été ajoutés au contrat d’achat.  
9. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]