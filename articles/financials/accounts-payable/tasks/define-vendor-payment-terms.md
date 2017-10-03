--- 
title: "Définir les conditions de paiement fournisseur"
description: "Définissez les conditions de paiement pour les factures fournisseur."
author: abruer
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
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: cbac3b27c25377abff341c4bf259e553c14a4ae8
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="define-vendor-payment-terms"></a>Définir les conditions de paiement fournisseur

[!include[task guide banner](../../includes/task-guide-banner.md)]

Définissez les conditions de paiement pour les factures fournisseur. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Conditions de paiement.
2. Cliquez sur Nouveau.
    * La page Conditions de paiement est utilisée pour définir la manière dont la date d'échéance est calculée. Elle ne permet pas de définir la manière dont la date d'escompte de règlement est calculée.  
3. Tapez une valeur dans le champ Conditions de paiement.
4. Dans le champ Description, entrez une valeur.
5. Entrez un nombre dans le champ Jour.
    * Le nombre entré ici sera ajouté à la date d'échéance ou à la fin de la période identifiée dans le mode de paiement. Par exemple, si vous sélectionnez Net, le nombre sera ajouté à la date d'échéance. Si vous sélectionnez Mois en cours, le nombre sera ajouté au dernier jour du mois actuel pour calculer la date d'échéance.  
6. Cliquez sur Enregistrer.
7. Fermez la page.
8. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Escomptes de règlement.
9. Cliquez sur Nouveau.
10. Entrez un ID dans le champ Escompte de règlement.
11. Dans le champ Description, entrez une valeur.
12. Si le fournisseur offre une remise progressive, sélectionnez l'escompte de règlement suivant une fois que l'escompte actuel a expiré.
13. Fermez la page.
14. Entrez un nombre dans le champ Jour.
    * La quantité entrée dans le champ Jours sera utilisée pour calculer la date d'escompte de règlement, selon l'option sélectionnée dans champ Net/actuel. Si Net est sélectionné, la quantité est ajoutée à la date de facturation pour déterminer la date d'escompte de règlement. Si Mois en cours est sélectionné, la quantité est ajoutée à la fin du mois en cours pour déterminer la date d'escompte de règlement.  
15. Entrez le pourcentage de l'escompte de règlement dans le champ Remise. 
16. Entrez le compte principal dans lequel l'escompte de règlement sera validé pour les factures client.
17. Entrez le compte principal dans lequel l'escompte de règlement sera validé pour les factures fournisseur.
    * Si « Comptes de contrepartie pour les remises » est défini pour utiliser le compte principal pour la remise fournisseur, le compte principal est utilisé.  Si l'option est définie sur Comptes sur les lignes de facture, l'escompte de règlement sera validé sur les comptes de dépense/d'actif sur les lignes de la facture.  
18. Cliquez sur Enregistrer.

