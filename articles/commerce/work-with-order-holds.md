---
title: Configurer et utiliser des blocages de commande dans le centre d'appels
description: Cette rubrique décrit l'utilisation de blocages sur les commandes à l'aide de Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans, MCROrderEventSetup, MCROrderEventTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b11dd48ac629910a82b4d5bfdf9889809b0d829d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412284"
---
# <a name="configure-and-work-with-call-center-order-holds"></a>Configurer et utiliser les blocages de commande dans le centre d'appels

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctions de blocage de commande de Dynamics 365 Commerce pour les commandes du centre d'appels.

## <a name="configuring-call-center-order-holds"></a>Configuration des blocages de commande dans le centre d'appels

Pour utiliser les fonctions de blocage de commande dans le centre d'appels, vous devez d'abord définir des codes de blocage. Pour créer un ensemble de codes de blocage définis par l'utilisateur, selon les besoins de votre organisation, accédez à **Ventes et marketing** \> **Paramétrage** \> **Commandes client** \> **Codes de blocage de commande**. Vous pouvez également marquer l'un des codes de blocage comme valeur par défaut en définissant l'option **Valeur par défaut de commande client** sur **Oui**. Ce code de blocage est utilisé à chaque fois qu'une commande client est mise en attente. Si une commande client a un stock réservé, et les réservations doivent être automatiquement supprimées si la commande est mise en attente pour une raison donnée, définissez l'option **Supprimer les réservations de stock** sur **Oui** pour les codes motif.

Pour spécifier le type de note à capturer lorsque les utilisateurs qui mettent en attente une commande client entrent des notes facultatives, accédez à **Ventes** \> **Paramétrage** \> **Paramètres de la comptabilité client**, puis, dans l'organisateur **Paramétrage des ventes**, sous l'onglet **Général**, définissez le champ **Type de note**. Utilisez le champ **Statut de la commande client En attente** pour définir la couleur à utiliser pour mettre en surbrillance les commandes client en attente lorsqu'elles sont affichées sur la page **Service client**.

Pour créer un ensemble facultatif de codes motif de blocage, accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Codes info**. Ces codes info peuvent être utilisés comme code motif secondaire pour définir davantage le code de blocage principal. Sélectionnez **Nouveau** pour créer un ensemble de codes motif, puis sélectionnez **Sous-codes** pour définir la liste des motifs supplémentaires. Pour lier les codes info que vous définissez au canal du centre d'appels, accédez à **Retail et Commerce** \> **Canaux** \> **Centres d'appels** \> **Tous les centres d'appels**. Dans l'organisateur **Général**, définissez le champ **Code de blocage**.

## <a name="putting-orders-on-hold"></a>Mise en attente de commandes

Les commandes créées par les utilisateurs du centre d'appels dans le programme Commerce de back-office peuvent être mises en attente manuellement ou automatiquement dans certains cas.

Lors de la saisie de la commande, mais avant l'envoi et la confirmation de la commande, les utilisateurs du centre d'appels peuvent mettre en attente manuellement une commande pour empêcher qu'elle soit lancée dans l'entrepôt pour traitement. Par exemple, le client qui passe la commande peut ne pas être prêt à la valider, ou des données critiques requises pour traiter la commande peuvent être manquantes.

Dans la page de saisie de la commande, l'utilisateur du centre d'appels peut mettre une commande en attente à l'aide de l'option **Blocage de commandes** sous l'onglet **Commande client** du menu de saisie de commande. Sinon, l'utilisateur peut sélectionner l'élément de menu **Blocage** sur la page **Résumé de la commande client** qui s'affiche lorsqu'il sélectionne **Terminer** dans une commande client du centre d'appels.

Dans les deux cas, la page **Blocage de commandes** s'affiche. L'utilisateur peut alors sélectionner **Nouveau** pour créer une blocage pour la commande. Dans le champ **Code de blocage**, l'utilisateur doit sélectionner le code qui décrit le mieux le motif du blocage. Dans le champ **Code motif**, l'utilisateur peut éventuellement sélectionner un code supplémentaire pour fournir un deuxième niveau de description du blocage.

Dans l'organisateur **Notes**, dans le champ **Notes de blocage**, l'utilisateur peut entrer des notes supplémentaires en forme libre pour fournir un contexte ou des informations supplémentaires sur le blocage. Ces notes peuvent être utiles aux autres utilisateurs qui révisent ou utilisent la commande en attente ultérieurement.

Une fois que les informations de blocage sont saisies et enregistrées, l'utilisateur peut fermer la page **Blocage de commandes**. L'utilisateur est redirigé vers la page de saisie de la commande client. Si aucune action supplémentaire n'est requise sur la commande client, l'utilisateur peut fermer la page de saisie de la commande client.

Si l'indicateur **Activer l'achèvement de la commande** est activé dans le canal du centre d'appels, il n'est pas nécessaire d'appliquer le paiement à une commande mise en attente. En revanche, pour une commande client qui n'est pas mise en attente, les utilisateurs ne peuvent pas quitter la page de saisie de la commande client jusqu'à ce que le paiement soit appliqué. Bien évidemment, le paiement est requis pour débloquer la commande.

En outre, les utilisateurs du centre d'appels peuvent bloquer manuellement pour fraude des commandes suspectes pour une raison quelconque. Les commandes peuvent également être mises en attente automatiquement lorsqu'elles correspondent aux critères et règles de fraude actifs. Pour plus d'informations sur ce type de blocage de commande, voir [Paramétrer les alertes de fraude](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Affichage et gestion des commandes en attente

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Afficher des informations de blocage pour une commande client unique

Dans la page **Service client**, les utilisateurs peuvent identifier visuellement les commandes en attente, car les lignes de commande sont mises en surbrillance dans une couleur spécifique. Cette couleur est définie par le champ **Statut de la commande client En attente** dans la page **Paramètres de la comptabilité client**.

> [!NOTE]
> Si la ligne est sélectionnée sur la page, la couleur de surbrillance n'est pas visible.

Les utilisateurs peuvent également afficher les informations détaillées sur le statut d'une commande client pour savoir si la commande est en attente. Les informations détaillées sur le statut sont accessibles à partir de la page **Toutes les commandes client** ou **Service client**. Si une commande est en attente, l'indicateur **Ne pas traiter** est défini, et le champ **Statut détaillé** indique **En attente** ou **Blocage pour fraude**, selon le scénario.

Pour afficher les détails d'un blocage de commande individuel, les utilisateurs peuvent ouvrir une vue détaillée de la page **Blocage de commande** à partir de la page **Service client**, à l'aide du menu **Options** pour la commande sélectionnée. Les utilisateurs peuvent également accéder à cette vue à partir de la page **Toutes les commandes client**, en sélectionnant l'élément de menu **Blocage de commandes** sous l'onglet **Commande client**.

### <a name="viewing-all-orders-that-are-on-hold"></a>Affichage de toutes les commandes en attente

Pour afficher toutes les commandes mises en attente manuellement ou automatiquement, accédez à **Retail et Commerce** \> **Clients** \> **Blocage de commandes**.

La fenêtre **Blocage de commandes** fournit une vue de liste de toutes les commandes mises en attente en raison d'actions de blocage manuel ou pour fraude. En utilisant les options de filtrage et de tri standard disponibles sur la page, les utilisateurs peuvent créer des vues leur permettant d'utiliser ou de gérer des codes de blocage spécifiques qu'ils doivent réviser. La fenêtre **Blocage de commandes** indique également le nombre de jours pendant lesquels une commande a été mise en attente. Ces informations peuvent aider les utilisateurs à classer par priorité la file d'attente.

Pour obtenir une vue plus détaillée des commandes en attente, les utilisateurs peuvent cliquer sur l'option **Blocage de commande** dans le menu. Cette vue donne des informations sur le client, ainsi que les notes qui ont été appliquées à la commande, au client ou à l'action de blocage. La vue fournit également des détails sur le motif d'un blocage automatique, si la commande a été mise en attente du fait de la correspondance avec une règle de fraude.

Dans la vue de liste et la vue détaillée de la page **Blocage de commandes**, les utilisateurs peuvent afficher ou modifier les informations supplémentaires associées à la commande, telles que les paiements, les totaux et les notes.

Les options disponibles sous l'onglet **Extraire le blocage** peuvent être utiles si plusieurs utilisateurs de votre société utilisent la file d'attente de blocage en même temps. En sélectionnant l'option **Extraction**, les utilisateurs peuvent indiquer qu'ils sont en train d'examiner et d'analyser le blocage de la commande. Ainsi, les autres utilisateurs ne perdent pas de temps à essayer d'en faire de même. Dans la vue détaillée de la page **Blocage de commandes**, les utilisateurs peuvent afficher des informations sur la date et l'heure d'extraction, ainsi que l'utilisateur qui a extrait l'enregistrement de blocage.

Une fois qu'un enregistrement de blocage est extrait, seul l'utilisateur qui l'a extrait peut supprimer l'extraction. Cette restriction permet d'empêcher les utilisateurs de sélectionner des enregistrements qui sont déjà utilisés par d'autres utilisateurs. Pour remettre une commande dans la file d'attente afin que d'autres utilisateurs puissent l'utiliser, l'utilisateur qui a extrait l'enregistrement sélectionne l'option **Supprimer l'extraction**.

> [!NOTE]
> Le blocage n'est pas terminé lorsque l'extraction est supprimée.

Dans certains cas, par exemple lorsqu'un utilisateur est en congé maladie ou a quitté la société, les enregistrements extraits par cet utilisateur doivent être réaffectés à un autre utilisateur. Un responsable peut réaffecter des enregistrements à l'aide de l'option **Remplacer l'extraction**.

## <a name="releasing-orders-that-are-on-hold"></a>Lancer des commandes en attente

Dans la vue de liste et la vue détaillée de la page **Blocage de commandes**, l'onglet **Supprimer le blocage** contient les options utilisées pour supprimer un blocage de commande. Utilisez l'option **Supprimer les blocages** pour lancer une commande à partir du code de blocage sélectionné.

Les commandes du centre d'appels requièrent le paiement. Par conséquent, un blocage ne peut pas être entièrement supprimé si le paiement n'a pas été appliqué à la commande. Dans la page **Paramètres du centre d'appels**, sous l'onglet **Blocage**, vérifiez que le paramètre **Soumettre après règlement** est activé. Ce paramètre permet de garantir que la commande en attente suit la logique d'envoi de commande correcte pour valider et autoriser le paiement. Si des paiements sont manquants, l'utilisateur reçoit un message d'erreur, et le code de blocage n'est pas supprimé.

Si le paramètre **Soumettre après règlement** n'a pas été défini, les utilisateurs doivent sélectionner l'option **Supprimer et soumettre** dans le menu **Supprimer le blocage** pour garantir que la commande passe par toutes les validations de paiement requises. Si l'envoi de la commande échoue lorsque l'indicateur **Activer l'achèvement de la commande** est activé dans le canal du centre d'appels, la commande est lancée à partir de son statut En attente, mais l'indicateur **Ne pas traiter** reste défini. Par conséquent, la commande n'est pas lancée dans l'entrepôt jusqu'à ce que les paiements corrects aient été appliqués et validés.

Si les utilisateurs souhaitent supprimer un blocage mais effectuer des modifications supplémentaires à la commande avant de la lancer pour traitement, ils peuvent sélectionner l'option **Supprimer et modifier**. Cette option supprime le code de blocage et affiche les détails de la commande client afin que les utilisateurs puissent apporter des modifications supplémentaires à la commande. Les utilisateurs peuvent également appliquer le paiement et envoyer la commande client via la logique de validation du paiement lorsque l'indicateur **Activer l'achèvement de la commande** est activé dans le canal du centre d'appels.

## <a name="reporting-options"></a>Options de génération d'états

Accédez à **Retail et Commerce** \> **Recherches et états** \> **États du centre d'appels** \> **État des commandes en attente** pour exécuter un état sur les blocages de commande par plage de dates, code de blocage ou d'autres critères associés.
