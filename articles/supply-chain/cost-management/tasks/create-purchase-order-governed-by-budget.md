---
title: Créer une commande fournisseur régie par budget
description: Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016186"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Créer une commande fournisseur régie par budget

[!include [banner](../../includes/banner.md)]

Cette procédure permet de créer une commande fournisseur dont la disponibilité budgétaire est vérifiée.

## <a name="review-the-budget-control-configuration"></a>Examiner la configuration du contrôle budgétaire

1. Accédez à **Budgétisation > Paramétrage > Contrôle budgétaire > Configuration du contrôle budgétaire**.
1. Sélectionnez l’onglet **Fonds budgétaires disponibles**.
1. Sélectionnez l’onglet **Documents et journaux**.
1. Sélectionnez l’onglet **Définir les règles de contrôle budgétaire**.
1. Sélectionnez l’onglet **Définir des groupes budgétaires**.
1. Fermez la page.

## <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur**.
1. Cliquez sur **Nouveau**.
1. Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.
1. Développez l’organisateur **Général**.
1. Dans le champ **Date comptable**, définissez la date.
1. Sélectionnez **OK** pour fermer la boîte de dialogue et ouvrir votre nouvelle commande fournisseur.
1. Sur le raccourci **Lignes de bon de commande**, sélectionnez **Ajouter une ligne** dans la barre d’outils pour ajouter une nouvelle ligne, puis remplissez la ligne au besoin pour ajouter un article à la commande.
1. Dans la barre d’outils Raccourcis **Facture fournisseur**, sélectionnez **Finances \> Distribuer le montant**.
1. Dans le champ **Compte général**, indiquez un compte.
1. Fermez la page.

## <a name="perform-budget-checking"></a>Réaliser un contrôle budgétaire

1. Continuez à travailler avec le bon de commande auquel vous venez d’ajouter une ligne.
1. Dans la barre d’outils Raccourcis **Facture fournisseur**, sélectionnez **Finances \> Réaliser un contrôle budgétaire**.
1. Dans la barre d’outils Raccourcis **Facture fournisseur**, sélectionnez **Finances \> Erreurs ou avertissements du contrôle budgétaire**.
1. La boîte de dialogue **Erreurs ou avertissements du contrôle budgétaire** s’ouvre. Vérifiez les résultats de la vérification, puis sélectionnez **Fermer** pour fermer la boîte de dialogue.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]