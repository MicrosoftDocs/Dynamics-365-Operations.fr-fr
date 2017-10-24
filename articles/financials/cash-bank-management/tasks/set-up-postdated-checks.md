--- 
title: "Paramétrage de chèques postdatés"
description: "Cette rubrique explique comment indiquer s'il faut valider les écritures de journal pour les chèques postdatés et quels journaux de validation utiliser pour les écritures de compensation et les paiements fournisseur."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d83713f9d54b396a10894995024ac1c8dd47a6f1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-postdated-checks"></a>Paramétrage de chèques postdatés

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment indiquer s'il faut valider les écritures de journal pour les chèques postdatés et quels journaux de validation utiliser pour les écritures de compensation et les paiements fournisseur. Vous pouvez également spécifier les comptes de compensation pour les chèques émis, les chèques reçus et la retenue à la source. Les chèques postdatés sont émis à des fins d'émission ou de réception de paiements à une date future. Vous pouvez indiquer si le chèque doit être pris en compte dans les registres comptables avant sa date d'échéance.



Le rôle de cette procédure Trésorier. La société fictive USMF sert d'exemple dans cette procédure.


## <a name="set-up-postdated-checks"></a>Paramétrage de chèques postdatés
1. Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.
2. Cliquez sur l'onglet Chèques postdatés.
3. Activez ou désactivez la case à cocher Activer les chèques postdatés.
4. Activez ou désactivez les écritures de journal de validation pour la case à cocher des chèques postdatés.
5. Dans le champ Compensation du compte pour des émissions de chèques, indiquez les valeurs souhaitées.
6. Dans le champ Compensation du compte pour des réceptions de chèques, indiquez les valeurs souhaitées.
7. Dans le champ Journal des opérations diverses pour les entrées de compensation, tapez une valeur.
8. Dans le champ Transférer les chèques postdatés vers ce journal des paiements fournisseur, tapez une valeur.
9. Dans le champ Montant de compensation de retenue à la source, indiquez les valeurs souhaitées.
10. Cliquez sur Enregistrer.
11. Fermez la page.
12. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.
13. Cliquez sur Nouveau.
14. Tapez une valeur dans le champ Mode de paiement.
15. Sélectionnez l'option Validation de la compensation des chèques postdatés pour indiquer que le montant du chèque est validé dans un compte de compensation.
16. Sélectionnez Banque dans le champ Type de compte.
    * Le compte de contrepartie du mode de paiement est une banque.  
17. Dans le champ Compte de paiement, indiquez les valeurs souhaitées.
    * Sélectionnez le compte bancaire utilisé pour déduire le montant de la facture.  
18. Fermez la page.
19. Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.
20. Cliquez sur Nouveau.
21. Tapez une valeur dans le champ Mode de paiement.
22. Sélectionnez l'option Validation de la compensation des chèques postdatés pour indiquer que le montant du chèque est validé dans un compte de compensation.
23. Sélectionnez Banque dans le champ Type de compte.
    * Le compte de contrepartie du mode de paiement est une banque.  
24. Dans le champ Compte de paiement, indiquez les valeurs souhaitées.
    * Sélectionnez le compte bancaire utilisé pour déduire le montant de la facture.  
25. Fermez la page.


