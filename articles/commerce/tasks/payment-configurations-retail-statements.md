---
title: Configurations de paiements pour les relevés de vente au détail
description: Cette procédure illustre les configurations de modes de paiement des magasins de commerce qui affectent la création et la validation des relevés de vente au détail.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 390ccdfde3f9bb93770d456af7532a42e81955a1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412306"
---
# <a name="payment-configurations-for-retail-statements"></a>Configurations de paiements pour les relevés de vente au détail

[!include [banner](../includes/banner.md)]

Cette procédure illustre les configurations de modes de paiement des magasins de commerce qui affectent la création et la validation des relevés de vente au détail.

La société fictive USRT sert d'exemple dans cet enregistrement.

1. Accédez à Retail et Commerce > Canaux > Magasins > Tous les magasins.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le volet Actions, cliquez sur Paramétrer.
5. Cliquez sur Modes de paiement.
6. Développez ou réduisez la section Validation.
7. Cliquez sur Modifier.
    * Sélectionnez si les montants reçus pour ce mode de paiement doivent être validés dans un compte général ou sur un compte bancaire.  
    * Sélectionnez le compte dans lequel valider les montants reçus par le biais de ce mode de paiement.  
    * Sélectionnez un compte pour valider les différences possibles entre le montant total de la transaction reçu et le montant compté pour ce mode de paiement.  
    * Ce champ vous permet de spécifier un montant à contrôler lorsque le montant de la différence doit être validé dans un autre compte de différence. Vous pouvez utiliser cette option pour effectuer le suivi des grandes différences.  
    * Sélectionnez un compte pour la validation des différences possibles entre le montant total de la transaction reçu et le montant compté, lorsqu'il dépasse la valeur définie dans le champ « Montant de différence maximale ».  
    * Sélectionnez « Oui » pour valider les montants de remise en banque dans un compte distinct.  
    * Ce champ vous permet de sélectionner si les montants de remise en banque doivent être validés dans un compte général ou sur un compte bancaire.  
    * Sélectionnez le compte sur lequel valider les montants de remise en banque.  
    * Sélectionnez le type de transaction bancaire à utiliser lors de la validation de montants de remise en banque sur le compte bancaire.  
    * Sélectionnez « Oui » pour valider les montants de mise en coffre-fort sur un compte distinct.  
    * Sélectionnez si les montants de mise en coffre-fort doivent être validés sur le compte général ou le compte bancaire.  
    * Sélectionnez le compte sur lequel valider les montants de mise en coffre-fort.  
8. Cliquez sur Enregistrer.

