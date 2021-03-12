---
title: Stratégies de réapprovisionnement
description: Cette rubrique fournit des informations sur les stratégies de réapprovisionnement et explique comment vous pouvez utiliser le champ Stratégie de réapprovisionnement sur les lignes de modèle de réapprovisionnement de la demande de vague pour sélectionner le mode de réapprovisionnement.
author: mirzaab
manager: tfehr
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 9c23126c6ab15a1924b34f98d33a0661011ba8bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996096"
---
# <a name="replenishment-strategies"></a>Stratégies de réapprovisionnement

[!include [banner](../includes/banner.md)]

Les modèles définis sur les **Modèles de réapprovisionnement** incluent des lignes de modèle de réapprovisionnement de la demande de vague qui vous permettent de sélectionner la façon dont le réapprovisionnement est effectué. Chaque ligne comprend désormais un champ **Stratégie de reconstitution**.

La stratégie *Quantité de demande de vague* est la stratégie par défaut. C'est la stratégie de réapprovisionnement qui a été utilisée avant l'introduction du champ **Stratégie de réapprovisionnement**. Il utilise les directives d'emplacement de réapprovisionnement pour trouver les emplacements qui peuvent être réapprovisionnés. Il réapprovisionne ensuite ces emplacements jusqu'à ce que la demande soit couverte.

La stratégie *Capacité maximale d'emplacement* introduit de nouvelles fonctionnalités. Comme la stratégie *Quantité de demande de vague*, cette stratégie utilise les directives d'emplacement de réapprovisionnement pour trouver les emplacements qui peuvent être réapprovisionnés, puis elle réapprovisionne ces emplacements jusqu'à ce que la demande soit couverte. Elle diffère de la stratégie *Quantité de demande de vague* en ce que tous les emplacements réapprovisionnés sont réapprovisionnés à leur capacité maximale, telle que définie par les limites de stockage des emplacements. La stratégie *Capacité maximale d'emplacement* tente de créer du travail pour apporter la quantité demandée, plus une quantité supplémentaire, pour remplir les emplacements qui sont réapprovisionnés. Cependant, dans certains cas, cette tentative peut échouer. Par exemple, les emplacements en vrac peuvent ne pas avoir suffisamment de stock pour couvrir la quantité supplémentaire. Dans ces cas, le système détecte l'échec et tente de récupérer.

La haute saison est un exemple de situation où la stratégie *Capacité maximale d'emplacement* est préférable à la stratégie *Quantité de demande de vague*. Pendant la haute saison, certains articles peuvent se vendre à un volume élevé. Par conséquent, vous souhaiterez peut-être réapprovisionner de manière proactive les emplacements de prélèvement appropriés autant que possible, afin de réduire le nombre d'ID de travail créés pour le réapprovisionnement.

> [!IMPORTANT]
> Pour profiter pleinement de la stratégie *Capacité maximale d'emplacement*, vous devez redéfinir les limites de stockage pour les emplacements concernés. Sinon, cette stratégie fonctionne comme la stratégie *Quantité de demande de vague*.

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a>Activez la fonction Réapprovisionner au maximum en fonction des limites de stockage

Avant de pouvoir utiliser cette fonctionnalité, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l'espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de cette fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Réapprovisionner au maximum en fonction des limites de stockage*

## <a name="set-up-replenishment-strategies"></a>Configurer les stratégies de réapprovisionnement

Pour accéder aux modèles, accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement**. Dans la section **Aperçu**, sélectionnez ou créez un modèle de réapprovisionnement de la demande de vague où le champ **Type de réapprovisionnement** est défini sur *Demande de vague*. Configurez ensuite les lignes de modèle de réapprovisionnement dans la section **Détails du modèle de réapprovisionnement**. Pour chaque ligne, dans le champ **Stratégie de réapprovisionnement**, sélectionnez la stratégie de réapprovisionnement que vous souhaitez utiliser.

![Page Modèles de réapprovisionnement](media/ReplenTempWaveDmdMaxLocCap.png "Page Modèles de réapprovisionnement")

Si la colonne **Stratégie de réapprovisionnement** n'apparaît pas dans la grille dans la section **Détails du modèle de réapprovisionnement**, assurez-vous que la fonction a été activée et que le modèle de réapprovisionnement sélectionné a un type de réapprovisionnement de *Demande de vague*.

> [!NOTE]
> La stratégie *Quantité de demande de vague* est la stratégie par défaut. Par conséquent, il vous suffit de mettre à jour les lignes du modèle de réapprovisionnement où vous souhaitez utiliser la stratégie *Capacité maximale d'emplacement* à la place.

## <a name="example-scenarios"></a>Exemple de scénarios

### <a name="example-1"></a>Exemple 1

Pour cet exemple, il n'existe qu'un seul modèle de réapprovisionnement qui n'a qu'une seule ligne de modèle de réapprovisionnement.

Vous créez une commande client pour 130 pièces (pcs) de l'article A0001. Avant de lancer la commande vers l'entrepôt, l'entrepôt est configuré de la manière suivante :

- Il n'y a qu'un seul emplacement en vrac, et il dispose de 500 pièces de stock disponibles.
- Il existe trois emplacements de prélèvement, chacun ayant une limite de stockage de 100 pièces. (N'oubliez pas que des limites de stockage sont requises pour la stratégie *Capacité maximale d'emplacement*.)
- Les emplacements de prélèvement de réapprovisionnement seront les mêmes que les points de vente.
- L'unité de réapprovisionnement est une boîte (1 boîte = 20 pièces).

Au moment de la commande, le stock suivant est disponible aux points de vente :

- **Pick-001 :** 20 pièces (1 boîte)
- **Pick-002 :** 0 pièces
- **Pick-003 :** 0 pièces

Au départ, la stratégie de réapprovisionnement est définie sur *Quantité de demande de vague*.

Une fois que vous avez lancé la commande client dans l'entrepôt et que le traitement de la vague est exécuté pour la vague, vous obtenez le travail de réapprovisionnement suivant :

- **Travail de réapprovisionnement 1 :** Choisissez 4 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-001.
- **Travail de réapprovisionnement 2 :** Choisissez 2 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-002.

Vous obtenez deux ID de travail de réapprovisionnement, car vous devez réapprovisionner deux emplacements et les rangements multiples ne sont pas pris en charge.

Si vous définissez la stratégie de réapprovisionnement sur *Capacité maximale d'emplacement* à la place, vous obtenez le travail de réapprovisionnement suivant :

- **Travail de réapprovisionnement 1 :** Choisissez 4 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-001.
- **Travail de réapprovisionnement 2 :** Choisissez 5 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-002.

[![Exemple 1](media/ReplenTemp_example_1.png "Exemple 1")](media/ReplenTemp_example_1_large.png)

### <a name="example-2"></a>Exemple 2

Cet exemple montre ce qui se passe lorsque l'emplacement en vrac ne dispose pas d'un stock suffisant pour couvrir la quantité supplémentaire. Il utilise le même scénario que l'exemple 1, mais l'emplacement en vrac a 160 pièces (8 boîtes).

La stratégie *Quantité de demande de vague* crée le même travail que dans l'exemple 1.

Cependant, parce que la stratégie *Capacité maximale d'emplacement* tente de créer les ID de travail comme elle l'a fait dans l'exemple 1, elle peut échouer. À ce stade, le système tente de récupérer.

Selon le paramètre de l'option **Autoriser le fractionnement** sur les directives d'emplacement pour le prélèvement de réapprovisionnement, deux résultats sont possibles :

- Si l'option **Autoriser le fractionnement** est définie sur *Oui*, le travail de réapprovisionnement suivant est créé :

    - **Travail de réapprovisionnement 1 :** Choisissez 4 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-001.
    - **Travail de réapprovisionnement 2 :** Choisissez 4 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-002.

- Si l'option **Autoriser le fractionnement** est définie sur *Non*, le travail de réapprovisionnement suivant est créé :

    - **Travail de réapprovisionnement 1 :** Choisissez 4 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-001.
    - **Travail de réapprovisionnement 2 :** Choisissez 2 boîtes dans l'emplacement en vrac et placez-les au point de vente pick-002.

Les résultats diffèrent en raison des informations disponibles lorsque vous créez le travail. Quand **Autoriser le fractionnement** est défini sur *Oui* sur les directives d'emplacement pour le prélèvement de réapprovisionnement, vous savez que vous avez réussi à trouver 160 pièces. Par conséquent, vous pouvez créer du travail pour cette quantité. Cependant, lorsque l'option **Autoriser le fractionnement** est définie sur *Non*, vous ne connaissez pas l'existence des 160 pcs. Comme la quantité supplémentaire que vous avez décidé de réapprovisionner était de 3 boîtes, vous supprimez cette quantité supplémentaire et essayez à nouveau la quantité d'origine.

[![Exemple 2](media/ReplenTemp_example_2.png "Exemple 2")](media/ReplenTemp_example_2_large.png)

Par conséquent, pour obtenir la quantité maximale vers les emplacements réapprovisionnés, vous devez définir l'option **Autoriser le fractionnement** sur *Oui* sur les directives d'emplacement pour le prélèvement de réapprovisionnement.
