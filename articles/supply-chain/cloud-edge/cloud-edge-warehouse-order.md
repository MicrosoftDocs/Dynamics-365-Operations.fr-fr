---
title: Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie
description: Cette rubrique fournit des informations sur la capacité de commandes d’entrepôt dans le cadre de la charge de travail de l’unité d’échelle d’entrepôt.
author: perlynne
manager: tfeyr
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9102f53ab1b63d08b8bba7b0ae505416ec5a83fd
ms.sourcegitcommit: 70b1567d316f19c15a4b032b4897f15c8dcdca09
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5556360"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Toutes les fonctionnalités d’entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque des charges de travail d’unité d’échelle sont utilisées. Si vous utilisez des unités d’échelle, veillez à n’utiliser que les processus que cette rubrique décrit explicitement comme pris en charge.

## <a name="what-are-warehouse-orders"></a>Que sont les commandes d’entrepôt ?

Les *commandes d’entrepôt* désignent un type de commande créée pour prendre en charge les déploiements en entrepôt de l’unité d’échelle et du hub. Ils vous permettent de recevoir un inventaire lorsque vous exécutez une charge de travail d’entrepôt sur une unité d’échelle. Actuellement, ils sont utilisés uniquement avec les commandes fournisseur.

Les commandes d’entrepôt sont utilisées dans le cadre du traitement de la gestion en entrepôt, comme lorsque l’application d’entreposage est utilisée pour enregistrer l’inventaire physique disponible pendant le traitement d’une commande fournisseur entrante. Les commandes d’entrepôt sont créées dans le cadre du processus *Libération dans l’entrepôt* disponible pour les commandes fournisseur qui précisent un entrepôt d’unité d’échelle et des éléments qui sont activés pour utiliser les processus de gestion de l’entrepôt.

> [!IMPORTANT]
> Les commandes d’entrepôt sont disponibles uniquement dans les déploiements qui utilisent les [charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Créer une commande d’entrepôt

Pour créer une commande d’entrepôt, procédez comme suit.

1. Connectez-vous à l’instance de Microsoft Dynamics 365 Supply Chain Management en cours d’exécution sur le hub. (Vous devez lancer le processus *Libération dans l’entrepôt* pendant que vous êtes connecté au hub.)
1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Libérer dans l’entrepôt**.
1. Pour afficher les lignes de la commande d’entrepôt associé, ouvrez la commande fournisseur pertinente, sélectionnez une ligne dans la section **Lignes de la commande fournisseur**, et sur la barre d’outils, sélectionnez **Entrepôt \> Lignes de la commande d’entrepôt**. Pour afficher toutes les lignes, accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.

Vous pouvez également déclencher le processus *Libération dans l’entrepôt* à partir d’un traitement par lots en accédant à **Gestion des entrepôts > Libération vers l’entrepôt > Libération automatique des commandes fournisseur**. Lors de la configuration du traitement par lots, vous pouvez sélectionner des lignes de commande fournisseur spécifiques en fonction d’une requête. Un scénario typique serait de configurer un traitement par lots récurrent qui libère toutes les lignes de commande fournisseur confirmées qui devraient arriver le jour suivant.

## <a name="cancel-a-warehouse-order"></a>Annuler une commande d’entrepôt

Dans le cadre du processus de *Libération dans l’entrepôt*, les transactions d’inventaire des commandes fournisseur sont liées aux commandes d’entrepôt et verrouillées pour ne pas être mises à jour par le hub. Si vous avez libéré vers l’entrepôt par erreur, ou si vous avez pour toute autre raison annulé la création des lignes de commande d’entrepôt, vous pouvez demander l’annulation des lignes de commande d’entrepôt.

Pour ce faire, procédez comme suit.

1. Connectez-vous à l’instance de Supply Chain Management en cours d’exécution sur le hub.
1. Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.
1. Sélectionnez la ligne appropriée.
1. Dans le volet Actions, sélectionnez **Annuler les lignes de commande d’entrepôt**.

> [!NOTE]
> La demande d’annulation de lignes sera refusée pour toutes les lignes qui sont déjà en attente d’annulation ou qui sont en cours de traitement dans un entrepôt qui exécute sa charge de travail sur une unité d’échelle.

## <a name="monitor-a-warehouse-order"></a>Surveiller une commande d’entrepôt

Dans la vue **Lignes de commande d’entrepôt**, vous pouvez surveiller la progression de la réception entrante en examinant les valeurs dans la colonne **Quantité en attente de réception**. Pour afficher les détails liés au travail effectué à l’aide de l’application d’entreposage, suivez l’une de ces étapes.

- Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt** et utilisez le filtre pour trouver les lignes que vous recherchez.
- Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur** et ouvrez la commande fournisseur pertinente. Dans la section **Lignes de commande fournisseur**, sélectionnez une ou plusieurs lignes, puis, dans la barre d’outils, sélectionnez **Entrepôt \> Entrées de réception d’entrepôt**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]