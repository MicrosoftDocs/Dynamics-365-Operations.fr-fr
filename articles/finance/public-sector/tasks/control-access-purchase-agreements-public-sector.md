---
title: Contrôler l’accès aux contrats d’achat dans le secteur public
description: Vous pouvez vous assurer que seuls les départements approuvés peuvent accéder à un contrat d’achat.
author: twheeloc
ms.date: 02/14/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementFinDimensionAccess_PSN
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.search.industry: Public sector
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95f6b5133d7bae1a93a709322e11ee1632aa4985
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119442"
---
# <a name="control-access-to-purchase-agreements-in-the-public-sector"></a>Contrôler l’accès aux contrats d’achat dans le secteur public

[!include [banner](../../includes/banner.md)]

Vous pouvez vous assurer que seuls les départements approuvés peuvent accéder à un contrat d’achat. Vous pouvez également limiter le montant que chaque département peut dépenser dans le cadre du contrat d’achat. Pour ce faire, la structure de compte et les dimensions financières pour l’accès au département doivent être définies sur la page **Paramètres de la comptabilité fournisseur**. Cette procédure a été créée pour les organisations du secteur public français, en utilisant les données de la société fictive PSUS dans la partition du secteur public.

1. Accédez à **Comptabilité fournisseur > Commandes fournisseur > Contrats d’achat**.
2. Dans la liste, sélectionnez le contrat d’achat auquel vous souhaitez contrôler l’accès.
3. Dans le **volet Action**, cliquez sur **Contrat d’achat**.
4. Cliquez sur **Accès du département**.
5. Cliquez sur **Nouveau**.
6. Dans le champ **Département**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, sélectionnez la dimension financière pour un département qui a accès à ce contrat d’achat.
8. Dans le champ **Montant autorisé**, entrez le montant total que ce département est autorisé à débloquer dans le cadre de ce contrat d’achat.
    * Ajoutez des départements supplémentaires jusqu’à ce que tous les départements autorisés aient été ajoutés au contrat d’achat.  
9. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
