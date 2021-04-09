---
title: Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones
description: Cette rubrique décrit comment modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
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
ms.openlocfilehash: 5113f7ac0d308076ebaa9daeca0929eb537e94ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792679"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Entre les versions 10.0.5 et 10.0.6 de Commerce, la prise en charge de la modification des transactions au comptant sans livraison (comme les ventes et le vidage de caisse) et des transactions de gestion de trésorerie (comme les entrées de fonds et la suppression des offres) a été ajoutée. Dans Commerce version 10.0.7, la prise en charge de la modification des transactions de commande en ligne et des transactions de commande client asynchrones a été ajoutée.

## <a name="edit-and-audit-order-transactions"></a>Modifier et vérifier des transactions de commandes

Pour modifier et vérifier les transactions de commande dans Commerce Headquarters, procédez comme suit.

1. Installez [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Dans la page **Paramètres des ventes au détail**, sous l’onglet **Commandes client**, dans le raccourci **Commande**, spécifiez un code de blocage pour **Code de blocage pour les erreurs de synchronisation des commandes**.
1. Ouvrez l’espace de travail **Finances du magasin**. Les vignettes **Erreurs de synchronisation des commandes en ligne** et **Erreurs de synchronisation des commandes client** fournissent une vue préfiltrée de la page des transactions de vente au détail. Chaque vignette affiche les enregistrements de transaction dont la synchronisation a échoué pour le type de commande correspondant.
1. Ouvrez la page **Erreurs de synchronisation des commandes en ligne** ou la page **Erreurs de synchronisation des commandes client**. Sélectionnez un enregistrement pour afficher les détails de l’erreur de synchronisation. Le raccourci **État de la synchronisation** fournit les détails d’erreur suivants :

    - Statut de commande en attente
    - Détails des erreurs de commande
    - Date et heure de modification
    - Nombre de nouvelles tentatives

1. Si les détails de l’erreur indiquent que l’enregistrement doit être corrigé, sélectionnez **Office Add in**, puis sélectionnez **Modifier la transaction sélectionnée**. Un fichier Excel affichant les détails de la transaction sélectionnée s’ouvert.

    - Si la transaction en cours de modification est une transaction de commande en ligne, le fichier Excel contient les feuilles de calcul suivantes :

        - **Transaction** – Cette feuille de calcul contient les détails de l’en-tête pour la transaction.
        - **Transaction de vente** – Cette feuille de calcul contient les détails de la ligne pour la transaction.
        - **Transactions de paiement** – Cette feuille de calcul contient les détails des lignes de paiement pour la transaction.
        - **Transactions de remise** – Cette feuille de calcul contient les détails de la remise pour la transaction.
        - **Transactions de taxe** – Cette feuille de calcul contient les détails de la taxe pour la transaction.
        - **Transactions de frais** – Cette feuille de calcul contient les détails des frais pour la transaction.

    - Si la transaction en cours de modification est une transaction de commande client asynchrone, le fichier Excel contient les feuilles de calcul suivantes :

        - **Lignes** – Cette feuille de calcul contient les détails de l’en-tête et de la ligne pour la transaction.
        - **Paiements** – Cette feuille de calcul contient les détails des lignes de paiement pour la transaction.
        - **Remises** – Cette feuille de calcul contient les détails de la remise pour la transaction.
        - **Taxes** – Cette feuille de calcul contient les détails de la taxe pour la transaction.
        - **Frais** – Cette feuille de calcul contient les détails des frais pour la transaction.

1. Dans le fichier Excel, dans le champ **Statut de commande en attente**, entrez **Modification**, puis publiez la modification. De cette façon, vous évitez que la tâche **Synchroniser la commande** qui s’exécute en mode lot ignore cet enregistrement pendant le traitement.
1. Dans le fichier Excel, modifiez les champs appropriés, puis chargez les données dans Commerce Headquarters en utilisant la fonctionnalité de publication du complément Dynamics Excel. Une fois les données publiées, les modifications sont répercutées dans le système. Lors de la publication, aucune validation n’est exécutée pour les modifications effectuées par les utilisateurs.
1. Vous pouvez afficher une piste d’audit complète des modifications en sélectionnant **Afficher la piste d’audit** dans l’en-tête **Transaction de vente au détail** pour les modifications au niveau de l’en-tête et dans la section et l’enregistrement appropriés dans la page de transaction appropriée. Par exemple, toutes les modifications liées aux lignes de vente seront affichées sur la page **Transactions de vente**, et toutes les modifications liées aux paiements seront affichées sur la page **Opérations de paiement**. Les détails d’audit suivants sont conservés pour les modifications :

    - Date et heure de modification
    - Champ
    - Ancienne valeur
    - Nouvelle valeur
    - Modifié par

1. Après avoir effectué et publié vos modifications, sélectionnez **Synchroniser la commande** pour démarrer immédiatement le processus de synchronisation. Vous pouvez également attendre que le processus de synchronisation qui s’exécute en mode lot traite la transaction.

Par défaut, une fois les commandes synchronisées avec succès, elles sont mises en attente, en fonction du code de blocage défini dans les paramètres de Commerce. Le blocage des commandes doit être supprimé pour que l’exécution des commandes ou d’autres opérations puissent être effectuées.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison](edit-cash-trans.md)

[Modifier les dimensions financières des transactions de vente au détail](edit-financial-dim.md)

[Créer un classeur Excel pour modifier les transactions de vente au détail](create-excel-edit.md)

[Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]