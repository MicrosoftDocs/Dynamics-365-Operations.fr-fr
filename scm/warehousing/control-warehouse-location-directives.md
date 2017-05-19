---
title: "Contrôler le travail d&quot;entrepôt à l&quot;aide de modèles de travail et d&quot;instructions d&quot;emplacement"
description: "Cet article décrit comment utiliser les modèles de travail et les instructions d&quot;emplacement pour déterminer comment et à quel endroit effectuer les travaux dans l&quot;entrepôt."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e90741b9151f19c70923685fdf1edb2552296a08
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Contrôler le travail d'entrepôt à l'aide de modèles de travail et d'instructions d'emplacement

[!include[banner](../includes/banner.md)]


Cet article décrit comment utiliser les modèles de travail et les instructions d'emplacement pour déterminer comment et à quel endroit effectuer les travaux dans l'entrepôt.

Les instructions que les magasiniers reçoivent sur un appareil mobile sont déterminées par les modèles de travail que vous paramétrez dans Microsoft Dynamics 365 for Operations afin de définir les divers processus et tâches d'entrepôt. Les modèles de travail déterminent la manière dont le travail est effectuée pour chaque processus d'entrepôt. En liant une instruction d'emplacement à des modèles de travail, vous pouvez garantir que le travail se produit dans des zones physiques spécifiques des entrepôts.

## <a name="work-templates"></a>Modèles de travail
La page **Modèles de travail** vous permet de définir les opérations de travail qui doivent être effectuées dans l'entrepôt. Généralement, les opérations de travail d'entrepôt se composent d'une paire d'actions : un magasinier prend un stock disponible dans un emplacement et le range dans un autre emplacement. 

Les modèles de travail se composent d'un en-tête et de lignes associées. Chaque modèle de travail concerne un *type d'ordre de travail* spécifique. Plusieurs types d'ordres de travail sont associés aux documents source, tels que les commandes fournisseur ou client. Toutefois, les autres types d'ordres de travail représentent des processus distincts d'entrepôt, tels que l'inventaire tournant. Les *ID de pool de travail *vous permettent d'organiser le travail en groupes. 

Les paramètres dans la définition d'en-tête de travail peuvent être utilisés pour déterminer le moment où un nouveau travail doit être créé. Par exemple, vous pouvez définir un nombre maximal de lignes de prélèvement et un temps prévu de sélection maximal. Ensuite, si le travail pour un processus de prélèvement de commande client dépasse l'une de ces valeurs, ce travail est fractionné en deux travaux. 

Les lignes de travail représentent les tâches physiques requises afin de traiter le travail. Par exemple, pour un processus sortant d'entrepôt, il peut y avoir une ligne de travail pour prélever les articles dans l'entrepôt et une autre ligne pour ranger ces articles dans une zone de transit. Il peut ensuite y avoir une ligne supplémentaire pour prélever les articles dans la zone de transit, et une autre ligne pour mettre les articles dans un camion dans le cadre du processus de chargement. Vous pouvez définir un *code directif *sur les lignes de modèle de travail. Un code directif est lié à une instruction d'emplacement et donc permet de garantir que le travail d'entrepôt est traité dans l'emplacement approprié de l'entrepôt. 

Vous pouvez paramétrer une requête pour contrôler le moment où un modèle particulier de travail est utilisé. Par exemple, vous pouvez définir une limitation afin qu'un modèle spécifique puisse être utilisé pour le travail uniquement dans un entrepôt particulier. Sinon, vous pouvez avoir plusieurs modèles utilisés pour créer le travail pour le traitement de la commande client sortante, en fonction de l'origine des ventes. Le système utilise le champ **N° de souche** pour déterminer l'ordre dans lequel les modèles de travail disponibles sont évalués. Par conséquent, si vous avez une requête très spécifique pour un modèle particulier de travail, vous devez lui attribuer un faible numéro de souche. Cette requête sera alors évaluée avant d'autres requêtes plus générales. 

Pour arrêter ou suspendre un processus de travail, vous pouvez utiliser le paramètre **Arrêter le travail** dans la ligne de travail. Dans ce cas, le collaborateur qui exécute le travail n'est pas invité à effectuer l'étape de la ligne de travail suivante. Pour passer à l'étape suivante, ce collaborateur ou un autre doit resélectionner le travail. Vous pouvez également séparer les tâches dans un travail en utilisant un autre *ID classe de travail *dans les lignes de modèle de travail.

## <a name="location-directives"></a>Instructions d'emplacement
Les instructions d'emplacement sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock. Par exemple, dans une transaction de commande client, une instruction d'emplacement détermine où les articles seront prélevés, et où les articles prélevés seront rangés. Les instructions d'emplacement sont composés d'un en-tête et de lignes associées, et vous les créez dans la page **Instructions d'emplacement**. 

Dans l'en-tête, chaque instruction d'emplacement doit être associée à un *type d'ordre de travail *qui spécifie le type de transaction de stock pour lequel l'instruction sera utilisée, tels que les commandes client, le réapprovisionnement, ou le prélèvement de matières premières. Le *type de travail *indique si l'instruction d'emplacement sera utilisée pour le travail de prélèvement ou de rangement, ou pour un autre processus d'entrepôt, par exemple le comptage ou les modifications de statut du stock. Vous devez également spécifier un *site* et un *entrepôt*. Un *code directif *que vous spécifiez dans l'en-tête peut être utilisé pour lier l'instruction d'emplacement à un ou plusieurs modèles de travail. 

Quant aux modèles de travail, vous pouvez paramétrer une requête pour déterminer si une instruction particulière d'emplacement est utilisée. Par exemple, vous pouvez spécifier que lorsque l'e-commerce est l'origine d'une commande client, le stock doit être prélevé dans une zone dédiée de l'entrepôt. Le système utilise le champ **N° de souche** pour déterminer l'ordre dans lequel les instructions d'emplacements disponibles sont évaluées. 

Les lignes d'instruction d'emplacement définissent des restrictions supplémentaires sur l'application des règles de recherche d'emplacement. Vous pouvez spécifier une quantité minimale et une quantité maximale auxquelles l'instruction doit s'appliquer, vous pouvez spécifier que l'instruction doit concerner une unité de stock spécifique. Par exemple, si l'unité de mesure est en palettes, les articles en palettes peuvent être rangés dans un emplacement spécifique. Vous pouvez également indiquer si la quantité peut être fractionnée entre plusieurs emplacements. Comme l'en-tête des instructions de l'emplacement, chaque ligne d'instruction d'emplacement possède un numéro de souche qui détermine l'ordre des lignes dans lequel les lignes sont évaluées. 

Les instructions d'emplacement ont un niveau de détail supplémentaire : *actions d'instruction d'emplacement*. Vous pouvez définir plusieurs actions d'instruction d'emplacement pour chaque ligne. De nouveau, un numéro de souche est utilisé pour déterminer l'ordre dans lequel les actions sont évaluées. À ce niveau, vous pouvez paramétrer une requête pour définir la manière dont rechercher le meilleur emplacement dans l'entrepôt. Vous pouvez également utiliser les paramètres **Stratégie**prédéfinis pour rechercher un emplacement optimal.

### <a name="example-of-the-use-of-location-directives"></a>Exemple d'utilisation des instructions d'emplacement

Pour cet exemple, nous examinerons un processus de commande fournisseur dans lequel l'instruction d'emplacement doit trouver une capacité libre dans un entrepôt pour des articles en stock qui viennent d'être enregistrés au quai de réception. Nous voulons d'abord essayer de trouver de la capacité libre dans l'entrepôt par la consolidation avec le stock disponible existant. Si la consolidation n'est pas possible, nous souhaitons alors trouver un emplacement vide. 

Pour ce scénario, nous devons définir deux actions d'instruction d'emplacement. La première action dans l'ordre doit utiliser la stratégie **Consolider**, et la deuxième doit utiliser la stratégie **Emplacement vide sans travail entrant**. À moins de définir une troisième action pour gérer un scénario de dépassement de capacité, deux résultats sont possibles lorsqu'il n'y a plus de capacité dans l'entrepôt : le travail peut être créé même si aucun emplacement n'est défini, ou le processus de création de travail peut échouer. Les résultats sont déterminés par le paramétrage dans la page **Échecs d'instruction d'emplacement**, dans laquelle vous pouvez décider de sélectionner ou non l'option **Arrêter le travail à l'échec d'instruction d'emplacement** pour chaque type d'ordre de travail.




