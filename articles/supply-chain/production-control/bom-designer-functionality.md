---
title: Fonctionnalités du concepteur de nomenclatures
description: Cette rubrique décrit la manière dont vous pouvez utiliser la page du concepteur de nomenclatures pour concevoir et utiliser des structures arborescentes pour des nomenclatures.
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3bae68c9daf7aaaee1802e1def64d04ccea01b8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569473"
---
# <a name="bom-designer-functionality"></a>Fonctionnalités du concepteur de nomenclatures

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la manière dont vous pouvez utiliser la page du concepteur de nomenclatures pour concevoir et utiliser des structures arborescentes pour des nomenclatures. Vous pouvez cliquer sur Paramétrage pour sélectionner différentes configurations et spécifier les informations qui s'affichent dans les lignes de l'arborescence.

Lorsque vous ouvrez la page **Concepteur de nomenclatures** depuis la page **Produits lancés**, celle-ci affiche la hiérarchie des nomenclatures actives et approuvées pour l'article sélectionné, le site de commande par défaut de l'article et la date réelle.  

Cliquez sur **Filtre** pour modifier la sélection initiale dans l'affichage. En définissant le principe d'affichage sur **Sélectionné/actif ou Sélectionné**, vous pouvez sélectionner des versions individuelles de nomenclature ou de gamme dans l'affichage. Vous pouvez sélectionner des versions de nomenclature non-approuvées et inactives à afficher ou à tenir à jour dans le concepteur de nomenclatures.  

**Remarque :** Si vous ouvrez le concepteur de nomenclatures à partir de la page de liste **Nomenclatures**, les informations propres à la gamme ne s'affichent pas. Actuellement, la sélection d'une version de nomenclature ou d'une version de gamme est une propriété de la version de nomenclature et de la version de gamme, et s'applique à toutes les instances du concepteur de nomenclatures.  

Les sections suivantes décrivent la fonctionnalité disponible sous les différents onglets du concepteur de nomenclatures.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Analyse de la structure de la nomenclature à l'aide du concepteur de nomenclatures
Le concepteur de nomenclatures est constitué de deux sections :

-   L'arborescence de la structure de nomenclature.
-   La section Détails, qui indique les détails des données sélectionnées. Lorsque vous sélectionnez un nœud dans l'arborescence, les organisateurs de la section Détails sont mis à jour en fonction de ce nœud :
    -   **Détails de ligne de nomenclature** : permet d'afficher les détails de la ligne de nomenclature sélectionnée dans l'arborescence.
    -   **Données des articles** : permet d'afficher les détails de l'article principal ou de l'article utilisé dans le nœud sélectionné. Vous pouvez cliquer sur **Modifier le produit lancé** pour mettre à jour l'article sélectionné.
    -   **Nomenclature** : permet d'indiquer l'en-tête de nomenclature associée au nœud sélectionné.
    -   **Gamme** : permet d'indiquer l'en-tête de gamme associée au nœud sélectionné.
    -   **Opérations de gamme** : permet d'indiquer un aperçu des opérations de la gamme. Lorsqu'une ligne de nomenclature affectée à une opération spécifique est sélectionnée, l'opération est marquée comme **Composant nécessaire aux opérations**.

## <a name="selecting-a-bom-and-route"></a>Sélection d'une nomenclature et d'une gamme
Le filtre appliqué pour la nomenclature et la gamme s'affiche en en-tête du concepteur de nomenclatures. Vous pouvez modifier le filtre à l'aide de la boîte de dialogue **Filtre**. Le tableau suivant décrit les champs de cette boîte de dialogue.

<table>
<thead>
<tr class="header">
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dimensions de produit</td>
<td>Si le produit fini est un produit générique, vous pouvez définir les dimensions de produit actives pour la sélection principale. <strong>Remarque :</strong> si vous ouvrez le Concepteur de nomenclatures pour un produit qui n&#39;est pas un produit générique, aucune dimension de produit ne pourra être sélectionnée dans la boîte de dialogue <strong>Filtrer</strong>.</td>
</tr>
<tr class="even">
<td>site ;</td>
<td>Modifiez le site pour lequel l'arborescence de nomenclatures est affichée. Le site par défaut est le site de stock par défaut de l'article fini.</td>
</tr>
<tr class="odd">
<td>Principe d'affichage</td>
<td>Sélectionnez le principe d'affichage de la version qui s'applique à la structure de nomenclature et à la gamme actuelles :
<ul>
<li>Si le principe est défini sur <strong>Actif ou Sélectionné/actif</strong>, la version valide de la nomenclature ou de la gamme pour cette date est trouvée.</li>
<li>Si le principe est défini sur <strong>Sélectionné/actif ou Sélectionné</strong>, vous pouvez sélectionner une version de nomenclature ou de gamme en cliquant sur <strong>Nomenclature</strong> &gt; <strong>Versions de nomenclature</strong> ou <strong>Gamme</strong> &gt; <strong>Versions de gamme</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Date de version</td>
<td>Entrer la date de version pour la nomenclature et la gamme. La version identifie la version de nomenclature utilisée à une date spécifique, tel que déterminé par les dates de version dans le paramétrage des versions de nomenclature.</td>
</tr>
<tr class="odd">
<td>Quantité de départ</td>
<td>Filtrez les versions en sélectionnant une quantité de début spécifique. Si vous définissez une valeur, différentes versions de nomenclature et de gamme peuvent être sélectionnées.</td>
</tr>
<tr class="even">
<td>Afficher valides uniquement</td>
<td>Si vous cochez la case, l'arborescence affiche uniquement les lignes de nomenclature avec des dates valides. Double-cliquez ou cliquez avec le bouton droit sur une ligne de nomenclature pour ouvrir la page <strong>Modifier une ligne de nomenclature</strong>, sur laquelle vous pouvez voir les dates de validité pour cette ligne de nomenclature.</td>
</tr>
</tbody>
</table>

Si vous utilisez le concepteur de nomenclatures pour passer en revue ou modifier les nomenclatures constituées d'un ou de plusieurs niveaux de fantômes, la gamme associée à l'article supérieur couvre généralement la totalité de la hiérarchie de nomenclature. Pour simplifier la vue d'ensemble, vous pouvez verrouiller la gamme de niveau supérieur dans l'affichage en cliquant sur **Vue** &gt; **Verrouiller la gamme**. Pour déverrouiller la gamme, cliquez sur **Vue** &gt; **Déverrouiller la gamme**.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Ajout et modification des nomenclatures et des lignes de nomenclature
Utilisez les fonctions **Lignes de nomenclature** ou **Nomenclature** pour modifier les lignes de nomenclature ou la nomenclature. Si vous sélectionnez un nœud dans l'arborescence, le type de nœud détermine les fonctions disponibles.

| Fonction                            | description ;                                                                                               | Type et conditions de nœud                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lignes de nomenclature &gt; Modifier                 | Permet d'ouvrir une boîte de dialogue dans lequel vous pouvez modifier les attributs de ligne de nomenclature.                                             | Cette fonction est disponible lorsqu'un nœud de ligne de nomenclature est sélectionné.                                                                                                                                                                                                                                   |
| Lignes de nomenclature &gt; Supprimer               | Permet de supprimer une ligne de nomenclature depuis la nomenclature sélectionnée.                                                                  | Cette fonction est disponible lorsqu'un nœud de ligne de nomenclature est sélectionné, et lorsque la nomenclature n'est pas verrouillée pour modification.                                                                                                                                                                                             |
| Lignes de nomenclature &gt; Ajouter avant la ligne      | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner une variante de produit à inclure avant la ligne de nomenclature sélectionnée.         | Cette fonction est disponible lorsqu'un nœud de ligne de nomenclature est sélectionné.                                                                                                                                                                                                                                   |
| Lignes de nomenclature &gt; Ajouter à la nomenclature du composant | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner une variante de produit à inclure à la fin de la nomenclature sélectionnée.       | Cette fonction est disponible lorsque le nœud qui est sélectionné a une ligne de nomenclature sélectionnée. Si cette fonction n'est pas disponible, une version de nomenclature peut être manquante pour la variante d'article sélectionné. Dans ce cas, vous pouvez cliquer sur **Nomenclature** &gt; **Créer une version** pour créer la version manquante du nœud sélectionné. |
| Lignes de nomenclature &gt; Ajouter après la ligne       | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner une variante de produit à inclure après la ligne de nomenclature sélectionnée.          | Cette fonction est disponible lorsqu'un nœud de ligne de nomenclature est sélectionné.                                                                                                                                                                                                                                   |
| Nomenclature &gt; Créer une version             | Permet de créer une version de nomenclature ou une nomenclature pour la variante de produit du nœud sélectionné.                             | Cette fonction est disponible lorsque le nœud de ligne de nomenclature sélectionné est associé à un article dont le type de production est **Nomenclature** ou **Formule**.                                                                                                                                                  |
| Nomenclature &gt; Calcul                | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez exécuter le calcul du coût ou du prix de vente pour la variante de produit sélectionnée. | Cette fonction est disponible lorsque le nœud qui est sélectionné est associé à une version de nomenclature.                                                                                                                                                                                                         |
| Nomenclature &gt; Vérifier                      | Permet de valider et de vérifier la nomenclature sélectionnée.                                                                      | Cette fonction est disponible lorsque le nœud qui est sélectionné est associé à une version de nomenclature.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>Paramétrage de l'arborescence
Cliquez sur **Paramétrage** pour personnaliser les informations qui s'affichent dans l'arborescence du concepteur de nomenclatures.

| Groupe de champs | Description                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nomenclature         | Utilisez les cases à cocher pour sélectionner les critères affichés dans l'arborescence. Le concepteur de nomenclatures affiche les critères sélectionnés en bas des deux onglets. |
| Route       | Utilisez les cases à cocher pour sélectionner les critères affichés pour les gammes.                                                                                    |





