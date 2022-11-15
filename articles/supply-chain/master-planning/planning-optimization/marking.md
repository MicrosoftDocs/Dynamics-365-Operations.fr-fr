---
title: Marquage du stock
description: Cet article fournit des informations sur les options disponibles pour marquer le stock dans les commandes confirmées.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c86db6a670d7d0f7bfe74b7466b9bce766e4a08d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740574"
---
# <a name="inventory-marking"></a>Marquage du stock

[!include [banner](../../includes/banner.md)]

Cet article fournit des informations sur les options disponibles pour marquer le stock dans les commandes confirmées.

Le *Marquage* est utilisé pour relier l’offre et la demande. Il ressemble à l’*origine des besoins*, qui indique comment la planification prévoit de couvrir la demande. Du point de vue de la planification, la principale différence est que le marquage est plus permanent que l’origine des besoins.

Le marquage a été introduit pour prendre en charge des scénarios de coûts spéciaux pour le premier entré, premier sorti (FIFO) et le dernier entré, premier sorti (LIFO). Cependant, il est maintenant également utilisé pour certains scénarios sans coût. Le marquage entre l’offre et la demande est facultatif et presque permanent. Le marquage peut être supprimé manuellement par un utilisateur, ou il peut être supprimé en exécutant une explosion de ligne de commande client où l’option **Supprimer le marquage** est sélectionnée.

L’origine des besoins est contrôlé par la planification générale pendant la couverture pour lier la demande à l’offre requise. L’origine des besoins peut être mis à jour pour chaque cycle de planification afin d’optimiser l’approvisionnement nécessaire pour couvrir la demande. Lorsque la planification générale met à jour les informations d’origine des besoins, elle respecte tout marquage existant.

L’origine des besoins commence par inclure le marquage pertinent, les réservations disponibles et les réservations sur commande, dans l’ordre suivant :

1. Marquage entre demande et offre
1. Réservations disponibles
1. Réservation sur commande

Lorsque vous confirmez une commande planifiée, la boîte de dialogue **Confirmation** fournit un champ **Mettre à jour le marquage** que vous utilisez pour définir les options de marquage des commandes créées lors de la confirmation. Sélectionnez l’une des valeurs suivantes :

- *Non* – Aucun marquage de stock n’est appliqué.
- *Standard* – Le marquage du stock est mis à jour en fonction de l’origine des demandes. Un ordre de besoins (demande) est marqué par rapport à un ordre d’exécution de commande (offre). S’il reste une quantité sur l’ordre d’exécution, elle n’est pas marquée et les informations de référence sont laissées vides. Par exemple, si une commande client de 100 unités est liée à une commande d’achat de 150 unités, les informations de référence ne seront affectées qu’à la commande client.
- *Prolongé* - L’ordre de besoins (demande) et l’ordre d’exécution de commande (offre) sont marqués, indépendamment de la quantité restant dans l’ordre d’exécution de commande. Par exemple, si une commande client de 100 unités est liée à une commande d’achat de 150 unités, les informations de référence ne seront affectées qu’à la commande client et à la commande fournisseur.
- *Norme à niveau unique* – Marquage à niveau unique est utilisé. Le marquage à niveau marque uniquement l’article principal, et non ses composants de nomenclature (BOM). Par conséquent, vous pouvez conserver une affectation de composants flexible pour les ordres de fabrication après la confirmation. Le marquage à niveau unique permet au système d’optimiser les changements de demande de dernière minute. Dans la *norme* marquage à niveau unique, les commandes de besoins sont marquées par rapport à leurs commandes d’exécution, mais les commandes d’exécution ne sont pas marquées s’il reste de la quantité.
- *Prolongé à niveau unique* – Marquage à niveau unique est utilisé. Dans le marquage *prolongé* à niveau unique, les commandes de besoins sont marquées par rapport à leurs commandes d’exécution, et les commandes d’exécution sont toujours marquées, indépendamment du fait qu'il reste ou non une quantité.

Pour définir l’option de marquage par défaut pour votre système, accédez à **Planification générale \> Configurer \> Paramètres de planification générale**. Ensuite, sur l'onglet **Mise à jour standard**, définissez le champ **Mettre à jour le marquage** à votre option préférée.

> [!NOTE]
> Les options *Standard à niveau unique* et *Niveau unique étendu* ne sont disponibles que si la fonction *Automatisation de l’approvisionnement de fabrication à la commande* est activée sur votre système. Pour plus d’informations sur cette fonctionnalité et comment l’activer, voir [Automatisation de l’approvisionnement de fabrication à la commande](../make-to-order-supply-automation.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
