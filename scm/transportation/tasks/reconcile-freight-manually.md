--- 
title: Rapprocher manuellement les frais de transport
description: "Cette procédure indique comment rapprocher manuellement les frais de transport."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 28de4c720cd771f476f379d925e9500e41482aa6
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="reconcile-freight-manually"></a>Rapprocher manuellement les frais de transport

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment rapprocher manuellement les frais de transport. Cette opération est généralement réalisée par un coordinateur transport. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.


## <a name="select-a-load-to-reconcile"></a>Sélectionner une charge à rapprocher
1. Accédez à Gestion du transport > Planning > Console de planification des charges.
2. Désactivez la case à cocher Masquer les éléments expédiés et reçus. 
3. Dans la liste, sélectionnez la charge dont l'ID de charge est 00006.

## <a name="create-a-carrier-invoice"></a>Créer une facture transporteur
    * Si vous rapprochez manuellement les frais de transport et ne recevez pas automatiquement les factures du transporteur, vous pouvez créer une facture sur la base de la facture des frais de transport.  
1. Cliquez sur Informations associées.
2. Cliquez sur Détails de la facture des frais de transport.
3. Cliquez sur Générer la facture de transport.
4. Tapez une valeur dans le champ Facture.
5. Cliquez sur OK.

## <a name="reconcile-the-invoice"></a>Rapprocher la facture
    * Lorsque vous rapprochez une facture du transporteur et une facture des frais de transport, cette procédure est effectuée ligne par ligne.  
1. Cliquez sur Mettre en correspondance les facture des frais de transport et les factures.
2. Développez la section Détails de la facture.
3. Développez la section Détails de la facture des frais de transport non rapprochés.
4. Dans la liste, marquer la ligne sélectionnée.
5. Cliquez sur Correspondance.
6. Développez la section Détails de la facture des frais de transport rapprochés.

## <a name="submit-the-invoice-for-approval"></a>Soumettre la facture pour approbation
1. Cliquez sur Soumettre pour approbation.
2. Fermez la page.
3. Désactivez la case à cocher Masquer l'approbation. 
4. Cliquez sur Journaux des factures fournisseur.
5. Cliquez pour suivre le lien dans le champ Numéro du journal de référence.
6. Cliquez sur Lignes.

