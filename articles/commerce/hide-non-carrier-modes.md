---
title: Masquer les modes de livraison hors transporteur dans les options d’expédition dans PDV
description: Cet article décrit une option de configuration qui peut empêcher les modes de livraison hors transporteur de s’afficher pour la sélection lorsque des ordres d’expédition sont créés dans l’application de point de vente (PDV).
author: hhainesms
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 469e6ebb8afed26a6bf25f4c9c3ab8f7f4ac78ba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897003"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Masquer les modes de livraison hors transporteur dans les options d’expédition dans PDV


[!include [banner](includes/banner.md)]

Cet article décrit une option de configuration disponible pour l’application de point de vente (PDV). Cette option de configuration modifie le comportement de la sélection d’un mode de livraison lorsque des ordres d’expédition sont créés dans PDV.

Lorsque les utilisateurs créent des ordres d’expédition client dans PDV, ils peuvent sélectionner un mode de livraison pour l’expédition. Cette fonctionnalité est disponible, que la commande soit expédiée dans son ensemble ou uniquement les lignes sélectionnées.

Par défaut, la boîte de dialogue dans laquelle un mode de livraison est sélectionné affiche tous les modes de livraison valides pour la combinaison d’un canal, d’un article et d’une adresse de livraison. Ces modes de livraison sont définis sur la page **Modes de livraison** de Headquarters (**Ventes et marketing \> Paramétrage \> Distribution \> Modes de livraison**). Les modes de livraison « hors transporteur », tels que **À emporter** ou **Prélèvement**, peuvent également être affichés pour la sélection dans la boîte de dialogue.

Toutefois, une fonctionnalité a été ajoutée pour vous permettre de masquer les modes de livraison hors transporteur dans la boîte de dialogue. Pour activer cette fonctionnalité, sur la page **Paramètres de commerce**, sous l’onglet **Commandes client**, définissez l’option **Afficher uniquement les options de mode transporteur pour les ordres d’expédition** sur **Oui**. Après avoir activé cette fonctionnalité et exécuté les tâches de distribution appropriées pour synchroniser les informations avec la base de données du canal, les modes de livraison hors porteur n’apparaissent pas pour la sélection au cours du processus de créer des ordres d’expédition dans PDV.


[!INCLUDE[footer-include](../includes/footer-banner.md)]