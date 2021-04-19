---
title: Rappeler l’opération de commande dans le PDV
description: Cette rubrique explique les fonctionnalités disponibles pour les pages de rappel de commande améliorées dans le PDV.
author: hhainesms
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2f7ad4f53917bb607afe84a2c457518c3f8f7a08
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799104"
---
# <a name="recall-order-operation-in-pos"></a>Rappeler l’opération de commande dans le PDV

[!include [banner](includes/banner.md)]

L’opération de **rappel de commande** dans le point de vente (PDV) Commerce fournit des fonctionnalités de recherche et de filtre de commande mises à jour ainsi que des informations spécifiques à la commande. Cette fonctionnalité est disponible dans les versions de Commerce 10.0.15 et ultérieures.

Pour activer cette fonctionnalité, activez la fonctionnalité **Rappeler l’opération de commande dans le PDV améliorée** dans l’espace de travail **Gestion des fonctionnalités** au siège de Commerce. Après avoir activé la fonctionnalité, pensez à mettre à jour les [dispositions de l’écran](pos-screen-layouts.md) dans PDV pour profiter de certaines des fonctionnalités modifiées.

La configuration du bouton de l’opération **Rappeler la commande** permet aux organisations de déployer l’opération avec un affichage prédéfini.

![Configuration de la grille de boutons](media/recallorderbuttongrid.png)

Les options d’affichage sont les suivantes.
- **Aucun** - Cette option déploie l’opération sans affichage spécifique. Lorsqu’un utilisateur ouvre l’opération avec cette configuration, il sera invité à rechercher et trouver des commandes ou à choisir un filtre de commande prédéfini.
- **Commandes à traiter** - Lorsqu’un utilisateur lance l’opération, une requête s’exécute automatiquement pour rechercher et afficher une liste des commandes qui doivent être traitées par le magasin actuel de l’utilisateur. Ces commandes sont configurées pour un retrait en magasin ou une expédition en magasin, et les lignes de ces commandes n’ont pas encore été prélevées ou emballées.
- **Commandes à prélever** - Lorsqu’un utilisateur lance l’opération, une requête s’exécute automatiquement pour rechercher et afficher une liste des commandes qui doivent être configurées pour un retrait en magasin dans le magasin actuel de l’utilisateur.
- **Commandes à expédier** - Lorsqu’un utilisateur lance l’opération, une requête s’exécute automatiquement pour rechercher et afficher une liste des commandes qui doivent être configurées pour être expédiées depuis le magasin actuel de l’utilisateur.

Lors du lancement de l’opération **Rappel de la commande** à partir du PDV, si l’écran est configuré pour **Aucun**, un utilisateur pourra rechercher et récupérer des commandes de l’une des manières suivantes.
- Numérisez les codes-barres des commandes. Cette opération effectue une recherche de correspondances dans les champs du numéro de commande, de la référence de canal et d’ID de ticket de caisse.
- Sélectionnez l’icône **Rechercher les commandes** ou **Rechercher et filtrer** sur la barre des applications pour utiliser le mécanisme de filtre afin de localiser les commandes qui répondent aux critères de filtre.
- Choisissez un filtre prédéfini dans le menu déroulant **Afficher les commandes** (commandes à traiter, commandes à prélever ou commandes à expédier).

![RecallOrderMainMenu](media/recallordermain.png)

Après application des critères de recherche, l’application affichera une liste des commandes client correspondantes. Il est important de noter que lors de l’utilisation des options de recherche/filtrage, les commandes récupérées ne doivent pas nécessairement être des commandes liées au magasin actuel de l’utilisateur. Ce processus de recherche récupérera et affichera toute commande client qui correspond aux critères de recherche, même si la commande a été créée ou définie pour être exécutée par un autre magasin, canal ou emplacement d’entrepôt.

![RecallOrderDetail](media/orderrecalldetail.png)

Un utilisateur peut sélectionner une commande dans la liste pour afficher des détails supplémentaires. Le panneau d’informations situé sur le côté droit de l’écran affiche les détails de la commande sélectionnée, y compris les détails de la ligne de commande, les détails de livraison et les détails d’exécution.

Dans la barre des applications, un utilisateur peut sélectionner une opération. Selon l’état de la commande, certaines opérations peuvent ne pas être activées.

- **Retourner** - Lance le processus de création d’un retour pour l’un des produits facturés sur la commande client sélectionnée.

- **Annuler** - Émet une annulation complète de la commande client sélectionnée. Cette option ne sera pas disponible pour les commandes initiées via un canal de centre d’appels et ne peut pas être utilisée pour annuler partiellement une commande.

- **Traiter** - Transfère l’utilisateur vers la page de traitement de la commande, qui sera pré-filtrée pour la commande sélectionnée. Seules seront affichées les lignes de commande ouvertes pour le traitement par le magasin de l’utilisateur pour la commande sélectionnée.

- **Modifier** - Permet aux utilisateurs d’apporter des modifications à la commande client sélectionnée. Les commandes ne sont modifiables que dans [certains scénarios](customer-orders-overview.md#edit-an-existing-customer-order).

- **Prélever** - Cette option sera disponible si la commande comporte une ou plusieurs lignes désignées pour le prélèvement dans le magasin actuel de l’utilisateur. Cette opération lance le flux de prélèvement, qui permet à l’utilisateur de choisir les produits à prélever et crée la transaction de prélèvement.

## <a name="add-notifications-to-the-recall-order-operation"></a>Ajouter des notifications pour rappeler l’opération de commande

Dans les versions 10.0.18 et ultérieures, vous pouvez configurer les notifications de PDV et les alertes de vignettes actives pour l’opération **Rappel de commande**. Pour plus d’informations, voir [Afficher les notifications de commande dans le point de vente (PDV)](notifications-pos.md).  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
