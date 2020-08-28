---
title: Créer des instructions d’emplacement
description: Cette rubrique explique comment créer des instructions d’emplacement. Les instructions d’emplacement sont des règles définies par l’utilisateur qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: bdd99b5faefd7054023b45a91fad070aac055a26
ms.sourcegitcommit: ecad92c9cb7e9e57688e678f79f747673c921df5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2020
ms.locfileid: "3692136"
---
# <a name="create-location-directives"></a>Créer des instructions d’emplacement

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer des instructions d’emplacement. Les instructions d’emplacement sont des règles définies par l’utilisateur qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock. Par exemple, dans une transaction de commande client, une instruction d’emplacement détermine où les articles seront prélevés, et où les articles prélevés seront rangés.

> [!NOTE]
> Cette rubrique s’applique aux fonctionnalités du module **Gestion des entrepôts**. Il ne s’applique pas aux fonctionnalités du module [Gestion des stocks](../inventory/inventory-home-page.md).

Les instructions d’emplacement vous permettent d’effectuer les tâches suivantes :

- Ranger les articles entrants.
- Prélever des articles et déterminer la phase des transactions sortantes.
- Prélever et ranger des matières premières pour la production.
- Réapprovisionner l’emplacement.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir créer une instructions d’emplacement, vous devez suivre ces étapes pour vous assurer que les conditions préalables sont en place.

1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Créez un entrepôt.
1. Dans le raccourci **Entrepôt**, définissez l’option **Utiliser les processus de gestion des entrepôts** sur *Oui*.
1. Créez des emplacements, des types d’emplacement, des profils d’emplacement, et des formats d’emplacement. Pour plus d’informations, consultez [Configurer les emplacements dans un entrepôt compatible WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Créez des sites, des zones, et des groupes de zones. Pour plus d’informations, consultez [Configuration de l’entrepôt](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) et [Configurer les emplacements dans un entrepôt compatible WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Paramétrage

### <a name="create-location-directives"></a>Créer des instructions d’emplacement

Pour créer une instruction d’emplacement, procédez comme suit.

1. Allez dans **Gestion des entrepôts \> Configuration \> Instructions d’emplacements**.
1. Dans le volet de liste, définissez le champ **Type d’ordre de travail** sur le type de transaction d’inventaire pour laquelle vous créez une instruction d’emplacement.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer une instruction d’emplacement.
1. Pour la nouvelle instruction d’emplacement, définissez les champs comme décrit dans le tableau suivant.

    | Champ | Description |
    |---|---|
    | Souche de N° | Entrez un nombre entier qui indique la position de séquence de l’instruction d’emplacement. Les positions de séquence déterminent à quel moment chaque instruction d’emplacement est traitée pour le type d’ordre de travail sélectionné. |
    | Nom | Entrez un nom pour l’instruction d’emplacement. | 
    | Type de travail | Sélectionnez le type de travail à effectuer. La liste des valeurs dépend du type de mouvement de stock sélectionné dans le champ **Type d’ordre de travail**. Les valeurs disponibles peuvent être les suivantes :<ul><li>**Ranger** – L’instruction d’emplacement essaiera de trouver le meilleur emplacement pour placer ou localiser l’inventaire qui entre dans le système par la réception, la production ou les ajustements du stock. L’instruction d’emplacement est également utilisée pour définir l’emplacement de rangement ou l’emplacement d’expédition final dans le flux sortant.</li><li>**Prélever** – L’instruction d’emplacement essaiera de trouver les meilleurs emplacements pour réserver physiquement le stock (créer un travail). Le prélèvement peut être effectué (c’est-à-dire que la ligne de travail de prélèvement peut être clôturée), même si le travail n’est pas terminé. L’utilisateur peut effectuer le prélèvement physique. Dans le système, cette action est une étape de prélèvement. L’utilisateur peut ensuite annuler le travail à partir de l’appareil mobile et le terminer (par exemple le ranger) ultérieurement. Toutefois, l’en-tête de travail est d’abord clôturé lorsque le placement final est terminé.</li><li>**Comptage**, **Ajustements**, **Personnalisé**, **Modification du statut du stock**, **Création de contenant**, **Imprimer**, **Modification du statut**, **Conditionner dans des contenants imbriqués** – Ces valeurs ne peuvent pas être utilisées dans le paramétrage des instructions d’emplacement.</li></ul> |
    | Site | Sélectionnez le site où le travail doit être exécuté. |
    | Entrepôt | Sélectionnez l’emplacement d’entrepôt où le travail doit être exécuté. |
    | Code instructions | Sélectionnez un code instructions pour guider la sélection des instructions d’emplacement qui sont associées aux lignes de modèle de travail où ce code est attribué. Sur la page **Code de l’instruction**, vous pouvez créer des codes pouvant être utilisés pour connecter un modèle de travail à une instruction d’emplacement. Vous pouvez utiliser cette page pour établir le lien entre une ligne de modèle de travail et une instruction d’emplacement (par exemple un emplacement de porte de baie ou intermédiaire). Pour plus d’informations sur la configuration d’une code de directive avec un modèle de travail, voir [Contrôle du travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](control-warehouse-location-directives.md).<p>Si un code d’instruction est défini, lorsque le travail doit être généré, le système recherche les instructions d’emplacement par code d’instruction plutôt que par séquence. Ainsi, vous pouvez être plus précis sur le modèle d’emplacement utilisé pour une étape spécifique d’un modèle de travail, par exemple l’étape d’échelonnement des matières.</p> |
    | Code disposition | Sélectionnez le code disposition pour rediriger le rangement des articles reçus vers un emplacement. (Pour plus d’informations, consultez [Configurer les codes de dispositions](tasks/set-up-dispositions-codes.md).) Ce champ n’est disponible que lorsque le champ **Type d’ordre de travail** est défini sur *Commandes fournisseur*, *Ordres de retour* ou *Produits finis rangés*. |
    | Plusieurs SKU | Définissez cette option sur *Oui* pour utiliser plusieurs unités de gestion de stock (SKU) à un emplacement. Par exemple, cette option doit être définie sur *Oui* pour la porte de la baie.<p>Si l’option **Plusieurs SKU** est définie sur *Oui*, l’emplacement de rangement sera spécifié dans le travail (comme prévu). Cependant, l’emplacement de rangement ne pourra gérer le rangement de plusieurs éléments que si le travail comprend différents SKU qui doivent être prélevés et rangés, pas si le travail comprend un seul SKU qui doit être rangé.</p><p>Si l’option **Plusieurs SKU** est définie sur *Non*, l’emplacement de rangement sera spécifié uniquement si le rangement a un seul type de SKU.</p><p>Pour utiliser les deux approches, vous devez spécifier deux lignes qui ont les mêmes structure et configuration, mais définissez l’option **Plusieurs SKU** sur *Oui* pour l’une des lignes et *Non* pour l’autre. Autrement dit, deux instructions d’emplacement identiques sont requises pour les opérations de rangement, même si vous n’avez pas besoin de distinguer les SKU uniques et multiples dans l’ID de travail. Vous devez également définir une instruction d’emplacement pour le prélèvement si vous avez une commande contenant plusieurs articles.</p><p>**Remarque :** si vous définissez l’option **Plusieurs SKU** sur *Oui* pour une instruction d’emplacement du type de travail *Placement*, le système sélectionne toujours la première ligne d’instruction d’emplacement, indépendamment des autres restrictions créées sur les lignes.</p> |

1. Facultatif : Sur le volet Action, sélectionnez **Modifier la requête** pour sélectionner les emplacements ou pour spécifier les restrictions qui s’appliquent lorsque vous sélectionnez une instruction d’emplacement spécifique.
1. Dans le raccourci **Lignes**, créez une ou plusieurs lignes pour spécifier des unités et pour localiser ou réserver une quantité dans un entrepôt.
1. Sur chaque nouvelle ligne, définissez les champs comme décrit dans le tableau suivant.

    | Champ | Description |
    |---|---|
    | Souche de N° | Entrez un nombre entier qui indique la position de séquence de l’instruction d’emplacement. Les positions de séquence déterminent à quel moment chaque instruction d’emplacement est traitée pour le type de travail sélectionné. |
    | Quantité de départ | Spécifiez la plage de quantités de début pour la sélection de la séquence de la grille médiane. Spécifiez la quantité dans l’unité de mesure sélectionnée dans le champ **Unité**. |
    | Quantité d’arrivée | Spécifiez la plage de quantités de fin pour la sélection de la séquence de la grille médiane. Spécifiez la quantité dans l’unité de mesure sélectionnée dans le champ **Unité**. |
    | Unité | Sélectionnez l’unité de mesure des articles.<p>Vous pouvez spécifier une quantité minimale et une quantité maximale auxquelles l’instruction doit s’appliquer. Vous pouvez également spécifier que l’instruction doit être utilisée pour une unité de stock spécifique. Le champ **Unité** est utilisé uniquement pour l’évaluation de la quantité.</p><p>Pour déterminer si une ligne d’instruction d’emplacement s’applique, le système évalue les quantités à l’aide de la valeur **Unité** spécifiée sur la ligne. Chaque fois qu’une ligne d’instruction d’emplacement est atteinte, le système essaiera de convertir l’unité de la demande dans l’unité spécifiée sur la ligne. Si la conversion d’unité n’existe pas, le système passera à la ligne suivante.</p> |
    | Localiser la quantité | Ce champ n’est valide que lorsque vous essayez de ranger ou de localiser la quantité dans l’entrepôt. En d’autres termes, il n’est valable que pour le travail de *Rangement*. Sélectionnez la méthode utilisée pour évaluer si la quantité est dans la plage définie dans les champs **Quantité de départ** et **Quantité d’arrivée**. Si l’instruction d’emplacement concerne une transaction entrante, sélectionnez l’une des options suivantes :<ul><li>**Quantité du contenant** – Pour évaluer si une quantité est comprise dans la plage de quantité cible, utilisez la quantité reçue dans le contenant.</li><li>**Quantité unitisée** – Pour évaluer si une quantité est comprise dans la plage de quantité cible, utilisez la quantité unitisée pendant la transaction. Par exemple, si votre entrepôt peut recevoir une quantité de 1 000 et vous pouvez la diviser en 10 contenants, chacun contenant 100 articles, vous pouvez utiliser une quantité de 1 000 articles au lieu de la quantité de contenant de 100.</li><li>**Quantité restante** – Pour évaluer si une quantité est comprise dans la plage de quantité cible, utilisez la quantité restante à recevoir sur la ligne de commande fournisseur en cours d’archivage.</li><li>**Quantité prévue** – Pour évaluer si une quantité est comprise dans la plage de quantité cible, utilisez la quantité totale de la ligne de commande fournisseur, indépendamment de la quantité déjà reçue.</li></ul> |

1. Facultatif : Sur le raccourci **Lignes**, vous pouvez définir les champs supplémentaires suivants.

    | Champ | Description |
    |---|---|
    | Restreindre par unité | Cochez cette case pour restreindre les unités de mesure considérées comme des critères de sélection valides pour les lignes d’instruction d’emplacement. Lorsque des unités de mesure ont été spécifiées, seuls les éléments dont l’unité correspond à au moins une unité définie pour le groupe de séquences d’unités seront considérés comme valides pour la sélection de ligne.<p>Par exemple, l’unité est limitée aux palettes et l’article est associé à un groupe de séquences d’unités qui comprend l’unité *palettes*. Dans ce cas, les éléments seront considérés comme une option valide pour l’instruction d’emplacement.</p><p>Cependant, la case à cocher **Restreindre à l’unité** ne contrôle pas l’unité ou les unités appliquées sur les lignes de travail. La restriction d’unité s’applique uniquement aux unités mises à disposition via le groupe de séquences d’unités.</p><p>Par exemple, un article est associé à un groupe de séquences d’unités qui comprend les unités *palettes* et *pcs*. Une unité de mesure a été définie où 1 palette = 100 pièces, et l’instruction d’emplacement utilise la fonctionnalité **Restreindre à l’unité** uniquement pour les palettes. En outre, un modèle de travail a été défini qui limite la création de l’en-tête de travail à 50 pièces. Dans ce cas, des lignes de travail de 50 pièces seront créées.</p><p>Pour spécifier l’unité de mesure de la restriction, procédez comme suit :</p><ol><li>Sur le raccourci **Lignes**, sélectionnez **Restreindre à l’unité**. Ce bouton n’est disponible qu’après avoir coché la case **Restreindre à l’unité** sur la ligne, puis sélectionné **Enregistrer**.</li><li>Dans le champ **Unité**, sélectionnez l’unité de mesure selon laquelle limiter les processus de prélèvement et de rangement.</li></ol> |
    | Arrondir à l’unité | Sélectionnez cette option pour indiquer si le prélèvement de matières premières est arrondie à un multiple de l’unité de manutention spécifiée dans le champ **Restreindre par unité**. Ce champ s’applique uniquement au prélèvement de matières premières et aux instructions d’emplacement de type *Prélèvement*. |
    | Localiser la quantité de conditionnement | Cochez cette case si une quantité d’unités d’emballage est spécifiée sur la page **Commande client**. Si vous cochez cette case, seuls les emplacements dont la quantité d’unités d’emballage correspond sont sélectionnés. |
    | Autoriser le fractionnement | Cochez cette case pour répartir la quantité entre plusieurs emplacements. |
    | Modèle de réapprovisionnement immédiat | Créez une connexion vers un modèle de réapprovisionnement afin de démarrer immédiatement le réapprovisionnement si les articles ne sont pas affectés. Si vous laissez ce champ vide, le réapprovisionnement d’article ne commencera pas tant que toutes les lignes de l’instruction d’emplacement n’auront pas été traitées.<p>Ce champ est disponible uniquement sur les types d’ordres de travail sélectionnés pour lesquels le réapprovisionnement est autorisé, tels que *Commandes* et *Prélèvement de matières premières*.</p> |

1. Dans le raccourci **Actions d’instructions d’emplacement**, cliquez sur **Nouveau** pour sélectionner l’emplacement ou la plage d’emplacements.
1. Le champ **Numéro de séquence** indique la séquence dans laquelle l’instruction d’emplacement sera traitée pour le type de travail sélectionné. Vous pouvez modifier la séquence. Cependant, soyez prudent avec les numéros de séquence pour les actions d’instruction d’emplacement, car les actions d’instruction d’emplacement seront toujours exécutées dans cette séquence.
1. Dans le champ **Nom**, entrez le nom de l’action liée à l’instruction d’emplacement. Soyez précis, afin que l’action soit claire.
1. Facultatif : cliquez sur **Modifier la requête** pour modifier les emplacements d’entrepôt et d’autres critères.
1. Facultatif : vous pouvez définir les champs supplémentaires suivants pour une instruction d’emplacement.

    | Champ | Description |
    |---|---|
    | Utilisation d’un emplacement fixe | Sélectionnez les emplacements que l’instruction d’emplacement doit prendre en compte :<ul><li>**Emplacements fixes et non fixes** – L’instruction d’emplacement prendra en considération tous les emplacements.</li><li>**N’utiliser des emplacements fixes que pour le produit** – L’instruction d’emplacement ne prendra en considération que des emplacements fixes pour les produits.</li><li>**N’utiliser des emplacements fixes que pour la variante de produit** – L’instruction d’emplacement ne prendra en considération que des emplacements fixes pour les variantes de produit.</li></ul> |
    | Autoriser un stock négatif | Cochez cette case pour autoriser un stock négatif dans l’emplacement d’entrepôt. |
    | Traitement par lots activé | Cochez cette case pour utiliser des stratégies de traitement par lots pour les articles activés pour le traitement par lots. Si cette case est cochée et que le champ **Stratégie** est défini sur *Aucun*, le système passera à la ligne d’action suivante. |
    | Stratégie | Sélectionnez la stratégie que l’instruction d’emplacement doit utiliser :<ul><li>**Aucun** – Aucune stratégie ne sera utilisée.</li><li>**Faire correspondre la quantité de conditionnement** – Cette stratégie vérifie si un emplacement de prélèvement contient la quantité de conditionnement spécifiée. Cette stratégie n’est valable que lorsque le champ **Type de travail** est défini sur *Prélèvement*.</li><li>**Consolider** – Cette stratégie consolide des articles à un emplacement spécifique lorsque des articles similaires sont déjà disponibles. Cette stratégie n’est valable que lorsque le champ **Type de travail** est défini sur *Rangement*. Dans une configuration typique de rangement, le système essaie de consolider sur la première ligne d’action, puis, sur la deuxième ligne d’action, il essaie de ranger sans consolidation. La consolidation des marchandises améliore l’efficacité du prélèvement ultérieur.</li><li>**Réservation de traitement par lots FEFO** – Cette stratégie est utilisée lorsque le stock est organisé en fonction de la date d’expiration d’un lot et est affecté pour la réservation par lots. La stratégie de réservation par lots FEFO est également utilisée lorsque le stock est organisé en fonction de la DLUO et de la date d’expiration d’un lot. Vous ne pouvez utiliser cette stratégie que pour les articles activés pour le traitement par lots. Cette stratégie n’est valable que lorsque le champ **Type de travail** est défini sur *Prélèvement*. Lorsque vous sélectionnez cette stratégie, vous remplacez tout tri de requête pour les numéros de lot qui est appliqué.</li><li>**Arrondir au contenant complet** – Cette stratégie arrondit la quantité de stock afin qu’elle corresponde à la quantité du contenant affectée aux articles à prélever. Cette stratégie ne peut être utilisée que pour le type de réapprovisionnement des instructions d’emplacement, et uniquement lorsque le champ **Type de travail** est défini sur *Prélèvement*.</li><li>**Emplacement vide sans travail entrant** – Cette stratégie permet de rechercher des emplacements vides. Un emplacement est considéré comme vide s’il ne contient pas de stock physique, ni aucun travail entrant prévu. Cette stratégie n’est valable que lorsque le champ **Type de travail** est défini sur *Rangement*.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Exemple d’utilisation des instructions d’emplacement

Pour cet exemple, imaginez un processus de commande fournisseur dans lequel l’instruction d’emplacement doit trouver de la capacité disponible dans un entrepôt pour des articles en stock qui viennent d’être enregistrés au quai de réception. Vous devez d’abord trouver de la capacité disponible dans l’entrepôt en consolidant le stock disponible existant. Si la consolidation n’est pas possible, vous devez trouver un emplacement vide.

Pour ce scénario, vous devez définir deux actions d’instruction d’emplacement. La première action dans l’ordre doit utiliser la stratégie **Consolider**, et la deuxième doit utiliser la stratégie **Emplacement vide sans travail entrant**. À moins de définir une troisième action pour gérer un scénario de dépassement de capacité, deux résultats sont possibles lorsqu’il n’y a plus de capacité dans l’entrepôt : le travail peut être créé même si aucun emplacement n’est défini, ou le processus de création de travail peut échouer. Les résultats sont déterminés par le paramétrage dans la page **Échecs d’instruction d’emplacement**, dans laquelle vous pouvez décider de sélectionner ou non l’option **Arrêter le travail à l’échec d’instruction d’emplacement** pour chaque type d’ordre de travail.

## <a name="next-step"></a>Étape suivante

Après avoir créé des instructions d’emplacement, vous pouvez associer chaque code d’instruction à un code de modèle de travail pour la création du travail. Pour plus d’informations, voir [Contrôler le travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Informations destinées aux administrateurs système

Si vous n’avez pas accès aux pages qui vous permettent d’effectuer cette tâche, contactez l’administrateur système et fournissez les informations répertoriées dans le tableau suivant.

| Catégorie | Logiciel requis |
|---|---|
| Clés de configuration | Accédez à **Administration système \> Paramétrage \> Configuration des licences**. Développez la clé de licence **Commerce**, et sélectionnez la clé de configuration **Gestion des entrepôts et du transport**. |
