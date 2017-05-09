---
title: "Ordres de contrôle"
description: "Cet article décrit la manière dont les ordres de contrôle sont utilisés pour bloquer le stock."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 394276e6908f2c1f6bc72eea061facc3afe701e9
ms.lasthandoff: 03/31/2017


---

# <a name="quarantine-orders"></a>Ordres de contrôle

[!include[banner](../includes/banner.md)]


Cet article décrit la manière dont les ordres de contrôle sont utilisés pour bloquer le stock. 

Les ordres de contrôle peuvent être utilisés pour bloquer le stock. Par exemple, vous pouvez contrôler des articles à des fins de contrôle de la qualité. Le stock qui a été mis en contrôle est transféré vers un entrepôt de contrôle. **Remarque :** Si vous utilisez des processus de gestion avancée des entrepôts (dans le module gestion des entrepôts), le traitement d'ordre de contrôle n'est utilisé que pour les commandes client retournées.

## <a name="quarantine-onhand-inventory-items"></a>Contrôler des articles disponibles dans le stock
Lorsque vous contrôlez des articles, vous pouvez créer des ordres de contrôle manuellement ou paramétrer le système pour que celui-ci crée des ordres de contrôle automatiquement lors du traitement entrant. Pour créer des ordres de contrôle automatiquement, sélectionnez l'option **Gestion des contrôles** dans l'onglet **Stratégies de stock** dans la page **Groupes de modèles d'article**. Vous devez également spécifier un entrepôt de contrôle par défaut dans le champ **Entrepôts de contrôle** pour les entrepôts de réception. Lorsque le stock physique disponible est enregistré dans une commande fournisseur ou un ordre de fabrication, les articles mis sous contrôle sont déplacés automatiquement dans des entrepôts de contrôle dans Microsoft Dynamics 365 for Operations. Ce mouvement se produit car le statut de l'ordre de contrôle est changé en **Commencé**. Lorsque vous créez des ordres de contrôle manuellement, il n'est pas nécessaire que l'article actuel soit paramétré pour la gestion des contrôles dans le groupe de modèles d'article associé. Pour ce processus, vous devez spécifier le stock disponible qui doit être mis sous contrôle et l'entrepôt de contrôle qui doit être utilisé. Utilisez les statuts d'ordre de contrôle pour aider à planifier le processus.

## <a name="quarantine-order-statuses"></a>Statuts de l'ordre de contrôle
Les ordres de contrôle peuvent avoir les statuts suivants :

-   Créé
-   Commencé
-   Déclaré terminé
-   Terminé

### <a name="created"></a>Créé

Lorsqu'un ordre de contrôle a été créé manuellement, mais que l'article n'est pas encore placé dans l'entrepôt de contrôle, l'ordre de contrôle a le statut **Créé**. Deux mouvements de stock sont générés. La première transaction est une transaction de sortie qui peut être dotée du statut **En commande**, **Physique réservé** ou **Prélevé**. Le deuxième est une transaction de réception qui peut avoir les statuts **Commandé** ou **Enregistré** à l'entrepôt de contrôle. Vous pouvez réserver, prélever et enregistrer les mises à jour du stock à l'aide des processus habituels.

### <a name="started"></a>Commencé

Quand un ordre de contrôle a le statut **Commencé**, le stock est transféré de l'entrepôt ordinaire vers l'entrepôt de contrôle et deux mouvements de stock sont générés. Une transaction a le statut **Déduit** et l'autre a le statut **Reçu**. En même temps, deux mouvements de stock sont créés pour gérer le transfert en retour. Ces transactions ne sont pas datées. Une transaction a le statut **Physique réservé** et l'autre a le statut **Commandé**.

### <a name="reported-as-finished"></a>Déclaré terminé

Pour déclarer un ordre de contrôle commencé comme terminé, cliquez sur **Déclaration de fin**. L'article n'est plus sous contrôle mais il n'est pas encore replacé dans l'entrepôt ordinaire. Le mouvement vers l'entrepôt ordinaire peut être traité via un Journal des arrivées d'articles pouvant être initialisé lors de l'État dans le cadre du processus de déclaration de fin.

### <a name="ended"></a>Terminé

Lorsqu'un ordre de contrôle prend fin, l'article est déplacé de l'entrepôt de contrôle vers l'entrepôt ordinaire. Le statut de la transaction d'article est défini sur **Vendu** au niveau de l'entrepôt de contrôle et sur **Acheté** au niveau de l'entrepôt ordinaire.

## <a name="quarantine-order-scrap"></a>Rebut d'ordre de contrôle
Dans le cadre du processus d'ordre de contrôle, vous pouvez mettre le stock au rebut. Lors du traitement d'une mise au rebut, le statut du stock sera défini sur **Vendu** par une transaction de sortie de l'entrepôt de contrôle.

<a name="see-also"></a>Voir également :
--------

[Blocage du stock](inventory-blocking.md)




