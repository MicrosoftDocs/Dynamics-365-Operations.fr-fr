---
title: Traiter les remises pour le paiement
description: Cette procédure illustre comment convertir des remises client approuvées et traitées en avoirs.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1d32d94daef570e37a1a36d948fe18cd4041e46
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966153"
---
# <a name="process-rebates-for-payment"></a>Traiter les remises pour le paiement

[!include [banner](../../includes/banner.md)]

Cette procédure illustre comment convertir des remises client approuvées et traitées en avoirs. Vous pouvez utiliser ce guide à l'aide de la société USMF fictive. La condition préalable à ce guide est d'avoir une ou plusieurs réclamations de remise qui présentent le statut Marquer. Si vous utilisez USMF, vous devez exécuter le guide « Générer et traiter les remises client » avant de lancer ce guide.


## <a name="convert-rebate-claims-to-credit-note"></a>Convertir des réclamations de remise en avoir
1. Accédez à Tous les clients.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Collecter dans le volet Actions.
5. Cliquez sur Régler les transactions.
6. Cliquez sur Fonctions.
7. Cliquez sur Programme de remises.
    * La page Remise répertorie la réclamation de remise que vous avez traitée dans la console des remises client et dont le statut est Marquer.    
8. Cliquez sur Modifier.
    * Définissez les traits de repère dans le champ Marquer pour les réclamations à inclure dans l'avoir.   
9. Cliquez sur Fonctions.
10. Cliquez sur Créer un avoir.
    * Un message vous informe qu'un journal a été validé (il s'agit du journal des consommations de comptabilité client, comme indiqué dans la page Paramètres comptabilité). Cela entraîne le déplacement du montant réel passif (crédit) vers le solde du client. Cela signifie que le compte du client est crédité et que le compte de régularisation des remises est débité.  
11. Fermez la page.
12. Cliquez sur Annuler.
    * Cela actualise la page afin de pouvoir afficher les mises à jour.  
13. Cliquez sur Collecter dans le volet Actions.
14. Cliquez sur Régler les transactions.
    * Notez qu'une transaction pour un montant négatif, représentant le montant total de remise, sans référence de facture a été ajoutée au solde client.   
15. Cliquez sur Annuler.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]