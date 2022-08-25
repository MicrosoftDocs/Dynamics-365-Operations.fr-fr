---
title: Traiter les retraits de commandes client dans le PDV
description: Cet article explique la fonctionnalité disponible dans l’application de point de vente (PDV) pour traiter les retraits de commandes client.
author: hhainesms
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 7fd7d08ac59f6fe7381b79d854160188ef1c325a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286355"
---
# <a name="process-customer-order-pickups-in-pos"></a>Traiter les retraits de commandes client dans le PDV

[!include [banner](includes/banner.md)]

Lorsqu’une [commande client](customer-orders-overview.md) est prête à être retirée en magasin, un utilisateur du magasin peut utiliser l’application de point de vente (POS) pour démarrer le retrait en stock. Le PDV exécutera la capture du paiement final selon les besoins. Il va également imputer les quantités prélevées dans l’inventaire et la comptabilisation financière.

Si vous êtes un utilisateur du magasin, vous pouvez effectuer le retrait en utilisant soit l’opération **Rappeler la commande** soit l’opération **Exécution des commandes** dans le PDV. Pour rendre l’opération de **retrait** disponible, vous devez d’abord suivre l’une de ces étapes :

- Pour utiliser l’opération **Rappeler la commande**, recherchez et sélectionnez la commande qui sera retirée.
- Pour utiliser l’opération **Exécution des commandes**, recherchez et sélectionnez une ou plusieurs lignes de commande.

Si la commande ou les lignes de commande sélectionnées ne sont pas configurées pour le retrait dans ce magasin spécifique, ou si la commande a déjà été entièrement retirée, l’opération de **retrait** ne sera pas disponible.

![Opération de retrait.](media/pickupoperation.png)

Dans Microsoft Dynamics 365 Commerce version 10.0.17 et ultérieure, la fonction **Expérience utilisateur améliorée pour le traitement des commandes à retirer dans le point de vente** peut être activée via la gestion des fonctionnalités dans Commerce Headquarters. Si cette fonction est désactivée, les utilisateurs ne peuvent pas sélectionner les quantités à retirer. Par défaut, la quantité totale qui a été commandée pour la ligne est la quantité qui sera retirée. Cette expérience peut être problématique, car les utilisateurs peuvent oublier de sélectionner certains articles pour le retrait lorsqu’ils effectuent le retrait via le traitement des commandes.

La fonction **Expérience utilisateur améliorée pour le traitement des commandes à retirer dans le point de vente** donne aux utilisateurs plus de contrôle sur la sélection et la quantité de produits qui seront retirés. Les utilisateurs n’ont pas à sélectionner chaque ligne de la commande client sur la page d’exécution de la commande avant de sélectionner **Retirer**. Tous les articles pouvant être retirés seront affichés. Les utilisateurs peuvent spécifier plusieurs lignes pour le retrait même si une seule ligne de produits est sélectionnée.

Quand la fonction **Expérience utilisateur améliorée pour le traitement des commandes à retirer dans le point de vente** est activée et que vous sélectionnez l’opération **Retirer**, la boîte de dialogue **Retirer** apparaît. Vous pouvez alors sélectionner les articles et les quantités qui seront retirées. Par défaut, toute quantité commandée dont le stock est dans un état retiré ou emballé est considérée comme éligible pour le retrait. Par défaut, cette quantité est définie comme quantité à retirer. Vous pouvez modifier la quantité saisie, à condition qu’elle ne soit pas de 0 (zéro) et ne dépasse pas la quantité totale ouverte (c’est-à-dire non facturée) pour la ligne sélectionnée.

![Boîte de dialogue Retrait.](media/pickupselect.png)

Après avoir sélectionné les quantités qui seront retirées, sélectionnez **Retrait** et la page de transaction apparaît. Si la fonction de [paiements omnicanaux](omni-channel-payments.md) est activée, et qu’il y a des paiements préautorisés par carte de crédit dans le dossier, vous devez appliquer le paiement.

Sur la page de transaction, le système calcule les montants dus en calculant le total dû pour les articles de retrait sélectionnés, puis en soustrayant les dépôts précédemment appliqués ou les paiements par carte de crédit autorisés. Vous devez traiter le paiement pour terminer la transaction de retrait. Si la [mise en page de l’écran](pos-screen-layouts.md) de la page de transaction est configurée pour inclure l’opération **Conclure la transaction**, et qu’aucun montant n’est dû, vous pouvez terminer la transaction sans sélectionner de mode de paiement. Si l’opération **Conclure la transaction** n’est pas disponible, vous pouvez sélectionner le lien **Montant de 0,00 $ dû** dans le volet **Totaux** pour conclure la transaction sans avoir à sélectionner de mode de paiement.

![Page de transaction pour une transaction de retrait de commande client.](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Modification des lignes ou des quantités à retirer

Si vous devez modifier la quantité à retirer après avoir sélectionné les articles qui seront retirés, vous pouvez sélectionner **Définir la quantité**. Vous ne pouvez pas définir la quantité à retirer sur **0** (zéro) ou l’augmenter à une valeur qui dépasse la quantité non facturée qui reste pour la ligne commandée. Pour supprimer une ligne de retrait du panier de transaction, sélectionnez **Annuler la transaction**. La transaction en cours sera arrêtée et le flux de l’opération **Retrait** sera redémarré.

Si la fonction **Expérience utilisateur améliorée pour le traitement des commandes à retirer dans le point de vente** est activée, les organisations peuvent ajouter un bouton pour l’opération **Changer les lignes de retrait** dans la mise en page de l’écran de la page de transaction. Après avoir créé le panier de transaction pour le retrait dans le PDV et sélectionné les articles, vous pouvez sélectionner **Changer les lignes de retrait** si vous devez changer les articles à retirer mais que vous ne voulez pas annuler toute la transaction. Dans la boîte de dialogue **Changer les lignes de retrait** qui apparaît, vous pouvez modifier les articles et les quantités à retirer. Le panier de transaction est ensuite mis à jour pour refléter vos modifications.

![Boîte de dialogue Modifier les articles de retrait.](media/pickupchange.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
