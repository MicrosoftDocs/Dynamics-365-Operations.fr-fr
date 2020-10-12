---
title: Enregistrer les commissions sur les ventes
description: Cette rubrique explique comment les commissions sur les ventes sont calculées et enregistrées.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83cea952f4883d49621a9f7d16440927a8eddb98
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830556"
---
# <a name="register-sales-commissions"></a>Enregistrer les commissions sur les ventes

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment les commissions sur les ventes sont calculées et enregistrées. Vous pouvez exécuter cette procédure dans la société fictive de démonstration USMF ou utiliser vos propres données. Avant de lancer ce guide, exécutez le guide appelé « Configurer les règles de commission sur les ventes » pour vous assurer que vous disposez de tout le paramétrage nécessaire au calcul de la commission.

Prenez note des numéros de client et d'article que vous avez choisis pour le processus de commission et utilisez-les quand il vous sera demandé de créer une commande client dans ce guide.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Facturer une commande client qui qualifie un commercial pour une commission
1. Dans le volet de navigation, accédez à **Volet de navigation > Modules > Ventes et marketing > Commandes client > Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte client**, sélectionnez l'enregistrement souhaité dans le menu déroulant.
4. Cliquez sur **OK**.
5. Dans le volet Actions, sélectionnez **Options**.
6. Sélectionnez **Modifier la vue**.
7. Sélectionnez **Vue de l'en-tête**.
8. Développez la section **Paramétrage**.

    - La valeur dans le champ **Groupe de ventes** représente un groupe avec un ou plusieurs commerciaux lui étant affectés. Les personnes du groupe sont celles qui reçoivent les commissions à la facturation de la commande, selon les taux prédéfinis et la répartition.   
    - La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.  
    - Le groupe de ventes est également copié dans la ligne de commande client. Vous pouvez le modifier de sorte qu'il diffère de celui de l'en-tête et/ou des lignes.  
    - La valeur dans le champ **Groupe de commissions** représente un groupe que vous avez créé pour un ou plusieurs clients avec l'objectif de suivre les commissions.   
    - La valeur est copiée de la fiche client, mais vous pouvez la modifier si vous le souhaitez.   

9. Dans le volet Actions, sélectionnez **Options**.
10. Sélectionnez **Modifier la vue**.
11. Sélectionnez **Vue de ligne**.
12. Dans le menu déroulant du champ **Numéro d’article**, sélectionnez l'article à paramétrer pour les commissions. 
13. Entrez un nombre dans le champ **Quantité**. Prenez note du Montant HT de la ligne. Il représente le produit de la vente, qui dans cet exemple sert de base au calcul de la commission.  
14. Sélectionnez **Enregistrer**.
15. Dans le volet Actions, sélectionnez **Facture**.
16. Sélectionnez **Facture**.
17. Développez la section **Paramètres**.
18. Sélectionnez **Tout** dans le champ **Quantité**.
19. Sélectionnez **Oui** dans le champ **Validation**.
20. Sélectionnez **OK**, puis sélectionnez **OK** dans le prochain volet. La validation de la transaction peut prendre une minute environ. Laissez le traitement s'achever sans fermer la page.  

## <a name="review-the-registered-sales-commissions"></a>Examiner les commissions sur les ventes enregistrées
1. Dans le volet Actions, sélectionnez **Facture**, puis sélectionnez à nouveau **Facture**.
2. Dans le volet Actions, sélectionnez **Facture**, puis sélectionnez à nouveau **Transactions de commission**.

    - L'onglet **Vue d'ensemble** présente des lignes représentant les montants de commission à payer aux commerciaux associés à la commande client facturée. Examinons les détails.  
    - Si vous avez utilisé le guide « Configurer les règles de **commission sur les ventes** » pour définir le groupe de commissions de vente, deux commerciaux vont recevoir une commission et celle-ci est divisée équitablement entre eux.  
    - Dans cet exemple, le montant total de la commission est calculé comme un pourcentage du produit de la vente (montant HT de la ligne de commande).  
3. Fermez la page.
4. Sélectionnez **N° document**. Vous pouvez examiner les transactions du N° document pour les montants de commission qui ont été validés dans les comptes prédéfinis de dépense et de commission à payer.  

