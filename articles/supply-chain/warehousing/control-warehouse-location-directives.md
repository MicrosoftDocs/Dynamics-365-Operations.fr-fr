---
title: "Contrôler le travail d'entrepôt à l'aide de modèles de travail et d'instructions d'emplacement"
description: "Cette rubrique décrit comment utiliser les modèles de travail et les instructions d'emplacement pour déterminer comment et à quel endroit effectuer les travaux dans l'entrepôt."
author: perlynne
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4428613441424c81f4fd7dd92bbf842c62ce860
ms.openlocfilehash: 74e7c36fb912f35252d6e40d17477ac2962cbc23
ms.contentlocale: fr-fr
ms.lasthandoff: 09/22/2018

---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Contrôler le travail d'entrepôt à l'aide de modèles de travail et d'instructions d'emplacement

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser les modèles de travail et les instructions d'emplacement pour déterminer comment et à quel endroit effectuer les travaux dans l'entrepôt.

Les instructions que les magasiniers reçoivent sur un appareil mobile sont déterminées par les modèles de travail que vous paramétrez dans Microsoft Dynamics 365 for Finance and Operations afin de définir les divers processus et tâches d'entrepôt. Les modèles de travail déterminent la manière dont le travail est effectuée pour chaque processus d'entrepôt. En liant une instruction d'emplacement à des modèles de travail, vous pouvez garantir que le travail se produit dans des zones physiques spécifiques des entrepôts.

## <a name="work-templates"></a>Modèles de travail
La page **Modèles de travail** vous permet de définir les opérations de travail qui doivent être effectuées dans l'entrepôt. Généralement, les opérations de travail d'entrepôt se composent d'une paire d'actions : un magasinier prend un stock disponible dans un emplacement et le range dans un autre emplacement. 

Les modèles de travail se composent d'un en-tête et de lignes associées. Chaque modèle de travail concerne un *type d'ordre de travail* spécifique. Plusieurs types d'ordres de travail sont associés aux documents source, tels que les commandes fournisseur ou client. Toutefois, les autres types d'ordres de travail représentent des processus distincts d'entrepôt, tels que l'inventaire tournant. Les *ID de pool de travail* vous permettent d'organiser le travail en groupes. 

Les paramètres dans la définition d'en-tête de travail peuvent être utilisés pour déterminer le moment où un nouveau travail doit être créé. Par exemple, vous pouvez définir un nombre maximal de lignes de prélèvement et un temps prévu de sélection maximal. Ensuite, si le travail pour un processus de prélèvement de commande client dépasse l'une de ces valeurs, ce travail est fractionné en deux travaux. 

Les lignes de travail représentent les tâches physiques requises afin de traiter le travail. Par exemple, pour un processus sortant d'entrepôt, il peut y avoir une ligne de travail pour prélever les articles dans l'entrepôt et une autre ligne pour ranger ces articles dans une zone de transit. Il peut ensuite y avoir une ligne supplémentaire pour prélever les articles dans la zone de transit, et une autre ligne pour mettre les articles dans un camion dans le cadre du processus de chargement. Vous pouvez définir un *code directif* sur les lignes de modèle de travail. Un code directif est lié à une instruction d'emplacement et donc permet de garantir que le travail d'entrepôt est traité dans l'emplacement approprié de l'entrepôt. 

Vous pouvez paramétrer une requête pour contrôler le moment où un modèle particulier de travail est utilisé. Par exemple, vous pouvez définir une limitation afin qu'un modèle spécifique puisse être utilisé pour le travail uniquement dans un entrepôt particulier. Sinon, vous pouvez avoir plusieurs modèles utilisés pour créer le travail pour le traitement de la commande client sortante, en fonction de l'origine des ventes. Le système utilise le champ **N° de souche** pour déterminer l'ordre dans lequel les modèles de travail disponibles sont évalués. Par conséquent, si vous avez une requête très spécifique pour un modèle particulier de travail, vous devez lui attribuer un faible numéro de souche. Cette requête sera alors évaluée avant d'autres requêtes plus générales. 

Pour arrêter ou suspendre un processus de travail, vous pouvez utiliser le paramètre **Arrêter le travail** dans la ligne de travail. Dans ce cas, le collaborateur qui exécute le travail n'est pas invité à effectuer l'étape de la ligne de travail suivante. Pour passer à l'étape suivante, ce collaborateur ou un autre doit resélectionner le travail. Vous pouvez également séparer les tâches dans un travail en utilisant un autre *ID classe de travail* dans les lignes de modèle de travail.

## <a name="location-directives"></a>Instructions d'emplacement
Les instructions d'emplacement sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock. Par exemple, dans une transaction de commande client, une instruction d'emplacement détermine où les articles seront prélevés, et où les articles prélevés seront rangés. Les instructions d'emplacement sont composés d'un en-tête et de lignes associées, et vous les créez dans la page **Instructions d'emplacement**. 

Dans l'en-tête, chaque instruction d'emplacement doit être associée à un *type d'ordre de travail* qui spécifie le type de transaction de stock pour lequel l'instruction sera utilisée, tels que les commandes client, le réapprovisionnement, ou le prélèvement de matières premières. Le *type de travail* indique si l'instruction d'emplacement sera utilisée pour le travail de prélèvement ou de rangement, ou pour un autre processus d'entrepôt, par exemple le comptage ou les modifications de statut du stock. Vous devez également spécifier un *site* et un *entrepôt*. Un *code directif* que vous spécifiez dans l'en-tête peut être utilisé pour lier l'instruction d'emplacement à un ou plusieurs modèles de travail. 

Quant aux modèles de travail, vous pouvez paramétrer une requête pour déterminer si une instruction particulière d'emplacement est utilisée. Par exemple, vous pouvez spécifier que lorsque l'e-commerce est l'origine d'une commande client, le stock doit être prélevé dans une zone dédiée de l'entrepôt. Le système utilise le champ **N° de souche** pour déterminer l'ordre dans lequel les instructions d'emplacements disponibles sont évaluées. 

Les lignes d'instruction d'emplacement définissent des restrictions supplémentaires sur l'application des règles de recherche d'emplacement. Vous pouvez spécifier une quantité minimale et une quantité maximale auxquelles l'instruction doit s'appliquer, vous pouvez spécifier que l'instruction doit concerner une unité de stock spécifique. Par exemple, si l'unité de mesure est en palettes, les articles en palettes peuvent être rangés dans un emplacement spécifique. Vous pouvez également indiquer si la quantité peut être fractionnée entre plusieurs emplacements. Comme l'en-tête des instructions de l'emplacement, chaque ligne d'instruction d'emplacement possède un numéro de souche qui détermine l'ordre des lignes dans lequel les lignes sont évaluées. 

Les instructions d'emplacement ont un niveau de détail supplémentaire : *actions d'instruction d'emplacement*. Vous pouvez définir plusieurs actions d'instruction d'emplacement pour chaque ligne. De nouveau, un numéro de souche est utilisé pour déterminer l'ordre dans lequel les actions sont évaluées. À ce niveau, vous pouvez paramétrer une requête pour définir la manière dont rechercher le meilleur emplacement dans l'entrepôt. Vous pouvez également utiliser les paramètres **Stratégie** prédéfinis pour rechercher un emplacement optimal.

## <a name="location-directives-configuration-details"></a>Détails de configuration des instructions d'emplacement 

 ### <a name="sequence-number"></a>Numéro de séquence
 
Ce numéro indique l'ordre selon laquel une instruction d'emplacement est traitée pour un type de travail sélectionné. Il peut être modifié à l'aide des options **Déplacer vers le haut** et **Déplacer vers le bas** dans le menu.
 
 ### <a name="work-type"></a>Type de travail
 
Il s'agit du type de travail à effectuer. Le type de travail disponible dépend du type de mouvement de stock sélectionné dans le champ **Type d'ordre d'exécution**.
-   **Placement** - Un travail de type **Placement** signifie que l'instruction d'emplacement va rechercher l'emplacement le plus approprié pour placer ou localiser le stock entrant dans le système, en provenance de la réception, de la production ou des ajustements de stock. Il permet également de définir un placement sur un emplacement intermédiaire ou un emplacement d'expédition final.
-   **Prélèvement** - Un travail de type **Prélèvement** signifie que l'entrepôt va rechercher l'emplacement le plus approprié à partir duquel réserver physiquement le stock (créer un travail). Le prélèvement peut être effectué (la ligne de travail de prélèvement peut être clôturée), même si le travail n'est pas terminé. L'utilisateur peut effectuer le prélèvement physique, qui est une étape de prélèvement. L'utilisateur peut ensuite annuler le travail à partir d'un appareil mobile et le terminer ultérieurement. Toutefois, l'en-tête de travail est clôturé lorsque le placement final est terminé. 
-   **Comptage, Ajustements, Personnalisé, Modification du statut du stock, Création de contenant, Imprimer, Modification du statut, Conditionner dans des contenants imbriqués** - Ces options ne peuvent pas être utilisées dans le paramétrage des instructions d'emplacement. Il s'agit d'une énumération, aucun filtrage n'est donc associé au type d'ordre de travail. 

### <a name="directive-code"></a>Code instructions

Sélectionnez le code d'instruction à associer à un modèle de travail ou à un modèle de réapprovisionnement. Dans l'écran **Code instructions**, vous pouvez créer des codes qui peuvent être utilisés pour les connexions entre un modèle de réapprovisionnement du modèle de travail et une instruction d'emplacement. Cette option peut également être utilisée pour établir le lien entre une ligne de modèle de travail et une instruction d'emplacement (par exemple un emplacement de porte de baie ou intermédiaire).

Notez que si le code est défini, le système ne recherchera pas l'instruction d'emplacement par séquence lorsque le travail sera généré. La recherche s'effectuera par code d'instruction. Cela signifie que vous pouvez être plus précis sur le modèle d'emplacement utilisé pour une certaine étape d'un modèle de travail, par exemple l'échelonnement des matières. 

### <a name="site"></a>Site

Le champ Site est obligatoire, car l'instruction d'emplacement requiert le site et l'entrepôt pour lesquels elle est valide. 

### <a name="warehouse"></a>Entrepôt

Le champ Entrepôt est obligatoire, car l'instruction d'emplacement requiert le site et l'entrepôt pour lesquels elle est valide.

### <a name="multiple-sku"></a>Plusieurs SKU

Ce champ autorise plusieurs unités de gestion de stock (SKU) dans un emplacement, comme la porte de baie. Si vous sélectionnez **Plusieurs SKU**, l'emplacement de rangement sera spécifié dans le travail (qui est prévu), mais il pourra uniquement gérer plusieurs rangements d'articles (si le travail contient différents SKU à prélever et ranger, et non un seul rangement SKU). Si vous ne sélectionnez pas **Plusieurs SKU**, l'emplacement de rangement sera spécifié uniquement si le rangement a un seul type de SKU. Pour utiliser les deux actions, vous devez spécifier deux lignes, une avec l'option Plusieurs SKU activée et une avec l'option Plusieurs SKU désactivée. Elles doivent avoir la même structure et le même paramétrage. Pour les opérations de placement, les instructions d'emplacement doivent être identiques, même si vous ne faites pas la distinction entre les SKU uniques et multiples sur l'ID de travail. Vous devez également paramétrer le prélèvement si une commande contient plusieurs articles.

### <a name="sequence-number"></a>Souche de N°

Entrez l'ordre dans lequel les lignes d'instruction d'emplacement sont traitées pour le type de travail sélectionné. Vous pouvez également modifier l'ordre, si nécessaire, à l'aide des options **Déplacer vers le haut** et **Déplacer vers le bas**.

### <a name="fromto-quantity"></a>Quantité de départ/d'arrivée

Cette option permet de spécifier une plage de quantités pour la sélection de la séquence de la grille médiane. Vous pouvez spécifier la plage de quantités de début/de fin dans l'unité respective.

### <a name="unit"></a>Unité

Vous pouvez spécifier une quantité minimale et une quantité maximale auxquelles l'instruction doit s'appliquer, vous pouvez spécifier que l'instruction doit concerner une unité de stock spécifique. Le champ Unité de la ligne est utilisé uniquement pour l'évaluation de la quantité.

La vérification de l'applicabilité de la ligne d'instruction d'emplacement dépendra de la quantité dans l'unité respective spécifiée sur la ligne d'instruction d'emplacement. Chaque fois qu'une ligne d'instruction d'emplacement est atteinte, le système essaiera de convertir l'unité de la demande en une unité spécifiée sur la ligne. Si la conversion en UM n'existe pas, il passera à la ligne suivante. 

### <a name="locate-quantity"></a>Localiser la quantité

Cette option est uniquement utilisée pour placer/localiser la quantité dans l'entrepôt. Elle s'applique uniquement au type de travail Placement. Les valeurs valides sont :

-   **Quantité du contenant** - Lorsque vous évaluez si la quantité est comprise dans les plages de quantité de début et de fin, utilisez la quantité reçue dans le contenant.
-   **Quantité unitisée** - Lorsque vous évaluez si la quantité est comprise dans les plages de quantité de début et de fin, utilisez la quantité unitisée pendant la transaction spécifique.
-   **Quantité restante** - Lorsque vous évaluez si la quantité est comprise dans les plages de quantité de début et de fin, utilisez la quantité restante à recevoir sur la ligne de commande fournisseur en cours d'archivage.
-   **Quantité prévue** - Lorsque vous évaluez si la quantité est comprise dans les plages de quantité de début et de fin, utilisez la quantité totale de la ligne de commande fournisseur, indépendamment de la quantité déjà reçue.

### <a name="restrict-by-unit"></a>Restreindre par unité

Ce champ permet à une ligne d'instruction d'emplacement d'être spécifique à une ou plusieurs unités de mesure. Lors de la réservation de la quantité, si vous souhaitez uniquement réserver des palettes d'un ensemble spécifique d'emplacements, la séquence de la grille médiane restreint cette séquence spécifique au contenant afin que toute quantité inférieure à une palette ne sélectionne pas la séquence. Sélectionnez **Restreindre par unité** pour paramétrer les unités. Vous pouvez également restreindre la ligne à plusieurs unités. Ce champ est utilisé uniquement avec les instructions d'emplacement de type Prélèvement. 

### <a name="round-up-to-unit"></a>Arrondir à l'unité

Ce champ fonctionne avec le champ **Restreindre par unité**. Si la ligne d'instruction d'emplacement **Restreindre par unité** est définie sur « Boîte », la sélection de l'option **Arrondir jusqu'à l'unité** indique que le travail généré en dehors de l'instruction de prélèvement de matières premières doit être arrondi à un multiple d'une unité de manutention (spécifiée dans le champ **Restreindre par unité**). Notez que ce champ est utilisé uniquement pour le prélèvement de matières premières et uniquement avec les instructions d'emplacement de type Prélèvement.

### <a name="locate-packing-qty"></a>Localiser la quantité de conditionnement

Si une quantité de conditionnement est spécifiée sur une commande client, un ordre de transfert ou un ordre de fabrication, le système est contraint de sélectionner uniquement des emplacements avec une quantité de conditionnement dans l'emplacement. Ce champ est utilisé uniquement avec les instructions d'emplacement de type Prélèvement.

### <a name="allow-split"></a>Autoriser le fractionnement

Cette option spécifie si une instruction d'emplacement est autorisée à fractionner la quantité reçue ou la quantité réservée dans plusieurs emplacements d'entrepôt, ou si la quantité totale doit être localisée dans un emplacement unique ou réservée à partir d'un emplacement unique pour créer le travail. 

### <a name="sequence-number"></a>Numéro de séquence

Ce numéro indique l'ordre dans lequel l'instruction d'emplacement est traitée pour le type de travail sélectionné. Vous pouvez modifier la séquence, au besoin. Toutefois, veillez à utiliser des numéros de séquence, car le traitement sera toujours exécuté dans l'ordre. 

### <a name="name"></a>Nom

Entrez un nom pour l'action d'instruction d'emplacement. Veillez à être précis lorsque vous spécifiez un nom.

### <a name="fixed-location-usage"></a>Utilisation d'un emplacement fixe 

-   **Emplacements fixes et non fixes** - L'instruction d'emplacement prendra en considération tous les emplacements.
-   **N'utiliser des emplacements fixes que pour le produit** - L'instruction d'emplacement ne prendra en considération que des emplacements fixes pour les produits.
-   **N'utiliser des emplacements fixes que pour la variante de produit** - L'instruction d'emplacement ne prendra en considération que des emplacements fixes pour les variantes de produit.

### <a name="allow-negative-inventory"></a>Autoriser un stock négatif

Sélectionnez cette option pour autoriser un stock négatif à l'emplacement d'entrepôt spécifié dans les instructions d'emplacement. 

### <a name="batch-enabled"></a>Traitement par lots activé 

Sélectionnez cette option pour utiliser des stratégies de traitement par lots pour les articles activés pour le traitement par lots. Si une ligne est atteinte lorsque l'option **Traitement par lots activé** est définie sans article de traitement par lots, le processus passera à la ligne d'action suivante. 

### <a name="strategy"></a>Stratégie

-   **Consolider** - Cette stratégie est utilisée pour consolider des articles à un emplacement particulier lorsque des articles similaires sont déjà disponibles. Cette stratégie ne fonctionne que pour l'instruction d'emplacement de type Placement. Le paramétrage courant pour le placement consistera à consolider les articles sur la première ligne d'action, puis à placer les articles sans consolidation dans une deuxième tentative. La consolidation des marchandises améliore l'efficacité du prélèvement ultérieur.
-   **Faire correspondre la quantité de conditionnement** - Cette stratégie est utilisée pour vérifier si un emplacement de prélèvement contient la quantité de conditionnement spécifiée. Cette stratégie ne fonctionne que pour une instruction d'emplacement de type Prélèvement. 
-   **Réservation de traitement par lots FEFO** - Cette stratégie est utilisée lorsque le stock est organisé en fonction de la date d'expiration d'un lot et est affecté pour la réservation par lots. Vous ne pouvez utiliser cette stratégie que pour les articles activés pour le traitement par lots. Cette stratégie ne fonctionne que pour une instruction d'emplacement de type Prélèvement. 
-   **Arrondir au contenant complet** - Cette stratégie est utilisée pour arrondir la quantité de stock afin qu'elle corresponde à la quantité du contenant (LP) affectée aux articles à prélever. Vous ne pouvez utiliser cette stratégie que pour le type de réapprovisionnement d'une instruction d'emplacement de type Prélèvement. 
-   **Emplacement vide sans travail entrant** - Cette stratégie permet de rechercher des emplacements vides. L'emplacement est considéré comme vide s'il ne contient pas de stock physique, ni aucun travail entrant prévu. Cette stratégie n'est utilisée que pour une instruction d'emplacement de type Placement. 

### <a name="example-of-the-use-of-location-directives"></a>Exemple d'utilisation des instructions d'emplacement

Pour cet exemple, imaginez un processus de commande fournisseur dans lequel l'instruction d'emplacement doit trouver de la capacité disponible dans un entrepôt pour des articles en stock qui viennent d'être enregistrés au quai de réception. Vous devez d'abord trouver de la capacité disponible dans l'entrepôt en consolidant le stock disponible existant. Si la consolidation n'est pas possible, vous devez trouver un emplacement vide. 

Pour ce scénario, vous devez définir deux actions d'instruction d'emplacement. La première action dans l'ordre doit utiliser la stratégie **Consolider**, et la deuxième doit utiliser la stratégie **Emplacement vide sans travail entrant**. À moins de définir une troisième action pour gérer un scénario de dépassement de capacité, deux résultats sont possibles lorsqu'il n'y a plus de capacité dans l'entrepôt : le travail peut être créé même si aucun emplacement n'est défini, ou le processus de création de travail peut échouer. Les résultats sont déterminés par le paramétrage dans la page **Échecs d'instruction d'emplacement**, dans laquelle vous pouvez décider de sélectionner ou non l'option **Arrêter le travail à l'échec d'instruction d'emplacement** pour chaque type d'ordre de travail.

