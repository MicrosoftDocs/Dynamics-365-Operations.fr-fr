---
title: Déclaration de taxe INTERVAT
description: Cet article fournit les informations spécifiques au pays/à la région pour la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique uniquement.
author: anasyash
ms.date: 06/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntervat
audience: Application User
ms.reviewer: kfend
ms.custom: 273023
ms.search.region: Belgium
ms.author: anasyash
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: 68c7fc39b462c5ec4171d160bd7c0b05227b5d24
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883102"
---
# <a name="intervat-tax-declaration"></a>Déclaration de taxe INTERVAT

[!include [banner](../includes/banner.md)]
> [!NOTE]
> Cette fonctionnalité a été remplacée par la fonctionnalité de déclaration de TVA. Pour plus d’informations, voir [Déclaration de TVA (Belgique)](emea-bel-vat-declaration-belgium.md).

## <a name="overview"></a>Présentation

Cet article fournit les informations spécifiques au pays/à la région pour la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique.

Vous pouvez créer la déclaration de taxe INTERVAT sous la forme d’un fichier XML. Vous pouvez également prévisualiser les montants de la déclaration de taxe sur la valeur ajoutée (TVA) dans un format imprimable.

La déclaration INTERVAT que vous créez comprend les transactions fiscales de la période en cours. Elle peut également comprendre des corrections de la période précédente, si une transaction a été validée dans la période précédente après la clôture de cette période.

Vous pouvez entrer des informations supplémentaires pour la déclaration et corriger manuellement les données sur la page **Zones de déclaration de taxe supplémentaires**. La correction manuelle peut être nécessaire si, par exemple, vous ne pouvez pas imprimer le montant du code de déclaration dans la déclaration INTERVAT, car le montant est négatif. Les montants négatifs doivent être déduits de la prochaine déclaration de TVA et cette tâche doit être effectuée manuellement à l’aide de corrections. Avant de pouvoir indiquer le montant corrigé, vous devez indiquer quels codes de déclaration de taxe autorisent les corrections.

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables suivantes doivent être configurées avant de commencer à utiliser la déclaration de taxe INTERVAT :

-   Entité juridique
-   Numéro d’enregistrement
-   Informations sur le contact
-   Souches de numéros
-   Journal de validation
-   Administrations fiscales
-   Codes déclaration de taxe
-   Codes taxe
-   Numéro identifiant TVA

### <a name="legal-entity"></a>Entité juridique

1.  Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**, puis sélectionnez votre entité juridique.
2.  Dans l’organisateur **Adresses**, créez une adresse.
3.  Dans le champ **Pays/région**, sélectionnez **Belgique**.
4.  Renseignez les autres composants d’adresse et marquez l’adresse comme **Principale**.
5.  Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, spécifiez le numéro identifiant TVA de votre société.

### <a name="registration-number"></a>Numéro d’enregistrement

1.  Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**.
2.  Sélectionnez **ID enregistrement**, puis, dans l’onglet **ID enregistrement**, sélectionnez **Ajouter**.
3.  Dans le champ **Type d’enregistrement**, sélectionnez une valeur.
4.  Dans le champ **Numéro d’enregistrement**, entrez une valeur.
5.  Dans l’onglet **Général**, entrez une date d’effet. Pour plus d’informations, voir [Numéro d’enregistrement](emea-registration-ids.md).

### <a name="contact-information"></a>Informations sur le contact

1.  Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**.
2.  Dans l’onglet **Informations sur le contact**, ajoutez des lignes pour le numéro de téléphone et l’adresse e-mail et définissez-les sur **Principal**.

### <a name="number-sequences"></a>Souches de numéros

1.  Accédez à **Comptabilité** \> **Paramétrage de la comptabilité** \> **Paramètres de comptabilité**.
2.  Dans l’onglet **Souches de numéros**, définissez des souches de numéros pour les références **ID liste des ventes annuelles** et **ID INTERVAT**.

### <a name="posting-journal"></a>Journal de validation

1.  Allez dans **Comptabilité** \> **Paramétrage du journal** \> **Journaux de validation**.
2.  Sur la page **Paramétrage du journal**, sélectionnez **Créer**. La souche de N° de justificatif est créée automatiquement.

### <a name="sales-tax-authorities"></a>Administrations fiscales

1.  Allez dans **Taxe** \> **Taxes indirectes** \> **Administrations fiscales**.
2.  Vérifiez que le champ **Présentation d’état** est défini sur **Présentation d’état belge**.

### <a name="sales-tax-reporting-codes"></a>Codes déclaration de taxe

-   Allez dans **Taxe** \> **Paramétrage** \> **Taxe** \> **Codes déclaration de taxe** et créez des codes déclaration de taxe.

Si la case à cocher **Correction de taxe** est activée pour un code déclaration de taxe, ce code est disponible à la sélection dans la page **Zones de déclaration de taxe supplémentaires**.

Des exemples de code déclaration de taxe sont fournis dans la section [Paramétrer des codes déclaration de taxe](#set-up-sales-tax-reporting-codes) plus loin dans cet article.

### <a name="sales-tax-codes"></a>Codes taxe

1.  Allez dans **Taxe** \> **Taxes indirectes** \> **Codes taxe**.
2.  Ajoutez ou sélectionnez des informations dans les champs des onglets **État** et **État – avoir**.
3.  Sélectionnez les valeurs requises dans la grille **Codes déclaration de taxe**.

### <a name="tax-exempt-number"></a>Numéro identifiant TVA

1.  Allez dans **Taxe** \> **Paramétrage** \> **Taxe** \> **Numéros identifiant TVA**.
2.  Pour chaque numéro d’identifiant TVA, créez un enregistrement comprenant les informations suivantes :

    -   Dans le champ **Pays/région**, sélectionnez l’enregistrement de taxe de la contrepartie.
    -   Dans le champ **Numéro identifiant TVA**, entrez le numéro identifiant TVA de la contrepartie.
    -   Dans le champ **Nom de la société**, entrez le nom de la contrepartie.

Pour plus d’informations sur le paramétrage des déclarations de fin, voir [Déclarations de TVA pour l’Europe](emea-vat-reporting.md).

## <a name="settings"></a>Paramètres

### <a name="set-up-intervat"></a>Paramétrer INTERVAT

Créez des lignes sur la page **Paramétrage INTERVAT** (**Taxe \> Paramétrage \> Taxe \> Paramétrage INTERVAT**). Les informations que vous entrez dans cette page sont utilisées lorsque vous sélectionnez **Ouvrir le site web** sur la page **Déclaration de taxe INTERVAT**. Créez un élément pour chaque langue. Définissez les champs suivants : **Langue**, **Description** et **URL**.

![Page Paramétrage INTERVAT.](media/1_Intervat_setup.png)

### <a name="set-up-sales-tax-reporting-codes"></a>Paramétrer des codes déclaration de taxe

Pour plus d’informations sur le paramétrage des codes déclaration de taxe, voir [Paramétrer des codes déclaration de taxe](../general-ledger/tasks/set-up-sales-tax-reporting-codes.md).

Si les utilisateurs sont autorisés à corriger manuellement un code déclaration, activez la case à cocher **Corrections de taxe**. Le tableau suivant fournit un exemple de codes déclaration de taxe pour la Belgique.

<table width="100%">
<thead>
<tr>
<td width="17%">
<p><strong>Code et zone correspondante dans la déclaration de TVA</strong></p>
</td>
<td width="71%">
<p><strong>Description</strong></p>
</td>
<td width="10%">
<p><strong>Base/taxe</strong></p>
</td>
</tr>
</thead>
<tbody>
<tr>
<td colspan="3" width="100%">
<p><strong>Section II. Sorties</strong></p>
</td>
</tr>
<tr>
<td width="17%">
<p>100 (Zone 00)</p>
</td>
<td width="71%">
<p>Ventes soumises à une réglementation spéciale.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>01</p>
</td>
<td width="71%">
<p>Fournitures et services soumis au taux de taxe de 6 %%.</p>
<p>Livraison d’un produit ou de transactions de service soumis au taux de taxe de 6 %%.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>02</p>
</td>
<td width="71%">
<p>Fournitures et services soumis au taux de taxe de 12 %%.</p>
<p>Livraison d’un produit ou de transactions de service soumis au taux de taxe de 12 %%.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>03</p>
</td>
<td width="71%">
<p>Fournitures et services soumis au taux de taxe de 21 %%.</p>
<p>Livraison d’un produit ou de transactions de service soumis au taux de taxe de 21 %%.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>44</p>
</td>
<td width="71%">
<p>Services pour lesquels le partenaire contractuel doit la TVA étrangère.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>45</p>
</td>
<td width="71%">
<p>Chiffre d’affaires pour lequel le partenaire contractuel doit la TVA.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>46</p>
</td>
<td width="71%">
<p>Approvisionnement intracommunautaire de marchandises et transactions similaires (expéditions).</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>47</p>
</td>
<td width="71%">
<p>Autres ventes détaxées et autres ventes générées à l’étranger.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>48</p>
</td>
<td width="71%">
<p>Montant des avoirs émis et corrections négatives liées aux ventes des zones 44 et 46.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>49</p>
</td>
<td width="71%">
<p>Montant des crédits émis et ajustements négatifs liés aux autres zones de la section II, « Sorties ».</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p><strong>Section III. Entrées</strong></p>
</td>
</tr>
<tr>
<td width="17%">
<p>81</p>
</td>
<td width="71%">
<p>Montant de tous les achats de biens, matières premières, et consommables, et coûts d’acquisition associés, à l’exclusion de la TVA déductible.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>82</p>
</td>
<td width="71%">
<p>Montant de marchandises diverses et de services, peu importe s’ils sont soumis à la TVA, à l’exclusion de la TVA déductible.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>83</p>
</td>
<td width="71%">
<p>Montant des achats de biens d’équipement, peu importe s’ils sont soumis à la TVA, à l’exclusion de la TVA déductible.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>84</p>
</td>
<td width="71%">
<p>Montant des crédits reçus et ajustements négatifs liés aux ventes des zones 86 et 88.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>8684</p>
</td>
<td width="71%">
<p>Code de déclaration technique pour indiquer les montants des avoirs dans les zones 86 et 84.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>8884</p>
</td>
<td width="71%">
<p>Code de déclaration technique pour indiquer les montants des avoirs dans les zones 88 et 84.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>85</p>
</td>
<td width="71%">
<p>Montant des crédits reçus et ajustements négatifs liés aux autres zones de la section III, « Entrées », à l’exclusion du montant de la TVA (déductible et non déductible).</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>8185</p>
</td>
<td width="71%">
<p>Code de déclaration technique pour indiquer les montants des avoirs dans les zones 81 et 85.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>8285</p>
</td>
<td width="71%">
<p>Code de déclaration technique pour indiquer les montants des avoirs dans les zones 82 et 85.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>8385</p>
</td>
<td width="71%">
<p>Code de déclaration technique pour indiquer les montants des avoirs dans les zones 83 et 85.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>8785</p>
</td>
<td width="71%">
<p>Code de déclaration technique pour indiquer les montants des avoirs dans les zones 87 et 85.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>86</p>
</td>
<td width="71%">
<p>Acquisitions intracommunautaires et transactions similaires.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>87</p>
</td>
<td width="71%">
<p>Autres réceptions pour lesquelles la personne qui est tenue de s’enregistrer doit la TVA.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td width="17%">
<p>88</p>
</td>
<td width="71%">
<p>Services intra-communautaires avec transfert de l’enquête.</p>
</td>
<td width="10%">
<p>Base</p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p><strong>Section IV. Taxes à payer</strong></p>
</td>
</tr>
<tr>
<td width="17%">
<p>54</p>
</td>
<td width="71%">
<p>TVA collectée sur le chiffre d’affaires inclus dans les codes <strong>01</strong>, <strong>02</strong> et <strong>03</strong>.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>55</p>
</td>
<td width="71%">
<p>TVA collectée sur le chiffre d’affaires inclus dans les codes <strong>86</strong> et <strong>88</strong>.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>56</p>
</td>
<td width="71%">
<p>TVA sur les ventes déclarées dans la zone 87, hors importations impliquant le transfert de l’enquête.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>57</p>
</td>
<td width="71%">
<p>TVA sur les importations impliquant le transfert de l’enquête.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>61</p>
</td>
<td width="71%">
<p>Divers ajustements de TVA en faveur de l’État.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>63</p>
</td>
<td width="71%">
<p>TVA devant être retournée, comme indiqué sur les crédits reçus.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p><strong>Section V. Taxes déductibles</strong></p>
</td>
</tr>
<tr>
<td width="17%">
<p>59</p>
</td>
<td width="71%">
<p>Montant de la TVA déductible.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>62</p>
</td>
<td width="71%">
<p>Diverses corrections de TVA en faveur du déclarant.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>64</p>
</td>
<td width="71%">
<p>TVA devant être récupérée en raison des crédits accordés.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p><strong>Section VI. Solde</strong></p>
</td>
</tr>
<tr>
<td width="17%">
<p>71</p>
</td>
<td width="71%">
<p>Taxe devant être payée. Sur l’état INTERVAT, la valeur de cette zone est automatiquement calculée comme la somme des codes de déclaration <strong>54</strong>, <strong>55</strong>, <strong>56</strong>, <strong>57</strong>, <strong>61</strong> et <strong>63</strong>, moins les codes de déclaration <strong>59</strong>, <strong>62</strong> et <strong>64</strong>.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td width="17%">
<p>72</p>
</td>
<td width="71%">
<p>Taxe devant être récupérée. Sur l’état INTERVAT, la valeur de cette zone est automatiquement calculée comme la somme des codes de déclaration <strong>59</strong>, <strong>62</strong> et <strong>64</strong>, moins les codes de déclaration <strong>54</strong>, <strong>55</strong>, <strong>56</strong>, <strong>57</strong>, <strong>61</strong> et <strong>63</strong>.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
<tr>
<td colspan="3" width="100%">
<p><strong>Section VII. Dépôt</strong></p>
</td>
</tr>
<tr>
<td width="17%">
<p>91</p>
</td>
<td width="71%">
<p>TVA réellement due pour la période allant du 1er décembre au 20 décembre. Ce code s’applique à la déclaration mensuelle de décembre.</p>
</td>
<td width="10%">
<p>Taxes</p>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Il n’est pas nécessaire d’entrer les codes **71**, **72** et **91**, car ils sont générés automatiquement.

Pour paramétrer l’affectation de codes déclaration de taxe aux codes taxe, allez dans **Codes taxe \> Paramétrage d’état/Paramétrage d’état – Avoir**. Tenez compte des relations suivantes entre les codes déclaration de taxe :

-   S’il y a un montant dans le code **01**, **02** ou **03**, il devrait également y avoir un montant dans le code **54**.
-   S’il y a un montant dans le code **54**, il devrait également y avoir un montant dans le code **01**, **02** ou **03**.
-   S’il y a un montant dans le code **86**, il devrait également y avoir un montant dans le code **55**.
-   S’il y a un montant dans le code **87**, il devrait également y avoir un montant dans le code **56** ou **57**.
-   La différence entre le montant du code **54** et la somme des codes **01**, **02** et **03** multipliée par les taux de TVA correspondants ne peut pas être supérieure à 61,97 EUR.
-   La différence entre le montant du code **55** et la somme des codes **84** et **86** multipliée par les taux de TVA correspondants ne peut pas être supérieure à 610,97 EUR.
-   La différence entre la somme des montants des codes **56** et **57** et la somme des codes **85** et **87** multipliée par les taux de TVA correspondants ne peut pas être supérieure à 61,97 EUR.
-   Le montant du code **59** doit être supérieur à la somme des codes **81**, **82**, **83**, **84** et **85**.
-   Le montant du code **63** et du code **85** multiplié par les taux de TVA correspondants ne peut pas être supérieur à 61,97 EUR.
-   Le montant du code **64** et du code **49** multiplié par les taux de TVA correspondants ne peut pas être supérieur à 61,97 EUR.


### <a name="download-the-format-for-the-report"></a>Télécharger le format de l’état

Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations d’états électroniques pour le format de déclaration de TVA suivant :

-   Format INTERVAT (BE)

Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)

## <a name="additional-sales-tax-report-boxes"></a>Zones d’état de taxes supplémentaires

1.  Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Zones de déclaration de taxe supplémentaires**.
2.  Sélectionnez **Nouveau** pour créer des lignes contenant des informations supplémentaires sur les codes de déclaration, y compris les corrections manuelles de la déclaration de taxe INTERVAT. Avant de clôturer une période de règlement, vous devez créer la ligne correspondante, en validant le paiement de la taxe ou en créant une déclaration INTERVAT marquée comme **Mettre à jour**. Le tableau suivant décrit les champs que vous devez définir pour une nouvelle ligne.

| **Champ**         | **Description**                                                                                                                                                                           |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Période de règlement | Sélectionnez la période de déclaration applicable.                                                                                                                                                   |
| Date de début         | Indiquez le premier jour de la période du règlement de taxe à calculer. Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**. |
| Au           | Entrez la dernière date de la période de règlement de la taxe.                                                                                                                                   |

3.  Dans l’onglet **Général**, vous pouvez définir les champs suivants :

-   Section **Commandes**

| **Champ**                                 | **Description**                                                                                                                                                                                                                                              |
|-------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Demande le remboursement de la taxe réclamée | Sélectionnez cette option pour demander le remboursement de toute taxe réclamée.                                                                                                                                                                                      |
| Décaissement                              | Entrez le montant du décaissement. Un décaissement ne peut être effectué que pour le mois de décembre (déclaration mensuelle). Le décaissement correspond à la zone 91 de la déclaration de TVA belge. Vous ne pouvez définir ce champ que si le mois est égal à décembre (**12**). |
| Commande d’avis de dépôt                        | Sélectionnez cette option pour demander des pages de dépôt dans le cadre de la déclaration de taxe.                                                                                                                                                                                        |
| Liste annuelle nulle                        | Sélectionnez cette option pour indiquer qu’il n’y a aucune transaction à déclarer et que la société n’a pas d’obligation envers le gouvernement belge de déclarer la vente annuelle de l’année précédente.                                                                |

-   Section **Pourcentages au prorata**

| **Champ**           | **Description**                                                                                                                                                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pourcentage prorata | Entrez la valeur du pourcentage au prorata qui est exportée dans la balise **\<AdjustedValue\>** du fichier XML.                                                                                                              |
| B1, B2, B3, B4, B5  | Entrez les montants des valeurs de B1, B2, B3, B4 et B5, qui sont exportées dans la balise **\<SpecialProRataPercentage\>** du fichier XML, où **\<SpecialProRataGridNumber\>**=**"1"**, **"2"**, **"3"**, **"4"**, **"5"**. |

### <a name="tax-corrections"></a>Corrections de taxe

Suivez ces étapes pour entrer les montants de correction manuelle.

1.  Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Zones de déclaration de taxe supplémentaires**.
2.  Sélectionnez **Corrections de taxe** \> **Ajustements** et définissez les champs suivants.

| **Champ**         | **Description**                                                                                                                                                                           |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Période de règlement | Sélectionnez la période de déclaration applicable.                                                                                                                                                   |
| Date de début         | Indiquez le premier jour de la période du règlement de taxe à calculer. Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**. |
| Au           | Entrez le dernier jour de la période de règlement de la taxe.                                                                                                                                    |
| Code de déclaration    | Sélectionnez le code de déclaration. Seuls les codes de déclaration pour lesquels la case à cocher **Corrections de taxe** est activée sont disponibles lors de l’entrée d’une correction de taxe.                                 |
| Montant            | Entrez le montant de la correction.                                                                                                                                                              |

> [!NOTE]
> Les codes de déclaration composés qui sont utilisés pour les avoirs, comme le code **8185**, ne sont pas disponibles à la sélection. Il en va de même pour les codes **71**, **72** et **91**. Les codes **71** et **72** sont calculés automatiquement lorsque la déclaration de taxe belge est exécutée. Le code **91** est entré d’une autre manière (voir la description du champ **Décaissement** ci-dessus).
>
> Si une période fiscale est mise à jour, un N° de justificatif et une date s’affichent. (Pour plus d’informations, consultez la description de la case à cocher **Mettre à jour** dans la section [Générer une déclaration de taxe INTERVAT](#generate-an-intervat-tax-declaration) plus loin dans cet article.) La période comportant un justificatif et une date est une période de TVA clôturée pour la Belgique. Par conséquent, toutes les valeurs de l’onglet **Général** de la page **Corrections de taxe** sont en lecture seule. Lorsque de nouvelles transactions avec taxes sont entrées pour la période de TVA clôturée, les taxes sont transférées vers la prochaine période fiscale ouverte disponible.


## <a name="generate-an-intervat-tax-declaration"></a>Générer une déclaration de taxe INTERVAT
1.  Allez dans **Taxe** \>**Déclarations \> Taxe \> Déclaration de taxe INTERVAT**.
2.  Sélectionnez **Nouvelle déclaration** pour générer une déclaration de taxe INTERVAT.
3.  Dans la boîte de dialogue **INTERVAT : Déclaration de taxe belge**, définissez les champs suivants.

| **Champ**                | **Description**                                                                                                                                                                                                                                                                                                                                                                                                            |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Période de règlement        | Sélectionnez la période de déclaration applicable.                                                                                                                                                                                                                                                                                                                                                                                    |
| Date de début                | Indiquez le premier jour de la période du règlement de taxe à calculer. Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**.                                                                                                                                                                                                                                  |
| Date de transaction         | Indiquez la date à laquelle la déclaration de taxe est calculée. La valeur par défaut est la date actuelle. Le paiement de la taxe est calculé pour toutes les transactions validées pendant la période de règlement.                                                                                                                                                                                                                     |
| Mise à jour                   | Une case cochée clôture la période et crée un paiement de taxe, s’il n’a pas déjà été créé. Par conséquent, toutes les transactions de TVA entrées dans cette période après la mise à jour sont transférées vers la prochaine période ouverte disponible. Une case cochée crée également la ligne sur la page **Zones de déclaration de taxe supplémentaires**, si elle n’a pas déjà été créée. Aucune des valeurs sur cette nouvelle ligne ne peut être modifiée. |
| Remplacement de la déclaration de TVA | Entrez le numéro d’identification de la déclaration à remplacer.                                                                                                                                                                                                                                                                                                                                                             |
| Fichier                     | Entrez le nom du fichier vers lequel la déclaration de taxe INTERVAT sera exportée.                                                                                                                                                                                                                                                                                                                                                 |
| Mise en correspondance des formats           | Sélectionnez le format **Format INTERVAT (BE)** que vous avez téléchargé précédemment.                                                                                                                                                                                                                                                                                                                                                 |

Vous pouvez également clôturer la période fiscale en générant un paiement de taxe (**Taxe \> Déclarations \> Taxe \> Régler et valider la taxe**).

4.  Cliquez sur **OK**. Le système génère la ligne de déclaration de taxe INTERVAT et un fichier XML INTERVAT.
5.  Passez en revue les informations de la déclaration.

![Page Déclaration de taxe INTERVAT.](media/2_Intervat_tax%20declaration.png)

6.  Dans l’onglet **Général**, vérifiez les champs suivants : **ID INTERVAT**, **Date**, **Période**, **Date de début**, **Date de fin**, **Fréquence**, **Statut** et **Nom du fichier**.
7.  Dans l’onglet **Cadre I : Informations générales**, vérifiez les champs suivants. Vous pouvez modifier ces champs, même si la période a été clôturée. Les exceptions sont les champs de la section **Pourcentages au prorata**. Ces champs sont en lecture seule.

| **Champ**                        | **Description**                                                                                                                                                                                                                                                                           |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nom de la société                     | Nom de la société.                                                                                                                                                                                                                                                                         |
| Numéro de taxe                 | Numéro d’identification fiscale transféré à partir du paramètre que vous avez défini dans la section [Conditions préalables](#prerequisites) plus haut dans cet article.                                                                                                                                   |
| Numéro de l’entreprise                | Numéro d’entreprise transféré à partir du paramètre que vous avez défini dans la section [Conditions préalables](#prerequisites).                                                                                                                                                               |
| Téléphone, E-mail                 | Informations sur le contact transférées à partir du paramètre que vous avez défini dans la section [Conditions préalables](#prerequisites).                                                                                                                                                                 |
| Demande de remboursement        | Cochez cette case pour demander un remboursement de la taxe.                                                                                                                                                                                                                                  |
| Demande de formulaires de paiement        | Cochez cette case pour demander des pages de paiement pour les déclarations de taxe INTERVAT.                                                                                                                                                                                                         |
| Liste annuelle nulle               | Une case cochée indique que cette déclaration est une déclaration vide. La valeur est transférée à partir de la page **Zones de déclaration de taxe supplémentaires** décrite dans la section [Zones de déclaration de taxe supplémentaires](#additional-sales-tax-report-boxes) plus haut dans cet article |
| Remplacement de la déclaration de TVA         | Numéro d’identification de la déclaration, pour remplacer ce que vous avez défini dans la boîte de dialogue **INTERVAT : Déclaration de taxe belge** décrite plus haut dans cette section.                                                                                                          |
| Section **Pourcentages au prorata** | Vérifiez les montants des champs **Pourcentage au prorata**, **B1**, **B2**, **B3**, **B4** et **B5** que vous avez définis sur la page **Zones de déclaration de taxe supplémentaires** décrite dans la section [Zones de déclaration de taxe supplémentaires](#additional-sales-tax-report-boxes).         |

Sur la page **Déclaration de taxe INTERVAT**, vous pouvez effectuer les actions suivantes à l’aide des boutons du volet Actions.

| **Bouton**     | **Description**                                                                                                                                                                                                                                                   |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Paramétrage          | Ouvrez la page **Zones de déclaration de taxe supplémentaires** décrite dans la section [Zones de déclaration de taxe supplémentaires](#additional-sales-tax-report-boxes).                                                                                                     |
| Recréer le fichier | Recréez le fichier INTERVAT si la période n’a pas été clôturée.                                                                                                                                                                                                           |
| Ouvrir le fichier      | Ouvrez le fichier XML généré.                                                                                                                                                                                                                                      |
| Site Web ouvert  | Ouvrez le site web (URL) que vous avez défini sur la page **Paramétrage INTERVAT**.                                                                                                                                                                                           |
| Modifier le statut  | Modifiez le statut en **Envoyé**. Lorsqu’une déclaration est créée, son statut est **Créé**. Après avoir importé manuellement le fichier généré contenant la déclaration INTERVAT sur le site INTERVAT, vous pouvez utiliser ce bouton pour modifier le statut en **Envoyé**. |
| Détails        | Ouvrez la page **Détails INTERVAT**, où vous pouvez examiner les montants des codes de déclaration correspondants.                                                                                                                                                        |

## <a name="generate-an-intervat-summary-tax-declaration"></a>Générer une déclaration de taxe de synthèse INTERVAT
Pour imprimer une déclaration de taxe INTERVAT pour plusieurs périodes fiscales, procédez comme suit.

1.  Allez dans **Taxe** \> **Recherches et états** \> **États de taxe** \> **Déclaration de taxe de synthèse INTERVAT**.
2.  Utilisez les filtres pour spécifier les critères de sélection des données, puis passez en revue les informations de l’état.

![État des déclarations de taxe de synthèse INTERVAT généré.](media/3_Intervat_summary_tax_declarations.png)

## <a name="example"></a>Exemple
L’exemple suivant montre comment paramétrer des codes taxe et des codes déclaration de taxe, valider des transactions et générer la déclaration de taxe INTERVAT.

1.  Accédez à **Administration d’organisation \> Organisations \> Entités juridiques**.
2.  Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, entrez **0466.158.640**.
3.  Sélectionnez **ID enregistrement**, ajoutez une nouvelle ligne, puis définissez les valeurs suivantes :

-   **Type d’enregistrement :** ENTNUM
-   **Numéro d’enregistrement :** BTW BE 0466.158.640

4.  Allez dans **Taxe \> Taxes indirectes \> Taxe \> Codes taxe** et configurez les codes taxe suivants.

| **Code taxe** | **Pourcentage** | **Description**                                                                      |
|--------------------|----------------|--------------------------------------------------------------------------------------|
| BE21               | 21             | Ventes et achats nationaux à un taux de 21 %%.                                |
| BE12               | 12             | Ventes et achats nationaux à un taux de 12 %%.                                |
| BE6                | 6              | Ventes et achats nationaux à un taux de 6 %%.                                 |
| BEEU21             | 21             | Achats dans l’UE à un taux de 21 %% lorsque l’option **Taxe d’utilisation** est définie sur **Oui**. |
| BEEU12             | 12             | Achats dans l’UE à un taux de 12 %% lorsque l’option **Taxe d’utilisation** est définie sur **Oui**. |
| BEEU6              | 6              | Achats dans l’UE à un taux de 6 %% lorsque l’option **Taxe d’utilisation** est définie sur **Oui**.  |
| BEEUS              | 21             | Ventes dans l’UE où l’option **Exonéré** est définie sur **Oui**.                              |

5.  Sur la page **Codes taxe**, dans l’organisateur **Paramétrage d’état**, affectez des codes déclaration aux codes taxe.

Le tableau suivant montre comment affecter les codes déclaration de taxe aux codes taxe.

| **Code taxe** | **Ventes soumises à taxe** | **Vente détaxée** | **Taxe due** | **Achats soumis à taxe** | **Taxe déductible** | **Importation soumise à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|--------------------|-------------------|-------------------|-----------------------|-----------------------|--------------------------|--------------------|-------------|--------------------|
| BE21               | 03                |                   | 54                    |                       |                          |                    |             |                    |
| BE12               | 02                |                   | 54                    |                       |                          |                    |             |                    |
| BE6                | 01                |                   | 54                    |                       |                          |                    |             |                    |
| BEEU21             |                   |                   |                       |                       | 81                       | 86                 | 59          | 55                 |
| BEEU12             |                   |                   |                       |                       | 81                       | 86                 | 59          | 55                 |
| BEEU6              |                   |                   |                       |                       | 81                       | 86                 | 59          | 55                 |
| BEEUS              |                   | 46                |                       |                       |                          |                    |             |                    |

6.  Sur la page **Codes taxe**, dans l’organisateur **Paramétrage d’état – avoir**, affectez des codes déclaration aux codes taxe.

Le tableau suivant montre comment affecter les codes déclaration de taxe aux codes taxe.

| **Code taxe** | **Ventes soumises à taxe CN** | **Vente détaxée CN** | **Taxe collectée CN** | **Achats soumis à taxe CN** | **Taxe déductible CN** | **Importation soumise à taxe CN** | **Taxe d’utilisation CN** | **Contrepartie taxe d’utilisation CN** |
|--------------------|----------------------|----------------------|--------------------------|--------------------------|-----------------------------|-----------------------|----------------|-----------------------|
| BEEU21             |                      |                      |                          |                          | 8184                        | 86                    | 59             | 55                    |
| BEEU12             |                      |                      |                          |                          | 8184                        | 86                    | 59             | 55                    |
| BEEU6              |                      |                      |                          |                          | 8184                        | 86                    | 59             | 55                    |

Au lieu des codes **55** et **59**, vous pouvez utiliser les codes correctifs **63** et **64**.

> [!NOTE]
> La configuration précédente n’est qu’un exemple et dépend de la structure des codes taxe utilisés. Si vous souhaitez que les valeurs soient calculées et transférées dans la déclaration de taxe, pour chaque code taxe utilisé dans le processus de paiement de la taxe, vous devez définir un code déclaration de taxe approprié dans un ou plusieurs champs de l’onglet **Paramétrage d’état**.

7.  Validez les transactions suivantes. Par exemple, pour les factures client, allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**. Pour les factures fournisseur, allez dans **Comptabilité fournisseur** \> **Factures** \> **Journal des factures**.

| **Date**         | **Type de transaction**  | **Montant net** | **Montant de la TVA** | **Code taxe** | **Base de taxe prévue – code de déclaration**                 | **Montant de taxe prévu – code de déclaration** |
|------------------|-----------------------|----------------|----------------|--------------------|--------------------------------------------------------|------------------------------------------|
| 1 février 2020 | Facture client      | 1,100          | 132            | BE12               | 02                                                     | 54                                       |
| 1 février 2020 | Facture fournisseur (UE)   | 1 000          | 210            | BEEU21             | 86 – Base à payer 81 – Déduction de base                  | 55 – Taxe à payer 59 – Déduction de taxe      |
| 2 février 2020 | Facture fournisseur (UE)   | \-200          | \-42           | BEEU21             | 86 – Base à payer 81 – Déduction de base 84 – Base de crédit | 55 – Taxe à payer 59 – Déduction de taxe      |
| 1 février 2020 | Facture client (UE) | 100            | 0              | BEEUS              | 46                                                     | Non applicable                           |

8.  Allez dans **Taxe \> Déclarations \> Taxe \> État de la taxe pour la période de règlement**.
9.  Dans la boite de dialogue **État de la taxe pour la période de règlement**, dans le champ **Version de paiement de la taxe**, sélectionnez **Original**.
10.  Cliquez sur **OK** et passez en revue les données.

![Page Déclaration de taxe INTERVAT générée.](media/4_Intervat_tax_declaration.png)

Notez que le montant de l’avoir est indiqué dans le code **84**.

11.  Allez dans **Taxe \> Déclarations \> Taxe \> Zones de déclaration de taxe supplémentaires**.
12.  Cliquez sur **Nouveau** pour créer une ligne pour février 2020.
13.  Sélectionnez **Corrections de taxe \> Ajustements** et créez une ligne.

![Page Ajustements.](media/5_Adjustments.png)

14.  Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Régler et valider la taxe**.
15.  Dans la boite de dialogue **Régler et valider la taxe**, dans le champ **Version de paiement de la taxe**, sélectionnez **Original**.
16.  Allez dans **Taxe** \> **Déclarations** \> **Taxe** \> **Déclaration de taxe INTERVAT**.
17.  Sélectionnez **Nouvelle déclaration**, définissez les valeurs suivantes :

   -   **Période de règlement :** MEN
   -   **Date de début :** 1/2/2020 (1 février 2020)
   -   **Date de la transaction :** 29/02/2020 (29 février 2020)
   -   **Mettre à jour :** Non
   -   **Mise en correspondance des formats :** Format INTERVAT (BE)

![Nouvelle page Déclaration de taxe INTERVAT.](media/6_Intervat.png)

18.  Cliquez sur **OK**, ouvrez le fichier et examinez le rapport.

![État de déclaration de taxe INTERVAT au format xml.](media/7_Intervat_XML.png)

19.  Sélectionnez **Détails** et examinez les données.

![Page Détails INTERVAT.](media/8_Intervat_details.png)

Notez que le montant du code **62** est égal à **200**.
    
## <a name="reconciliation-reports-for-belgium"></a>États de rapprochement pour la Belgique

Pour plus d’informations sur les états de rapprochement pour la Belgique, voir [États de rapprochement pour la Belgique](emea-bel-reconciliation-reports.md).






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
