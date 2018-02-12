---
title: "Déclaration de taxe INTERVAT"
description: "Cette rubrique fournit les informations spécifiques au pays/à la région pour la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique uniquement."
author: v-oloski
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxIntervat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 273023
ms.search.region: Belgium
ms.author: v-oloski
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f5c30b13aa18e959fed3b6ac2040f4470157ddf3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="intervat-tax-declaration"></a>Déclaration de taxe INTERVAT

[!include[banner](../includes/banner.md)]


Cette rubrique fournit les informations spécifiques au pays/à la région pour la configuration et la création de la déclaration de taxe INTERVAT pour les entités juridiques en Belgique uniquement.

Vous pouvez créer la déclaration de taxe INTERVAT sous la forme d'un fichier XML. Vous pouvez également inclure des corrections de l'année précédente dans la déclaration INTERVAT. De plus, si vous ne disposiez pas des transactions nécessaires pour l'état du chiffre d'affaires ou la liste annuelle durant le précédent exercice budgétaire, vous pouvez indiquer que cette liste annuelle est vide. Les utilisateurs peuvent ajouter des données de correction dans la page **Zones d'état de taxes supplémentaires**. Dans certains cas, les corrections de taxe sont obligatoires pour la déclaration belge de taxe sur la valeur ajoutée (TVA). C'est le cas des codes de déclaration de taxe 63 et 64, qui sont utilisés pour les pénalités de taxe. D'autres exemples de codes de déclaration de taxe sont 81, 82, 83, et ainsi de suite. Ces codes ne sont pas imprimés lorsque les montants totaux des codes sont négatifs. Ces montants négatifs doivent être déduits de la prochaine déclaration de TVA, lorsque les montants seront de nouveau positifs. Cette tâche doit être exécutée à l'aide d'une correction de taxe. Avant que les utilisateurs fassent une correction de taxe, ils doivent indiquer quels codes de déclaration de taxe sont soumis à des corrections de taxe.

## <a name="prerequisites"></a>Conditions préalables
Le tableau suivant indique les conditions préalables qui doivent être configurées avant de commencer à travailler avec la déclaration de taxe INTERVAT.

|Catégorie|Logiciel requis||
|---------|----------------------------|---------------------------------------------|
|Configuration|Entité juridique|Dans la page <strong>Entités juridiques</strong> (cliquez sur <strong>Administration d'organisation</strong> &gt; <strong>Organisations</strong> &gt; <strong>Entités juridiques</strong>), sélectionnez votre entité juridique. Dans l'organisateur <strong>Adresses</strong>, créez une adresse. Sélectionnez <strong>Belgique</strong> dans le champ <strong>Pays/Région</strong>, remplissez les autres composants d'adresse, et marquez l'adresse comme <strong>Principale</strong>. Dans l'organisateur <strong>Immatriculation fiscale</strong>, dans le champ <strong>Numéro d'identification fiscale</strong>, spécifiez le numéro identifiant TVA de votre société.|
|Configuration| Numéro d'enregistrement|Configurez le numéro d'enregistrement dans la page <strong>Entités juridiques</strong> (cliquez sur <strong>Administration d'organisation</strong> &gt; <strong>Organisations</strong> &gt; <strong>Entités juridiques</strong>). Cliquez sur <strong>ID enregistrement</strong>, puis, dans l'organisateur <strong>ID enregistrement</strong>, cliquez sur <strong>Ajouter</strong>. Sélectionnez une valeur dans le champ <strong>Type d'enregistrement</strong>, puis entrez une valeur dans le champ <strong>Numéro d'enregistrement</strong>. Pour plus d'informations, voir <a href="emea-registration-ids.md">Numéro d'enregistrement</a>.|
|Configuration| Souches de numéros|Configurez les souches de numéros pour <strong>ID liste des ventes annuelles</strong> et <strong>ID INTERVAT</strong> sous l'onglet <strong>Souches de numéros</strong> de la page <strong>Paramètres de comptabilité</strong> (cliquez sur <strong>Comptabilité</strong> &gt; <strong>Paramétrage de la comptabilité</strong> &gt; <strong>Paramètres de comptabilité</strong>).</td>
|Configuration| Journal de validation|Configurez les journaux de validation dans la page <strong>Paramétrage de journaux</strong> (cliquez sur <strong>Comptabilité</strong> &gt; <strong>Paramétrage de journaux</strong>). </td>
|Configuration| Administrations fiscales|Configurez les administrations fiscales dans la page <strong>Administrations fiscales</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Administrations fiscales</strong>). Le champ <strong>Présentation d'état</strong> doit être défini sur <strong>Présentation d'état belge</strong>.|
|Configuration| Codes déclaration de taxe|Paramétrez les codes de déclaration de taxe dans la page <strong>Codes déclaration de taxe</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Taxe</strong> &gt; <strong>SCodes déclaration de taxe</strong>). Les codes de déclaration de taxe pour lesquels la case à cocher <strong>Correction de taxe</strong> est activée sont disponibles à la sélection dans la page <strong>Zones d'état de taxes supplémentaires</strong> (cliquez sur <strong>Corrections de taxe</strong> &gt; <strong>Ajustements</strong>). Un exemple de codes de déclaration de taxe est inclus plus loin dans cette rubrique.|
|Configuration| Codes taxe|Complétez les champs sous les onglets <strong>État</strong> et <strong>État - Avoir</strong> de la page <strong>Codes taxe</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Codes taxe</strong>). Sélectionnez les valeurs de la table <strong>Codes déclaration de taxe</strong>. |
|Configuration| Paramétrage INTERVAT|Créez des éléments pour INTERVAT dans la page <strong>Paramétrage INTERVAT</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Taxe</strong> &gt; <strong>Paramétrage INTERVAT</strong>). INTERVAT permet de compléter les déclarations fiscales électroniques en Belgique. Les informations que vous entrez dans cette page sont utilisées lorsque vous cliquez sur <strong>Ouvrir le site Web</strong> dans la page <strong>Déclaration de taxe INTERVAT</strong>. Vous devez créer un élément pour chaque langue et pour le programme utilisé pour naviguer sur les sites Web. Complétez les champs suivants : Langue, Description, URL.
|Configuration| Numéro identifiant TVA|Créez des numéros identifiant TVA pour les contreparties dans la page <strong>Numéros identifiant TVA</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Taxe</strong> &gt; <strong>Numéros identifiant TVA</strong>). Pour chaque numéro identifiant TVA, créez un enregistrement dans la page, puis spécifiez les informations suivantes :|
|     |                  |Pays/Région</strong> Sélectionnez le pays ou la région de l'enregistrement de taxe du compte de contrepartie.|
|     |                  |Numéro identifiant TVA</strong> Entrez le numéro identifiant TVA du compte de contrepartie.|
|     |                  |Nom de la société</strong> (Facultatif) Entrez le nom de la contrepartie.|
|Configuration|Paramètres de commerce extérieur|Configurez les paramètres de commerce extérieur sous l'onglet <strong>Propriétés de pays/région</strong> de la page <strong><strong>Paramètres de commerce extérieur</strong></strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Commerce extérieur</strong> &gt; <strong>Paramètres de commerce extérieur</strong>). |
|Configuration|Configuration de la déclaration de taxe INTERVAT|Configurez le modèle et le format de Gestion des états électroniques (ER) pour l'état. Voir la section &quot;Configurer le modèle et le format de Gestion des états électroniques pour l'état&quot; plus loin dans cette rubrique. Pour plus d'informations sur la création et la maintenance des configurations ER, consultez la documentation ER.|


Pour plus d'informations sur le paramétrage des déclarations de fin, voir [Déclarations de TVA (EU)](emea-vat-reporting.md).

### <a name="example-setup-of-sales-tax-reporting-codes"></a>Exemple : Paramétrer des codes déclaration de taxe

Le tableau ci-dessous montre un exemple de codes de déclaration de taxe qui peuvent être créés pour des utilisateurs d'entités juridiques en Belgique.

| Codes déclaration de taxe | description ;                                                                                                                                                                                 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 00                       | Vente de biens au taux de taxe de 0 %                                                                                                                                           |
| 01                       | Fournitures et services soumis au taux de TVA de 6 % - La livraison d'un produit ou de transactions de service soumis au taux de taxe de 6 %                                             |
| 02                       | Fournitures et services soumis au taux de TVA de 12 % - La livraison d'un produit ou de transactions de service soumis au taux de taxe de 12 %                                           |
| 03                       | Fournitures et services soumis au taux de TVA de 21 % - La livraison d'un produit ou de transactions de service soumis au taux de taxe de 21 %                                           |
| 44                       | Montant imposable de services aux personnes soumis à taxe (B2B) dans un autre État membre de l'Union européenne (EU) dans lequel la TVA doit être payée par le fournisseur et établie dans un autre État membre |
| 45                       | Montant imposable de travaux de construction                                                                                                                                                        |
| 46                       | Approvisionnement intracommunautaire de marchandises et transactions similaires (expéditions)                                                                                                                        |
| 47                       | Livraison de marchandises à un client dans un autre État membre de l'UE - Approvisionnement de marchandises pour assemblage ou installation à l'étranger, ventes à distance, etc.                                    |
| 48                       | Avoirs et autres corrections négatives pour les codes 44 et 46                                                                                                                             |
| 49                       | Ajustements du produit pour les codes 00, 01, 02, 03, 45, et 47                                                                                                                                    |
| 54                       | Montant total de la TVA collectée sur le chiffre d'affaires inclus dans les codes 01, 02, et 03                                                                                            |
| 55                       | Montant total de la TVA due sur les montants mentionnés dans les codes 86 et 88.                                                                                                   |
| 56                       | Marchandises et services de cofournisseur                                                                                                                                                            |
| 57                       | Importation hors État membre de l'Union européenne, TVA locale                                                                                                                                                                 |
| 59                       | Montant de la TVA déductible indiquée sur les factures entrantes relatives à l'achat de biens et services                                                                  |
| 62                       | Correction : total TVA remboursable                                                                                                                                                           |
| 64                       | La TVA est recouvrable pour les avoirs émis qui sont dus et qui concernent des factures où la TVA a été incluse dans le code 54.                                                       |
| 81                       | Montant de tous les achats de biens, matières premières, et consommables, et coûts d'acquisition associés                                                                                         |
| 82                       | Montant de marchandises diverses et de services, peu importe s'ils sont soumis à la TVA                                                                                               |
| 83                       | Montant d'achat de biens d'équipement, peu importe s'ils sont soumis à la TVA                                                                                                     |
| 84                       | Avoirs reçus qui concernent les transactions liées à des acquisitions intracommunautaires et à des services intracommunautaires pour les codes 86 et 88                                |
| 85                       | Avoirs relatifs à toutes les transactions à l'exception de celles incluses dans le code 84                                                                                         |
| 86                       | Acquisitions intracommunautaires et transactions similaires                                                                                                                                       |

Pour paramétrer l'affectation des codes de déclaration de taxe aux codes taxe, accédez à &gt; **Codes taxe** **Paramétrage d'état/Paramétrage d'état - Avoir**.

## <a name="configure-the-er-model-and-format-for-the-report"></a>Configurer le modèle et le format ER pour l'état
Pour consulter ou modifier la configuration de la déclaration INTERVAT pour les entités juridiques en Belgique, dans la page **Configurations des états**, sélectionnez **Modèle INTERVAT** dans la liste des modèles. Ce modèle est utilisé pour la déclaration INTERVAT belge. Dans le volet Actions, cliquez sur **Concepteur** pour examiner ou modifier le modèle. Pour consulter ou modifier le format de la déclaration INTERVAT pour les entités juridiques en Belgique, dans la page **Configurations des états**, sélectionnez **Modèle INTERVAT** dans la liste des modèles, puis, sous **Modèle INTERVAT**, sélectionnez **Format INTERVAT (BE)**. Dans le volet Actions, cliquez sur **Concepteur** pour examiner ou modifier le format.

## <a name="generate-an-intervat-tax-declaration"></a>Générer une déclaration de taxe INTERVAT
À la fin de la période de déclaration de TVA, exécutez la déclaration de taxe INTERVAT (cliquez &gt;sur **Taxe****Déclarations** &gt; **Taxe**) pour calculer les lignes de déclaration selon la définition des codes de déclaration de taxe créés. Le tableau suivant décrit les champs à paramétrer.

| Champ                    | description ;                                                                                                                                                                                                                                                                                                                                                    |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Période de règlement        | Sélectionnez la période de déclaration applicable.                                                                                                                                                                                                                                                                                                                        |
| Date de début                | Indiquez le premier jour de la période du règlement de taxe à calculer. Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**.                                                                                                                                                                      |
| Date de transaction         | Indiquez la date à laquelle la déclaration de taxe est calculée. La valeur par défaut est la date actuelle. La date de fin de la période de règlement qui s'affiche dans le champ **Début** correspond au champ **Fin** sur la page **Périodes de règlement fiscal**. Le paiement de la taxe est calculé pour toutes les transactions validées pendant la période de règlement. |
| Mise à jour                   | Activez cette case à cocher pour mettre à jour une déclaration qui a été précédemment envoyée.                                                                                                                                                                                                                                                                                   |
| Remplacement de la déclaration de TVA | Entrez le numéro d'identification de la déclaration à remplacer.                                                                                                                                                                                                                                                                                                 |
| Fichier                     | Entrez le nom du fichier vers lequel la déclaration de taxe INTERVAT sera exportée.                                                                                                                                                                                                                                                                                     |
| Mise en correspondance des formats           | Spécifiez **Format INTERVAT (BE)**.                                                                                                                                                                                                                                                                                                                              |

Le système génère automatiquement un fichier XML INTERVAT et vous propose de l'ouvrir.

## <a name="generate-an-intervat-summary-tax-declaration"></a>Générer une déclaration de taxe de synthèse INTERVAT
Pour créer une déclaration de taxe INTERVAT pour plusieurs périodes fiscales et ID déclaration de taxe INTERVAT, cliquez sur **Taxe** &gt; **Recherches et états** &gt; **Déclarations de taxe** &gt; **Déclaration de taxe de synthèse INTERVAT**, puis utilisez les filtres pour spécifier les critères de sélection des données.

## <a name="additional-sales-tax-report-boxes"></a>Zones d'état de taxes supplémentaires
Pour créer des corrections dans la déclaration de taxe INTERVAT pour la période précédente, cliquez sur **Taxe** &gt; **Déclarations** &gt; **Taxe** &gt; **Zones d'état de taxes supplémentaires**. Le tableau suivant décrit les champs à paramétrer.

| Champ             | description ;                                                                                                                                                                               |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Période de règlement | Sélectionnez la période de déclaration applicable.                                                                                                                                                   |
| Date de début         | Indiquez le premier jour de la période du règlement de taxe à calculer. Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**. |
| Au           | Entrez la dernière date.                                                                                                                                                                      |

Pour entrer la correction, cliquez sur **Corrections de taxe** &gt; **Ajustements**, puis complétez les champs suivants.

| Champ             | description ;                                                                                                                                                                               |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Période de règlement | Sélectionnez la période de déclaration applicable.                                                                                                                                                   |
| Date de début         | Indiquez le premier jour de la période du règlement de taxe à calculer. Cette valeur correspond à la date dans le champ **Début** sur la page **Périodes de règlement fiscal**. |
| Au           | Entrez la dernière date.                                                                                                                                                                      |
| Code de déclaration    | Sélectionnez le code de déclaration de taxe. Seuls les codes de déclaration applicables aux corrections de taxe sont activés et disponibles lors de l'entrée d'une correction de taxe.                                                       |
| Montant            | Entrez le montant de la correction.                                                                                                                                                              |



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Codes déclaration de taxe Belgique](http://www.taxexpert.be/bestand/Betekenis%20vakken%20BTW-aangifte.pdf)





