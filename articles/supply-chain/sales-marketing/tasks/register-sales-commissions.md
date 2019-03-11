---
title: Enregistrer les commissions sur les ventes
description: Cette procédure vous montre comment les commissions sur les ventes sont calculées et enregistrées.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c39b2fcf521106dfb58466bc45a316c0b506345
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355148"
---
# <a name="register-sales-commissions"></a>Enregistrer les commissions sur les ventes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous montre comment les commissions sur les ventes sont calculées et enregistrées. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Avant de lancer ce guide, exécutez le guide appelé « Configurer les règles de commission sur les ventes » pour vous assurer que vous disposez de tout le paramétrage nécessaire au calcul de la commission.

Prenez note des numéros de client et d'article que vous avez choisis pour le processus de commission et utilisez-les quand il vous sera demandé de créer une commande client dans ce guide.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Facturer une commande client qui qualifie un commercial pour une commission
1. Allez dans Ventes et marketing > Commandes client > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur OK.
7. Dans le volet Actions, cliquez sur Options.
8. Cliquez sur Changer de vue.
9. Cliquez sur Vue de l'en-tête.
10. Développez la section Paramétrage.
    * La valeur dans le champ Groupe de ventes représente un groupe avec un ou plusieurs commerciaux lui étant affectés. Les personnes du groupe sont celles qui reçoivent les commissions à la facturation de la commande, selon les taux prédéfinis et la répartition.   La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.  Le groupe de ventes est également copié dans la ligne de commande client. Vous pouvez le modifier de sorte qu'il diffère de celui de l'en-tête et/ou des lignes.  
    * La valeur dans le champ Groupe de commissions représente un groupe que vous avez créé pour un ou plusieurs clients avec l'objectif de suivre les commissions.   La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.   
11. Dans le volet Actions, cliquez sur Options.
12. Cliquez sur Changer de vue.
13. Cliquez sur Affichage des lignes.
14. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, sélectionnez l'article que vous avez paramétré pour des commissions. 
16. Dans le champ Quantité, entrer un numéro.
    * Prenez note du Montant HT de la ligne. Il représente le produit de la vente, qui dans cet exemple sert de base au calcul de la commission.  
17. Cliquez sur Enregistrer.
18. Dans le volet Actions, cliquez sur Facture.
19. Cliquez sur Facture.
20. Développez la section Paramètres.
21. Sélectionnez « Tout » dans le champ Quantité.
22. Sélectionnez Oui dans le champ Validation.
23. Cliquez sur OK.
24. Cliquez sur OK.
    * La validation de la transaction peut prendre une minute environ. Laissez le traitement s'achever sans fermer la page.  

## <a name="review-the-registered-sales-commissions"></a>Examiner les commissions sur les ventes enregistrées
1. Dans le volet Actions, cliquez sur Facture.
2. Cliquez sur Facture.
3. Dans le volet Actions, cliquez sur Facture.
4. Cliquez sur Transactions de commission.
    * L'onglet Vue d'ensemble présente des lignes représentant les montants de commission à payer aux commerciaux associés à la commande client facturée. Examinons les détails.     
    * Si vous avez utilisé le guide « Configurer les règles de commission sur les ventes » pour définir le groupe de commissions de vente, deux commerciaux vont recevoir une commission et celle-ci est divisée équitablement entre eux.  
    * Dans cet exemple, le montant total de la commission est calculé comme un pourcentage du produit de la vente (montant HT de la ligne de commande).   
5. Fermez la page.
6. Cliquez Document.
    * Vous pouvez examiner les transactions du N° document pour les montants de commission qui ont été validés dans les comptes prédéfinis de dépense et de commission à payer.  

