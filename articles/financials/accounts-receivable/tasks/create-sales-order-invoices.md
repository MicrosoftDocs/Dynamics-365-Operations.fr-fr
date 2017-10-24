--- 
title: "Créer des factures de commande client"
description: "Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b72d5b283f9401d358ee68f4650c486ebb2fd7d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-order-invoices"></a>Créer des factures de commande client

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots. La société fictive USMF sert d'exemple dans cette procédure.


## <a name="create-an-invoice-from-a-sales-order"></a>Créer une facture à partir d'une commande client
1. Allez dans Comptabilité client > Commandes > Commandes client expédiées mais pas facturées.
2. Sélectionnez une commande client dans la liste. 
3. Dans le volet Actions, cliquez sur Facture.
4. Cliquez sur Facture.
    * Notez que cette commande client a plusieurs bons de livraison associés. Elle indique uniquement le mot <multiple> au lieu du numéro de bon de livraison.  
5. Développez la section Paramètres.
    * La validation doit être définie sur Oui pour valider la facture. Vous pouvez également désactiver la validation et simplement imprimer la facture. Toutefois, vous pouvez obtenir le même résultat en créant une facture pro forma au lieu d'une facture.  
    * Cette option est utilisée pour les traitements par lots. La requête est exécutée lorsque le traitement par lots est exécuté.    
6. Sélectionnez Après dans le champ Imprimer.
7. Sélectionnez Oui en regard de Imprimer la facture.
    * La gestion de l'impression peut imprimer plusieurs copies de la facture et soumettre la facture par e-mail sous forme de fichier PDF.  
8. Sélectionnez Résumer dans le champ Imprimer les frais.
9. Sélectionnez Solde dans le champ Vérifier la limite de crédit.
10. Cliquez sur Annuler.

## <a name="combine-orders-into-a-single-invoice"></a>Combiner les commandes en une seule facture
1. Accédez à Comptabilité client > Commandes > Toutes les commandes client.
2. Recherchez un client ayant plusieurs factures en cours.
3. Sélectionnez une commande client en cours.
4. Sélectionnez une autre commande client en cours pour le même client.
5. Dans le volet Actions, cliquez sur Facture.
6. Cliquez sur Facture.
7. Développez la section Paramètres.
8. Sélectionnez « Tout » dans le champ Quantité.
    * Notez qu'il existe deux factures répertoriées dans la vue d'ensemble. À présent, nous allons les fusionner dans une seule facture.  
9. Sélectionnez Compte de facturation dans le champ Mise à jour récapitulative pour.
10. Cliquez sur Organiser pour fusionner les commandes client dans une seule facture.
    * Les deux commandes client sont désormais fusionnées dans une seule facture.   
11. Cliquez sur Annuler.
12. Cliquez sur Oui.

## <a name="post-invoices-in-a-batch"></a>Valider les factures dans un traitement par lots
1. Allez dans Comptabilité client > Factures > Facturation par traitement par lots > Facture.
2. Cliquez sur Sélectionner.
3. Cliquez sur OK.
4. Cliquez sur Traitement par lots.
5. Cliquez sur Oui pour activer le traitement par lots.
6. Cliquez sur Répétition.
7. Sélectionner Jours
8. Cliquez sur OK.
9. Cliquez sur OK.
10. Cliquez sur Annuler.
11. Cliquez sur Oui.


