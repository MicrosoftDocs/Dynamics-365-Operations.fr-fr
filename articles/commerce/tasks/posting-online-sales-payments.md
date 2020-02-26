---
title: Validation des ventes et des paiements en ligne
description: Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bf7f72be22539271649aa7f5541735b3d24dab66
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022504"
---
# <a name="posting-of-online-sales-and-payments"></a>Validation des ventes et des paiements en ligne

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.

La validation des ventes et des paiements en ligne est un processus en deux étapes.

- Extraction des données de transaction du commerce en ligne au siège social.
- Synchronisation des commandes pour créer des commandes client au siège social.

L'extraction des données de transaction en ligne peut se faire soit manuellement en exécutant la tâche P, soit en créant un traitement par lots récurrent.

### <a name="manually-running-the-p-job"></a>Exécution manuelle de la tâche P

1. Accédez à Tous les espaces de travail > Informatique Retail et Commerce.
2. Cliquez sur Programme de distribution.
3. Sélectionnez P-0001.
4. Ajustez les groupes de base de données des canaux, le cas échéant.
5. Cliquez sur Exécuter maintenant.
6. Cliquez sur Oui.

### <a name="scheduling-a-recurring-p-job"></a>Planification d'une tâche P récurrente

1. Accédez à Tous les espaces de travail > Informatique Retail et Commerce.
2. Cliquez sur Programme de distribution.
3. Sélectionnez P-0001.
4. Cliquez sur Créer un traitement par lots.
5. Cliquez sur Exécuter à l'arrière-plan.
5. Activez le traitement par lots.
6. Cliquez sur Répétition.
7. Sélectionnez l'option Pas de date de fin.
8. Dans le champ Nombre, saisissez l'intervalle entre les exécutions en minutes. Généralement ce serait 5-10.
9. Cliquez sur OK.
10. Cliquez sur OK.

Les commandes peuvent être synchronisées soit en exécutant manuellement la tâche « Synchroniser des commandes », soit en créant un traitement par lots récurrent.

### <a name="manually-running-order-synchronization"></a>Exécution d'une synchronisation manuelle d'une commande 

Suivez ces étapes pour exécuter manuellement la tâche « Synchroniser les commandes » une seule fois.

1. Accédez à Tous les espaces de travail > Finances du magasin.
2. Cliquez sur Synchroniser les commandes.
3. Dans le champ Hiérarchie d'organisation, sélectionnez Magasins par région.
    * Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.  
    * Cliquez sur la flèche pour ajouter votre sélection.  
4. Cliquez sur l'onglet Exécuter à l'arrière-plan.
5. Désactiver le traitement par lots
6. Cliquez sur Répétition.
7. Sélectionner l'option Fin après le
8. Dans le champ Fin après le, saisissez 1.
9. Cliquez sur OK.
10. Cliquez sur OK.

### <a name="scheduling-recurring-order-synchronization"></a>Planification de la synchronisation des commandes récurrentes

Cette procédure décrit la configuration et l'exécution d'un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Tous les espaces de travail > Finances du magasin.
2. Cliquez sur Synchroniser les commandes.
3. Dans le champ Hiérarchie d'organisation, sélectionnez Magasins par région.
    * Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.  
    * Cliquez sur la flèche pour ajouter votre sélection.  
4. Cliquez sur l'onglet Exécuter à l'arrière-plan.
5. Activer le traitement par lots
6. Cliquez sur Répétition.
7. Sélectionnez l'option Pas de date de fin.
8. Dans le champ Nombre, saisissez l'intervalle entre les exécutions en minutes. Généralement ce serait 2-20
9. Cliquez sur OK.
10. Cliquez sur OK.

## <a name="data-entities-involved-in-the-process"></a>Entités des données impliquées dans le processus

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans
