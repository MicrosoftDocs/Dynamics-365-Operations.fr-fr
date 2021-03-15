---
title: Déclaration de la liste des ventes intracommunautaires
description: Cet article fournit des informations sur la génération d’un état relatif à la liste des ventes intracommunautaires.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EUSalesList
audience: Application User
ms.reviewer: kfend
ms.custom: 12811
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1e9a566b7dc4dc2ed1970294a22e72b0bd21a7c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003007"
---
# <a name="eu-sales-list-reporting"></a>Déclaration de la liste des ventes intracommunautaires

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la génération d’un état relatif à la liste des ventes intracommunautaires.

<a name="eu-sales-list-reporting"></a>Déclaration de la liste des ventes intracommunautaires
-----------------------

Un fournisseur qui effectue des approvisionnements intracommunautaires en marchandises ou en services aux sociétés établies dans l’Union européenne (EU) doit soumettre une déclaration des livraisons intracommunautaires (liste des ventes intracommunautaires ou EEL). En général l’EEL doit être envoyée à l’administration fiscale pas plus tard que le dernier jour du mois suivant la période de calendrier couverte par l’EEL. Le fournisseur doit indiquer son numéro d’identification de taxe sur la valeur ajoutée (TVA) dans l’EEL et doit également indiquer, par client, les informations suivantes :

-   Numéro d’identification de la taxe sur la valeur ajoutée (TVA) du client de l’UE
-   Valeur totale des approvisionnements intracommunautaires des biens et services qui sont livrés au client de l’UE pendant cette période. Le fournisseur doit également fractionner les approvisionnements généraux en marchandises des approvisionnements de commerce triangulaire. Une transaction de commerce triangulaire implique la livraison directe des marchandises du fournisseur à son client lorsque les deux parties sont enregistrées dans d’autres états membres de l’UE.

À l’aide de l’EEL, les administrations fiscales de chaque état membre de l’UE peuvent vérifier si la TVA a été payée pour chaque transaction intracommunautaire. La combinaison des listings et des déclarations de TVA autorisent les états membres de l’UE à échanger des informations sur le flux des marchandises dans toute l’UE.

## <a name="overview-of-the-eu-sales-list-reporting-process"></a>Vue d’ensemble du processus de génération de liste des ventes intracommunautaires
Vous pouvez effectuer les tâches suivantes pour déclarer la liste des ventes intracommunautaires :

-   Collecter des informations sur les transactions d’échanges intracommunautaires. Une transaction d’échanges intracommunautaires peut être une facture client, une facture financière, une facture de projet ou une facture fournisseur. Une transaction est identifiée selon le pays/la région du compte de contrepartie. Les transactions d’échanges intracommunautaires de différents types sont collectées dans la table Liste des ventes intracommunautaires, dans laquelle elles sont représentées dans l’écran courant. Chaque enregistrement de cette table représente la transaction unique et inclut l’identificateur de TVA d’une contrepartie et la valeur totale des biens et services qui ont été fournis.
-   (Facultatif) Aperçu de l’état **Liste des ventes intracommunautaires**. Vous pouvez prévisualiser et valider l’état **Liste des ventes intracommunautaires** pour une période donnée sous forme de classeur Microsoft Excel.
-   Générer l’état **Liste des ventes intracommunautaires**. L’état **Liste des ventes intracommunautaires** est généré sous forme de fichier électronique d’un format spécifique à chaque état membre de l’UE. En général, un état **Liste des ventes intracommunautaires** contient des informations de base sur la partie de génération d’états et les valeurs des approvisionnements en biens et services. Les informations sont regroupées en fonction du pays et de l’identificateur de TVA d’une contrepartie.
-   Clôturer la période de déclaration de la liste des ventes intracommunautaires. Une fois l’état **Liste des ventes intracommunautaires** généré et envoyé aux autorités, vous pouvez marquer les enregistrements de la table EEL comme **Clôturé**. Ces transactions ne seront pas incluses dans les états supplémentaires.

## <a name="prerequisites"></a>Logiciels requis
Le tableau suivant indique la configuration requise qui doit être en place avant de commencer.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Logiciel requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Paramétrage :</strong> Entité juridique</td>
<td>L’adresse principale de l’entité juridique doit être dans un pays membre de l’UE. Dans la page <strong>Entités juridiques</strong> (cliquez sur <strong>Administration d’organisation</strong> &gt; <strong>Organisations</strong> &gt; <strong>Entités juridiques</strong>), sélectionnez votre entité juridique. Dans l’organisateur <strong>Adresses</strong>, créez une adresse, sélectionnez un pays/une région et d’autres composants d’adresse, puis marquez l’adresse comme <strong>Principale</strong>. Dans l’organisateur <strong>Immatriculation fiscale</strong>, dans le champ <strong>Numéro d’identification fiscale</strong>, spécifiez le numéro identifiant TVA de votre société.</td>
</tr>
<tr class="even">
<td><strong>Paramétrage :</strong> Paramètres d’identification d’exonération fiscale</td>
<td>Définissez les paramètres d’identification d’exonération fiscale dans la page <strong>Paramètres de pays/région</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Taxe</strong> &gt; <strong>Paramètres de pays/région</strong>). Pour chaque pays/région où vous avez des contreparties, créez un enregistrement dans la page, puis spécifiez les informations suivantes :
<ul>
<li><strong>Pays/Région</strong> : Sélectionnez un pays/une région à associer à un identifiant TVA.</li>
<li><strong>Taxe</strong> : Entrez le numéro d’identification d’exonération fiscale (autrement dit, le préfixe du numéro identifiant TVA) pour le pays/la région sélectionné(e).</li>
<li><strong>Vérifier le numéro identifiant TVA</strong> : Activez cette case à cocher pour contrôler l’identifiant TVA pour le pays/la région sélectionné.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Paramétrage : </strong>Numéros identifiant TVA</td>
<td>Créez des numéros identifiant TVA pour les contreparties dans la page <strong>Numéros identifiant TVA</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Taxe</strong> &gt; <strong>Numéros identifiant TVA</strong>). Pour chaque numéro identifiant TVA, créez un enregistrement dans la page, puis spécifiez les informations suivantes :
<ul>
<li><strong>Pays/Région </strong> : Sélectionnez le pays ou la région de l’enregistrement de taxe du compte de contrepartie.</li>
<li><strong>Numéro identifiant TVA</strong> : Entrez le numéro identifiant TVA du compte de contrepartie.</li>
<li><strong>Nom de la société</strong> : (Facultatif) Entrez le nom de la contrepartie.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Paramétrage : </strong>Enregistrement de taxe des contreparties</td>
<td>Définissez les informations d’enregistrement de taxe pour les contreparties dans la page <strong>Tous les clients</strong> (cliquez sur <strong>Ventes et marketing</strong> &gt; <strong>Clients</strong> &gt; <strong>Tous les clients</strong>, sélectionnez un enregistrement client, puis cliquez sur <strong>Options</strong> &gt; <strong>Changer de vue</strong> &gt; <strong>Vue Détails</strong>) ou sur la page <strong>Fournisseurs</strong> (cliquez sur <strong>Approvisionnements</strong> &gt; <strong>Fournisseurs</strong> &gt; <strong>Fournisseurs</strong>, sélectionnez un enregistrement fournisseur, puis cliquez sur <strong>Options</strong> &gt; <strong>Changer de vue</strong> &gt; <strong>Vue Détails</strong>). Dans l’organisateur <strong>Facture et livraison</strong>, dans le champ <strong>Numéro identifiant TVA</strong>, sélectionnez le numéro identifiant TVA.</td>
</tr>
<tr class="odd">
<td><strong>Paramétrage : </strong>Taxe</td>
<td>Définissez des codes taxe à inclure dans l’état <strong>Liste des ventes intracommunautaires</strong> dans la page <strong>Codes taxe</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Taxe indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Codes taxe</strong>). Dans l’organisateur <strong>Paramétrage d’état</strong>, pour chaque code taxe qui doit être compris dans l’état, désactivez la case à cocher <strong>Exclu</strong>. Définissez des paramètres de taxe pour les articles dans la page <strong>Groupes de taxe d’article</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Groupes de taxe d’article</strong>). Pour chaque article du groupe de taxe, sélectionnez une valeur dans le champ <strong>Type de déclaration</strong>. La valeur que vous sélectionnez détermine le montant de la colonne EEL dans laquelle sera inclus le montant de la ligne.
<ul>
<li><strong>Vide</strong> : Le montant de la ligne est inclus dans la colonne <strong>Valeur non affectée</strong>.</li>
<li><strong>Article</strong> : Le montant de la ligne de taxe est inclus dans la colonne <strong>Valeur des articles</strong>.</li>
<li><strong>Service</strong> : Le montant de la ligne de taxe est inclus dans la colonne <strong>Valeur des services</strong>.</li>
<li><strong>Investissement</strong> : Le montant de la ligne de taxe est inclus dans la colonne <strong>Valeur d’investissement</strong>. Cette colonne n’est pertinente que pour la Belgique.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Paramétrage :</strong> Configurations des états EEL</td>
<td>Importer ou créer des configurations de génération d’état électronique pour l’EEL. Pour plus d’informations sur la création et la tenue à jour des configurations de génération d’état électronique, voir la documentation sur les états électroniques.</td>
</tr>
<tr class="odd">
<td><strong>Paramétrage : </strong>Paramètres généraux</td>
<td>Définissez des paramètres de déclaration d’EEL dans la page <strong>Paramètres de commerce extérieur</strong> (cliquez sur <strong>Taxe</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Commerce extérieur</strong> &gt; <strong>Paramètres de commerce extérieur</strong>). Spécifiez les paramètres suivants :
<ul>
<li>Onglet <strong>Liste des ventes intracommunautaires</strong> :
<ul>
<li><strong>Générer un état de l’escompte de règlement</strong> : Activez cette case à cocher si un escompte de règlement doit être inclus dans la valeur lorsqu’une transaction est incluse dans l’EEL.</li>
<li><strong>Transférer les achats</strong> : Activez cette case à cocher pour inclure les achats dans l’EEL.</li>
<li><strong>Mise en correspondance des formats de fichier</strong> : Permet de sélectionner le format électronique de génération d’états à utiliser lorsqu’un fichier électronique est généré pour l’EEL.</li>
<li><strong>Mise en correspondance des formats d’état</strong> : Permet de sélectionner le format électronique de génération d’états à utiliser lorsqu’un état de l’aperçu est généré pour l’EEL.</li>
<li><strong>Règle d’arrondi</strong> : Permet de spécifier un nombre réel à utiliser pour l’arrondi. Les montants d’EEL sont arrondis en multiples de ce numéro.</li>
<li><strong>Méthode d’arrondi</strong> : Permet de sélectionner la méthode d’arrondi à utiliser lorsque des montants d’EEL sont arrondis (<strong>Normal</strong>, <strong>Inférieur</strong>, ou <strong>Supérieur</strong>).</li>
<li><strong>Utilisez la valeur minimale</strong> : Activez cette case à cocher si vous souhaitez que les montants inférieurs au nombre de la <strong>Règle d’arrondi</strong> soient arrondis au nombre de la <strong>Règle d’arrondi</strong>.</li>
<li><strong>Nombre de décimales</strong> : Permet de spécifier le nombre de décimales à afficher dans les montants de l’EEL (dans les fichiers électroniques et sur l’état <strong>Aperçu de l’EEL</strong>).</li>
</ul></li>
<li>Onglet <strong>Paramètres de pays/région</strong> : Permet d’identifier des états membres de l’UE. Pour chaque état membre de l’UE, vous pouvez créer un enregistrement dans la page, puis spécifier les informations suivantes :
<ul>
<li><strong>Pays/Région</strong> : Permet de sélectionner un pays/une région.</li>
<li><strong>Type de pays/région</strong> : Si la valeur <strong>Pays/Région</strong> est le pays/la région dans lequel votre société est enregistrée, sélectionnez <strong>Local</strong>. Si la valeur <strong>Pays/Région</strong> est un état membre de l’UE autre que le pays/la région dans lequel votre société est enregistrée, sélectionnez <strong>UE</strong>. Si la valeur <strong>Pays/Région</strong> n&#39;est pas un état membre de l’UE, sélectionnez <strong>Pays tiers/région tierce</strong>.</li>
</ul></li>
<li>Onglet <strong>Souches de numéros</strong> : Sur la ligne où la valeur <strong>Référence</strong> est <strong>Liste des ventes intracommunautaires</strong>, sélectionnez un code souche de numéros.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Transactions liées</strong></td>
<td><ul>
<li>Enregistrement d’une vente pour un client d’un autre état membre de l’UE.</li>
<li>Enregistrement d’une facture financière pour un client d’un autre état membre de l’UE.</li>
<li>Enregistrement d’une facture de projet pour un client d’un autre état membre de l’UE.</li>
<li>Enregistrement d’une facture d’un fournisseur d’un autre état membre de l’UE.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="working-with-the-esl"></a>Utilisation d’EEL
### <a name="collecting-information-about-intra-community-trade-transactions"></a>Collecte d’informations sur les transactions d’échanges intracommunautaires

Les transactions des types suivants peuvent être considérées comme des transactions d’échanges intracommunautaires :

-   Factures client
-   Factures financières
-   Factures de projet
-   Factures fournisseur

Une transaction est considérée comme une transaction d’échanges intracommunautaires si l’adresse de livraison de la transaction est un état membre de l’UE. Pour ces pays/régions, un enregistrement doit exister sous l’onglet **Paramètres de pays/région** de la page **Paramètres de commerce extérieur** et la valeur **Type de pays/région** doit être définie sur **UE**. Les transactions d’échanges intracommunautaires sont marquées dans le champ **Code liste**. Ce champ vous permet également de séparer les transactions générales d’échanges intracommunautaires à partir des transactions du commerce triangulaire. Vous pouvez collecter des informations sur les transactions d’échanges intracommunautaires dans la page **Liste des ventes intracommunautaires** (cliquez sur **Taxe** &gt; **Déclarations** &gt; **Commerce extérieur** &gt; **Liste des ventes intracommunautaires**) à l’aide de la fonction **Transfert**. Cette fonction permet d’inclure des transactions qui ont des montants de différents types de génération d’états (c’est-à-dire., des articles ou des services), en fonction des groupes de taxe d’article qui sont spécifiés dans les lignes de transaction. Vous pouvez également appliquer d’autres filtres pour définir les transactions qui doivent être incluses. La fonction **Transfert** crée un enregistrement dans la page **Liste des ventes intracommunautaires** pour chaque transaction d’échanges intracommunautaires incluse, et spécifie un numéro de compte de contrepartie, un pays/une région, un numéro identifiant TVA, un numéro de facture et une date, et les montants totaux des lignes par type de génération d’états. Elle copie également la valeur **Code liste** à partir de la transaction. Vous pouvez modifier manuellement le code liste pour une transaction dans la page **Liste des ventes intracommunautaires**. La fonction **Transfert** crée des enregistrements où la valeur **Statut de génération d’états** est définie sur **Inclus**. Vous pouvez valider les informations qui sont collectées dans la page **Liste des ventes intracommunautaires** à l’aide de la fonction **Valider**.

### <a name="generating-the-eu-sales-list-report"></a>Déclaration de l’état Liste des ventes intracommunautaires

Vous pouvez déclarer un état **Liste des ventes intracommunautaires** à l’aide de la fonction **Génération d’états** de la page **Liste des ventes intracommunautaires**. La fonction permet de sélectionner une période de déclaration et d’appliquer des filtres pour définir les enregistrements de liste des ventes intracommunautaires à inclure. En outre, vous pouvez spécifier d’autres paramètres spécifiques à chaque pays/région. Vous pouvez également choisir de générer un état de l’aperçu, un fichier électronique, ou les deux. La fonction **Génération d’états** utilise les paramètres d’état et de format de fichier spécifiés dans la page **Paramètres de commerce extérieur**. En général un état **Liste des ventes intracommunautaires** comprend des lignes distinctes qui décrivent les montants totaux des approvisionnements par pays/région de contrepartie, le numéro identifiant TVA et le type de déclaration (les transactions du commerce triangulaire sont incluses). Après avoir généré l’état **Liste des ventes intracommunautaires** pour une période spécifique, vous pouvez marquer les enregistrements de liste des ventes intracommunautaires inclus dans l’état en définissant la valeur de **Statut de génération d’états** sur **Déclaré**. Pour définir ce statut, utilisez la fonction **Marquer comme déclarée** de la page **Liste des ventes intracommunautaires**.

### <a name="closing-the-eu-sales-list-reporting-period"></a>Clôture de la période de déclaration de la liste des ventes intracommunautaires

Lorsque vous avez terminé le processus de génération d’états pour une période spécifique (par exemple, lorsque les administrations fiscales ont accepté l’état **Liste des ventes intracommunautaires**), vous pouvez marquer les enregistrements de la liste des ventes intracommunautaires inclus dans l’état pour la période en définissant la valeur **Statut de génération d’états** sur **Clôturé**. Pour définir ce statut, utilisez la fonction **Marquer comme clôturé** de la page **Liste des ventes intracommunautaires**. Si vous rétablissez la clôture de la période, vous pouvez marquer les enregistrements de la liste des ventes intracommunautaires en définissant la valeur de **Statut de génération d’états** sur **Inclus**. Ces enregistrements peuvent ensuite de nouveau être inclus dans **Liste des ventes intracommunautaires**. Pour définir ce statut, utilisez la fonction **Marquer comme** **inclus** de la page **Liste des ventes intracommunautaires**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]