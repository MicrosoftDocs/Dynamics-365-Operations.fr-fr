---
title: Déclaration d'échanges de biens
description: Cette rubrique fournit des informations sur la génération d'états de déclaration d'échanges de biens pour le commerce de marchandises et, dans certains cas, pour les services entre les pays/régions de l'Union européenne (UE). Il fournit une vue d'ensemble du processus de déclaration, et décrit les paramètres et les conditions préalables requises.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 50eb50c636d70dbdc374e8cfc89438433fb1f1b0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555511"
---
# <a name="intrastat"></a>Déclaration d'échanges de biens

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la génération d'états de déclaration d'échanges de biens pour le commerce de marchandises et, dans certains cas, pour les services entre les pays/régions de l'Union européenne (UE). Il fournit une vue d'ensemble du processus de déclaration, et décrit les paramètres et les conditions préalables requises.

Intrastat est le système de collecte d'informations et de génération de statistiques sur le commerce de marchandises entre les pays/régions de l'Union européenne (UE). Une génération d'états Intrastat est requise chaque fois qu'un produit franchit la frontière d'un autre pays/région de l'Union Européenne. Dans plusieurs pays/régions, la génération d'états Intrastat s'applique également aux services. Les éléments obligatoires et facultatifs peuvent être collectés dans la génération d'états Intrastat. Les éléments suivants sont obligatoires : le numéro de taxe sur la valeur ajoutée (TVA) de la partie responsable de fournir les informations, la période de référence, le flux (arrivée ou expédition), le code marchandise à huit chiffres, l'état membre partenaire (état membre de provenance à l'arrivée et état membre de destination à l'expédition), la valeur des marchandises, la quantité des marchandises (masse nette et unité supplémentaire) et la nature de la transaction. Les pays/régions peuvent également recueillir des éléments facultatifs sous diverses conditions. Certains éléments facultatifs sont le pays/la région d'origine, les conditions de livraison, le mode de transport, un code marchandise plus détaillé que CN8, la région d'origine à l'expédition et la région de destination à l'arrivée, la procédure statistique, la valeur statistique, une description des marchandises, et le port/aéroport de chargement/déchargement.

## <a name="overview-of-the-intrastat-reporting-process"></a>Vue d'ensemble du processus de génération d'états Intrastat
Les sections suivantes décrivent le flux global d'informations utilisé pour la génération d'états Intrastat.

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>1. Entrez une transaction qui franchit la frontière d'un autre pays de l'Union Européenne.

Une facture client, une facture financière, une facture d'achat, une facture de projet, un bon de livraison du client, un accusé de réception de marchandises de fournisseur ou un ordre de transfert est transféré au journal Intrastat uniquement si le type de pays/région de destination (à l'expédition) ou la consignation (à l'arrivée) est **EU**. Cette fonctionnalité a été étendue pour Microsoft Dynamics 365 for Operations (1611) et permet de spécifier des adresses de chargement pour une transaction intracommunautaire. Si une adresse de chargement diffère de l'adresse commerciale d'un fournisseur (ou de l'adresse commerciale d'un client pour l'ordre de retour), la déclaration d'échanges de biens utilisera ces informations. Lorsque vous créez une commande client, une facture financière, une commande fournisseur, une facture fournisseur, une facture de projet ou un ordre de transfert, certains champs liés au commerce extérieur ont des valeurs par défaut dans l'en-tête de document ou sur la ligne. Le code transaction par défaut provient du champ correspondant de la page **Paramètres de commerce extérieur**. Le code marchandise par défaut, le pays/la région d'origine, et l'état/la province d'origine proviennent de l'article. Vous pouvez modifier les valeurs par défaut et vous pouvez également remplir d'autres informations liées au commerce extérieur : la procédure statistique, le mode de transport, et le port.

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>2. Le journal de déclaration d'échanges de biens vous permet de générer des informations sur le commerce entre pays/régions de l'Union européenne.

À des fins statistiques, vous générez des informations sur le commerce entre les pays/régions de l'Union européenne tous les mois. Vous pouvez transférer des transactions d'une facture financière, d'une facture client, d'un bon de livraison du client, d'une facture fournisseur, d'un bon de livraison fournisseur, d'une facture de projet, ou d'un ordre de transfert, en fonction des critères de transfert paramétrées sur la page **Paramètres de commerce extérieur**. Sinon, vous pouvez saisir les transactions manuellement. Vous pouvez manuellement mettre à jour les transactions transférées dans le journal Intrastat, si des mises à jour sont requises. Sous des conditions spécifiques qui sont paramétrées sur la page **Compression de la déclaration d'échanges de biens**, vous pouvez compresser les transactions dans le journal Intrastat. Certains pays/régions vous permettent d'appliquer un seuil de transaction faible. Vous pouvez ensuite générer un état pour les transactions qui sont en dessous de ce seuil sous le code marchandise spécifié. Vous pouvez mettre à jour le code marchandise à jour dans les lignes correspondantes du journal Intrastat, en fonction du paramètre **Limite inférieure** de la page **Paramètres de commerce extérieur**. Vous pouvez également compresser ces transactions, en fonction du paramètre **Compression de la déclaration d'échanges de biens**. Vous pouvez valider l'exhaustivité des transactions dans le journal Intrastat, en fonction du paramètre **Vérifier le paramétrage** de la page **Paramètres de commerce extérieur**. Les données dans les champs correspondants peuvent être validées pour leur exhaustivité : pays/région, état ou province, poids, code marchandise, code transaction, unité supplémentaire, port, origine, conditions de livraison, mode de transport, et numéro identifiant TVA. Les transactions qui ne sont pas terminées sont marquées comme non valides.

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>3. Le journal de déclaration d'échanges de biens vous permet de générer des états sur les informations relatives au commerce entre pays/régions de l'Union européenne.

À des fins statistiques, vous générez des états sur les informations relative au commerce entre les pays/régions de l'Union européenne tous les mois. Vous pouvez imprimer l'état Intrastat, en fonction des paramètres **Mise en correspondance des formats d'état** de la page **Paramètres de commerce extérieur**. Vous pouvez également générer un fichier électronique, en fonction des paramètres **Mise en correspondance des formats de fichier** de la page **Paramètres de commerce extérieur**. Pour plus d'informations sur la déclaration d'échanges de biens, consultez les enregistrements de tâche de la déclaration d'échanges de biens :

-   Générer un fichier de déclaration d'échanges de biens de l'UE,
-   Transférer des transactions dans la déclaration d'échanges de biens,
-   Définition d'une adresse de chargement pour une transaction intracommunautaire.

## <a name="prerequisites"></a>Conditions préalables
Le tableau suivant répertorie les conditions préalables à la déclaration d'échanges de biens.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuration de l'adresse</td>
<td>Paramétrez les codes ISO (Organisation internationale de normalisation) des pays/régions.</td>
</tr>
<tr class="even">
<td>Entité juridique</td>
<td>Paramétrez les numéros identifiant TVA pour l'importation/exportation, l'extension du numéro d'agence pour l'importation/exportation, puis le code Intrastat affecté à l'entité juridique.</td>
</tr>
<tr class="odd">
<td>Hiérarchie de catégories de produit (hiérarchie de vente, hiérarchie d'approvisionnement)</td>
<td>Affectez les codes marchandise Intrastat aux nœuds de catégorie sous l'onglet <strong>Codes marchandise</strong> de la page <strong>Hiérarchie de catégories</strong>. Lorsque vous affectez un code marchandise à un nœud de catégorie parente, ce code peut s'applique à tous les nœuds de catégorie enfant. Les codes marchandise sélectionnés seront disponibles dans la vue <strong>Sélectionné</strong> lorsque vous sélectionnez un code marchandise dans les détails des produits lancés, et sur les lignes de commande client, de commande fournisseur et d'ordre de transfert.</td>
</tr>
<tr class="even">
<td>Détails des produits lancés</td>
<td>Paramétrez les données suivantes sur le commerce extérieur pour les produits lancés :
<ul>
<li><strong>Code marchandise</strong> – Effectuez votre sélection soit dans la liste des marchandises sélectionnées qui est extraite des catégories de produit affectées, soit dans la liste complète des codes marchandise Intrastat.</li>
<li><strong>Pourcentage des frais statistiques</strong></li>
<li><strong>Pays/région d'origine</strong> – Sélectionnez le pays/la région par défaut où les marchandises ont été entièrement obtenues ou produites.</li>
<li><strong>État/Province d'origine/de destination</strong> – Sélectionnez l'état/la province par défaut de destination à l'arrivée et l'état/la province d'origine à l'expédition.</li>
<li><strong>Poids net en kg</strong></li>
</ul></td>
</tr>
<tr class="odd">
<td>Clients</td>
<td>Paramétrez l'adresse de livraison du client dans le pays/la région de l'Union européenne.</td>
</tr>
<tr class="even">
<td>Fournisseurs</td>
<td>Paramétrez l'adresse de livraison du fournisseur dans le pays/la région de l'Union européenne.</td>
</tr>
<tr class="odd">
<td>Frais divers</td>
<td>Paramétrez un code frais divers à inclure avec le montant de la facture, le montant statistique, ou les deux. Sur la page <strong>Codes frais</strong> , sous l'onglet <strong>Commerce extérieur</strong>, activez <strong>Valeur de la facture de la déclaration d'échanges de biens</strong> afin d'inclure le montant des frais à la valeur de la facture, et activez <strong>Valeur statistique de la déclaration d'échanges de biens</strong> afin d'inclure le montant des frais à la valeur statistique.</td>
</tr>
<tr class="even">
<td>États électroniques</td>
<td>Paramétrez les configurations électroniques de génération d'états pour exporter les données Intrastat dans un fichier électronique au format requis par les autorités appropriées, et pour obtenir un aperçu des données Intrastat dans un format convivial et lisible (par exemple, dans Microsoft Excel).</td>
</tr>
<tr class="even">
<td>Entreposage</td>
<td>Associer les comptes fournisseur aux codes entrepôt pour remplir le numéro identifiant TVA lors du transfert de l'ordre de transfert.</td>
</tr>
</tbody>
</table>

## <a name="setup"></a>Configuration
Les sections suivantes décrivent les paramètres requis pour la génération d'états Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Paramétrer toutes les listes requises associées à Intrastat

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Liste</th>
<th>Informations supplémentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Codes marchandise</td>
<td>Paramétrez une hiérarchie de catégories de type <strong>Code marchandise</strong>, et entrez tous les codes marchandise selon la liste combinée de nomenclature. Pour chaque marchandise, vous paramétrez les informations suivantes :
<ul>
<li>Le nom de la marchandise et le code marchandise</li>
<li>Le nom convivial et/ou le nom traduit</li>
<li>Paramètres pour signaler des unités supplémentaires dans l'onglet <strong>Commerce extérieur</strong>. Vous pouvez sélectionner l'unité supplémentaire dans la liste des unités. Vous pouvez également spécifier si le poids des marchandises doit être déclaré en sus de l'unité supplémentaire sélectionnée.</li>
</ul></td>
</tr>
<tr class="even">
<td>Codes transaction</td>
<td>Paramétrez la nature de la transaction en fonction des exigences de votre pays/région. Pour chaque code transaction que vous paramétrez, vous devez définir les règles de calcul des montants de facture et les montants statistiques pour les ordres de transfert et les ventes/commandes fournisseur.
<ul>
<li>Pour les ordres de transfert, vous paramétrez une des règles suivantes pour le calcul des montants de facture et des montants statistiques :
<ul>
<li><strong>Vide</strong> – Le montant est 0 (zéro).</li>
<li><strong>Montant du coût financier</strong> – Le montant est égal au coût financier.</li>
<li><strong>Coût total</strong> – Le montant est égal au coût total de la transaction.</li>
<li><strong>Manuel</strong> – Le montant est égal au montant qui est spécifié manuellement sur la ligne d'ordre de transfert.</li>
</ul></li>
<li>Pour les commandes client et les commandes fournisseur, vous paramétrez une des règles suivantes pour le calcul des montants de facture et des montants statistiques :
<ul>
<li><strong>Vide</strong> – Le montant est 0 (zéro).</li>
<li><strong>Montant de la facture</strong> – Le montant est égal au montant facturé pour la marchandise.</li>
<li><strong>Montant de base</strong> – Le montant est égal au montant qui serait facturé avant que toute remise soit appliquée.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Modes de transport</td>
<td>Paramétrez le mode de transport en fonction des exigences de votre pays/région. Pour chaque mode de livraison, vous pouvez paramétrer une méthode de transport par défaut sous l'onglet <strong>Commerce extérieur</strong>.</td>
</tr>
<tr class="even">
<td>Ports</td>
<td>Paramétrez le port/aéroport de chargement/déchargement si ces informations sont recueillies par votre pays/région.</td>
</tr>
<tr class="odd">
<td>Procédures statistiques</td>
<td>Paramétrez la procédure statistique si ces informations sont recueillies par votre pays/région.</td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Paramétrage de règles pour la compression des transactions Intrastat

Sur la page **Compression de la déclaration d'échanges de biens**, vous pouvez sélectionner les champs à utiliser pour la compression. Toutes les transactions ayant la même combinaison de valeurs pour les champs sélectionnés dans le journal Intrastat seront compressées en une seule transaction lors de l'exécution de la fonction Compresser dans le journal Intrastat.

### <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

La page **Paramètres de commerce extérieur** permet de définir les paramètres du tableau suivant.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabulation</th>
<th>Paramètres</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Général</td>
<td><ul>
<li><strong>Général</strong> – Spécifiez les informations suivantes :
<ul>
<li>Les codes transaction par défaut pour les commandes client, les commandes fournisseur, les avoirs et les ordres de transfert. Le code transaction paramétré pour les avoirs est également utilisé comme code pour le retour des marchandises physiques et pour les écarts des retours physiques par rapport aux avoirs de correction.</li>
<li>L'employé responsable de la préparation des états Intrastat.</li>
</ul></li>
<li><strong>Limite inférieure</strong> – Permet de spécifier les paramètres de mise à jour des transactions qui sont en dessous du seuil :
<ul>
<li>Le montant et le poids de seuil</li>
<li>Le code marchandise à appliquer aux transactions qui sont sous le seuil</li>
</ul></li>
<li><strong>Transfert</strong> – Permet de spécifier les critères pour transférer les transactions vers le journal Intrastat. Vous pouvez spécifier que les transactions sont transférées uniquement lorsque les articles correspondent à l'un des les critères suivants ou à tous :
<ul>
<li>Les articles ne sont pas des articles de service.</li>
<li>L'article est doté d'un code marchandise.</li>
<li>Les articles ont un poids.</li>
<li>Les articles ont des unités supplémentaires.</li>
</ul></li>
<li><strong>Vérifier le paramétrage</strong> – Permet de spécifier les règles de validation de l'exhaustivité des données Intrastat. Vous pouvez sélectionner les données qui sont validées.</li>
<li><strong>Règles d'arrondi</strong> – Permet de spécifier les paramètres suivants pour les arrondis et les poids dans la génération d'états Intrastat :
<ul>
<li>La règle d'arrondi (précision)</li>
<li>La méthode d'arrondi : au chiffre supérieur, au chiffre inférieur ou normale</li>
<li>Le nombre de décimales pour les montants et les poids</li>
<li>Instructions pour l'arrondi des poids inférieurs à 1 kilogramme (kg) : jusqu'à 1 kg, normale, ou aucun arrondi</li>
</ul></li>
<li><strong>États électroniques</strong> – Permet de spécifier les références aux configurations de génération d'états électroniques, afin que vous puissiez générer un fichier électronique et un état.</li>
<li><strong>Hiérarchie des nomenclatures douanières</strong> – Permet de spécifier la hiérarchie de catégories du type de <strong>Code marchandise</strong> qui représente le code marchandise Intrastat CN8.</li>
  <li> <strong>Type de taux de change</strong> – Permet de spécifier éventuellement un taux de change à utiliser pour la génération d'états sur les transactions de vente et d'achat de déclaration d'échanges de biens en devises étrangères. Ce paramètre est utilisé si le taux est différent de celui appliqué lors de la validation de la transaction.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Coordonnées des agents</td>
<td>Spécifiez le nom, l'adresse, le numéro identifiant TVA, le numéro de téléphone, et le numéro de télécopie de l'agent.</td>
</tr>
<tr class="odd">
<td>Propriétés de pays/régions</td>
<td>Définissez le pays/la région de l'entité juridique actuelle sur <strong>Local</strong>. Définissez les pays/régions de l'UE qui participent au commerce intracommunautaire avec l'entité juridique actuelle sur <strong>UE</strong>. Pour chaque pays/région, identifiez également le code pays/région pour le commerce extérieur.</td>
</tr>
<tr class="even">
<td>Souche de numéros</td>
<td>Spécifiez la souche de numéros pour le journal Intrastat.</td>
</tr>
</tbody>
</table>

