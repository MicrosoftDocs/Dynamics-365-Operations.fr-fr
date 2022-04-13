---
title: Déclaration de TVA pour l’Europe
description: Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.
author: ShylaThompson
ms.date: 03/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 266844
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a1f7611dcf713e80f637a4b3f5542763050ac4a6
ms.sourcegitcommit: 6f6ec4f4ff595bf81f0b8b83f66442d5456efa87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487751"
---
# <a name="vat-reporting-for-europe"></a>Déclaration de TVA pour l’Europe

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations générales sur le paramétrage et la génération de la déclaration de TVA pour certains pays européens.

Cette rubrique fournit une approche générique du paramétrage et de la génération de la déclaration de TVA. Cette approche est commune pour les utilisateurs dans les entités juridiques des pays/régions suivants :

-   Autriche
-   Belgique
-   République tchèque
-   Estonie
-   Finlande
-   Allemagne
-   Lettonie
-   Lituanie
-   Pays-Bas
-   Suède

> [!IMPORTANT]
> Les fonctionnalités décrites dans cette rubrique pour l’Autriche, la République tchèque, l’Allemagne, les Pays-Bas et la Suède sont obsolètes. Pour plus d’informations, voir [Fonctions supprimées et obsolètes](../get-started/removed-deprecated-features-finance.md).
> Utilisez les liens du tableau suivant pour en savoir plus sur le nouveau design des déclarations de TVA dans les pays correspondants.
> 
>
> | Pays        | Informations supplémentaires                                                          |
> |----------------|---------------------------------------------------------------------------------|
> | Autriche        | [Déclaration de TVA (Autriche)](emea-aut-vat-declaration-austria.md)       |                                                                           
> | République tchèque | [Déclaration de TVA (République tchèque)](emea-cze-vat-declaration-tax-declaration-model.md) |
> | Danemark        | [Déclaration de TVA (Danemark)](emea-dnk-vat-declaration-denmark.md)         |
> | France         | [Déclaration de TVA (France)](emea-fra-vat-declaration-preview-france.md)       |
> | Allemagne        | [Déclaration de TVA (Allemagne)](emea-deu-vat-declaration-germany.md)           |
> | Pays-Bas    | [Déclaration de TVA (Pays-Bas)](emea-nl-vat-declaration-netherlands.md)    |
> | Norvège         | [Retour de TVA avec envoi direct à Altinn](emea-nor-vat-return.md) |
> | Espagne          | [Déclaration de TVA (Espagne)](emea-esp-vat-declaration-spain.md)              |
> | Suède         | [Déclaration de TVA (Suède)](emea-swe-vat-declaration-sweden.md)          |
> | Suisse    | [Déclaration TVA (Suisse)](emea-che-vat-declaration-switzerland.md) |
> | Royaume-Uni             | [Préparer l’intégration avec MRD pour la TVA](emea-gbr-mtd-vat-integration.md) |

## <a name="vat-statement-overview"></a>Vue d’ensemble de la déclaration de TVA
La déclaration de TVA est basée sur les montants des transactions de taxe. Le processus de génération d’une déclaration de TVA fait partie du processus de paiement de la taxe, qui est implémenté via la fonction Régler et valider la taxe. Cette fonction calcule la taxe due pour une période donnée. Le calcul du règlement inclut la taxe validée pour la période de règlement sélectionnée pour les transactions de taxe. Le processus de calcul des données d’une déclaration de TVA est basé sur la relation entre les codes taxe et les codes déclaration de taxe, où les codes déclaration de taxe correspondent aux zones de déclaration de TVA (ou balises en XML). Pour chaque code taxe, des codes déclaration de taxe doivent être définis pour chaque type de transaction, par exemple les ventes imposables, les achats imposables, les importations imposables. Ces types de transactions sont décrits dans la section Codes taxe pour la déclaration de TVA plus loin dans cette rubrique.

Pour chaque code déclaration de taxe, une présentation d’état spécifique doit être déterminée. Les codes taxe sont également liés à une administration fiscale spécifique via des périodes de règlement de la taxe. Pour chaque administration fiscale, une présentation d’état doit être déterminée. Ainsi, seuls les codes déclaration de taxe avec la même présentation d’état paramétrée pour une administration fiscale dans les périodes de règlement de la taxe pour le code taxe peuvent être sélectionnés dans le paramétrage d’état du code taxe. Une transaction de taxe générée lors de la validation d’une commande ou d’un journal, contient un code taxe, une source de taxe, une direction de taxe et des montants de transaction (montant de base de la taxe et montant de la taxe dans la devise comptable, la devise de taxe et la devise de la transaction). Selon la combinaison d’attributs de transaction de taxe, les montants des transactions composent les montants totaux pour les codes déclaration de taxe spécifiés pour les codes taxe. La relation des données est illustrée dans le graphique ci-dessous :

![diagramme.](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a>Paramétrage de la déclaration de TVA
Pour générer une déclaration de TVA, vous devez paramétrer les éléments suivants.

### <a name="sales-tax-authorities-for-vat-reporting"></a>Administrations fiscales pour la déclaration de TVA

Avant de paramétrer les codes déclaration de taxe, vous devez sélectionner la présentation d’état correcte pour l’administration fiscale. Dans la page **Administrations fiscales**, dans la section **Général**, sélectionnez une **Présentation d’état**. Cette présentation sera utilisée lors du paramétrage des codes déclaration de taxe.

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](../general-ledger/tasks/set-up-sales-tax-authorities.md). -->

### <a name="sales-tax-reporting-codes"></a>Codes déclaration de taxe

Les codes déclaration de taxe sont des codes de zone dans la déclaration de TVA ou des noms de balise au format XML. Ces codes sont utilisés pour regrouper et préparer les montants pour l’état. Lorsque vous configurez le format de génération d’états électroniques de la déclaration de TVA, les noms des montants de résultat sont utilisés. Vous pouvez créer et tenir à jour les codes déclaration de taxe dans la page **Codes déclaration de taxe**. Vous devez affecter une présentation d’état à chaque code. Après avoir créé les codes déclaration de taxe, vous pouvez choisir les codes dans la section **Paramétrage d’état** de la page **Codes taxe**. <!---For more information, see [Set up sales tax reporting codes](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).-->

### <a name="sales-tax-codes-for-vat-reporting"></a>Codes taxe pour la déclaration de TVA

<!---For general information about setting up sales tax codes, see [Set up sales tax codes](../general-ledger/tasks/set-up-sales-tax-codes.md).--> Les montants de base et les montants de taxe des transactions de taxe peuvent être regroupés à l’aide de codes déclaration dans la déclaration de TVA (balises XML ou zones de déclaration). Pour ce faire, associez les codes déclaration de taxe pour différents types de transaction aux codes taxe dans la page <strong>Codes taxe</strong>. Le tableau suivant décrit les types de transaction dans le paramétrage d’état pour les codes taxe. Le calcul comprend les transactions pour tous les types de sources à l’exception de la taxe.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Type de transaction</strong></td>
<td><strong>Description des transactions et des montants à comptabiliser sur le type de transaction</strong></td>
</tr>
<tr class="even">
<td><strong>Ventes soumises à taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée/</li>
<li>La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Vente détaxée</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxe collectée</strong></td>
<td>Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Avoir soumis à taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Avoir sur vente exonéré de taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est de type exportation (la <strong>Direction de la taxe</strong> est <strong>Vente détaxée</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Taxe sur avoir sur vente</strong></td>
<td>Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est locale (la <strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Achats soumis à taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L’achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Achat détaxé</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L’achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxe déductible</strong></td>
<td>Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L’achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Avoir sur achat soumis à taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L’achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Avoir sur achat exonéré de taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L’achat est de type importation (la <strong>Direction de la taxe</strong> est <strong>Achat détaxé</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Taxe sur avoir sur achat</strong></td>
<td>Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L’achat est local (la <strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Importation soumise à taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La <strong>Direction de la taxe</strong> est <strong>Taxe d’utilisation</strong></li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Contrepartie des importations soumises à taxe</strong></td>
<td>Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La <strong>Direction de la taxe</strong> est <strong>Taxe d’utilisation</strong>.</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Avoir sur importation soumis à taxe</strong></td>
<td>Somme des <strong>Montants de base de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
e<li>La <strong>Direction de la taxe</strong> est <strong>Taxe d’utilisation</strong>.</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Contrepartie des avoirs sur importations soumises à taxe</strong></td>
<td>Somme contrepassée des <strong>Montants de base de la taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La Direction de la taxe est <strong>Taxe d’utilisation</strong>.</li>
d<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &lt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxe d’utilisation</strong></td>
<td>Somme des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La <strong>Direction de la taxe</strong> est <strong>Taxe d’utilisation</strong>.</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Contrepartie taxe d’utilisation</strong></td>
<td>Somme contrepassée des <strong>Montants de taxe</strong> des transactions de taxe qui remplissent les conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La <strong>Direction de la taxe</strong> est <strong>Taxe d’utilisation</strong>.</li>
<li>Le <strong>Montant de base de taxe</strong> ou le <strong>Montant de taxe</strong> &gt; de la transaction est 0.</li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Pour le tableau ci-dessus, on suppose que les critères suivants sont remplis : 
> -   Le montant de base de la taxe est un montant de transaction issu du champ **Origine dans la devise comptable**.
> -   Le montant de la taxe est un montant de transition issu du champ **Montant réel de la taxe dans la devise comptable**.

### <a name="configure-the-er-model-and-format-for-the-report"></a>Configurer le modèle et le format ER pour l’état

Vous pouvez utiliser les états électroniques pour configurer les déclarations et l’état, et pour exporter les données dans différents formats électroniques sans modifier le code X++. Pour des informations supplémentaires :

-   [Vue d’ensemble des états électroniques](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md)
-   [Télécharger les configurations d’états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [Exigences de localisation – Créer une configuration GER](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md)

## <a name="countryspecific-resources-for-vat-statements"></a>Ressources spécifiques au pays pour les déclarations de TVA
La déclaration de TVA pour chaque pays doit répondre aux exigences de la législation du pays. Il existe des modèles et des formats généraux prédéfinis de déclarations de TVA pour les pays répertoriés dans le tableau suivant.


| Pays        | Informations supplémentaires                                                          |
|----------------|---------------------------------------------------------------------------------|
| Autriche        | [Détails de la déclaration de TVA pour l’Autriche](emea-aut-vat-statement-details.md)         |
| Belgique        |                                                                                 |
| République tchèque | [Relevé de TVA – République tchèque](emea-cze-vat-statement-details.md)   |
| Estonie        | [Détails de la déclaration de TVA pour l’Estonie](emea-est-vat-statement-details.md) |
| Finlande        | [Déclaration de taxe pour la Finlande](emea-fin-sales-tax-payment-report-finland.md)          |
| Allemagne        | [Déclaration de TVA pour l’Allemagne](emea-de-vat-declaration.md)                       |
| Italie          | [Détails de la déclaration de TVA pour l’Italie](emea-ita-vat-statements-details.md)            |
| Lettonie         | [Détails de la déclaration de TVA pour la Lettonie](emea-lva-vat-statement-details.md)           |
| Lituanie      | [Détails de la déclaration de TVA pour la Lituanie](emea-ltu-vat-statement-details.md)         |
| Pays-Bas    | [Déclaration de TVA pour les Pays-Bas](emea-nl-vat-declaration.md)           |
| Suède         | [Déclaration de taxe pour la Suède](emea-swe-sales-tax-payment-report-sweden.md)          |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
