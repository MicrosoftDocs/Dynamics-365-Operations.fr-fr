---
title: Inverser le statut d’ordre de fabrication
description: Cet article décrit la procédure pour contrepasser le statut de l’ordre de fabrication.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmStatusDecrease, ProdSetupStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d50cbcb4031d5c9f2c814883afd1fb38777d2ba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903954"
---
# <a name="reverse-the-production-order-status"></a>Inverser le statut d’ordre de fabrication

[!include [banner](../includes/banner.md)]

Cet article décrit la procédure pour contrepasser le statut de l’ordre de fabrication. 

Le fait d’inverser le statut d’un ordre de fabrication ramène l’ordre et toutes les opérations associées aux gammes à une étape précédente du cycle de vie de la production. Par exemple, un ordre de fabrication a le statut **Prévu**, et vous rétablissez son statut sur **Créé**. Dans ce cas, le système doit d’abord définir le statut sur **Estimé**, qui est le statut qui vient juste avant le statut **Prévu**. Il peut ensuite modifier le statut pour le définir sur le statut souhaité, **Créé**. **Remarque :** si votre ordre a atteint le statut **Déclaration de fin**, il est toujours possible de rétablir un statut antérieur. Cependant, vous devez réexécuter une estimation et un ordonnancement ou une planification des tâches ou les deux types de planification pour mettre à jour les informations relatives à l’ordre. Cette étape est nécessaire, car les réservations de la consommation d’articles restants et de la consommation des ressources opérationnelles doivent également être redéfinies. Le reste de cet article décrit ce qui se produit lorsque vous contrepassez le statut d’un ordre de fabrication comme suit :

-   Du statut **Estimé** au statut **Créé**
-   Du statut **Prévu** au statut **Estimé**
-   Du statut **Lancé** au statut **Prévu**
-   Du statut **Commencé** au statut **Lancé**

## <a name="from-estimated-to-created"></a>Du statut Estimé au statut Créé
Lorsque vous contrepassez le statut d’un ordre de fabrication d’**Estimé** à **Créé**, la consommation d’articles calculée pour les articles dans la nomenclature est supprimée. Les mouvements de stock dans la ligne de production sont supprimés et le champ **Statut du solde** des lignes de nomenclature de l’ordre de fabrication est redéfini sur la valeur **Terminé**. Lorsque les options **Achats déduits** et **Production déduite** sont sélectionnées, les commandes fournisseur ou les ordres de fabrication sous-jacents sont supprimés. Si vous avez estimé les coûts de l’ordre de fabrication ou si vous avez réservé manuellement des articles en vue de leur utilisation dans la production, ces transactions sont supprimées.

## <a name="from-scheduled-to-estimated"></a>Du statut Prévu au statut Estimé
Lorsque vous contrepassez le statut d’un ordre de fabrication de **Prévu** à **Estimé**, les dates et heures de début et de fin prévues sont supprimées. Les réservations de capacité effectuées pendant la planification sont supprimées de même que les tâches créées pendant la planification des tâches. Toutes les informations enregistrées relatives à l’ordonnancement et à la planification des tâches dans la page **Détails de l’ordre de fabrication** sont réinitialisées.

## <a name="from-released-to-scheduled"></a>Du statut Lancé au statut Prévu
Lorsque vous contrepassez le statut d’un ordre de fabrication de **Lancé** à **Prévu**, seule la valeur du champ de statut est modifiée.

## <a name="from-started-to-released"></a>Du statut Commencé au statut Lancé
Lorsque vous contrepassez le statut d’un ordre de fabrication de **Commencé** à **Lancé**, tous les articles déclarés comme terminés sont redéfinis. Si du matériel a été prélevé ou si des livraisons entrantes ou sortantes ont été effectuées en production, ces paramètres sont contrepassés. Le champ **Statut du solde** des lignes de nomenclature de l’ordre de fabrication passe de **Terminé** à **Consommation de matières**. Si le délai a été enregistré ou si des quantités ont été déclarées comme terminées pour les opérations de la gamme de production, ces paramètres sont contrepassés. Le champ **Statut du solde** passe de **Terminé** à **Consommation de gamme** dans la gamme de production. Les paramètres de tous les articles validés comme étant en cours ou des travaux en cours sont contrepassés. Dans la page **Détails de l’ordre de fabrication**, les champs qui indiquent une quantité commencée ou déclarée comme terminée sont réinitialisés. Les dates pour ces transactions sont également réinitialisées.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]