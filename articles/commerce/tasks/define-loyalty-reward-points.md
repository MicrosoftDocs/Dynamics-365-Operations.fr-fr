---
title: Définir les points de récompense de fidélité
description: Cette procédure décrit la définition des points de récompense de fidélité.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailLoyaltyRewardPoints
ms.openlocfilehash: 9acd1429d17393f19a5e059b90a48b0b103535d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268890"
---
# <a name="define-loyalty-reward-points"></a>Définir les points de récompense de fidélité

[!include [banner](../includes/banner.md)]

Cette procédure décrit la définition des points de récompense de fidélité. Vous devez paramétrer les points de récompense de fidélité avant de paramétrer un programme de fidélité. La société fictive USRT sert d’exemple dans cette procédure.

1. Accédez à Commerce et vente au détail > Clients > Fidélité > Points de récompense de fidélité.
2. Cliquez sur Nouveau.
3. Dans le champ ID de point de récompense, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Type de point de récompense, sélectionnez une option.
    * Sélectionnez Quantité si vous souhaitez arrondir les points de récompense à l’entier le plus proche. Sélectionnez Montant si vous souhaitez arrondir les points de récompense en fonction des règles d’arrondi de devise. Si vous sélectionnez Quantité, ignorez l’étape suivante de cette procédure.  
6. Tapez une valeur dans le champ Devise.
    * Pour les points de récompense de type Montant, tous les points émis utilisent la devise sélectionnée. Pour les points de récompense de type Quantité, ce champ ne s’applique pas. Ignorez cette étape.  
7. Activez ou désactivez la case à cocher Remboursable.
8. Dans le champ Rembourser le classement, saisissez un nombre.
    * Le classement de remboursement est utilisé lorsque deux ou plusieurs points de récompense remboursables peuvent être utilisés pour payer les produits. Si les deux points de récompense ont le même classement de remboursement, celui qui doit réduire le nombre de points est utilisé.  
9. Dans le champ Valeur - durée avant expiration, saisissez un nombre.
    * Les points de récompense expirent le nombre spécifié de jours, mois ou années après l’émission des points. La valeur « 0 » signifie que les points de récompense de fidélité n’expirent jamais.  
10. Dans le champ Unité - durée avant expiration, sélectionnez une option.
11. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
