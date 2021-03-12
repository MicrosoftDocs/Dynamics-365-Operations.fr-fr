---
title: Statuts du stock
description: Cet article décrit la manière dont vous pouvez utiliser les statuts du stock pour classer et faire le suivi du stock.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4cad56389c7a8fd6d37591c1ff335fff715707
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001822"
---
# <a name="inventory-statuses"></a>Statuts du stock

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont vous pouvez utiliser les statuts du stock pour classer et faire le suivi du stock.

## <a name="set-up-and-use-inventory-statuses"></a>Configurer et utiliser les statuts de stock

Vous pouvez utiliser les statuts de stock pour classer le stock par catégorie. Vous pouvez ensuite initialiser les actions appropriées, telles qu'un réapprovisionnement ou un travail de rangement.

Voici quelques exemples d'utilisation des statuts de stock :

- Vous pouvez créer des statuts de stock pour un stock disponible, des transactions entrantes, et des transactions sortantes.
- Spécifier le statut de stock par défaut pour les transactions d'entrepôt.
- Vous pouvez modifier un statut de stock pour les articles avant l'arrivée, pendant l'arrivée, ou lorsque les articles sont rangés lors d'un mouvement de stock.
- Utiliser le statut de stock pour tarifer des articles qui sont retournés et pour planifier une couverture d'article lors de la planification.

Le statut du stock est l'une des dimensions dans le groupe de dimensions de stockage. Les statuts de stock peuvent être classés comme disponibles ou non disponibles, et vous pouvez utiliser le paramètre **Blocage du stock** pour bloquer les articles ayant un statut du stock disponible. Les articles dont le statut est bloqué sont considérés comme un stock physique et ne peuvent pas être utilisés dans un ordre de fabrication, une commande client, un ordre de transfert, ou une transaction sortante.

Vous pouvez utiliser des articles d'entrepôt dont les statuts de stock sont disponibles ou non disponibles pour un travail entrant. Par exemple, vous créez un statut disponible nommé *Prêt*, un statut non disponible nommé *Endommagé* et un statut bloqué nommé *Bloqué*. Lorsque vous créez une commande fournisseur pour des articles reçus ou retournés, si les articles sont endommagés ou arrêtés, vous pouvez modifier le statut de stock de ces articles sur *Endommagé* sur la ligne de commande fournisseur. Une fois ces articles reçus, le statut est automatiquement défini sur *Bloqué*. Si vous numérisez les articles endommagés à l'aide d'un appareil mobile, Supply Chain Management peut utiliser des directives d'emplacement et des modèles de travail pour afficher des informations sur un emplacement adapté ou une plage d'emplacements pour ranger ces articles. Pour les articles retournés, un type de sortie de *Réservation* est créé dans la page **Mouvements de stock**.

Pour un travail sortant, utilisez les articles qui ont un statut de stock disponible. Si vous avez des articles ayant un statut *Cassé*, et la planification est effectuée sur ces articles, les articles sont considérés comme manquants et le stock est automatiquement réapprovisionné.

Après avoir paramétré des statuts de stock, vous pouvez définir le statut du stock par défaut pour un site, un article, et un entrepôt. Vous pouvez également définir un statut par défaut pour les ventes, le transfert, les commandes fournisseur. Le statut par défaut pour les commandes client et l'ordre de transfert sortant ne peut pas avoir l'option **Blocage du stock** définie sur *Oui*. Le statut de stock qui est hérité des paramètres par défaut sur un site, un entrepôt, un article, une commande fournisseur, un ordre de transfert ou une commande client peut être modifié à l'aide de l'appareil mobile, ou sur la ligne de la commande fournisseur, de la commande client, ou de l'ordre de transfert.

Pour planifier la couverture pour les articles ayant un statut du stock disponible, sélectionnez l'option **Plan de couverture par dimension** pour une dimension de stockage dans la page **Groupes de dimensions de stockage**. Lorsque vous ouvrez l'Assistant **Couverture d'article**, les articles ayant un statut disponible s'affichent sur la page **Statut**. Pour créer des paramètres de couverture pour ces articles, sélectionnez l'ID de statut de stock pour les statuts de stock disponible. En fonction des paramètres de couverture, vous pouvez calculer les demandes d'articles et prévoir l'offre et la demande pour les articles disponibles pendant la planification. Vous ne pouvez pas créer un paramétrage de couverture d'article qui a un statut de stock bloqué. Sinon, utilisez la page **Couverture de l'article** pour créer ou modifier les paramètres de couverture d'article.

## <a name="change-inventory-statuses"></a>Modifier les statuts du stock

Vous pouvez modifier les statuts de stock en utilisant la page **Disponible par emplacement** ou en utilisant la tâche périodique *Changement du statut du stock*.

- Lors de l'utilisation de la tâche périodique *Changement du statut du stock*, vous pouvez sélectionner les enregistrements à inclure et définir la tâche à exécuter dans le lot à l'intervalle souhaité.
- Pour modifier l'état de l'inventaire en tant que processus ad hoc, accédez à la page **Sur place par emplacement**, sélectionnez les enregistrements appropriés, puis sélectionnez le bouton **Changement du statut du stock**.

> [!NOTE]
> La fonctionnalité *Modifier le statut du stock des articles contrôlés par le suivi des dimensions* vous permet de modifier le statut du stock des articles contrôlés par le suivi des dimensions, y compris la possibilité de mettre à jour uniquement les enregistrements sélectionnés. Utilisez la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonctionnalité selon les besoins. Lorsque la fonctionnalité est activée, vous pourrez effectuer les opérations suivantes :
>
> - Sur la page **Disponible par emplacement**, vous pouvez regrouper les lignes en fonction des dimensions affichées à l'aide de **Afficher les dimensions** et modifiez le statut des lignes sélectionnées.
> - Sur la page **Disponible par emplacement**, vous pouvez sélectionner plusieurs enregistrements, puis utiliser le bouton **Changement du statut du stock** pour les changer tous à la fois.
> - Sur la tâche périodique **Changement du statut du stock** vous pourrez filtrer en suivant les dimensions.
