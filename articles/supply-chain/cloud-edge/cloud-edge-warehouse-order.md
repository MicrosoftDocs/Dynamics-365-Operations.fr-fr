---
title: Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie
description: Cet article fournit des informations sur la capacité de commandes d’entrepôt dans le cadre de la charge de travail de l’unité d’échelle d’entrepôt.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: db254216e6c34b81f83c87a8fda454d0aeb1cece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893524"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Commandes d’entrepôt pour les unités d’échelle Cloud et périphérie

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Toutes les fonctionnalités d’entreprise ne sont pas entièrement prises en charge dans la version préliminaire publique lorsque des charges de travail d’unité d’échelle sont utilisées. Si vous utilisez des unités d’échelle, veillez à n’utiliser que les processus que cet article décrit explicitement comme pris en charge.

## <a name="what-are-warehouse-orders"></a>Que sont les commandes d’entrepôt ?

Les *commandes d’entrepôt* désignent un type de commande utilisé pour prendre en charge les déploiements en entrepôt de l’unité d’échelle et du hub. Elles vous permettent de recevoir et d'expédier du stock lorsque vous exécutez une charge de travail d’entrepôt sur une unité d’échelle.

Les commandes d'entrepôt sont utilisées dans le cadre du traitement des entrées et des sorties de la gestion des entrepôts. Elles sont créées dans le cadre du processus *Lancement vers l'entrepôt*, qui est initialisé sur le hub.
Pour le traitement entrant, l'application mobile de l'entrepôt est utilisée pour enregistrer le stock physique disponible pendant le traitement des commandes entrantes; ceci est disponible pour les commandes achat et les ordres de production qui spécifient un entrepôt d'unité d'échelle et les articles qui sont activés pour utiliser les processus de gestion d'entrepôt.
Les commandes d'entrepôt sortantes sont utilisées dans le cadre du processus de transfert d'expédition pour les commandes de transfert et de vente.

> [!IMPORTANT]
> Les commandes d’entrepôt sont disponibles uniquement dans les déploiements qui utilisent les [charges de gestion d’entrepôt pour les unités d’échelle Cloud et périphérie](cloud-edge-workload-warehousing.md).

## <a name="create-an-inbound-warehouse-order"></a>Créer un ordre de transfert entrant dans l'entrepôt

Pour créer une commande d'entrepôt entrante pour un processus de commande fournisseur, procédez comme suit.

1. Connectez-vous à l’instance de Microsoft Dynamics 365 Supply Chain Management en cours d’exécution sur le hub. (Vous devez lancer le processus *Lancement vers l’entrepôt* pendant que vous êtes connecté au hub.)
1. Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans le volet Actions, sous l’onglet **Entrepôt**, dans le groupe **Actions**, sélectionnez **Lancement vers l’entrepôt**.
1. Pour afficher les lignes de la commande d’entrepôt associé, ouvrez la commande fournisseur pertinente, sélectionnez une ligne dans la section **Lignes de la commande fournisseur**, et sur la barre d’outils, sélectionnez **Entrepôt \> Lignes de la commande d’entrepôt**. Pour afficher toutes les lignes, accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.

Vous pouvez également déclencher le processus *Lancement vers l’entrepôt* à partir d’un traitement par lots en accédant à **Gestion des entrepôts > Lancement vers l’entrepôt > Lancement automatique des commandes fournisseur**. Lors de la configuration du traitement par lots, vous pouvez sélectionner des lignes de commande fournisseur spécifiques en fonction d’une requête. Un scénario typique serait de configurer un traitement par lots récurrent qui libère toutes les lignes de commande fournisseur confirmées qui devraient arriver le jour suivant.

## <a name="cancel-a-warehouse-order"></a>Annuler une commande d’entrepôt

Dans le cadre du processus de *Lancement vers l’entrepôt*, les transactions d’inventaire des commandes fournisseur sont liées aux commandes d’entrepôt et verrouillées pour ne pas être mises à jour par le hub. Si vous avez libéré vers l’entrepôt par erreur, ou si vous avez pour toute autre raison annulé la création des lignes de commande d’entrepôt, vous pouvez demander l’annulation des lignes de commande d’entrepôt.

Pour ce faire, procédez comme suit.

1. Connectez-vous à l’instance de Supply Chain Management en cours d’exécution sur le hub.
1. Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt**.
1. Sélectionnez la ligne appropriée.
1. Dans le volet Actions, sélectionnez **Annuler les lignes de commande d’entrepôt**.

> [!NOTE]
> La demande d’annulation de lignes sera refusée pour toutes les lignes qui sont déjà en attente d’annulation ou qui sont en cours de traitement dans un entrepôt qui exécute sa charge de travail sur une unité d’échelle.

## <a name="monitor-a-warehouse-order"></a>Surveiller une commande d’entrepôt

Dans la vue **Lignes de commande d’entrepôt**, vous pouvez surveiller la progression de la réception entrante en examinant les valeurs dans la colonne **Quantité en attente de réception**. Pour afficher les détails liés au travail effectué à l’aide de l’application mobile Warehouse Management, suivez l’une de ces étapes.

- Accédez à **Gestion des entrepôts \> Recherches et états \> Lignes de commande d’entrepôt** et utilisez le filtre pour trouver les lignes que vous recherchez.
- Accédez à **Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur** et ouvrez la commande fournisseur pertinente. Dans la section **Lignes de commande fournisseur**, sélectionnez une ou plusieurs lignes, puis, dans la barre d’outils, sélectionnez **Entrepôt \> Entrées de réception d’entrepôt**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
