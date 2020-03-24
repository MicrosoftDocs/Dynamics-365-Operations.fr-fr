---
title: Modifier le mode de livraison dans le PDV
description: Cette rubrique décrit comment configurer et utiliser le mode de changement d'opération de livraison dans le PDV.
author: hhainesms
manager: annbe
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 26e798c664844b575de6f019ad8f5349ed92be98
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2020
ms.locfileid: "3114402"
---
# <a name="change-mode-of-delivery-in-pos"></a>Modifier le mode de livraison dans le PDV

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cette rubrique décrit comment configurer et utiliser la fonctionnalité « Modifier le mode de livraison » dans votre environnement de point de vente (PDV). 

Dans Dynamics 365 Commerce versions 10.0.10 et ultérieures, l'opération **Modifier le mode de livraison** (647) peut être ajoutée aux mises en page de votre écran de PDV.

La fonction de modification du mode de livraison vous offre la possibilité de modifier le mode de livraison pour une ou plusieurs lignes de vente configurées pour l'envoi sur la transaction du PDV. Dans les versions précédentes de Commerce, vous deviez parcourir l'intégralité des flux de configuration **Expédier tout** ou **Expédition sélectionnée** si vous souhaitez modifier le mode de livraison sur une ligne existante configurée pour l'expédition. Ce processus prenait du temps et pouvait entraîner des modifications accidentelles de l'origine ou des dates de livraison de la ligne. La nouvelle fonctionnalité fournit une méthode alternative pour mettre à jour efficacement le mode de livraison sur ces lignes de vente.

Pour plus d'informations sur l'ajout d'une opération à un bouton de votre grille de boutons de PDV, consultez [Mises en page de l'écran pour le point de vente](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).

Une fois cette fonctionnalité configurée dans le PDV, lorsque vous sélectionnez **Modifier le mode de livraison**, une page de liste vous sera présentée afin de choisir les lignes de la transaction dont vous souhaitez modifier le mode de livraison. Vous pouvez choisir certaines ou toutes les lignes, ou quitter sans apporter de modifications. Les lignes de vente précédemment configurées pour l'expédition sont les seules lignes de la liste que vous pouvez modifier. Si vous souhaitez modifier une ligne désignée pour le prélèvement ou le retrait à expédier, vous devez utiliser les opérations **Expédier tout** ou **Expédition sélectionnée**. Inversement, si vous souhaitez remplacer une ligne désignée comme expédition par un prélèvement ou un retrait, vous devez utiliser les opérations **Prélever tout**, **Prélèvement sélectionné**, **Exécuter tout** ou **Exécution sélectionnée**.

Après avoir sélectionné les lignes que vous souhaitez modifier, cliquez sur **Modifier le mode de livraison** pour être invité à sélectionner les options du mode de livraison. Si vous avez sélectionné plusieurs lignes à modifier, le PDV n'affichera que les modes de livraison qui ont été configurés comme étant autorisés pour tous les produits sélectionnés. Les modes de livraison peuvent être configurés pour prendre en charge des produits et des adresses de livraison spécifiques. S'il existe un mode de livraison acceptable pour une combinaison de produits et d'adresses, mais pas pour une autre combinaison de produits et d'adresses sélectionnée, le mode de livraison n'est pas disponible. Vous devrez peut-être sélectionner les lignes une par une et modifier le mode de livraison pour chaque ligne séparément si vous souhaitez sélectionner un mode de livraison pour un produit qui n'est pas pris en charge par un autre produit.  

Après avoir sélectionné le nouveau mode de livraison, la page de transaction s'affiche. Pour revoir vos nouvelles sélections de mode de livraison, sélectionnez l'onglet **Livraison** dans la liste des transactions.   
