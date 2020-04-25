---
title: Fusionner les traitements par lots de stock
description: Cet article fournit des informations sur la manière de consolider au moins deux traitements par lots de stock dans un traitement par lots fusionné.
author: pjacobse
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa571fb7392f6f7154f7f1bfd908e11e1bebd3a6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214180"
---
# <a name="merge-inventory-batches"></a>Fusionner les traitements par lots de stock

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la manière de consolider au moins deux traitements par lots de stock dans un traitement par lots fusionné.

Lorsque vous fusionnez des traitements par lots, des calculs peuvent aider à optimiser les caractéristiques et les attributs de lot dans le traitement par lots fusionné. Une fois que vous avez sélectionné les traitements par lots sources, vous pouvez réviser et modifier le traitement par lots fusionné avant de le valider. Vous pouvez également transférer la fusion du traitement par lots vers un journal de stock pour approbation. Le stock peut ensuite être réservé ou validé directement à partir de ce journal de stock. Lorsque vous validez un traitement par lots fusionné, le stock est ajusté pour les traitements par lots sources et le traitement par lots fusionné.

## <a name="are-there-any-prerequisites"></a>Y-a-t-il une configuration requise ?
Oui, il existe certaines choses que vous devez paramétrer avant d'utiliser les outils de fusion de traitements par lots. Le tableau suivant décrit la configuration requise.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Page</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Noms des journaux, stock</td>
<td>Vous devez créer un nom de journal de la nomenclature type à utiliser par défaut lors de la validation des fusions de traitements par lots dans les journaux de stock. Facultatif mais recommandé : Vous pouvez spécifier que les réservations soient effectuées automatiquement lorsque la fusion de traitements par lots est transférée au journal de stock. Sinon, il existe un risque que le stock disponible soit modifié après que les détails de la fusion de traitements par lots ont été définis et le journal validé. Pour activer les réservations automatiques pour le nom de journal, sélectionnez  <strong>Automatique</strong>dans le champ <strong><strong>Réservation</strong></strong>.</td>
</tr>
<tr class="even">
<td>Paramètres de gestion des stocks et des entrepôts</td>
<td>Vous devez spécifier le nom du journal par défaut pour le journal de stock.</td>
</tr>
<tr class="odd">
<td>Produits lancés</td>
<td>Voici les paramètres recommandés pour l'article :
<ul>
<li>Pour générer automatiquement des numéros de lot pour les traitements par lots fusionnés, vous devez affecter le produit lancé à un groupe de numéros de lot. Vous pouvez également entrer un numéro de lot manuellement lorsque vous créez un traitement par lots fusionné, ou sélectionnez un numéro de lot existant. Si vous sélectionnez un numéro de lot existant, vérifiez que le lot sélectionné n'a été inclus dans aucun mouvement de stock.</li>
<li>Si vous utilisez une durée de conservation ou des délais de péremption pour le produit lancé, les dates d'un traitement par lots fusionné sont calculées en fonction de la sélection effectuée dans le champ <strong>Calcul de la date de fusion des traitements par lots</strong>. Les options suivantes sont disponibles :
<ul>
<li><strong>Le plus tôt possible</strong> – Le calcul est basé sur la date la plus proche spécifiée pour un traitement par lots source sélectionné pour la fusion des traitements par lots.</li>
<li><strong>Le plus tard possible</strong> – Le calcul est basé sur la date la plus éloignée spécifiée pour un traitement par lots source sélectionné pour la fusion des traitements par lots.</li>
<li><strong>Manuel</strong> – Aucun calcul n'est réalisé. Si une date est la même sur tous les traitements par lots sources, une date est suggérée. Vous pouvez modifier cette date. Si la date n'est pas la même sur les traitements par lots sources, vous pouvez entrer la date manuellement.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Groupe de numéros de lot</td>
<td>Facultatif : Pour générer un numéro de lot lorsque vous créez un traitement par lots fusionné, vous devez affecter un groupe de numéros de lot au produit lancé. Sinon, vous pouvez entrer un numéro de lot manuellement.</td>
</tr>
</tbody>
</table>

## <a name="when-might-i-want-to-merge-batches-of-inventory"></a>Quand fusionner les traitements par lots du stock ?
Voici quelques exemples illustrant des scénarios pour lesquels il peut être utile de fusionner les traitements par lots :

-   Alors que Sammy visite son entrepôt, il remarque qu'il existe plusieurs lots du même article dont les quantités sont basses. Il compte recevoir nouvelles plusieurs livraisons, et se rend compte qu'il peut libérer de l'espace au sol en fusionner les quantités inégales dans un nouveau traitement par lots.
-   Sammy reçoit le stock et il souhaite combiner le nouveau traitement par lots avec un traitement par lots qu'il a déjà reçu pour améliorer la valeur d'attribut de lot du traitement par lots existant. Cela vous permet de créer un nouveau lot.

## <a name="can-i-merge-batches-across-sites-and-legal-entities"></a>Puis-je fusionner des traitements par lots sur plusieurs sites et entités juridiques ?
Non, vous pouvez fusionner uniquement les traitements par lots ayant les mêmes dimensions de site et de stockage d'entrepôt dans une entité juridique. Toutefois, vous pouvez spécifier un emplacement et un ID palette différents pour le traitement par lots fusionné.

## <a name="can-i-merge-partial-quantities"></a>Est-ce que je peux fusionner des quantités partielles ?
Non, vous pouvez fusionner uniquement la quantité complète des traitements par lots. La fonctionnalité de fusion de traitements par lots est conçue comme une fonctionnalité de stock et non une fonctionnalité de production.

## <a name="what-if-the-batches-have-different-batch-attribute-values"></a>Que se passe-t-il si les traitements par lots ont différentes valeurs d'attribut de lot ?
Lorsque vous sélectionnez les traitements par lots sources à combiner dans le traitement par lots fusionné, Supply Chain Management vérifie si tous les traitements par lots possèdent les caractéristiques ou les valeurs d'attribut. Lorsqu'une valeur d'attribut est identique, une valeur est suggérée pour le traitement par lots fusionné. Vous pouvez modifier cette valeur. Les valeurs d'attribut qui ne sont pas identiques sont laissées vides pour le traitement par lots fusionné et vous pouvez entrer ces valeurs manuellement. Si le type d'attribut de lot pour la valeur d'attribut est un entier ou une fraction, et que les valeurs ne sont pas identiques pour tous les traitements par lots sources, la valeur est calculée à l'aide du calcul de la moyenne pondérée. La valeur calculée est arrondie à l'incrément supérieur ou inférieur le plus proche. Si la valeur est vide pour un traitement par lots source, le traitement par lots et sa quantité ne sont pas inclus dans le calcul. **Exemple** L'exemple suivant montre un calcul de la moyenne pondérée pour un traitement par lots fusionné. Deux des traitements par lots sources ont une valeur vide pour un type d'attribut de lot qui est un entier. L'attribut suivant est affecté aux traitements par lots sources.

| Attribut | Minimal | Incrément | Maximal |
|-----------|---------|-----------|---------|
| Niveau     | 3       | 3         | 30      |

Les traitements par lots sources ont les valeurs d'attribut suivantes pour l'attribut **Niveau de lot**.

| Traitement par lots | Quantité | Attribut | Valeur de l'attribut |
|-------|----------|-----------|-----------------|
| B1    | 10       | Niveau     | Blanc           |
| B2    | 15       | Niveau     | 15              |
| B3    | 20       | Niveau     | 20              |
| B4    | 25       | Niveau     | Blanc           |
| B5    | 30       | Niveau     | 25              |

Lorsque vous ajoutez ces traitements par lots en tant que traitements par lots sources, les valeurs suivantes sont attribuées au lot fusionné.

| Traitement par lots | Quantité | Attribut | Valeur de l'attribut |
|-------|----------|-----------|-----------------|
| B6    | 100      | Niveau     | 21              |

Les valeurs et les quantités pour les traitements par lots B1 et B4 ne sont pas incluses dans le calcul de la moyenne pondérée. Par conséquent, voici comment la valeur pour le traitement par lots fusionné est calculée.

| Valeur | Quantité (poids)                              | Poids relatif | Poids relatif × Valeur                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15    | 15                                             | 0.230769231     | 3.461538462                                                           |
| 20    | 20                                             | 0.307692308     | 6.153846154                                                           |
| 25    | 30                                             | 0.461538462     | 11.53846154                                                           |
|       | **Total :** 65, ce qui correspond à la somme des poids |                 | **Total :** 21,5384615, qui est arrondi à 21 (l'incrément le plus proche). |

## <a name="what-if-the-batches-have-different-batch-dates"></a>Que se passe-t-il si les traitements par lots ont des dates de lot différentes ?
Si les traitements par lots ont des dates de traitement différentes, certaines dates sont calculées en fonction des valeurs du groupe **Dates de lot** dans l'organisateur **Traitement par lots fusionné** de la page **Fusion de traitements par lots**. Le système calcule les valeurs pour les champs dans le groupe **Dates de lot**. Ces valeurs comprennent les dates de fabrication, d'expiration, de durée d'expiration et la DLUO. Les dates sont calculées en fonction des paramètres de l'article dans le groupe de champs **Données des articles** de la page **Détails des produits lancés**. Vous pouvez modifier les valeurs ou les entrer manuellement. Pour toutes les autres dates, aucun calcul n'est effectué. Le même principe est utilisé pour les valeurs d'attribut de lot. Si une date est la même pour tous les traitements par lots source, cette date sera suggérée pour le traitement par lots fusionné. Si elle n'est pas la même pour tous les traitements par lots source, la date est vide dans le traitement par lots fusionné et vous pouvez l'entrer manuellement.

## <a name="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge"></a>Que se passe-t-il si les dimensions sont différentes sur les traitements par lots que je souhaite fusionner ?
Voici comment sont gérées les dimensions de produit, de suivi et de stockage :

-   **Dimensions de produit** – Toutes les dimensions de produit pour l'article sélectionné doivent être identiques. Il est impossible de fusionner les traitements par lots sur différentes dimensions de produit.
-   **Dimensions de suivi** – Un nouveau numéro de lot est généré automatiquement si un groupe de numéros de lot est spécifié pour l'article. Si un groupe de numéros de lot n'est pas affecté à un article, vous pouvez sélectionner un traitement par lots existant ou entrer le numéro manuellement. Les numéros de série sont transférés du traitement par lots source aux lignes de journal de stock pour le traitement par lots fusionné.
-   **Dimensions de stockage** – Les dimensions de stockage du site et de l'entrepôt doivent être identiques pour tous les traitements par lots sources et le traitement par lots fusionné. Toutefois, vous pouvez spécifier un nouvel emplacement et un ID palette pour le traitement par lots fusionné.

## <a name="how-does-posting-work"></a>Comment la validation fonctionne-t-elle ?
La validation fonctionne de deux manières, selon que vous utilisez un processus d'approbation pour les journaux ou non. Vous pouvez utiliser les actions **Transférer vers le journal** et **Valider la fusion des traitements par lots** pour transférer la fusion de traitements par lots vers un journal dans lequel elle pourra être vérifiée et validée, ou vous pouvez valider la fusion de traitements par lots directement. La différence principale entre les deux actions est que le transfert vers un journal ne valide pas la fusion des traitements par lots. Les deux actions créeront un nouveau traitement par lots si aucun traitement par lots existant n'est sélectionné, elles mettront à jour tous les détails et les valeurs d'attribut de lot, et elles créeront un journal de stock.

-   **Transférer vers le journal** – Transfère les détails de la fusion de traitements par lots vers un nouveau journal de stock. Si vous avez définit des réservations automatiques, les quantités dans les traitements par lots sources sont réservées. Les détails de la fusion de traitements par lots ne peuvent pas être modifiés. Pour modifier la fusion de traitements par lots, vous devez supprimer le journal. Le journal peut servir de tâche qu'un autre employé devra effectuer ultérieurement. La réservation de la quantité de lot vers la ligne de journal est sécurisée. Cette répartition permet à un planificateur de qualité ou à un responsable d'entrepôt de créer des tâches pour son ou ses employé(s).
-   **Valider la fusion des traitements par lots** – Valide la fusion des traitements par lots directement. Cette action peut être effectuée après la réalisation de la fusion physique.

Vous pouvez approuver le journal de stock pour la fusion de traitements par lots depuis la page de liste **Toutes les fusions de traitements par lots**. Cliquez sur **Journal** &gt; **Valider**. Une fois le journal validé, vous ne pouvez pas modifier les détails du traitement par lots fusionné. Après avoir transféré une fusion de traitements par lots vers un journal de stock, vous ne pouvez modifier les détails que si le journal est supprimé.

## <a name="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal"></a>Une fois que j'ai fusionné un article de poids variable, pourquoi est-ce que je ne peux pas afficher les informations de poids variable dans le journal de stock ?
Vous pouvez fusionner des lots d'articles de poids variable comme tous les autres articles. Toutefois, les informations de poids variable ne sont pas affichées dans le journal de stock. Il est recommandé de vérifier les informations de poids variable avant de transférer la fusion de traitements par lots vers le journal de stock.
