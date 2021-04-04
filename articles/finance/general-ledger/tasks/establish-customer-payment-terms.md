---
title: Établir les conditions de paiement client
description: Cette procédure définit un escompte de règlement et une date d’échéance.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d463b3fc138e4f63bcc4f5ca3543bb6b4633176
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240712"
---
# <a name="establish-customer-payment-terms"></a>Établir les conditions de paiement client

[!include [banner](../../includes/banner.md)]

Cette procédure définit un escompte de règlement et une date d’échéance. La société fictive USMF sert d’exemple dans ce guide de tâche.

1. Accédez à **Volet de navigation > Modules > Comptabilité client > Paramétrage des paiements > Jours de paiement**. Le paramétrage des **Conditions de paiement** est partagé pour la **Comptabilité client** et la **Comptabilité fournisseur**. Si vous le définissez dans le module, il est disponible dans l’autre module également. Pour ce guide de tâche, je paramètre toutes les conditions de paiement sous **Comptabilité client**.
2. Cliquez sur **Nouveau**. Créez un jour de paiement si les conditions de paiement ont besoin d’un jour de la semaine (lundi, mardi, etc.). ou d’une date spécifique du mois (le 5, le 10, etc.). 
3. Entrez un ID dans le champ **Jour de paiement**.
4. Dans le champ **Description**, entrez une description du jour de paiement.
5. Dans le champ **Semaine/Mois**, sélectionnez Semaine ou Mois. Si vous souhaitez entrer un jour de la semaine, par exemple le lundi, sélectionnez Semaine. Si vous souhaitez entrer une date dans le mois, le 10 par exemple, sélectionnez Mois. Sélectionnez Mois pour cet exemple. 
6. Entrez une date dans le champ **Jour du mois**. La date doit être entrée sous forme de numéro, par exemple « 10 » et non en tant que « 10ème ». 
7. Cliquez sur **Enregistrer**.
8. Fermez la page.
9. Accédez à **Volet de navigation > Modules > Comptabilité client > Paramétrage des paiements > Conditions de paiement**.
10. Cliquez sur **Nouveau**. Les conditions de paiement sont utilisées pour définir la manière dont les dates d’échéance sont calculées. Le paramétrage de date d’escompte de règlement est défini dans une page indépendante. 
11. Entrez un ID dans le champ **Conditions de paiement**.
12. Entrez une description dans le champ **Description**.
13. Sélectionnez un **Mode de paiement** comme Contre remboursement, Net, Mois en cours, etc. Le mode de paiement est utilisé pour définir le début de la manière dont le solde sera calculé. Par exemple, Net est utilisé si la date d’échéance est toujours un nombre de mois ou de jours définis après la date de facture. Contre remboursement peut être utilisé lorsque le paiement est requis à la facturation, une date d’échéance n’est donc pas calculée. Sélectionnez Mois en cours pour ce guide de tâche.  
14. Sélectionnez un **Jour de paiement** si un jour de la semaine spécifique ou la date sont inclus dans le calcul. Selon vos conditions de paiement, vous pouvez entrer une quantité dans Mois ou Jours. Ou vous pouvez choisir d’ajouter **Échéancier de paiement** ou **Jour de paiement** à la fin du mode de paiement. Si la date d’échéance est toujours le 10 du mois suivant, sélectionnez 10 comme **Jour de paiement**. 
15. Cliquez sur **Enregistrer**.
16. Fermez la page.
17. Accédez à **Comptabilité client > Paramétrage des paiements > Escomptes de règlement**.
18. Cliquez sur **Nouveau**. Cette page permet de définir la manière dont la date d’escompte de règlement est calculée. 
19. Entrez un ID dans le champ **Escompte de règlement**.
20. Entrez une description dans le champ **Description**.
21. Si un escompte de règlement progressif est disponible, sélectionnez le **Code remise suivant** approprié après ce nouvel escompte de règlement.
22. Dans le champ **Jours**, saisissez le nombre de jours utilisés pour calculer la date d’escompte de règlement. Si le principe **Net** est sélectionné, le nombre de jours est ajouté à la date de facturation pour calculer la date d’escompte de règlement.  
23. Dans le champ **Pourcentage de l’escompte**, saisissez le pourcentage de l’escompte de règlement.
24. Dans **Compte principal pour les remises client**, entrez le compte principal dans lequel l’escompte de règlement validera les factures client.
25. Sélectionnez une option dans le champ **Comptes de contrepartie pour les remises**. Si vous sélectionnez « Comptes sur les lignes de facture », l’escompte de règlement va valider sur le même compte principal de dépense/d’actif sur les lignes de la facture fournisseur. Si vous sélectionnez « Utiliser le compte principal pour les factures fournisseur », l’escompte de règlement va valider sur le même compte principal que celui défini dans Compte principal pour les factures fournisseur. Pour cet exemple, sélectionnez « Utiliser le compte principal pour les factures fournisseur ». 
26. Dans **Compte principal pour les remises fournisseur**, entrez le compte principal dans lequel l’escompte de règlement validera les factures fournisseur.
27. Cliquez sur **Enregistrer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]