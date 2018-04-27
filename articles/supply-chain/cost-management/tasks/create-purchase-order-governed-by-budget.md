--- 
title: "Créer une commande fournisseur régie par budget"
description: "Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7cc024caa54db6629a1e573df295fe8333996647
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-purchase-order-governed-by-budget"></a>Créer une commande fournisseur régie par budget

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée. Cet enregistrement utilise la société fictive USMF.


## <a name="review-the-budget-control-configuration"></a>Examiner la configuration du contrôle budgétaire
1. Accédez à Budgétisation > Paramétrage > Contrôle budgétaire > Configuration du contrôle budgétaire.
2. Cliquez sur l'onglet Fonds budgétaires disponibles.
3. Cliquez sur l'onglet Documents et journaux.
4. Cliquez sur l'onglet Définir les règles de contrôle budgétaire.
5. Cliquez sur l'onglet Définir des groupes budgétaires.
6. Fermez la page.

## <a name="create-the-purchase-order-header"></a>Créer l'en-tête de commande fournisseur
1. Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.
4. Développez la section Général.
5. Dans le champ Date comptable, définissez la date sur « 01-01-2016 ».
6. Cliquez sur OK.

## <a name="add-a-purchase-order-line"></a>Ajouter une ligne de commande fournisseur
1. Saisissez ou sélectionnez une valeur dans le champ Catégorie d'approvisionnement.
2. Définissez la quantité sur 2.
3. Saisissez ou sélectionnez une valeur dans le champ Unité.
4. Définissez le prix unitaire sur « 10 000 ».
5. Cliquez sur Finances.
6. Cliquez sur Distribuer les montants.
7. Dans le champ Compte général, indiquez la valeur « 601300-001-023-- ».
8. Fermez la page.

## <a name="perform-budget-checking"></a>Réaliser un contrôle budgétaire
1. Cliquez sur Finances.
2. Cliquez sur Réaliser un contrôle budgétaire.
3. Cliquez sur Finances.
4. Cliquez sur Erreurs ou avertissements du contrôle budgétaire.
5. Cliquez sur Fermer.


