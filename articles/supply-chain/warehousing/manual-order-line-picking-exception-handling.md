---
title: Gérer manuellement les ventes et les exceptions de prélèvement de ligne de transfert
description: Cet article décrit comment les administrateurs peuvent sélectionner (ou désélectionner) manuellement des transactions de stock pour résoudre les problèmes causés par des ventes corrompues et des données de commande de transfert.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403668"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Gérer manuellement les ventes et les exceptions de prélèvement de ligne de transfert

[!include [banner](../includes/banner.md)]

La gestion manuelle des exceptions de prélèvement des lignes de vente et de transfert permet aux administrateurs de résoudre les problèmes causés par des données de commande de vente et de transfert corrompues. Elle permet aux utilisateurs de confiance de sélectionner (ou d’annuler) manuellement les transactions de stock liées aux lignes de commande de vente et de transfert alors que les processus d’entrepôt sont déjà en cours.

La fonctionnalité décrite ici doit être utilisée uniquement dans les cas où le système ne peut pas terminer le traitement de la pile des processus d’entrepôt de la manière habituelle. Par défaut, seuls les utilisateurs qui ont un rôle d’administrateur système sont autorisés à l’utiliser. Cependant, vous pouvez lui accorder l’accès en attribuant le privilège *Prélever des lignes vente manuellement* à d’autres rôles selon vos besoins.

## <a name="turn-on-this-feature-for-your-system"></a>Activez cette fonctionnalité pour votre système

Avant de pouvoir utiliser une des fonctionnalités décrites dans cet article, vous devez l’activer dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de ces fonctionnalités et les activer. Dans l’espace de travail **Gestion des fonctionnalités**, les fonctionnalités sont répertoriées avec les noms suivants :

- *Service de prélèvement de ligne vente manuel pour les administrateurs ou les utilisateurs approuvés similaires*<br>(Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et ne peut pas être désactivée.)
- *Service de prélèvement de ligne de transfert manuel pour les administrateurs ou les utilisateurs approuvés similaires*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Corriger les transactions liées aux lignes d’ordre de vente ou de transfert

Utilisez la procédure suivante pour corriger les transactions liées aux lignes d’ordre de vente ou de transfert.

1. Procédez comme suit, selon le type de rapport que vous devez corriger :

    - Pour corriger une transaction liée à une commande client, accédez à **Gestion d’entrepôt \> Tâches périodiques \> Nettoyer \> Sélectionner la ligne de vente manuellement**.
    - Pour corriger une transaction liée à un ordre de transfert, accédez à **Gestion d’entrepôt \> Tâches périodiques \> Nettoyer \> Prélever des lignes de transfert manuellement**.

1. Sur la page **Prélever des lignes de vente manuellement** ou **Prélever des lignes de transfert manuellement**, utilisez les filtres en haut de la grille pour trouver la ligne que vous recherchez, puis sélectionnez la ligne de commande cible dans la grille supérieure.
1. Utilisez les onglets **Mouvements de stock**, **Lignes de chargement**, **Lignes de travail** et **Lignes de conteneurs** dans la section inférieure pour afficher plus d’informations sur la ligne sélectionnée. Les informations de ces onglets donnent un aperçu de base des processus d’entrepôt associés et de leurs statuts.
1. Sur la page **Prélever**, dans le volet Actions, sélectionnez **Prélever** pour ouvrir la ligne de commande sélectionnée pour les transactions de stock. Vous pouvez effectuer cette étape même pour les lignes de commande qui ont déjà été lancées dans l’entrepôt. (Généralement, les lignes de commande qui ont été lancées dans l’entrepôt ne peuvent pas être ouvertes sur la page **Prélever**.)

    > [!NOTE]
    > Vous pouvez recevoir divers avertissements lorsque vous ouvrez la page **Prélever**. Effectuez toutes les actions recommandées par ces avertissements. Par exemple, vous pouvez recevoir un avertissement concernant les lignes de commande liées au travail d’entrepôt. Dans ce cas, il est logique d’essayer d’annuler le travail en utilisant la fonctionnalité standard [Annuler le travail](cancel-warehouse-work.md) avant de procéder à la correction manuelle.

1. Sélectionnez la ligne dans la grille **Transactions**, puis sélectionnez **Ajouter une ligne de prélèvement** sur la barre d’outils **Transactions**.
1. La ligne sélectionnée est déplacée vers la grille **Lignes de prélèvement**. Définissez les valeurs appropriées pour toutes les colonnes auxquelles manquent les informations requises. (Par exemple, spécifiez l’emplacement et la plaque d’immatriculation à partir desquels l’article doit être prélevé/retiré.)
1. Sélectionnez **Confirmer Prélever tout** sur la barre d’outils **Lignes de prélèvement**.

## <a name="correct-load-line-quantities"></a>Corriger des quantités de ligne de chargement

Suivez la procédure suivante pour corriger une quantité de la ligne de chargement.

1. Procédez comme suit, selon le type de rapport que vous devez corriger :

    - Pour corriger une transaction liée à une commande client, accédez à **Gestion d’entrepôt \> Tâches périodiques \> Nettoyer \> Sélectionner la ligne de vente manuellement**.
    - Pour corriger une transaction liée à un ordre de transfert, accédez à **Gestion d’entrepôt \> Tâches périodiques \> Nettoyer \> Prélever des lignes de transfert manuellement**.

1. Sur la page **Prélever des lignes de vente manuellement** ou **Prélever des lignes de transfert manuellement**, utilisez les filtres en haut de la grille pour trouver la ligne que vous recherchez, puis sélectionnez la ligne de commande cible dans la grille supérieure.
1. Sur l’onglet **Lignes de chargement** dans la section inférieure, sélectionnez **Corriger les lignes de chargement manuellement** sur la barre d’outils.
1. Sur la page **Corriger les lignes de chargement manuellement**, dans la grille **Mouvements de stock**, passez en revue les transactions de stock liées à la ligne de chargement sélectionnée.
1. Dans la grille supérieure, corrigez les quantités de ligne de chargement dans les colonnes suivantes selon les besoins :

    - **Quantité de travail créé**
    - **Quantité prélevée**
    - **Quantité de cross-docking planifiée**

    Le système validera toutes les modifications que vous apportez à ces colonnes.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
