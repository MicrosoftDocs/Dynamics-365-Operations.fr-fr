---
title: Masquer les modes de livraison hors transporteur dans les options d'expédition dans PDV
description: Cette rubrique décrit une option de configuration qui peut empêcher les modes de livraison hors transporteur de s'afficher pour la sélection lorsque des ordres d'expédition sont créés dans l'application de point de vente (PDV).
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 09ea83b3336b208f8af0a91025c2e6c50d64c385
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2019
ms.locfileid: "2659019"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Masquer les modes de livraison hors transporteur dans les options d'expédition dans PDV

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique décrit une option de configuration disponible pour l'application de point de vente (PDV). Cette option de configuration modifie le comportement de la sélection d'un mode de livraison lorsque des ordres d'expédition sont créés dans PDV.

Lorsque les utilisateurs créent des ordres d'expédition client dans PDV, ils peuvent sélectionner un mode de livraison pour l'expédition. Cette fonctionnalité est disponible, que la commande soit expédiée dans son ensemble ou uniquement les lignes sélectionnées.

Par défaut, la boîte de dialogue dans laquelle un mode de livraison est sélectionné affiche tous les modes de livraison valides pour la combinaison d'un canal, d'un article et d'une adresse de livraison. Ces modes de livraison sont définis sur la page **Modes de livraison** de Retail Headquarters (**Ventes et marketing \> Paramétrage \> Distribution \> Modes de livraison**). Les modes de livraison « hors transporteur », tels que **À emporter** ou **Prélèvement**, peuvent également être affichés pour la sélection dans la boîte de dialogue.

Toutefois, une fonctionnalité a été ajoutée pour vous permettre de masquer les modes de livraison hors transporteur dans la boîte de dialogue. Pour activer cette fonctionnalité, sur la page **Paramètres des ventes au détail**, sous l'onglet **Commandes client**, définissez l'option **Afficher uniquement les options de mode transporteur pour les ordres d'expédition** sur **Oui**. Après avoir activé cette fonctionnalité et exécuté les tâches de distribution appropriées pour synchroniser les informations avec la base de données du canal, les modes de livraison hors porteur n'apparaissent pas pour la sélection au cours du processus de créer des ordres d'expédition dans PDV.
