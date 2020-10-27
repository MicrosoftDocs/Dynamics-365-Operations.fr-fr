---
title: Concepteur de formule
description: Cette rubrique décrit l'utilisation du concepteur de formules pour analyser et tenir à jour les formules dans une arborescence.
author: cvocph
manager: tfehr
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8778d6a4d834af2151e0bced0b0f27d98f088a34
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986996"
---
# <a name="formula-designer"></a>Concepteur de formule

[!include [banner](../includes/banner.md)]

Cette rubrique décrit l'utilisation du concepteur de formules pour analyser et tenir à jour les formules dans une arborescence.

Lorsque vous ouvrez la page **Concepteur de formules** à partir de la page **Produits lancés**, l'arborescence du volet gauche affiche la liste des coproduits et la hiérarchie des substances pour le produit lancé. La structure est dérivée de la hiérarchie des formules actives et approuvées pour l'article sélectionné et ses substances, le site de commande par défaut de l'article et la date réelle.

Cliquez sur **Paramétrage** pour sélectionner différentes configurations et spécifier les informations qui s'affichent dans les lignes de l'arborescence.

Cliquez sur **Filtre** pour modifier la sélection initiale dans l'affichage. Si vous définissez le principe d'affichage sur **Sélectionné/actif** ou **Sélectionné**, vous pouvez sélectionner des versions de formules ou de gammes individuelles dans l'affichage. Vous pouvez sélectionner des versions de formule non-approuvées et inactives à afficher ou à tenir à jour dans le concepteur de formules.  

> [!NOTE]
> Si vous ouvrez le **Concepteur de formules** à partir de la page de liste **Nomenclatures**, les informations propres à la gamme ne s'affichent pas. Actuellement, la sélection d'une version de formule ou de gamme s'applique à toutes les instances du concepteur de formules.  

Les sections suivantes décrivent la fonctionnalité disponible dans le concepteur de nomenclatures.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>Analyser une structure de formule à l'aide du concepteur de formules
Le concepteur de formules est constitué de deux sections :

-   L'arborescence de la structure de formules.
-   La section Détails, qui indique les détails des données sélectionnées. Lorsque vous sélectionnez un nœud dans l'arborescence, les organisateurs de la section Détails sont mis à jour en fonction de ce nœud :
    -   **Détails de ligne de formule** : Affiche les détails de la ligne de formule sélectionnée dans l'arborescence.
    -   **Données des articles** : Affiche les détails de l'article principal ou de l'article utilisé dans le nœud sélectionné. Vous pouvez cliquer sur **Modifier le produit lancé** pour mettre à jour l'article sélectionné.
    -   **Formule** – Affiche l'en-tête de la formule qui est associé au nœud sélectionné.
    -   **Gamme** : Indiquer l'en-tête de gamme associée au nœud sélectionné.
    -   **Opérations de gamme** : Affiche un aperçu des opérations de la gamme. Lorsqu'une ligne de nomenclature affectée à une opération spécifique est sélectionnée, l'opération est marquée comme **Composant nécessaire aux opérations**.

## <a name="select-a-formula-and-route"></a>Sélectionner une formule et une gamme
Le filtre appliqué pour la formule et la gamme s'affiche en en-tête du concepteur de formules. Vous pouvez modifier le filtre à l'aide de la boîte de dialogue **Filtre**. Le tableau suivant décrit les champs de cette boîte de dialogue.

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
<td>Si le produit fini est un produit générique, vous pouvez définir les dimensions de produit actives pour la sélection principale. Notez que si vous ouvrez le Concepteur de formules pour un produit qui n'est pas un produit générique, aucune dimension de produit ne pourra être sélectionnée dans la boîte de dialogue <strong>Filtrer</strong>.</p></td>
</tr>
<tr class="even">
<td>site ;</td>
<td>Modifiez le site pour lequel l'arborescence des substances est affichée. Le site par défaut est le site de stock par défaut de l'article fini.</td>
</tr>
<tr class="odd">
<td>Principe d'affichage</td>
<td><p>Permet de sélectionner le principe d'affichage de la version qui s'applique à la structure de formule et à la gamme actuelles :</p>
<ul>
<li>Si le principe est défini sur <strong>Actif</strong> ou <strong>Sélectionné/actif</strong>, la version de formule ou de gamme pour cette date est trouvée.</li>
<li>Si le principe est défini sur <strong>Sélectionné/actif</strong> ou <strong>Sélectionné</strong>, vous pouvez sélectionner une version de formule ou de gamme en cliquant sur <strong>Nomenclature</strong> &gt; <strong>Versions de formule</strong> ou <strong>Gamme</strong> &gt; <strong>Versions de gamme</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Date de version</td>
<td>Permet d'entrer la date de version pour la formule et la gamme. La version identifie la version de formule qui doit être utilisée à une date spécifique, en fonction des dates de version dans le paramétrage des versions de formule.</td>
</tr>
<tr class="odd">
<td>Quantité de départ</td>
<td>Filtrez les versions en sélectionnant une quantité de &quot;début&quot; spécifique. Si vous définissez une valeur, différentes versions de formule et de gamme peuvent être sélectionnées.</td>
</tr>
<tr class="even">
<td>Afficher valides uniquement</td>
<td>Si vous cochez la case, l'arborescence affiche uniquement les lignes de formule avec des dates valides. Double-cliquez ou cliquez avec le bouton droit sur une ligne de formule pour ouvrir la page <strong>Modifier la ligne de formule</strong>, sur laquelle vous pouvez voir les dates de validité pour cette ligne de formule.</td>
</tr>
</tbody>
</table>

Si vous utilisez le concepteur de formules pour passer en revue ou modifier les formules constituées d'un ou de plusieurs niveaux de fantômes, la gamme associée à l'article supérieur couvre généralement la totalité de la hiérarchie de formule. Pour simplifier la vue d'ensemble, vous pouvez verrouiller la gamme de niveau supérieur dans l'affichage en cliquant sur **Vue** &gt; **Verrouiller la gamme**. Pour déverrouiller la gamme, cliquez sur **Vue** &gt; **Déverrouiller la gamme**.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Ajouter/modifier des formules et des lignes de formule
Utilisez les fonctions **Lignes de nomenclature** ou **Formule** pour modifier les lignes de nomenclature ou la formule. Si vous sélectionnez un nœud dans l'arborescence, le type de nœud détermine les fonctions disponibles.

| Fonction                            | Description                                                                                               | Type et conditions de nœud |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Lignes de nomenclature &gt; Modifier                 | Permet d'ouvrir une boîte de dialogue dans lequel vous pouvez modifier les attributs de ligne de formule.                                         | Cette fonction est disponible lorsqu'un nœud de ligne de formule est sélectionné. |
| Lignes de nomenclature &gt; Supprimer               | Supprimez une ligne de formule de la formule sélectionnée.                                                          | Cette fonction est disponible lorsqu'un nœud de ligne de formule est sélectionné, et lorsque la formule n'est pas verrouillée pour modification. |
| Lignes de nomenclature &gt; Ajouter avant la ligne      | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner une variante de produit à inclure avant la ligne de formule sélectionnée.     | Cette fonction est disponible lorsqu'un nœud de ligne de formule est sélectionné. |
| Lignes de nomenclature &gt; Ajouter à la nomenclature du composant | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner une variante de produit à inclure à la fin de la formule sélectionnée.   | Cette fonction est disponible lorsque le nœud qui est sélectionné a une ligne de formule sélectionnée. Si cette fonction n'est pas disponible, une version de formule peut être manquante pour la variante d'article sélectionné. Dans ce cas, vous pouvez cliquer sur **Formule** &gt; **Créer une version** pour créer la version manquante du nœud sélectionné. |
| Lignes de nomenclature &gt; Ajouter après la ligne       | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez sélectionner une variante de produit à inclure après la ligne de formule sélectionnée.      | Cette fonction est disponible lorsqu'un nœud de ligne de formule est sélectionné. |
| Formule &gt; Création d'une version         | Permet de créer une version de formule ou une formule pour la variante de produit du nœud sélectionné.                     | Cette fonction est disponible lorsque le nœud de ligne de formule sélectionné est associé à un article dont le type de production est **Nomenclature** ou **Formule**. |
| Formule &gt; Calcul            | Permet d'ouvrir une boîte de dialogue dans laquelle vous pouvez exécuter le calcul du coût ou du prix de vente pour la variante de produit sélectionnée. | Cette fonction est disponible lorsque le nœud qui est sélectionné est associé à une version de formule. |
| Formule &gt; Vérification                  | Permet de valider et de vérifier la formule sélectionnée.                                                                  | Cette fonction est disponible lorsque le nœud qui est sélectionné est associé à une version de formule. |

## <a name="configuring-the-tree-view"></a>Paramétrage de l'arborescence
Cliquez sur **Paramétrage** pour personnaliser les informations qui s'affichent dans l'arborescence du concepteur de formules.


| Groupe de champs |                                                                          Description                                                                          |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Nomenclature     | Utilisez les cases à cocher pour sélectionner les critères affichés dans l'arborescence. Le concepteur de formule affiche les critères sélectionnés en bas des deux onglets. |
|    Gamme    |                                           Utilisez les cases à cocher pour sélectionner les critères affichés pour les gammes.                                           |

