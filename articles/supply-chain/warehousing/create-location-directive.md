---
title: Utiliser des instructions d’emplacement
description: Cette rubrique décrit comment utiliser les instructions d’emplacement. Les instructions d’emplacement sont des règles définies par l’utilisateur qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock.
author: Mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84821fe4e7c5054b2121dbd7f9e536c80080b978
ms.sourcegitcommit: 1f23adbc6c7e6f9ffe8c48c10659b9fae2155aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470517"
---
# <a name="work-with-location-directives"></a>Utiliser des instructions d’emplacement

[!include [banner](../includes/banner.md)]

Les instructions d’emplacement sont des règles qui aident à identifier les emplacements de prélèvement et de rangement pour le mouvement du stock. Par exemple, dans une transaction de commande client, une instruction d’emplacement détermine où les articles seront prélevés, et où les articles prélevés seront rangés. les instructions d’emplacement se composent d’un en-tête et de lignes associées. Ils sont créés pour des *types d’ordre de travail* spécifiques.

> [!NOTE]
> Cette rubrique s’applique aux fonctionnalités du module **Gestion des entrepôts**. Il ne s’applique pas aux fonctionnalités du module [Gestion des stocks](../inventory/inventory-home-page.md).

Les instructions d’emplacement vous permettent d’effectuer les tâches suivantes :

- Ranger les articles entrants.
- Prélever des articles et déterminer la phase des transactions sortantes.
- Prélever et ranger des matières premières pour la production.
- Réapprovisionner l’emplacement.

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir créer une instructions d’emplacement, vous devez suivre ces étapes pour vous assurer que les conditions préalables sont en place.

1. Assurez-vous que la clé de licence requise est activée. Accédez à **Administration du système \> Configurer \> Configuration de la licence**, développez la clé de licence **Commerce**, puis sélectionnez la clé de configuration **Gestion de l’entrepôt et du transport**. Notez que l’accès administrateur est requis pour cette étape.
1. Accédez à **Gestion des entrepôts \> Configuration \> Entrepôt \> Emplacements fixes**.
1. Créez un entrepôt.
1. Dans le raccourci **Entrepôt**, définissez l’option **Utiliser les processus de gestion des entrepôts** sur *Oui*.
1. Créez des emplacements, des types d’emplacement, des profils d’emplacement, et des formats d’emplacement. Pour plus d’informations, consultez [Configurer les emplacements dans un entrepôt compatible WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Créez des sites, des zones, et des groupes de zones. Pour plus d’informations, consultez [Configuration de l’entrepôt](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) et [Configurer les emplacements dans un entrepôt compatible WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="work-order-types-for-location-directives"></a>Types d’ordre de travail pour les instructions d’emplacement

La plupart des champs qui peuvent être définis pour les instructions d’emplacement sont communs à tous les types d’ordres de travail. Cependant, d’autres champs sont spécifiques à des types d’ordre de travail particuliers.

![Types d’ordre de travail des instruction d’emplacement](media/Location_Directives_Work_Order_Types.png "Types d’ordre de travail des directives d’emplacement")

> [!NOTE]
> Deux types d’ordres de travail, *Travail annulé* et *Inventaire tournant*, ne sont utilisés que par le système. les instructions d’emplacement ne peuvent pas être créées pour ces types d’ordres de travail.

Les tableaux des sous-sections suivantes répertorient les champs communs et spécifiques au type d’ordre de travail disponibles lorsque vous configurez une instruction d’emplacement.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Champs communs à tous les types d’ordres de travail

Le tableau suivant répertorie les champs communs à tous les types d’ordres de travail.

| Organisateur | Champ |
|---|---|
| Instructions d’emplacement | Type de travail |
| Instructions d’emplacement | Site |
| Instructions d’emplacement | Entrepôt |
| Instructions d’emplacement | Code instructions |
| Instructions d’emplacement | Plusieurs SKU |
| Lignes | Souche de N° |
| Lignes | Quantité de départ |
| Lignes | Quantité d’arrivée |
| Lignes | Unité |
| Lignes | Localiser la quantité |
| Lignes | Restreindre par unité |
| Lignes | Arrondir à l’unité |
| Lignes | Localiser la quantité de conditionnement |
| Lignes | Autoriser le fractionnement |
| Actions d’instruction d’emplacement | Souche de N° |
| Actions d’instruction d’emplacement | Nom |
| Actions d’instruction d’emplacement | Utilisation d’un emplacement fixe |
| Actions d’instruction d’emplacement | Autoriser un stock négatif |
| Actions d’instruction d’emplacement | Traitement par lots activé |
| Actions d’instruction d’emplacement | Stratégie |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Champs communs spécifiques aux types d’ordres de travail

Le tableau suivant répertorie les champs spécifiques aux types d’ordres de travail.

| Organisateur | Champ | Type d’ordre d’exécution |
|---|---|---|
| Instructions d’emplacement | Localiser par | Commandes fournisseur |
| Instructions d’emplacement | Code disposition applicable | Commandes fournisseur |
| Instructions d’emplacement | Code disposition | Commandes fournisseur |
| Instructions d’emplacement | Code disposition applicable | Rangement des produits finis |
| Instructions d’emplacement | Code disposition | Rangement des produits finis |
| Instructions d’emplacement | Code disposition applicable | Ordres de retour |
| Instructions d’emplacement | Code disposition | Ordres de retour |
| Instructions d’emplacement | Code disposition applicable | Rangement de kanban |
| Instructions d’emplacement | Code disposition applicable | Prélèvement de kanban |
| Lignes | Modèle de réapprovisionnement immédiat | Commandes client |
| Lignes | Modèle de réapprovisionnement immédiat | Prélèvement de matières premières |
| Lignes | Modèle de réapprovisionnement immédiat | Sortie de transfert |
| Lignes | Modèle de réapprovisionnement immédiat | Prélèvement de kanban |

## <a name="open-the-location-directives-page"></a>Ouvrez la page des instruction d’emplacement

Pour ouvrir page **instruction d’emplacement**, accédez à **Gestion des entrepôts \> Paramétrage \> instruction d’emplacement**.

À partir de là, vous pouvez afficher, créer et modifier vos instruction d’emplacement à l’aide des commandes du volet Actions. Consultez les sections restantes de cette rubrique pour savoir comment utiliser tous les champs disponibles sur la page.

## <a name="action-pane"></a>Volet Actions

Le volet Actions sur la page **Directives de localisation** contient des boutons que vous pouvez utiliser pour créer, modifier et supprimer des directives (**Modifier**, **Nouveau**, et **Supprimer**). Il contient également les boutons suivants qui vous permettent d’ajuster la séquence dans laquelle l’instruction d’emplacement est traitée et de configurer une requête qui définit les critères d’application de l’instruction d’emplacement :

- **Déplacer vers le haut** – Déplacer l’instruction d’emplacement sélectionnée vers le haut dans la séquence. Par exemple, vous pouvez le déplacer du numéro de séquence 4 au numéro de séquence 3.
- **Déplacer vers le bas** – Déplacer l’instruction d’emplacement sélectionnée vers le bas dans la séquence. Par exemple, vous pouvez le déplacer du numéro de séquence 4 au numéro de séquence 5.
- **Modifier la requête** – Ouvrez une boîte de dialogue dans laquelle vous pouvez définir les conditions dans lesquelles l’instruction d’emplacement sélectionnée doit être traitée. Par exemple, vous souhaiterez peut-être qu’il s’applique uniquement à un entrepôt spécifique.

## <a name="location-directives-header"></a>En-tête des instruction d’emplacement

L’en-tête de l’instruction d’emplacement comprend les champs suivants pour le numéro de séquence et le nom descriptif de l’instruction d’emplacement :

- **Numéro de séquence** – Ce champ indique la séquence dans laquelle le système tente d’appliquer chaque instruction d’emplacement pour le type d’ordre de travail sélectionné. Les nombres bas sont appliqués en premier. Vous pouvez modifier la séquence en utilisant les boutons **Déplacer vers le haut** et **Déplacer vers le bas** du volet Actions.
- **Nom** – Entrez un nom descriptif pour l’instruction d’emplacement. Ce nom devrait aider à identifier l’usage général de la directive. Par exemple, entrez *Prélèvement de la commande client dans l’entrepôt 24*.

## <a name="location-directives-fasttab"></a>Raccourci instruction d’emplacement

Les champs sur le raccourci **instruction d’emplacement** sont spécifiques au type d’ordre de travail sélectionné dans le champ **Type d’ordre de travail** dans le volet de liste.

- **Type de travail** – Sélectionnez le type de travail devant être effectué. Les valeurs disponibles dépendent du type de mouvement de stock sélectionné dans le champ **Type d’ordre de travail**. Vous devez sélectionner l’une des valeurs suivantes :

    - **Ranger** – L’instruction d’emplacement essaiera de trouver l’emplacement le plus adapté pour ranger ou localiser l’inventaire qui entre dans le système par la réception, la production ou les ajustements du stock. Il permet également de définir le rangement à l’emplacement intermédiaire ou à l’emplacement d’expédition final.
    - **Prélever** – L’instruction d’emplacement essaiera de trouver les emplacements les plus adaptés pour réserver physiquement le stock (autrement dit, créer un travail). Le prélèvement peut être effectué (c’est-à-dire que la ligne de travail de prélèvement peut être clôturée), même si le travail n’est pas terminé. L’utilisateur peut effectuer le prélèvement physique. Dans le système, cette action est une étape de prélèvement. L’utilisateur peut ensuite annuler le travail à partir de l’appareil mobile et le terminer ultérieurement. Toutefois, l’en-tête de travail est d’abord clôturé lorsque le placement final est terminé.

    > [!IMPORTANT]
    > Les autres valeurs du champ **Ordre de travail** ne sont pas pertinents pour les instructions d’emplacement. Ils apparaissent uniquement parce que le champ n’est pas filtré pour correspondre au type d’ordre de travail sélectionné.

- **Site** – Ce champ est obligatoire, car l’instruction d’emplacement doit déterminer le site et l’entrepôt pour lesquels elle est valide.
- **Entrepôt** – Ce champ est obligatoire, car l’instruction d’emplacement doit déterminer le site et l’entrepôt pour lesquels elle est valide.
- **Code directive** – Sélectionnez le code d’instruction à associer à un modèle de travail ou à un modèle de réapprovisionnement. Sur la page **Code de l’instruction**, vous pouvez créer des codes pouvant être utilisés pour connecter des modèles de travail ou de réapprovisionnement à des instruction d’emplacement. Les codes de directives peuvent également être utilisées pour établir un lien entre une ligne de modèle de travail et une instruction d’emplacement (par exemple un emplacement de porte de baie ou intermédiaire).

    > [!TIP]
    > Si un code de directive est défini, le système ne recherche pas les instructions d’emplacement par numéro de séquence lorsque le travail doit être généré. Au lieu de cela, il recherche par code de directive. Ainsi, vous pouvez être plus spécifique sur le modèle d’emplacement utilisé pour une étape particulier d’un modèle de travail, par exemple l’étape d’échelonnement des matières.

- **SKU multiples** – Définissez cette option sur *Oui* pour activer l’utilisation de plusieurs unités de gestion de stock (SKU) à un emplacement. Par exemple, plusieurs SKU doivent être activés pour l’emplacement de la porte de baie. Si vous activez plusieurs SKU, votre emplacement de rangement sera spécifié dans le travail, comme prévu. Cependant, l’emplacement de rangement ne pourra gérer qu’un ranger avec plusieurs articles (si le travail comprend différents SKU qui doivent être prélevés et rangés). Il ne sera pas en mesure de gérer un rangement avec une seule SKU. Si vous définissez cette option sur *Non*, votre emplacement de rangement ne sera spécifié que si votre rangement ne contient qu’un seul type de SKU.

    > [!IMPORTANT]
    > Pour pouvoir effectuer à la fois des rangements de plusieurs articles et des rangements d’un seul SKU, vous devez spécifier deux lignes qui ont la même structure et la même configuration, mais vous devez définir l’option **SKU multiples** sur *Oui* pour une ligne et *Non* pour l’autre. Par conséquent, pour les opérations de rangement, les instructions d’emplacement doivent avoir deux instruction d’emplacement identiques, même si vous ne faites pas la distinction entre les SKU uniques et multiples sur l’ID d’un travail. Souvent, si vous ne configurez pas ces deux instruction d’emplacement, des emplacements de processus d’entreprise inattendus proviendront de l’instruction d’emplacement appliquée. Vous devez utiliser une configuration similaire pour les instructions d’emplacement qui ont un **Type de travail** de *Rangement* si vous devez traiter des commandes comprenant plusieurs SKU.

    Utilisez l’option **SKU multiples** pour les lignes de travail qui traitent plus d’un numéro d’article. (Le numéro d’article sera vide dans les détails du travail, et il sera défini sur **Plusieurs** sur les pages de traitement de l’application d’entrepôt.)

    Dans un exemple de scénario typique, un modèle de travail est configuré de sorte qu’il comporte plusieurs paires de prélèvement/rangement. Dans ce cas, vous souhaiterez peut-être rechercher un emplacement de préparation spécifique à utiliser pour les lignes avec un **Type de travail** de *Rangement*.

    > [!NOTE]
    > Si l’option **SKU multiples** est définie sur *Oui*, vous ne pouvez pas sélectionner **Modifier la requête** dans le volet Actions, car la requête ne peut pas être évaluée au niveau de l’article lorsqu’il y a plusieurs articles. Pour vous assurer que l’instruction d’emplacement souhaitée est sélectionnée, utilisez le champ **Code de directive** pour guider la sélection de l’instruction d’emplacement liée aux lignes de rangement où ce code de directive est affecté dans le modèle de travail.

    À moins que vous ne travailliez toujours avec des opérations d’article unique ou d’articles mixtes, il est important que vous définissiez deux instruction d’emplacement pour le type de travail *Rangement* : celui où l’option **SKU multiples** est définie sur *Oui* et celui où elle est défini sur *Non*.

- **Code disposition applicable** – Spécifiez si le code disposition de l’instruction d’emplacement doit correspondre au code disposition appliqué à la réception d’article ou si l’instruction d’emplacement peut être sélectionnée en fonction de n’importe quel code disposition. Si vous sélectionnez *Correspondance parfaite* et que le champ **Code disposition** est vide, seuls codes disposition vides seront pris en compte pour cette instruction d’emplacement.

    > [!NOTE]
    > Ce champ est disponible uniquement pour les types d’ordres de travail sélectionnés où le réapprovisionnement est autorisé. Pour une liste complète, consultez la section [Champs spécifiques aux types d’ordres de travail](#fields-specific-types) précédente dans cette rubrique.

- **Localiser par** – Indiquez si la quantité en stock doit être la quantité totale indiquée sur le contenant ou si elle doit être article par article. Utilisez ce champ pour vous assurer que tout le contenu d’un contenant est placé dans un seul emplacement et que le système ne suggère pas de diviser le contenu en plusieurs emplacements pour **APE** (réception de contenant), le **contenant mixte** de réception, et les processus de réception de **groupement**. (Le processus de réception en **Groupement** exige que la *Fonctionnalité de rangement par groupement* soit activée.) Le comportement de la requête de directive de rangement, des lignes et des actions d’instruction d’emplacement variera en fonction de la valeur que vous sélectionnez. Le raccourci **Lignes** n’est utilisé que lorsque **Localiser par** est défini sur *Article*.

    > [!NOTE]
    > Ce champ est disponible uniquement pour les types d’ordres de travail sélectionnés où le réapprovisionnement est autorisé. Pour une liste complète, consultez la section [Champs spécifiques aux types d’ordres de travail](#fields-specific-types).

- **Code de disposition** – Ce champ est utilisé pour les instructions d’emplacement qui ont un type d’ordre de travail *Acheter en ligne*, *Rangement des produits finis*, ou *Ordres de retour*, et un type de travail de *Rangement*. Utilisez-le pour guider le flux afin d’utiliser une instructions d’emplacement spécifique, en fonction du code d’instruction sélectionné par un collaborateur dans l’application d’entrepôt. Par exemple, vous pouvez diriger les marchandises retournées vers un site d’inspection avant qu’elles ne soient renvoyées en stock. Un code disposition peut être lié à un statut de stock. De cette manière, il peut être utilisé pour modifier le statut du stock dans le cadre d’un processus de réception. Par exemple, vous avez un code de disposition, *CQ*, qui définit le statut du stock sur *CQ*. Vous pouvez ensuite avoir une directive d’emplacement distincte pour déplacer ce stock vers un emplacement de quarantaine.

    > [!NOTE]
    > Ce champ est disponible uniquement pour les types d’ordres de travail sélectionnés où le réapprovisionnement est autorisé. Pour une liste complète, consultez la section [Champs spécifiques aux types d’ordres de travail](#fields-specific-types).

## <a name="lines-fasttab"></a>Raccourci Lignes

Utilisez le raccourci **Lignes** pour établir les conditions d’application des actions associées spécifiées sur le raccourci **Actions de directive de localisation**. Pour chaque ligne, vous pouvez spécifier la quantité minimale et la quantité maximale auxquelles les actions doivent s’appliquer. Vous pouvez également spécifier que les actions doivent s’appliquer à une unité de stock spécifique.

- **Numéro de séquence** – Entrez la séquence dans laquelle chaque ligne d’instruction d’emplacement sera traitée pour le type de travail sélectionné. Vous pouvez modifier la séquence comme requis en utilisant les boutons **Déplacer vers le haut** et **Déplacer vers le bas** de la barre d’outils.
- **Quantité de départ** – Spécifiez le début de la plage de quantités à laquelle s’applique la ligne. Spécifiez la quantité dans l’unité de mesure sélectionnée dans le champ **Unité**.
- **Quantité d’arrivée** – Spécifiez le fin de la plage de quantités à laquelle s’applique la ligne. Spécifiez la quantité dans l’unité de mesure sélectionnée dans le champ **Unité**.
- **Unité** – Sélectionnez l’unité de mesure des articles. Vous pouvez spécifier une quantité minimale et une quantité maximale auxquelles l’instruction doit s’appliquer, vous pouvez spécifier que l’instruction doit concerner une unité de stock spécifique. Le champ **Unité** est utilisé *uniquement* pour l’évaluation de la quantité. Pour déterminer si la ligne d’instruction d’emplacement s’applique, le système utilise les quantités de l’unité spécifiée sur cette ligne. Chaque fois qu’elle est atteinte un ligne de directive d’emplacement, le système essaie de convertir l’unité de la demande dans l’unité spécifiée sur la ligne. Si la conversion d’unité de mesure n’existe pas, le système passe à la ligne suivante.
- **Localiser la quantité** – Ce champ n’est utilisé que lors des tentatives de placement ou de localisation d’articles dans l’entrepôt. (Par conséquent, il s’applique que lorsque le champ **Type de travail** est défini sur *Rangement*). Sélectionnez l’une des valeurs suivantes pour spécifier la quantité utilisée pour évaluer si une quantité est comprise dans l’intervalle de la **Quantité de départ** à la **Quantité d’arrivée** :

    - **Quantité de contenant** – Utilisez la quantité sur le contenant qui est reçu.
    - **Quantité unitisée** – Utilisez la quantité utilisée lors de la transaction. Par exemple, vous recevez une quantité de 1 000 dans un entrepôt et la divisez en 10 contenant, chacun contenant une quantité de 100. Dans ce cas, vous pouvez utiliser une quantité de 1 000 articles au lieu de la quantité de contenant de 100.
    - **Quantité restante** – Utilisez la quantité qui doit encore être reçue sur la ligne de commande fournisseur en cours de traitement.
    - **Quantité attendue** – Utilisez la quantité totale de la ligne de commande, indépendamment de ce qui a déjà été reçu.

- **Restreindre à l’unité** – Cette case à cocher vous permet de rendre la ligne de directive d’emplacement spécifique à une unité de mesure ou à plusieurs unités de mesure. Cochez cette case pour restreindre les unités de mesure considérées comme des critères de sélection valides pour les lignes d’instruction d’emplacement. Cette fonctionnalité ne fonctionne que pour les directives d’emplacement où le champ **Type de travail** est défini sur *Ranger*.

    Par exemple, lorsque vous réservez des quantités, vous souhaitez réserver des palettes uniquement à partir d’un ensemble spécifique d’emplacements. Dans ce cas, les lignes limiteront cette séquence aux palettes de telle sorte que toute quantité inférieure à une palette ne sera pas sélectionnée pour la directive d’emplacement.

    Notez que la case à cocher **Restreindre à l’unité** ne contrôle pas l’unité ou les unités appliquées sur les lignes de travail. La restriction d’unité s’applique uniquement aux unités mises à disposition via le groupe de séquences d’unités. Par exemple, un article est associé à un groupe de séquences d’unités qui comprend l’unité *palettes* et *pcs*. Une unité de mesure a été définie où 1 palette = 100 pièces, et l’instruction d’emplacement utilise la fonctionnalité **Restreindre à l’unité** uniquement pour les palettes. En outre, un modèle de travail a été défini qui limite la création de l’en-tête de travail à 50 pièces. Dans ce cas, des lignes de travail de 50 pièces seront créées. Pour spécifier l’unité de mesure de la restriction, procédez comme suit :

    1. Sur le raccourci **Lignes**, sélectionnez **Restreindre à l’unité** dans la barre d’outils. (Ce bouton n’est disponible qu’après avoir coché la case **Restreindre à l’unité** sur la ligne, puis sélectionné **Enregistrer**.)
    1. Sur la page **Restreindre par unités**, dans le champ **Unité**, sélectionnez l’unité de mesure que vous souhaitez restreindre pour les processus de prélèvement et de rangement.

- **Arrondir à l’unité** – Ce champ fonctionne avec la case à cocher **Restreindre à l’unité**. Par exemple, si **Restreindre par unité** et **Arrondir jusqu’à l’unité** sont sélectionnés sur la ligne de directive d’emplacement, le travail généré à partir de l’instruction de prélèvement de matières premières doit être arrondi à un multiple d’une unité de manutention spécifiée sur la page **Restreindre par unité**.

    > [!NOTE]
    > Cette configuration **Arrondir à l’unité** ne fonctionne que pour le type d’ordre de travail de *Prélèvement de matières premières*, et uniquement pour les directives d’emplacement où le champ **Type de travail** est défini sur *Prélèvement*.

- **Localiser la quantité d’emballage** – Si vous spécifiez une quantité d’emballage sur une commande client, un ordre de transfert ou un ordre de fabrication, cette case à cocher vous permet de restreindre le système afin qu’il ne puisse sélectionner que les emplacements qui ont au moins cette quantité d’emballage.

    > [!NOTE]
    > Cette fonctionnalité est utilisée uniquement avec les instructions d’emplacement de type *Prélèvement*.

- **Autoriser le fractionnement** – Spécifie si une instruction d’emplacement peut fractionner la quantité reçue ou la quantité réservée dans plusieurs emplacements d’entrepôt, ou si la quantité totale doit être localisée à un emplacement unique ou réservée à partir d’un emplacement unique pour créer le travail.
- **Modèle de réapprovisionnement immédiat** – Utilisez ce champ pour créer une connexion vers un modèle de réapprovisionnement afin de démarrer immédiatement le réapprovisionnement si les articles ne sont pas affectés. Si vous laissez ce champ vide, le réapprovisionnement d’article ne commencera pas tant que toutes les lignes de l’instruction d’emplacement n’auront pas été traitées.

    > [!NOTE]
    > Ce champ est disponible uniquement pour les types d’ordres de travail sélectionnés où le réapprovisionnement est autorisé. Pour une liste complète, consultez la section [Champs spécifiques aux types d’ordres de travail](#fields-specific-types).

## <a name="location-directive-actions-fasttab"></a>Raccourci Actions de directive d’emplacement

Vous pouvez définir plusieurs actions d’instruction d’emplacement pour chaque ligne. De nouveau, un numéro de souche est utilisé pour déterminer l’ordre dans lequel les actions sont évaluées. À ce niveau, vous pouvez paramétrer une requête pour définir la manière dont le meilleur emplacement dans l’entrepôt est trouvé. Vous pouvez également utiliser les valeurs **Stratégie** prédéfinies pour rechercher un emplacement optimal.

- **Numéro de séquence** – Ce champ indique la séquence dans laquelle les actions seront traitées pour le type de travail sélectionné. Vous pouvez modifier la séquence en utilisant les boutons **Déplacer vers le haut** et **Déplacer vers le bas** de la barre d’outils.
- **Nom** – Entrez le nom de l’action liée à l’instruction d’emplacement. Soyez précis, afin que l’action qui est effectuée soit claire grâce au nom.
- **Utilisation de l’emplacement fixe** – Spécifiez les emplacements que la directive d’emplacement doit prendre en compte. Vous devez sélectionner l’une des valeurs suivantes :

    - **Emplacements fixes et non fixes** – L’instruction d’emplacement prendra en considération tous les emplacements.
    - **N’utiliser des emplacements fixes que pour le produit** – L’instruction d’emplacement ne prendra en considération que des emplacements fixes pour les produits.
    - **N’utiliser des emplacements fixes que pour la variante de produit** – L’instruction d’emplacement ne prendra en considération que des emplacements fixes pour les variantes de produit.

- **Autoriser un stock négatif** – Cochez cette case pour autoriser un stock négatif à l’emplacement d’entrepôt spécifié dans les instructions d’emplacement.
- **Traitement par lots activé** – Cochez cette case pour utiliser des stratégies de traitement par lots pour les articles activés pour le traitement par lots. Il est important de cocher cette case pour les processus qui utilisent des directives d’emplacement pour trouver des emplacements à partir desquels choisir les articles suivis par numéro de lot. De cette façon, la recherche d’emplacements contenant des articles suivis par numéro de lot est incluse. Si cette case est cochée et que le champ **Stratégie** est défini sur *Aucun*, le système passera à la ligne d’action suivante.
- **Stratégie** – Pour faciliter et accélérer la définition des actions associées à chaque ligne de directive d’emplacement, vous pouvez sélectionner l’une des stratégies prédéfinies suivantes :

    - **Aucun** – Aucune stratégie ne sera utilisée.
    - **Faire correspondre la quantité de conditionnement** – Cette stratégie vérifie si un emplacement de prélèvement contient la quantité de conditionnement spécifiée. Cette stratégie n’est valable que lorsque le champ **Type de travail** est défini sur *Prélèvement*.
    - **Consolider** – Cette stratégie consolide des articles à un emplacement spécifique lorsque des articles similaires sont déjà disponibles. Cette stratégie n’est valable que lorsque le champ **Type de travail** est défini sur *Rangement*. Une configuration typique de rangement essaie de consolider sur la première ligne d’action, puis, sur la deuxième ligne d’action, elle essaie de ranger sans consolidation. La consolidation des marchandises améliore l’efficacité du prélèvement ultérieur.
    - **Réservation de traitement par lots FEFO** – Cette stratégie utilise les réservations de traitement par lots FEFO (première date d’expiration, premier sorti). Utilisez-la lorsque le stock est organisé en fonction de la date d’expiration d’un lot et est affecté pour la réservation par lots. Vous ne pouvez utiliser cette stratégie que pour les articles activés pour le traitement par lots. Elle n’est valable que lorsque le champ **Type de travail** est défini sur *Prélèvement*.
    - **Arrondir au traitement par lots complet de LP et FEFO** – Cette stratégie combine les éléments des stratégies *Réservation de traitement de lots FEFO* et *Arrondir à un LP complet*. Elle n’est valide que pour les articles activés pour le traitement par lots et les directives d’emplacement qui ont un type de travail de *Prélever*. La ligne doit être activée pour le traitement par lots pour utiliser la stratégie *Réservation de traitement par lots FEFO* et la stratégie *Arrondir à un LP complet* ne peut être utilisée que pour le réapprovisionnement. Si cette stratégie est configurée avec une limite de stockage sur site, elle peut entraîner une surcharge du lieu de travail de mise sélectionné et ignorer les limites de stockage.
    - **Arrondir à un contenant complet** – Cette stratégie est utilisée pour arrondir la quantité de stock afin qu’elle corresponde à la quantité du contenant affectée aux articles à prélever. Vous ne pouvez utiliser cette stratégie que pour les instructions d’emplacement de réapprovisionnement de type *Prélèvement*. Si cette stratégie est configurée avec une limite de stockage sur site, elle peut entraîner une surcharge du lieu de travail de mise sélectionné et ignorer les limites de stockage.
    - **Guidé par contenant** – Utilisez cette stratégie lorsque vous lancez la commande à l’entrepôt pour créer le travail de prélèvement/rangement. Vous pouvez utiliser cette approche pour plusieurs emplacements. Cette stratégie tentera de réserver et de créer un travail de prélèvement aux emplacements renfermant les contenants demandés qui ont été associés aux lignes d’ordre de transfert. Cependant, si ces actions ne peuvent pas être effectuées, mais que vous souhaitez toujours créer un travail de prélèvement, vous devez revenir à une autre stratégie pour les actions de directive de localisation. En fonction des exigences de votre processus d’entreprise, vous pouvez également rechercher un stock dans une autre zone de l’entrepôt.
    - **Emplacement vide sans travail entrant** – Utilisez cette stratégie pour rechercher des emplacements vides. Un emplacement est considéré comme vide s’il ne contient pas de stock physique, ni aucun travail entrant prévu. Vous ne pouvez utiliser cette stratégie que pour les instructions d’emplacement de type de travail *Rangement*.
    - **FIFO par âge d’emplacement** – Utilisez la stratégie de premier entré, premier sorti (FIFO) pour expédier à la fois les articles suivis par lots et les articles non suivis par lots, en fonction de la date à laquelle le stock est entré dans l’entrepôt. Cette fonctionnalité peut être particulièrement utile pour les stocks non suivis par lots, où aucune date d’expiration n’est pas disponible pour le tri. La stratégie FIFO recherche l’emplacement qui contient la date d’âge la plus ancienne et alloue le prélèvement en fonction de cette date d’âge.
    - **LIFO par âge d’emplacement** – Utilisez la stratégie de dernier entré, premier sorti (LIFO) pour expédier à la fois les articles suivis par lots et les articles non suivis par lots, en fonction de la date à laquelle le stock est entré dans l’entrepôt. Cette fonctionnalité peut être particulièrement utile pour les stocks non suivis par lots, où aucune date d’expiration n’est pas disponible pour le tri. La stratégie LIFO recherche l’emplacement qui contient la date d’âge la plus récente et alloue le prélèvement en fonction de cette date d’âge.

## <a name="example-using-location-directives"></a>Exemple : Utilisation des instructions d’emplacement

Pour cet exemple, imaginez un processus de commande fournisseur dans lequel l’instruction d’emplacement doit trouver de la capacité disponible dans un entrepôt pour des articles en stock qui viennent d’être enregistrés au quai de réception. Vous devez d’abord trouver de la capacité disponible dans l’entrepôt en consolidant le stock disponible existant. Si la consolidation n’est pas possible, vous devez trouver un emplacement vide.

Pour ce scénario, vous devez définir deux actions d’instruction d’emplacement. La première action dans l’ordre doit utiliser la stratégie *Consolider*, et la deuxième doit utiliser la stratégie *Emplacement vide sans travail entrant*. À moins de définir une troisième action pour gérer un scénario de dépassement de capacité, deux résultats sont possibles lorsqu’il n’y a plus de capacité dans l’entrepôt : le travail peut être créé même si aucun emplacement n’est défini, ou le processus de création de travail peut échouer. Les résultats sont déterminés par le paramétrage dans la page **Échecs d’instruction d’emplacement**, dans laquelle vous pouvez choisir de sélectionner ou non l’option **Arrêter le travail à l’échec d’instruction d’emplacement** pour chaque type d’ordre de travail.

## <a name="next-step"></a>Étape suivante

Après avoir créé des instructions d’emplacement, vous pouvez associer chaque code d’instruction à un code de modèle de travail pour la création du travail. Pour plus d’informations, voir [Contrôler le travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="additional-resources"></a>Ressources supplémentaires

- Vidéo : [Analyse approfondie de la configuration de la gestion des entrepôts](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Rubrique d’aide : [Contrôler le travail d’entrepôt à l’aide de modèles de travail et d’instructions d’emplacement](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
