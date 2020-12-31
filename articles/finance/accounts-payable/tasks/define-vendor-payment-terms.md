---
title: Définir les conditions de paiement fournisseur
description: Cette rubrique explique comment paramétrer des conditions de paiement pour les factures fournisseur.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7e6778f61a9367399e4b71d5b2bb2459c09ba508
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443010"
---
# <a name="define-vendor-payment-terms"></a>Définir les conditions de paiement fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer des conditions de paiement pour les factures fournisseur. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à **Volet de navigation > Modules > Comptabilité fournisseur > Paramétrage des paiements > Conditions de paiement**.
2. Sélectionnez **Nouveau**. La page Conditions de paiement est utilisée pour définir la manière dont la date d’échéance est calculée. Elle ne permet pas de définir la manière dont la date d’escompte de règlement est calculée.  
3. Tapez une valeur dans le champ **Conditions de paiement**.
4. Tapez une valeur dans le champ **Description**.
5. Entrez un nombre dans le champ **Jours**. Le nombre entré ici sera ajouté à la date d’échéance ou à la fin de la période identifiée dans le mode de paiement. Par exemple, si vous sélectionnez **Net**, le nombre sera ajouté à la date d’échéance. Si vous sélectionnez **Mois en cours**, le nombre sera ajouté au dernier jour du mois actuel pour calculer la date d’échéance.  
6. Sélectionnez **Enregistrer**.
7. Fermez la page.
8. Accédez à **Comptabilité fournisseur > Paramétrage des paiements > Escomptes de règlement**.
9. Sélectionnez **Nouveau**.
10. Entrez un ID dans le champ **Escompte de règlement**.
11. Tapez une valeur dans le champ **Description**.
12. Si le fournisseur offre une remise progressive, sélectionnez l’escompte de règlement suivant une fois que l’escompte actuel a expiré.
13. Fermez la page.
14. Entrez un nombre dans le champ **Jours**. La quantité entrée dans le champ **Jours** sera utilisée pour calculer la date d’escompte de règlement, selon l’option sélectionnée dans champ **Net/actuel**. Si **Net** est sélectionné, la quantité est ajoutée à la date de facturation pour déterminer la date d’escompte de règlement. Si **Mois en cours** est sélectionné, la quantité est ajoutée à la fin du mois en cours pour déterminer la date d’escompte de règlement.  
15. Entrez le pourcentage de l’escompte de règlement dans le champ **Remise**. 
16. Saisissez le compte principal sur lequel l’escompte de règlement sera imputé pour les factures clients, puis le compte principal sur lequel l’escompte de règlement sera imputé pour les factures fournisseurs. Si **Comptes de contrepartie pour les remises** est défini pour **utiliser le compte principal pour la remise fournisseur**, le compte principal est utilisé. Si l’option est définie sur **Comptes sur les lignes de facture**, l’escompte de règlement sera validé sur les comptes de dépense/d’actif sur les lignes de la facture.  
17. Sélectionnez **Enregistrer**.

