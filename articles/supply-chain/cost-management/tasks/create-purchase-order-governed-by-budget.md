---
title: Créer une commande fournisseur régie par budget
description: Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 319eb0070a3677035e2a5d89744e80cd38c08d8e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427964"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Créer une commande fournisseur régie par budget

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]