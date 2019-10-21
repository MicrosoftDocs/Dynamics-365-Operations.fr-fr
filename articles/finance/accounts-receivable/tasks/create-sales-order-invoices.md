---
title: Créer des factures de commande client
description: Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a41524c773284812aa6eebddcd832c78bd29166
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177765"
---
# <a name="create-sales-order-invoices"></a>Créer des factures de commande client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ce guide de tâche décrit la facturation d'une commande client, notamment la fusion des factures et le traitement par lots. La société fictive USMF sert d'exemple dans cette procédure.


## <a name="create-an-invoice-from-a-sales-order"></a>Créer une facture à partir d'une commande client
1. Accédez au **volet Navigation > Modules > Comptabilité client > Commandes > Commandes client expédiées mais pas facturées**.
2. Sélectionnez une commande client dans la liste. 
3. Dans le **volet Actions**, cliquez sur **Facture > Générer > Facture**. Notez que cette commande client a plusieurs bons de livraison associés. Elle indique uniquement le mot <multiple> au lieu du numéro de bon de livraison.  
4. Développez la section **Paramètres**.
    - La validation doit être définie sur Oui pour valider la facture. Vous pouvez également désactiver la validation et simplement imprimer la facture. Toutefois, vous pouvez obtenir le même résultat en créant une facture pro forma au lieu d'une facture.  
    - Cette option est utilisée pour les traitements par lots. La requête est exécutée lorsque le traitement par lots est exécuté.
5. Sélectionnez Après dans le champ **Imprimer**.
6. Sélectionnez **Oui** en regard de **Imprimer la facture**. La gestion de l'impression peut imprimer plusieurs copies de la facture et soumettre la facture par e-mail sous forme de fichier PDF.  
7. Sélectionnez Résumer dans le champ **Imprimer les frais**.
8. Dans le champ **Vérifier la limite de crédit**, sélectionnez Solde.
9. Cliquez sur **Annuler**.

## <a name="combine-orders-into-a-single-invoice"></a>Combiner les commandes en une seule facture
1. Allez dans **Volet de navigation > Modules > Comptabilité client > Commandes > Toutes les commandes client**.
2. Recherchez un client ayant plusieurs factures en cours.
3. Sélectionnez plusieurs commandes client en cours du même client.
4. Dans le **volet Actions**, cliquez sur **Facture > Générer > Facture**.
5. Développez la section **Paramètres**.
6. Dans le champ **Quantité**, sélectionnez 'Tout'. Notez qu'il existe deux factures répertoriées dans la vue d'ensemble. À présent, nous allons les fusionner dans une seule facture.  
7. Sélectionnez Compte de facturation dans le champ **Mise à jour récapitulative pour** .
8. Cliquez sur **Organiser** pour fusionner les commandes client dans une seule facture. Les deux commandes client sont désormais fusionnées dans une seule facture.   
9. Cliquez sur **Annuler**.
10. Cliquez sur **Oui**.

## <a name="post-invoices-in-a-batch"></a>Valider les factures dans un traitement par lots
1. Accédez à **Volet de navigation > Modules > Comptabilité client > Factures > Facturation par traitement par lots > Facture**.
2. Cliquez sur **Sélectionner**.
3. Cliquez sur **OK**.
4. Cliquez sur **Lots**.
5. Sélectionnez sur **Oui** dans **Traitement par lots**.
6. Cliquez sur **Répétition**.
7. Sélectionnez **Jours**.
8. Cliquez sur **OK**.
9. Cliquez sur **OK**.
10. Cliquez sur **Annuler**.
11. Cliquez sur **Oui**.

