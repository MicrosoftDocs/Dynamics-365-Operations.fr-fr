---
title: Créer et traiter les non-conformités
description: Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d’un ordre de qualité existant.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 032f5b712c2be5312524129cd25e655e778f5f44
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580862"
---
# <a name="create-and-process-nonconformances"></a>Créer et traiter les non-conformités

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment effectuer la gestion de non-conformité, en fonction d’un ordre de qualité existant. En règle générale, la gestion des non-conformités est effectuée par un commis au contrôle de la qualité. Au préalable, vous devez disposer d'un ordre de qualité. (Pour plus d'informations sur la création d'un ordre de qualité, voir [Inspecter la qualité des marchandises](inspect-quality-goods.md) .)

Avant qu'un utilisateur puisse traiter l'approbation d'une non-conformité, un collaborateur doit lui être affecté dans le champ **Personne** sur la page **Utilisateurs**. De plus, avant que l'utilisateur puisse utiliser les notes du document, l'option **Activer la gestion des documents** doit être définie sur *Oui* dans leurs options de l'utilisateur.

## <a name="create-a-nonconformance"></a>Créer une non-conformité

Pour créer une non-conformité, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Créer une non-conformité**, dans le champ **Type de problème**, sélectionnez le type de problème détecté lors du processus d'inspection.
1. Cliquez sur **OK**.

## <a name="approve-or-reject-a-nonconformance"></a>Approuver ou rejeter une non-conformité

Pour approuver ou rejeter une non-conformité, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous ne pouvez ajouter une correction qu'aux non-conformités approuvées.

1. Dans le volet Actions, sélectionnez **Fonctions \> Approuver la non-conformité** pour approuver la non-conformité ou **Fonctions \> Refuser la non-conformité** pour la rejeter. Vous pouvez associer des non-conformités approuvées aux [opérations connexes](../quality-operations.md). De cette manière, vous pouvez enregistrer le travail effectué dans le cadre de la gestion des non-conformités et du traitement de la gestion des corrections.
1. Vous êtes invité à confirmer la sélection. Sélectionnez **Oui** pour continuer.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Ajouter des opérations et d'autres détails aux non-conformités

Après avoir créé une non-conformité, vous pouvez commencer à ajouter des opérations associées et spécifier des informations supplémentaires sur ces opérations. Vous ne pouvez ajouter des opérations connexes qu'aux non-conformités approuvées.

Outre les informations de base, vous pouvez ajouter les détails suivants à une opération :

- **Articles** - Vous pouvez créer une liste d'articles consommés pour effectuer la correction. Par exemple, les articles peuvent être des produits nécessaires à la réparation de l'équipement ou des substances nécessaires pour retravailler un produit fini.
- **Frais de qualité** - Vous pouvez créer une liste des frais encourus ou facturés à des sources externes.
- **Emploi du temps** - Vous pouvez créer un journal du temps que chaque collaborateur passe sur l'opération.

Les paramètres restantes sont facultatifs. Le coût de chaque article, les frais de qualité et la feuille de temps sont additionnés et indiqués sur l'opération. Vous ne pouvez pas modifier directement le champ **Coût** sur l'opération.

### <a name="create-an-operation-for-a-nonconformance"></a>Créer une opération pour une non-conformité

Pour créer une opération pour une non-conformité, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.

1. Dans le volet Actions, sélectionnez **Opérations connexes**.
1. Sur la page **Opérations connexes**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Opération** - Sélectionnez le code de l'opération qui sera effectuée pour la non-conformité.
    - **Raison** - Entrez une description détaillée expliquant pourquoi l'opération est requise.
    - **Commande client** - Si le code d'opération sélectionné est lié au type de commande client, sélectionnez la commande client à laquelle vous liez l'opération.
    - **Commande fournisseur** - Si le code d'opération sélectionné est lié au type de commande fournisseur, sélectionnez la commande fournisseur à laquelle vous liez l'opération.

1. Fermez les pages.

### <a name="add-items-to-an-operation"></a>Ajouter des articles à une opération

Pour ajouter des articles à une opération, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.

1. Dans le volet Actions, sélectionnez **Opérations connexes**.
1. Dans la page **Opérations connexes**, sélectionnez l'opération à laquelle vous souhaitez ajouter des articles.
1. Dans le volet Actions, sélectionnez **Articles**.
1. Sur la page **Opérations connexes**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Numéro d'article** - Sélectionnez le produit qui sera consommé dans le cadre de l'opération sélectionnée.
    - **Quantité** - Entrez le nombre d'articles qui seront consommés.

    > [!NOTE]
    > Vous pouvez afficher le coût de l'article dans le champ **Coût** sur l'onglet **Général**. Le coût qui y est indiqué provient du coût défini sur la page **Produit lancé**. Le coût ne peut pas être mis à jour directement sur la page **Article d'opération connexe**. Le coût de tous les articles ajoutés sur la page **Articles d'opération connexe** est automatiquement ajouté au champ **Coût** sur la page **Opérations connexes**.

1. Répétez l'étape précédente pour chaque article supplémentaire que vous devez ajouter.
1. Fermez les pages.

### <a name="add-quality-charges-to-an-operation"></a>Ajouter des frais de qualité à une opération

Pour ajouter des frais de qualité à une opération, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.

1. Dans le volet Actions, sélectionnez **Opérations connexes**.
1. Dans la page **Opérations connexes**, sélectionnez l'opération à laquelle vous souhaitez ajouter des frais de qualité.
1. Dans le volet Actions, cliquez sur **Frais de qualité**.
1. Sur la page **Frais d'opération connexe**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Code de frais** - Sélectionnez les frais de qualité que vous souhaitez ajouter.
    - **Description** - Entrez une description détaillée des frais.
    - **Valeur des frais** – Entrez le montant des frais.

1. Répétez l'étape précédente pour les frais supplémentaires individuels que vous devez ajouter.
1. Fermez les pages.

> [!NOTE]
> Le montant dans le champ **Valeur des frais** est automatiquement additionné pour tous les frais de qualité et ajouté à tout autre montant dans le champ **Coût** sur la page **Opérations connexes**.

### <a name="create-a-timesheet-on-an-operation"></a>Créer une feuille de temps sur une opération

Pour ajouter une feuille de temps à une opération, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous pouvez ajouter et mettre à jour des opérations connexes uniquement pour des non-conformités approuvées.

1. Dans le volet Actions, sélectionnez **Opérations connexes**.
1. Dans la page **Opérations connexes**, sélectionnez l'opération à laquelle vous souhaitez ajouter une feuille de temps.
1. Dans le volet Actions, sélectionnez **Feuille de temps**.
1. Sur la page **Feuille de temps d'opération connexe**, dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Date** - Précisez la date à laquelle le travail a été effectué. Par défaut, ce champ est défini sur la date actuelle.
    - **Collaborateur** – Permet de sélectionner le collaborateur qui a effectué le travail. Par défaut, ce champ est défini sur le collaborateur affecté à l'utilisateur actuel.
    - **Heures de l'opération** - Saisissez le nombre d'heures travaillées sur l'opération sélectionnée.
    - **Facturé** - Cochez cette case si le temps a été facturé à un client ou fournisseur au moyen d'une facture.

    > [!NOTE]
    > Vous pouvez consulter le coût dans le champ **Coût** sur l'onglet **Général**. Le coût est calculé en utilisant le taux que vous définissez sur la page **Paramètres de gestion des stocks**.

1. Répétez l'étape précédente pour chaque feuille de temps que vous devez ajouter.
1. Fermez les pages.

> [!NOTE]
> Le montant dans le champ **Coût** est automatiquement additionné pour toutes les feuilles de temps et ajouté à tout autre montant dans le champ **Coût** sur la page **Opérations connexes**.

## <a name="add-a-correction-to-a-nonconformance"></a>Ajouter une correction à une non-conformité

Pour ajouter une correction à une non-conformité, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous ne pouvez ajouter une correction qu'aux non-conformités approuvées.

1. Sur le volet Actions, sélectionnez **Correction**.
1. Dans la page **Corrections**, sur le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Diagnostique** - Sélectionnez le type de diagnostic qui identifie le type de correction que vous créez.
    - **Collaborateur** – Sélectionnez la personne responsable de la correction.
    - **Priorité de correction** - Sélectionnez une option pour indiquer comment la correction doit être priorisée (priorité *Faible*,*Normale*, ou alors *Haute*).
    - **Date demandée** - Saisissez la date à laquelle l'action corrective a été demandée.
    - **Date prévue** - Entrez la date à laquelle la correction devrait être terminée.
    - **Solution a court terme** - Cochez cette case si l'action corrective ne corrige la non-conformité que pendant une courte période.

1. Fermez les pages.

## <a name="mark-a-correction-as-completed"></a>Marquer une correction comme terminée

Pour marquer une correction de non-conformité comme terminée, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.

    > [!NOTE]
    > Vous ne pouvez ajouter une correction qu'aux non-conformités approuvées.

1. Sur le volet Actions, sélectionnez **Correction**.
1. Sur la page **Corrections**, dans la grille, sélectionnez la correction que vous souhaitez marquer comme terminée.
1. Dans le volet Actions, sélectionnez **Marquer comme terminé**.
1. Vous êtes invité à confirmer la sélection. Cliquez sur **OK** pour continuer. Le champ **Date et heure de fin** est défini sur la date et l'heure actuelles, et la case à cocher **Terminé** est cochée.
1. Fermez la page.

## <a name="reopen-a-completed-correction"></a>Rouvrir une correction terminée

Pour rouvrir une correction terminée, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Non-conformités**.
1. Dans la liste, localisez et sélectionnez la non-conformité que vous voulez mettre à jour.
1. Sur le volet Actions, sélectionnez **Correction**.
1. Sur la page **Corrections**, dans la grille, sélectionnez la correction que vous souhaitez rouvrir.
1. Dans le volet Actions, sélectionnez **Rouvrir**.
1. Vous êtes invité à confirmer la sélection. Cliquez sur **OK** pour continuer. La valeur est effacée du champ **Date et heure de fin**, et la case à cocher **Terminé** est désactivée.
1. Fermez la page.

Vous pouvez désormais apporter des modifications ou des mises à jour supplémentaires à la correction. Lorsque vous avez terminé, vous pouvez marquer à nouveau la correction comme terminée.

## <a name="close-a-nonconformance"></a>Clôturer une non-conformité

Pour fermer une non-conformité, procédez comme suit.

1. Allez dans **Gestion des stocks \> Tâches périodiques \> Gestion de la qualité \> Ordres de qualité**.
1. Sélectionnez un ordre de qualité dans la grille.
1. Dans le volet Actions, sélectionnez **Recherches \> Non-conformités**.
1. Sur la page **Non-conformités**, sélectionnez la non-conformité cible dans la grille.
1. Dans le volet Actions, sélectionnez **Fonctions \> Clôturer la non-conformité**.
1. Vous êtes invité à confirmer la sélection. Sélectionnez **Oui** pour continuer.
1. Fermez les pages.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](../quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](../enable-quality-management.md)
- [Collaborateurs chargés d'approuver les non-conformités](../quality-responsible-workers.md)
- [Zones de quarantaine pour les non-conformités](../quality-quarantine-zones.md)
- [Types de diagnostic pour les non-conformités](../quality-diagnostic-types.md)
- [Frais de qualité pour les non-conformités](../quality-charges.md)
- [Opérations pour les non-conformités](../quality-operations.md)
- [Gestion de la qualité pour les processus d'entrepôt](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
