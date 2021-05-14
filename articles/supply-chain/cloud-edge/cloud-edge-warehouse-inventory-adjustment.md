---
title: Ajustement du stock de l’entrepôt
description: Cette rubrique fournit des informations sur le journal d'ajustement des stocks de l'entrepôt et le traitement lorsque vous utilisez des unités d'échelle.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: be386539ea7addf20256ac2b1f8a2a72736fcbec
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938224"
---
# <a name="warehouse-inventory-adjustment"></a>Ajustement du stock de l’entrepôt

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La fonction d'ajustement du stock en entrepôt est utilisée lors de l'exécution des unités d'échelle cloud et de périphérie pour les [charges de travail de fabrication](cloud-edge-workload-manufacturing.md) et les [charges de travail de gestion d'entrepôt](cloud-edge-workload-warehousing.md).

Lorsqu'un collaborateur effectue un ajustement de stock à l'aide de l'application d'entrepôt pour une charge de travail de gestion d'entrepôt utilisant un unité d'échelle, le stock physique disponible doit être mis à jour par la tâche de traitement par lots **Journal d'ajustement des stocks d'entrepôt**, que vous exécutez et planifiez en accédant à **Gestion des entrepôts >Tâches périodiques > Journal d'ajustement des stocks d'entrepôt**.

Les processus de travail suivants de l'application d'entrepôt utilisent actuellement les charges de travail d'unité d'échelle **Journal d'ajustement des stocks d'entrepôt** :

- Ajustement (entrée/sortie)
- Inventaire tournant
- Chargement de contenant

Plusieurs transactions de stock sont créées dans le cadre du cloud et de la périphérie lors d'un processus d'ajustement, car les déploiements du hub et des unités d'échelle partagent les enregistrements de stock.

## <a name="inventory-adjustment-example"></a>Exemple d’ajustement de stock

Dans cet exemple, un magasinier a utilisé l'application d'entrepôt pour enregistrer un ajout de stock disponible.

Tout d'abord, la charge de travail de l'unité d'échelle crée une transaction d'ajustement de stock d'entrepôt pour ajustement physique positif, qui est ensuite synchronisée avec le hub et entraîne une augmentation du stock disponible sur le hub.

| Type                                    | Unité d’échelle | Direction | Hub |
|-----------------------------------------|------------|-----------|-----|
| Ajustement du stock de l’entrepôt          | +1         | ->        | +1  |

Le hub traite ensuite une écriture de journal de comptage, qui est reçue via les [messages du processeur de messages](cloud-edge-message-processor-messages.md). Cela met à jour le stock supplémentaire disponible. Pour éviter un double stock disponible, le hub crée une transaction de compensation dans le cadre de ce processus et supprime le stock disponible précédemment enregistré, lié à l'ajustement de stock d'entrepôt.

| Type                                    | Unité d’échelle | Direction | Hub |
|-----------------------------------------|------------|-----------|-----|
| Comptage                                | +1         | <-        | +1  |
| Ajustement de l'inventaire d'entrepôt (contrepartie) | -1         | <-        | -1  |

Une fois qu'une unité d'échelle a créé un **Journal d'ajustement des stocks d'entrepôt** sur le hub, vous pouvez consulter à la fois le **Journal de comptage** et le **Journal de compensation**, qui sont créés par le hub dans le cadre du processus d'ajustement.

Vous pouvez consulter chacune de ces écritures de journal et transactions dans Supply Chain Management en procédant comme suit :

1. Connectez-vous à l'unité d'échelle.
1. Accédez à **Gestion des entrepôts \> Tâches périodiques \> Journal d'ajustement des stocks d'entrepôt**.
1. Sur la page **Journal d'ajustement des stocks d'entrepôt**, recherchez et ouvrez le journal qui a enregistré la variation de stock disponible. La section **Lignes de journal** montre chaque ajustement enregistré par ce journal.
1. Connectez-vous au hub.
1. Accédez à **Gestion des entrepôts \> Tâches périodiques \> Journal d'ajustement des stocks d'entrepôt**.
1. Sur la page **Journal d'ajustement des stocks d'entrepôt**, vous devriez voir le même journal répertorié si le hub et l'unité d'échelle ont été synchronisés.
1. Ouvrez le journal. Si les [messages du processeur de messages](cloud-edge-message-processor-messages.md) ont été traités, vous verrez des liens vers le **Journal de comptage** et le **Journal de compensation** dans l'en-tête.
    - Le **Journal de comptage** doit afficher les mêmes valeurs de dimension que les lignes du journal.
    - Le **Journal de compensation** doit afficher la compensation, ce qui supprime le double ajustement de stock.
    > [!NOTE]
    > Une fois la synchronisation et le traitement terminés, le **Journal de comptage** et le **Journal de compensation** sont synchronisés avec l'unité d'échelle. Cela peut également être vérifié à partir de la page **Journal d'ajustement des stocks d'entrepôt**.
