---
title: "Génération d&quot;états de TVA pour Europe"
description: "Cette rubrique fournit des informations générales sur le paramétrage et de générer la déclaration de (VAT) de taxe sur la valeur ajoutée pour certains pays européens."
author: ShylaThompson
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266844
ms.assetid: 06798e29-6140-489e-9b4e-66b45b26be2b
ms.search.region: Austria, Belgium, Czech Republic, Estonia, Finland, Germany, Latvia, Lithuania, Netherlands, Sweden
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 84a639b25c64821e00ca4397f42f69298953e599
ms.lasthandoff: 03/31/2017


---

# <a name="vat-reporting-for-europe"></a>Génération d'états de TVA pour Europe

Cette rubrique fournit des informations générales sur le paramétrage et de générer la déclaration de (VAT) de taxe sur la valeur ajoutée pour certains pays européens.

Cette rubrique fournit une approche générique à paramétrer et à générer la déclaration de TVA. Cette approche est commune à des utilisateurs aux entités juridiques implantées dans des pays/régions suivants :

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

## <a name="vat-statement-overview"></a>Vue d'ensemble de la déclaration de TVA
Le déclaration de TVA est basée sur les montants des transactions de taxe. Le processus de générer une déclaration de TVA fait partie du processus de paiement de la taxe, qui est implémenté par la fonction de taxe de règlement et de valider. Cette fonction permet de calculer la taxe due pour une période donnée. Le calcul du règlement inclut la taxe validée pour la période de règlement sélectionnée pour les transactions de taxe. Le processus pour calculer les données dans un relevé de TVA est basée sur la relation entre les codes taxe et les codes déclaration de taxe, où codes déclaration de taxe correspondent aux champs de relevés de TVA (ou des balises en XML). Pour chaque code taxe, codes déclaration de taxe doivent être définis pour chaque type de transaction, telles que des ventes soumises à taxe, les achats soumis à taxe, importation soumis à taxe. Ces le type de transactions sont décrits dans le champ [codes taxe pour la déclaration de TVA] (codes taxe de #Sales de déclaration de la TVA) section plus loin dans cette rubrique.

Pour chaque code déclaration de taxe, une présentation d'état spécifique doit être déterminée. En même temps, codes taxe sont liés à une administration fiscale particulière dans les périodes de règlement de la taxe. Pour chaque administration fiscale, une présentation d'état doit être déterminée. Ainsi, seules les codes déclaration de taxe avec la même présentation d'état paramétrée pour une administration fiscale en périodes de règlement de la taxe pour le code taxe pouvant être sélectionnés dans le paramétrage des états de code taxe. Une transaction de taxe a généré en validant une commande ou un journal, contient un code taxe, une source de taxe, une direction de la taxe, et les montants de transaction (montant et le montant de la taxe de la base de taxe dans la devise comptable, la devise de taxe, et la devise de la transaction). Selon la combinaison des attributs de transaction de taxe, montants des transactions constituent des montants totaux pour les codes déclaration de taxe spécifiés pour les codes taxe. L'illustration suivante présente la relation de données.

![diagramme](./media/diagram4.jpg)

## <a name="vat-statement-setup"></a>Paramétrage de la déclaration de TVA
Pour générer une déclaration de TVA vous devez paramétrer les suivantes.

### <a name="sales-tax-authorities-for-vat-reporting"></a>Administrations fiscales pour la déclaration de TVA

<!---For general information about setting up a sales tax authority, see [Set up sales tax authorities](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-authorities/). -->
Avant de paramétrer les codes déclaration de taxe, vous devez sélectionner la présentation d'état correcte pour l'administration fiscale. Sous ** des administrations fiscales ** page, dans ** général ** la section, sélectionnez un ** présentation d'état **. Cette mise en page sont utilisées lorsque vous paramétrez des codes déclaration de taxe.

### <a name="sales-tax-reporting-codes"></a>Codes déclaration de taxe

Codes déclaration de taxe sont des codes de zone dans la déclaration de TVA ou référencent des noms au format XML. Ces codes sont utilisés pour regrouper et de préparer des montants pour l'état. Lorsque vous configurez le format électronique de génération d'états de la déclaration de TVA, les noms des montants de résultat sont utilisés. Vous pouvez créer et tenir à jour les codes déclaration de taxe sur ** codes déclaration de taxe ** la page. Vous devez affecter à chaque code une présentation d'état. Après avoir créé les codes déclaration de taxe, vous pouvez choisir les codes dans ** état paramétré ** la section sur ** codes taxe ** la page. <!---For more information, see [Set up sales tax reporting codes](http://ax.help.dynamics.com/en/wiki/set-up-sales-tax-reporting-codes/) and [Sales tax reporting codes page (Field descriptions)](http://ax.help.dynamics.com/en/wiki/sales-tax-reporting-codes-page-field-descriptions/).-->

### <a name="sales-tax-codes-for-vat-reporting"></a>Codes taxe pour la déclaration de TVA

 Les montants et les montants de taxe de base de transactions de taxe peuvent être regroupés sous des codes déclaration dans la déclaration de TVA (des balises XML ou des zones de déclaration). Vous pouvez configurer cela en associant les codes déclaration de taxe pour différents types de transaction pour les codes taxe sur ** codes taxe ** la page. Le tableau suivant décrit les types de transaction dans l'état paramétré pour les codes taxe. Le calcul comprend les transactions pour tous les types de sources à l'exception de la taxe.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Transaction type</strong></td>
<td><strong>Description des transactions et montants à compter sur le type de transaction</strong></td>
</tr>
<tr class="even">
<td><strong>Ventes soumises</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée</li>
<li>La vente est locale (<strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Ventes détaxées</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est exporté (<strong>Direction de la taxe</strong> est <strong>Vente exonérée de TVA</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Sales tax payable</strong></td>
<td>Somme de <strong>Montants de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est locale (<strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Taxable sales credit note</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est locale (<strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Avoir exempté de ventes de télécopie</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est exporté (<strong>Direction de la taxe</strong> est <strong>Vente exonérée de TVA</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Sales tax on sales credit note</strong></td>
<td>Somme de <strong>Montants de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La vente est locale (<strong>Direction de la taxe</strong> est <strong>Taxe collectée</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxable purchases</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L'achat est locale (<strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Tax-free purchase</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L'achat est importation (is)<strong>Direction de la taxe</strong>  <strong>Achats non taxés d'impôts</strong>.</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Sales tax receivable</strong></td>
<td>Somme de <strong>Montants de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L'achat est locale (<strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Taxable purchase credit note</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L'achat est locale (<strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Tax exempt purchase credit note</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L'achat est importation (is)<strong>Direction de la taxe</strong>  <strong>Achats non taxés d'impôts</strong>.</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Sales tax on purchase credit note</strong></td>
<td>Somme de <strong>Montants de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>L'achat est locale (<strong>Direction de la taxe</strong> est <strong>Taxe déductible</strong>).</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxable import</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li><strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong></li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Offset taxable import</strong></td>
<td>Somme contrepassée de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li><strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Taxable import credit note</strong></td>
<td>Somme de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
e<li><strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Offset taxable import credit note</strong></td>
<td>Somme contrepassée de <strong>Montants de base de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li>La direction de la taxe est <strong>Taxe d'utilisation</strong>.</li>
d<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &lt; le 0.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Use tax</strong></td>
<td>Somme de <strong>Montants de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li><strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Offset use tax</strong></td>
<td>Somme contrepassée de <strong>Montants de la taxe</strong> les transactions de taxe qui répondent aux conditions suivantes :
<ul>
<li>La date de transaction se trouve dans la période sélectionnée.</li>
<li><strong>Direction de la taxe</strong> est <strong>Taxe d'utilisation</strong>.</li>
<li>La transaction <strong>Montant de base de taxe</strong> ou <strong>Montant de taxe</strong> &gt; le 0.</li>
</ul></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Pour le tableau ci-dessus, l'on suppose que les critères suivants sont remplis : 
> -   Montant de base de la taxe est un montant de transaction ** origine dans la devise comptable ** du champ.
> -   Montant de la taxe est un montant de transition ** montant réel de la taxe dans la devise comptable ** du champ.

### <a name="configure-the-er-model-and-format-for-the-report"></a>Configurez le modèle et le format d'ER pour l'état

Vous pouvez utiliser (ER) de déclaration électronique pour configurer les relevés et l'état, et d'exporter différents formats électroniques de données sans modifier le code X++. Pour les informations supplémentaires :

-   [Vue d'ensemble des États électroniques](/dynamics365/operations/dev-itpro/dev-itpro/analytics/general-electronic-reporting)
-   [Télécharger les configurations des états électroniques à partir de Lifecycle Services](/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)
-   [Les besoins de localisation – Permet de créer une configuration de GER] (/dynamics365/operations/dev-itpro/analytics/electronic-reporting-configuration)

## <a name="countryspecific-resources-for-vat-statements"></a>Ressources Countryspecific de relevés de TVA
Le déclaration de TVA pour chaque pays doit répondre aux exigences de la législation du pays. Il existe des modèles et des formats généraux prédéfinis des relevés de TVA pour les pays répertoriés dans le tableau suivant.


| Pays        | Informations supplémentaires                                                          |
|----------------|---------------------------------------------------------------------------------|
| Autriche        |  [Détails de la déclaration de TVA pour l'Autriche] (emea-aut-vat-statement-details.md)         |
| Belgique        |                                                                                 |
| République tchèque |  [Détails de relevé de TVA pour République tchèque emea-cze-vat-statement-details.md] ()   |
| Estonie        |  [Détails de relevé de TVA pour l'Estonie emea-est-vat-statement-details.md] () |
| Finlande        |                                                                                 |
| Allemagne        |                                                                                 |
| Italie          | [Détails de relevé de TVA pour l'Italie] (emea-ita-vat-statements-details.md)            |
| Lettonie         | [Détails de relevé de TVA pour la Lettonie emea-lva-vat-statement-details.md] ()           |
| Lituanie      | [Détails de relevé de TVA pour la Lithuanie] (emea-ltu-vat-statement-details.md)         |
| Pays-Bas    |                                                                                 |
| Suède         |                                                                                 |




