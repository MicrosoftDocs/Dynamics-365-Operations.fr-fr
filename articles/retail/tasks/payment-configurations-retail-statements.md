--- 
title: "Configurer des paramètres de mode de paiement qui affectent les relevés de vente au détail"
description: "Cette procédure illustre les configurations de modes de paiement des magasins de vente au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ba21db9ee97dc4d851c77a906927ef513940b743
ms.contentlocale: fr-fr
ms.lasthandoff: 08/08/2018

---
# <a name="configure-payment-method-settings-that-affect-retail-statements"></a>Configurer des paramètres de mode de paiement qui affectent les relevés de vente au détail

[!include [task guide banner](../includes/task-guide-banner.md)]

Cette procédure illustre les configurations de modes de paiement des magasins de vente au détail qui affectent la manière dont les relevés de vente au détail sont créés et validés.

La société fictive USRT sert d'exemple dans cet enregistrement.

1. Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.
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


