---
title: Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison
description: Cette rubrique décrit comment modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison dans Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 296dbf03ed65c1994562149a2c4b8fccd9073f0d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221917"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Les clients Dynamics 365 Commerce utilisent une application de PDV interne ainsi que des applications de PDV tierces. Dans le cas d’une application interne, les transactions en magasin sont extraites dans Commerce Headquarters depuis les canaux via un processus de traitement par lots. Dans le cas d’applications tierces, les transactions sont extraites dans Commerce Headquarters par intégration. Dans les deux cas, une fois les transactions extraites dans Commerce Headquarters, un processus de vérification de la cohérence doit être effectué. Ce processus exécute plusieurs validations sur les transactions, et seules les transactions qui sont validées avec succès sont extraites dans le relevé afin d’être validées dans Commerce Headquarters.

La validation des transactions commerciales peut échouer pour plusieurs raisons. Un bogue dans le code d’intégration ou dans l’application de PDV peut entraîner l’incohérence des données. Une erreur utilisateur peut également entraîner une incohérence des données. Prenons l’exemple d’un utilisateur qui supprime un produit après sa synchronisation avec le canal, ou d’un utilisateur qui clôture une période fiscale sans valider les transactions de cette période. Même si ces transactions sont marquées et exclues des relevés, elles peuvent perturber le processus quotidien de validation des ventes quotidiennes dans les finances. Dans Commerce, vous pouvez modifier les transactions qui n’ont pas été validées tout en tenant à jour un audit de toutes les modifications.

## <a name="edit-transactions"></a>Modifier les transactions

Dans Commerce version 10.0.5, seules les transactions au comptant sans livraison, comme les ventes et les retours, peuvent être modifiées. Les commandes client et les commandes en ligne ne peuvent pas être modifiées. À partir de Commerce version 10.0.6, les transactions de gestion des disponibilités peuvent également être modifiées.

Pour modifier les transactions dans Commerce Headquarters, procédez comme suit.

1. Installez [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Dans Commerce Headquarters, ouvrez l’espace de travail **Finances du magasin**. La vignette **Échecs de validation de transaction** offre une vue préfiltrée de la page des transactions pour lesquelles une ou plusieurs règles de validation ont échoué.
1. Ouvrez la page des transactions, sélectionnez l’enregistrement dont la validation a échoué, sélectionnez **Office Add in**, puis sélectionnez **Modifier la transaction sélectionnée**. Un fichier Excel affichant les détails de la transaction sélectionnée s’ouvert. Ce fichier contient les feuilles de calcul suivantes :

    - **Lignes** – Cette feuille de calcul contient les lignes d’en-tête et de produit pour la transaction et les données associées pour la transaction.
    - **Paiements** – Cette feuille de calcul contient les détails des lignes de paiement pour la transaction.
    - **Remises** – Cette feuille de calcul contient les détails de la remise pour la transaction.
    - **Taxes** – Cette feuille de calcul contient les détails de la taxe pour la transaction.
    - **Frais** – Cette feuille de calcul contient les détails des frais pour la transaction.

1. Dans le fichier Excel, modifiez les champs appropriés, puis chargez les données dans Commerce Headquarters en utilisant la fonctionnalité de publication du complément Dynamics Excel. Une fois les données publiées, les modifications sont répercutées dans le système. Lors de la publication, aucune validation n’est exécutée pour les modifications effectuées par les utilisateurs.
1. Vous pouvez afficher une piste d’audit complète des modifications en sélectionnant **Afficher la piste d’audit** dans l’en-tête **Transaction de vente au détail** pour les modifications au niveau de l’en-tête et dans la section et l’enregistrement appropriés dans la page de transaction appropriée. Par exemple, toutes les modifications liées aux lignes de vente seront affichées sur la page **Transactions de vente**, et toutes les modifications liées aux paiements seront affichées sur la page **Opérations de paiement**. Les détails d’audit suivants sont conservés pour les modifications :

    - Date et heure de modification
    - Champ
    - Ancienne valeur
    - Nouvelle valeur
    - Modifié par

1. Une fois que vous avez effectué et publié les modifications, exécutez l’option **Valider les transactions en magasin** pour valider la cohérence et la validité de ces modifications.

> [!NOTE]
> Vous pouvez modifier uniquement les transactions qui n’ont pas été validées. Si vous souhaitez modifier une transaction qui a été validée, remplacez le statut de validation de la transaction **Erreur** par **Aucun**, puis publiez la modification. Vous pouvez ensuite modifier les données de l’en-tête ou de tout autre enregistrement enfant de la transaction, et publier l’en-tête ou les enregistrements.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Modifier en bloc des transactions liées à un relevé

À partir de Commerce version 10.0.6, l’option de modification en bloc des transactions au niveau du relevé est prise en charge.

Pour modifier en bloc des transactions liées à un relevé dans Commerce Headquarters, procédez comme suit.

1. Ouvrez la page **Relevés** et sélectionnez le relevé contenant les transactions à modifier.
1. Sélectionnez le bouton **Ouvrir dans Microsoft Office**.
1. En fonction des éléments qui doivent être modifiés, sélectionnez l’une des options suivantes :

    - **Modifier les transactions au comptant sans livraison** – Cette option vous permet de modifier toutes les transactions au comptant sans livraison incluses dans le relevé. Les feuilles de calcul Excel suivantes sont disponibles :

        - **Transaction** – Cette feuille de calcul contient toutes les informations au niveau de l’en-tête pour les transactions de vente.
        - **Transaction de vente** – Cette feuille de calcul contient toutes les informations au niveau des lignes pour les transactions de vente.
        - **Transactions de paiement** – Cette feuille de calcul contient toutes les informations sur les lignes de paiement pour les transactions de vente.
        - **Transactions de remise** – Cette feuille de calcul contient toutes les informations sur les lignes de remise pour les transactions de vente.
        - **Transactions de taxe** – Cette feuille de calcul contient toutes les informations sur les lignes de taxe pour les transactions de vente.
        - **Transactions de frais** – Cette feuille de calcul contient toutes les informations sur les lignes de frais pour les transactions de vente.

    - **Modifier les transactions de gestion des disponibilités** – Cette option vous permet de modifier toutes les transactions de gestion des disponibilités incluses dans le relevé. Les feuilles de calcul Excel suivantes sont disponibles :

        - **Transaction** – Cette feuille de calcul contient toutes les informations au niveau de l’en-tête pour les transactions de gestion des disponibilités.
        - **Transactions de mode de paiement en banque** – Cette feuille de calcul contient tous les détails des transactions de remise en banque.
        - **Transactions de paiements remises en coffre-fort** – Cette feuille de calcul contient tous les détails des transactions de paiement remises en coffre-fort.
        - **Comptage de caisse** – Cette feuille de calcul contient tous les détails des transactions de comptage de caisse.
        - **Transaction de revenus/dépenses** – Cette feuille de calcul contient tous les détails de la ligne de transaction de revenus/dépenses.
        - **Transactions de paiement** – Cette feuille de calcul contient toutes les informations de paiement pour l’opération **Payer la facture** ainsi que la transaction de revenus/dépenses.

1. Modifiez les transactions requises.

    > [!NOTE]
    > Les validations ne sont pas effectuées lorsque vous publiez des transactions qui ont été modifiées en bloc. Vous devez vous assurer que toutes vos modifications sont correctes et que la fidélité des données dans les feuilles de calcul est préservée. Par exemple, si vous souhaitez modifier la date de transaction afin de gérer les scénarios où la période fiscale ou d’inventaire des transactions en cours est clôturée, vous devez modifier la date sur toutes les feuilles de calcul Excel contenant la colonne **Date d’activité**. Pour valider les transactions après les avoir modifiées, vous pouvez sélectionner **Revalider les transactions** dans la page **Relevés**. Attendez la fin du travail de validation avant de publier le relevé.

1. Si l’agrégation a déjà été générée, ouvrez la page **Transactions regroupées** et sélectionnez **Régénérer la commande client au format xml**.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Modifier en bloc des transactions qui ne sont pas liées à un relevé

À partir de Commerce version 10.0.10, l’option de modification en bloc des transactions qui ne sont pas validées mais qui ne sont pas liées à un relevé est prise en charge.

Pour modifier en bloc des transactions qui ne sont pas liées à un relevé dans Commerce Headquarters, procédez comme suit.

1. Ouvrez la page **Tous les magasins** et sélectionnez le magasin pour lequel les transactions doivent être modifiées.
1. Sélectionnez le bouton **Ouvrir dans Microsoft Office**, puis sélectionnez **Modifier les transactions au comptant sans livraison**.
1. Modifiez les transactions requises, puis publiez-les.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones](edit-order-trans.md)

[Modifier les dimensions financières des transactions de vente au détail](edit-financial-dim.md)

[Créer un classeur Excel pour modifier les transactions de vente au détail](create-excel-edit.md)

[Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]