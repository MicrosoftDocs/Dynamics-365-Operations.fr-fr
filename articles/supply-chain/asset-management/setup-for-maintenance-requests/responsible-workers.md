---
title: Agents de maintenance responsables
description: Cette rubrique explique comment paramétrer des agents de maintenance responsables dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427998"
---
# <a name="responsible-maintenance-workers"></a>Agents de maintenance responsables

[!include [banner](../../includes/banner.md)]

 

Les agents de maintenance responsables peuvent être associés aux types d'actif, aux actifs, aux postes techniques, aux catégories de type de tâche de maintenance, aux types de tâche de maintenance, aux variantes de type de tâche de maintenance et aux transactions. Ils peuvent être utilisés dans des ordres de travail et des demandes de maintenance pour indiquer une préférence concernant les agents de maintenance qui doivent être responsables d'un ordre de travail. (Toutefois, ces agents de maintenance ne sont pas nécessairement les mêmes que ceux planifiés pour exécuter l'ordre de travail). L'utilisation de cette fonctionnalité est facultative. Par exemple, elle peut être utilisée pour sélectionner des agents responsables ou des groupes d'agents pour des types de travail ou des domaines de travail spécifiques.

Durant le cycle de vie d'un ordre de travail ou le cycle de vie d'une demande de maintenance, les agents de maintenance responsables peuvent être modifiés ou mis à jour. Cette modification ou mise à jour peut être associée à, par exemple, un changement de l'état du cycle de vie de la demande de maintenance ou de l'état du cycle de vie de l'ordre de travail.

Le paramétrage dans la page **Agents de maintenance responsables** *n'est pas* utilisé lors de la planification des ordres de travail.

> [!NOTE]
> Dans le module Gestion des actifs, vous pouvez également paramétrer des agents de maintenance *préférés* qui peuvent être affectés aux ordres de travail lors de la planification des ordres de travail.

Avant de paramétrer des agents de maintenance responsables, vous devez paramétrer les agents et les groupes d'agents de maintenance qui doivent être disponibles pour sélection. Pour plus d'informations sur le paramétrage des agents et des groupes d'agents de maintenance, voir [Agents de maintenance et groupes d'agents](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Définir des agents de maintenance responsables

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Collaborateurs** \> **Agents de maintenance responsables**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. Créez d'abord un paramétrage d'agent de maintenance responsable ou de groupe d'agents de maintenance responsables par défaut, où vous définissez uniquement le champ **Groupe d'agents de maintenance responsables** et/ou le champ **Collaborateur responsable**. Laissez les autres champs vides. Ce paramétrage par défaut sera utilisé lors de la planification des ordres de travail si aucune autre combinaison plus spécifique ne correspond au contenu de l'ordre de travail.

    > [!NOTE]
    > Lors de la création d'une demande de maintenance, lorsqu'un agent de maintenance responsable ou un groupe d'agents de maintenance responsables est disponible pour sélection dans la page **Toutes les demandes de maintenance**, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements d'agent de maintenance responsable. Il vérifie toujours la combinaison la plus spécifique en premier. En d'autres termes, le module Gestion des actifs recherche d'abord une correspondance pour le champ **Transaction**. Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Variante du type de tâche de maintenance**. Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Type de tâche de maintenance**, etc. Comme vous pouvez voir dans la disposition de la page, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche (d'abord **Transaction**, puis **Variante du type de tâche de maintenance**, puis **Type de tâche de maintenance**, puis **Catégorie de type de tâche de maintenance**, puis **Poste technique**, puis **Actif** et enfin **Type d'actif**). Si aucune correspondance n'est trouvée, l'enregistrement par défaut qui ne comporte aucune sélection dans ces sept champs est utilisé.

L'illustration suivante présente un exemple de la page **Agents de maintenance responsables**.

![Page Collaborateurs responsables de la maintenance](media/08-setup-for-requests.png)
