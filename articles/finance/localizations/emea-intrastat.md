---
title: Vue d’ensemble de déclaration d’échanges de biens
description: Cette rubrique fournit des informations sur la génération d’états de déclaration d’échanges de biens pour le commerce de marchandises et, dans certains cas, pour les services entre les pays/régions de l’Union européenne (UE).
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 97c2b4068f3b8d38281e637ec80f04b19d19be61
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986035"
---
# <a name="intrastat-overview"></a>Vue d’ensemble de déclaration d’échanges de biens

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la génération d’états de déclaration d’échanges de biens pour le commerce de marchandises et, dans certains cas, pour les services entre les pays/régions de l’Union européenne (UE). Cette rubrique fournit également une vue d’ensemble du processus de déclaration, et décrit les paramètres et les conditions préalables requises.

Intrastat est le système de collecte d’informations et de génération de statistiques sur le commerce de marchandises entre les pays/régions de l’Union européenne (UE). Une génération d’états Intrastat est requise chaque fois qu’un produit franchit la frontière d’un autre pays/région de l’Union Européenne. Dans plusieurs pays/régions, la génération d’états Intrastat s’applique également aux services. Les éléments obligatoires et facultatifs peuvent être collectés dans la génération d’états Intrastat. Les éléments suivants sont obligatoires : le numéro de taxe sur la valeur ajoutée (TVA) de la partie responsable de fournir les informations, la période de référence, le flux (arrivée ou expédition), le code marchandise à huit chiffres, l’état membre partenaire (état membre de provenance à l’arrivée et état membre de destination à l’expédition), la valeur des marchandises, la quantité des marchandises (masse nette et unité supplémentaire) et la nature de la transaction. Les pays/régions peuvent également recueillir des éléments facultatifs sous diverses conditions. Certains éléments facultatifs sont le pays/la région d’origine, les conditions de livraison, le mode de transport, un code marchandise plus détaillé que CN8, la région d’origine à l’expédition et la région de destination à l’arrivée, la procédure statistique, la valeur statistique, une description des marchandises, et le port/aéroport de chargement/déchargement.

## <a name="overview-of-the-intrastat-reporting-process"></a>Vue d’ensemble du processus de génération d’états Intrastat
Les sections suivantes décrivent le flux global d’informations utilisé pour la génération d’états Intrastat.

### <a name="enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>Entrez une transaction qui franchit la frontière d’un autre pays de l’Union Européenne

Une facture client, une facture financière, une facture d’achat, une facture de projet, un bon de livraison du client, un accusé de réception de marchandises de fournisseur ou un ordre de transfert est transféré au journal Intrastat uniquement si le type de pays/région de destination (à l’expédition) ou la consignation (à l’arrivée) est **EU**. Cette fonctionnalité a été étendue pour Microsoft Dynamics 365 for Operations (1611) et permet de spécifier des adresses de chargement pour une transaction intracommunautaire. Si une adresse de chargement diffère de l’adresse commerciale d’un fournisseur (ou de l’adresse commerciale d’un client pour l’ordre de retour), la déclaration d’échanges de biens utilisera ces informations. Lorsque vous créez une commande client, une facture financière, une commande fournisseur, une facture fournisseur, une facture de projet ou un ordre de transfert, certains champs liés au commerce extérieur ont des valeurs par défaut dans l’en-tête de document ou sur la ligne. Le code transaction par défaut provient du champ correspondant de la page **Paramètres de commerce extérieur**. Le code marchandise par défaut, le pays/la région d’origine, et l’état/la province d’origine proviennent de l’article. Vous pouvez modifier les valeurs par défaut et vous pouvez également remplir d’autres informations liées au commerce extérieur : la procédure statistique, le mode de transport, et le port.

### <a name="use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>Le journal de déclaration d’échanges de biens vous permet de générer des informations sur le commerce entre pays/régions de l’Union européenne.

À des fins statistiques, vous générez des informations sur le commerce entre les pays/régions de l’Union européenne tous les mois. Vous pouvez transférer des transactions d’une facture financière, d’une facture client, d’un bon de livraison du client, d’une facture fournisseur, d’un bon de livraison fournisseur, d’une facture de projet, ou d’un ordre de transfert, en fonction des critères de transfert paramétrées sur la page **Paramètres de commerce extérieur**. Sinon, vous pouvez saisir les transactions manuellement. Vous pouvez manuellement mettre à jour les transactions transférées dans le journal Intrastat, si des mises à jour sont requises. Sous des conditions spécifiques qui sont paramétrées sur la page **Compression de la déclaration d’échanges de biens**, vous pouvez compresser les transactions dans le journal Intrastat. Certains pays/régions vous permettent d’appliquer un seuil de transaction faible. Vous pouvez ensuite générer un état pour les transactions qui sont en dessous de ce seuil sous le code marchandise spécifié. Vous pouvez mettre à jour le code marchandise à jour dans les lignes correspondantes du journal Intrastat, en fonction du paramètre **Limite inférieure** de la page **Paramètres de commerce extérieur**. Vous pouvez également compresser ces transactions, en fonction du paramètre **Compression de la déclaration d’échanges de biens**. Vous pouvez valider l’exhaustivité des transactions dans le journal Intrastat, en fonction du paramètre **Vérifier le paramétrage** de la page **Paramètres de commerce extérieur**. Les données dans les champs correspondants peuvent être validées pour leur exhaustivité : pays/région, état ou province, poids, code marchandise, code transaction, unité supplémentaire, port, origine, conditions de livraison, mode de transport, et numéro identifiant TVA. Les transactions qui ne sont pas terminées sont marquées comme non valides.

### <a name="use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>Le journal de déclaration d’échanges de biens vous permet de générer des états sur les informations relatives au commerce entre pays/régions de l’Union européenne.

À des fins statistiques, vous générez des états sur les informations relative au commerce entre les pays/régions de l’Union européenne tous les mois. Vous pouvez imprimer l’état Intrastat, en fonction des paramètres **Mise en correspondance des formats d’état** de la page **Paramètres de commerce extérieur**. Vous pouvez également générer un fichier électronique, en fonction des paramètres **Mise en correspondance des formats de fichier** de la page **Paramètres de commerce extérieur**. Pour plus d’informations sur la déclaration d’échanges de biens, consultez les enregistrements de tâche de la déclaration d’échanges de biens :

  - Générer un fichier de déclaration d’échanges de biens de l’UE,
  - Transférer des transactions dans la déclaration d’échanges de biens,
  - Définition d’une adresse de chargement pour une transaction intracommunautaire.

## <a name="prerequisites"></a>Conditions préalables
Le tableau suivant répertorie les conditions préalables à la déclaration d’échanges de biens.

|  Logiciel requis  |  Description  |
|-------------------------|-------------------------|
| Configuration de l’adresse | Paramétrez les codes ISO (Organisation internationale de normalisation) des pays/régions. |
| Entité juridique | Paramétrez les numéros identifiant TVA pour l’importation/exportation, l’extension du numéro d’agence pour l’importation/exportation, puis le code Intrastat affecté à l’entité juridique. |
| Hiérarchie de catégories de produit (hiérarchie de vente, hiérarchie d’approvisionnement) | Affectez les codes marchandise Intrastat aux nœuds de catégorie sous l’onglet **Codes marchandise** de la page **Hiérarchie de catégories**. Lorsque vous affectez un code marchandise à un nœud de catégorie parente, ce code peut s’applique à tous les nœuds de catégorie enfant. Les codes marchandise sélectionnés seront disponibles dans la vue **Sélectionné** lorsque vous sélectionnez un code marchandise dans les détails des produits, et sur les lignes de commande client, de commande fournisseur et d’ordre de transfert. |
| Détails des produits lancés | Paramétrez les données suivantes sur le commerce extérieur pour les produits lancés :<ul><li>**Code marchandise** – Effectuez votre sélection soit dans la liste des marchandises sélectionnées qui est extraite des catégories de produit affectées, soit dans la liste complète des codes marchandise Intrastat.</li><li>**Pourcentage des frais statistiques**</li><li>**Pays/région d’origine** – Sélectionnez le pays/la région par défaut où les marchandises ont été entièrement obtenues ou produites.</li><li>**État/Province d’origine/de destination** – Sélectionnez l’état/la province par défaut de destination à l’arrivée et l’état/la province d’origine à l’expédition.</li><li>**Poids net en kg**</li><li>**Exclure** – activez ce paramètre pour ne pas transférer les transactions avec ce produit vers la déclaration d’échange de biens</li></ul> |
| Clients | Paramétrez l’adresse de livraison du client dans le pays/la région de l’Union européenne. |
| Fournisseurs | Paramétrez l’adresse de livraison du fournisseur dans le pays/la région de l’Union européenne. |
| Frais divers | Paramétrez un code frais divers à inclure avec le montant de la facture, le montant statistique, ou les deux. Sur la page **Codes frais** , sous l’onglet **Commerce extérieur**, activez **Valeur de la facture de la déclaration d’échanges de biens** afin d’inclure le montant des frais à la valeur de la facture, et activez **Valeur statistique de la déclaration d’échanges de biens** afin d’inclure le montant des frais à la valeur statistique.</br>Pour plus d’informations, consultez l’exemple [Codes de transaction et frais divers](#transaction-codes-and-miscellaneous-charges). |
| Notification électronique | Paramétrez les configurations électroniques de génération d’états pour exporter les données Intrastat dans un fichier électronique au format requis par les autorités appropriées, et pour obtenir un aperçu des données Intrastat dans un format convivial et lisible (par exemple, dans Microsoft Excel). |
| Entreposage | Associer les comptes fournisseur aux codes entrepôt pour remplir le numéro identifiant TVA lors du transfert de l’ordre de transfert.</br>Pour plus d’informations, consultez l’exemple [Ordre de transfert](#transfer-order).|

## <a name="setup"></a>Paramétrage
Les sections suivantes décrivent les paramètres requis pour la génération d’états Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Paramétrer toutes les listes requises associées à Intrastat

|   Liste   |   Informations supplémentaires   |
|-------------------------|-------------------------|
| Codes marchandise | Paramétrez une hiérarchie de catégories de type **Code marchandise**, et entrez tous les codes marchandise selon la liste combinée de nomenclature. Pour chaque marchandise, vous paramétrez les informations suivantes :<ul><li>Le nom de la marchandise et le code marchandise</li><li>Le nom convivial et/ou le nom traduit</li><li>Paramètres pour signaler des unités supplémentaires dans l’onglet **Commerce extérieur**. Vous pouvez sélectionner l’unité supplémentaire dans la liste des unités. Vous pouvez également spécifier si le poids des marchandises doit être déclaré en sus de l’unité supplémentaire sélectionnée.</li></ul>Pour plus d’informations, consultez l’exemple [Unités supplémentaires](#additional-units).|
| Codes transaction | Paramétrez la nature de la transaction en fonction des exigences de votre pays/région. Pour chaque code transaction que vous paramétrez, vous devez définir les règles de calcul des montants de facture et les montants statistiques pour les ordres de transfert et les ventes/commandes fournisseur.<ul><li>Pour les ordres de transfert, vous paramétrez une des règles suivantes pour le calcul des montants de facture et des montants statistiques :<ul><li>**Vide** – Le montant est 0 (zéro).</li><li>**Montant du coût financier** – Le montant est égal au coût financier.</li><li>**Coût total** – Le montant est égal au coût total de la transaction.</li><li>**Manuel** – Le montant est égal au montant qui est spécifié manuellement sur la ligne d’ordre de transfert.</li></ul></li><li>Pour les commandes client et les commandes fournisseur, vous paramétrez une des règles suivantes pour le calcul des montants de facture et des montants statistiques :<ul><li>**Vide** – Le montant est 0 (zéro).</li><li>**Montant de la facture** – Le montant est égal au montant facturé pour la marchandise.</li><li>**Montant de base** – Le montant est égal au montant qui serait facturé avant que toute remise soit appliquée.</li></ul></ul>Pour plus d’informations, consultez l’exemple [Codes de transaction et frais divers](#transaction-codes-and-miscellaneous-charges). |
| Modes de transport | Paramétrez le mode de transport en fonction des exigences de votre pays/région. Pour chaque mode de livraison, vous pouvez paramétrer une méthode de transport par défaut sous l’onglet **Commerce extérieur**. |
| Ports | Paramétrez le port/aéroport de chargement/déchargement si ces informations sont recueillies par votre pays/région. |
| Procédures statistiques | Paramétrez la procédure statistique si ces informations sont recueillies par votre pays/région. |



### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Paramétrage de règles pour la compression des transactions Intrastat

Sur la page **Compression de la déclaration d’échanges de biens**, vous pouvez sélectionner les champs à utiliser pour la compression. Toutes les transactions ayant la même combinaison de valeurs pour les champs sélectionnés dans le journal Intrastat seront compressées en une seule transaction lors de l’exécution de la fonction Compresser dans le journal Intrastat.

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
<li>Les codes transaction par défaut pour les commandes client, les commandes fournisseur, les avoirs et les ordres de transfert. Le code transaction paramétré pour les avoirs est également utilisé comme code pour le retour des marchandises physiques et pour les écarts des retours physiques par rapport aux avoirs de correction. Les retours de biens physiques sont déclarés dans le transfert Intrastat avec une direction différente. Le retour d’arrivée est signalé comme expédition et le retour d’expédition est signalé comme arrivée.</li>
<li>L’employé responsable de la préparation des états Intrastat.</li>
</ul></li>
<li><strong>Limite inférieure</strong> – Permet de spécifier les paramètres de mise à jour des transactions qui sont en dessous du seuil :
<ul>
<li>Le montant et le poids de seuil</li>
<li>Le code marchandise à appliquer aux transactions qui sont sous le seuil</li>
</ul></li>
<li><strong>Transfert</strong> – Permet de spécifier les critères pour transférer les transactions vers le journal Intrastat. Vous pouvez spécifier que les transactions sont transférées uniquement lorsque les articles correspondent à l’un des les critères suivants ou à tous :
<ul>
<li>Les articles ne sont pas des articles de service.</li>
<li>L’article est doté d’un code marchandise.</li>
<li>Les articles ont un poids.</li>
<li>Les articles ont des unités supplémentaires.</li>
</ul></li>
<li><strong>Vérifier le paramétrage</strong> – Permet de spécifier les règles de validation de l’exhaustivité des données Intrastat. Vous pouvez sélectionner les données qui sont validées.</li>
<li><strong>Règles d’arrondi</strong> – Permet de spécifier les paramètres suivants pour les arrondis et les poids dans la génération d’états Intrastat :
<ul>
<li>La règle d’arrondi (précision)</li>
<li>La méthode d’arrondi : au chiffre supérieur, au chiffre inférieur ou normale</li>
<li>Le nombre de décimales pour les montants et les poids</li>
<li>Instructions pour l’arrondi des poids inférieurs à 1 kilogramme (kg) : jusqu’à 1 kg, normale, ou aucun arrondi</li>
</ul></li>
<li><strong>États électroniques</strong> – Permet de spécifier les références aux configurations de génération d’états électroniques, afin que vous puissiez générer un fichier électronique et un état.</li>
<li><strong>Hiérarchie des nomenclatures douanières</strong> – Permet de spécifier la hiérarchie de catégories du type de <strong>Code marchandise</strong> qui représente le code marchandise Intrastat CN8.</li>
  <li> <strong>Type de taux de change</strong> – Permet de spécifier éventuellement un taux de change à utiliser pour la génération d’états sur les transactions de vente et d’achat de déclaration d’échanges de biens en devises étrangères. Ce paramètre est utilisé si le taux est différent de celui appliqué lors de la validation de la transaction.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Coordonnées des agents</td>
<td>Spécifiez le nom, l&#39;adresse, le numéro identifiant TVA, le numéro de téléphone, et le numéro de télécopie de l’agent.</td>
</tr>
<tr class="odd">
<td>Propriétés de pays/régions</td>
<td>Définissez le pays/la région de l’entité juridique actuelle sur <strong>Local</strong>. Définissez les pays/régions de l’UE qui participent au commerce intracommunautaire avec l’entité juridique actuelle sur <strong>UE</strong>. Pour chaque pays/région, identifiez également le code pays/région pour le commerce extérieur.</td>
</tr>
<tr class="even">
<td>Souche de numéros</td>
<td>Spécifiez la souche de numéros pour le journal Intrastat.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Exemple

### <a name="transaction-codes-and-miscellaneous-charges"></a><a name= "transaction-codes-and-miscellaneous-charges"></a>Codes de transaction et frais divers

Cette rubrique présente un scénario dans lequel une société en Allemagne doit acheter des marchandises à une société en Italie. Pour effectuer cet achat, la société allemande doit configurer de nouveaux codes de transaction et configurer des règles de calcul pour le montant de la facture et le montant statistique pour ces codes de transaction. De plus, lorsque l’entreprise crée une facture, elle doit spécifier les frais divers et leurs pourcentages. Ces valeurs seront prises en compte lors du calcul de la valeur statistique.

Ce scénario utilise l’entité juridique **DEMF**.

#### <a name="preliminary-setup"></a>Paramétrage préliminaire

1. Accédez à **Administration d’organisation** > **Organisation** > **Entités juridiques**, puis sélectionnez **DEMF**.
2. Sur le raccourci **Adresses** vérifiez que le champ **Pays/région** est défini sur **DEU(Allemagne)**.
3. Accédez à **Comptabilité fournisseur** > **Fournisseurs** > **Tous les fournisseurs**.
4. Dans la grille, sélectionnez **DE-001**.
5. Dans le raccourci **Adresse**, sélectionnez **Modifier**.
6. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **ITA**.
7. Sélectionnez **OK** pour fermer la boîte de dialogue.

#### <a name="set-up-transaction-codes"></a>Paramétrer des codes transaction

1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Codes transaction**.
2. Dans la grille, sélectionnez **11**. Ensuite, sélectionnez **Supprimer** dans le volet Action.
3. Dans le volet Actions, sélectionnez **Nouveau**.
4. Dans le raccourci **Codes de transaction**, dans le champ **Code** **transaction**, entrez **11**.
5. Dans le champ **Nom**, entrez **Achat ou vente au comptant**.
6. Dans la section **Ventes et achats**, dans le champ **Montant de la facture**, sélectionnez **Montant de la facture**.
7. Dans le champ **Montant statistique**, sélectionnez **Montant de la facture**.
8. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="set-up-miscellaneous-charges"></a>Paramétrage des frais divers

1. Accédez à **Comptabilité client** > **Paramétrage des frais** > **Codes frais**.
2. Dans la grille, sélectionnez **Transport**.
3. Dans le volet Actions, sélectionnez **Modifier**.
4. Dans le raccourci **Commerce extérieur**, définissez les options **Valeur de la facture de la déclaration d’échanges de biens** et **Valeur statistique de la déclaration d’échanges de biens** sur **Oui**.

#### <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code** **transaction**, sélectionnez **11**.
3. Dans le raccourci **Hiérarchie des codes marchandise**, vérifiez que le champ **Hiérarchie des catégories** est défini sur **Déclaration d’échanges de biens**.

#### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Comptabilité fournisseur** > **Commandes fournisseur** > **Toutes les commandes fournisseur**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande fournisseur**, dans le champ **Compte fournisseur**, sélectionnez **DE-001**.
4. Cliquez sur **OK**.
5. Sur l’onglet **En-tête**, sur le raccourci **Commerce** **étranger**, vérifiez que le champ **Code de transaction** est défini sur **11**.
6. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande fournisseur**, dans le champ **Numéro d’article**, sélectionnez **D0003**. Ensuite, dans le champ **Quantité**, entrez **10**.
7. Dans le raccourci **Détails de ligne**, dans l’onglet **Commerce extérieur**, dans la section **Commerce extérieur**, vérifiez que le champ **Code transaction** est automatiquement défini.
8. Dans le raccourci **Lignes commande fournisseur**, dans le menu **Finances**, dans la section **Frais**, sélectionnez **Tenir les frais à jour**.
9. Dans le champ **Codes frais**, sélectionnez **TRANSPORT**.
10. Dans le champ **Valeur des frais**, entrez **30**.
11. Dans le volet Actions, sélectionnez **Enregistrer**. Fermez ensuite la page.
12. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer**.
13. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
14. Sur le volet Action, sélectionnez **Par défaut**. Dans le champ **Quantité par défaut pour les lignes**, sélectionnez **Quantité commandée**. Puis sélectionnez **OK**.
15. Sur le raccourci **En-tête de facture fournisseur**, dans la section **Identification de la facture**, dans le champ **Numéro**, entrez **00100**.
16. Dans la rubrique **Dates de facturation**, dans le champ **Date de la facture**, sélectionnez **24/11/2021** (24 novembre 2021).
17. Dans le volet Actions, sélectionnez **Valider** pour valider la facture.

### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Transférer la facture fournisseur au journal de déclaration d’échange de biens

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture fournisseur** sur **Oui**.
4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

   ![Ligne représentant la commande fournisseur avec des rais divers sur la page de déclaration d’échanges de biens](media/intrastat_overview_1.png)

5. Examinez l’onglet **Général** pour la commande fournisseur. Remarquez que le champ **Montant de la facture** indique la somme des champs **Montant de la facture** et **Montant des frais facturés**, et que le champ **Valeur statistique** indique la somme des champs **Montant statistique** et **Montant statistique des frais**.

   ![Détails de la commande fournisseur avec des frais divers sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_overview_2.png)

### <a name="transfer-order"></a>Ordre de transfert

Dans cet exemple, une entreprise en Allemagne doit déplacer deux unités de marchandises d’un entrepôt en Allemagne vers un entrepôt en Italie. Des frais au taux de 20 % doivent également être spécifiés pour ce produit pour la comptabilisation dans le champ **Valeur statistique**. Cet exemple utilise l’entité juridique **DEMF**.

#### <a name="preliminary-setup"></a>Paramétrage préliminaire

1. Accédez à **Administration d’organisation** > **Organisation** > **Entités juridiques**, puis sélectionnez **DEMF**.
2. Sur le raccourci **Adresses** vérifiez que le champ **Pays/région** est défini sur **DEU(Allemagne)**.
3. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
4. Dans le raccourci **Hiérarchie des codes marchandise**, vérifiez que le champ **Hiérarchie des catégories** est défini sur **Déclaration d’échanges de biens**.
5. Accédez à **Comptabilité fournisseur** > **Fournisseurs** > **Tous les fournisseurs**.
6. Dans la grille, sélectionnez **DE-001**.
7. Dans le raccourci **Adresse**, sélectionnez **Modifier**.
8. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **ITA**.
9. Sélectionnez **OK** pour fermer la boîte de dialogue.

#### <a name="set-up-transaction-codes"></a>Paramétrer des codes transaction

1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Codes transaction**.
2. Dans la grille, sélectionnez **11**. Ensuite, sélectionnez **Supprimer** dans le volet Action.
3. Dans le volet Actions, sélectionnez **Nouveau**.
4. Dans le raccourci **Codes de transaction**, dans le champ **Code** **transaction**, entrez **11**.
5. Dans le champ **Nom**, entrez **Achat ou vente au comptant**.
6. Dans la section **Ordre de transfert**, dans le champ **Montant de la facture**, sélectionnez **Coût total**.
7. Dans le champ **Montant statistique**, sélectionnez **Coût total**.
8. Dans le volet Actions, sélectionnez **Enregistrer**.
9. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
10. Sur l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Ordre de transfert**, sélectionnez **11**.

#### <a name="set-up-charges-for-an-item"></a>Paramétrage des frais pour un article

1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
2. Dans la grille, sélectionnez **D0001**.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Pourcentage des frais**, entrez **20**.

#### <a name="change-the-site-address"></a>Changer l’adresse du site

1. Accédez à **Gestion des entrepôts** > **Paramétrage** > **Entrepôt** > **Sites**.
2. Dans la grille, sélectionnez **1**.
3. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
4. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **DEU**.
5. Cliquez sur **OK**.
6. Dans la grille, sélectionnez **2**.
7. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
8. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **ITA**.
9. Cliquez sur **OK**.
10. Accédez à **Gestion des entrepôts** > **Paramétrage** > **Entrepôt** > **Entrepôts**.
11. Dans la grille, sélectionnez **21**.
12. Dans le raccourci **Général**, dans la section **Référence**, dans le champ **Compte fournisseur**, sélectionnez **DE-001**.

#### <a name="create-a-transfer-order"></a>Création d’un ordre de transfert

1. Accédez à **Gestion des stocks** > **Commandes sortantes** > **Ordre de transfert**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans l’onglet **Lignes**, dans le raccourci **En-tête de l’ordre de transfert**, dans la section **Vue d’ensemble**, dans le champ **Entrepôt d’origine**, sélectionnez **11**. Dans le champ **Entrepôt de destination**, sélectionnez **21**.
4. Dans l’onglet **Lignes**, dans le raccourci **Lignes d’ordre de transfert**, sélectionnez **Ajouter**.
5. Dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité à transférer**, entrez **2**.
6. Dans le raccourci **Détails de ligne**, dans l’onglet **Commerce extérieur**, dans la section **Commerce extérieur**, vérifiez que le champ **Code transaction** est automatiquement défini.
7. Dans le volet Actions, sous l’onglet **Expédition**, dans le groupe **Opérations**, sélectionnez **Expédier l’ordre de transfert**.
8. Dans la boîte de dialogue **Expédition**, dans l’onglet **Vue d’ensemble**, dans le champ **Mettre à jour**, sélectionnez **Tout**.
9. Sélectionnez **OK** pour expédier la commande.
10. Dans le volet Actions, sous l’onglet **Recevoir**, dans le groupe **Opérations**, sélectionnez **Recevoir**.
11. Dans la boîte de dialogue **Recevoir**, dans l’onglet **Vue d’ensemble**, dans le champ **Mettre à jour**, sélectionnez **Tout**.
12. Sélectionnez **OK** pour expédier la commande.

#### <a name="transfer-the-transfer-order-to-the-intrastat-journal"></a>Transférer l’ordre de transfert au journal de déclaration d’échange de biens

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Ordre de transfert** sur **Oui** et toutes les autres options sur **Non**.
4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

   ![Ligne représentant l’ordre de transfert sur la page de déclaration d’échanges de biens](media/intrastat_overview_3.png)

5.  Examinez l’onglet **Général** pour l’ordre de transfert.

    Notez que les champs des sections **Montant de la facture** et **Valeur statistique** sont automatiquement définis. Les valeurs des champs **Montant de la facture** et **Montant statistique** sont basés sur les paramètres de la page **Codes de transaction**. La valeur **20** dans le champ **Pourcentage de frais** est la valeur qui est définie sur la page **Produit lancé**. La valeur dans le champ **Montant statistique des frais** est une expression quantitative des frais (parce que 107,24 est égal à 20 % de 536,18). La valeur du champ **Valeur statistique** est la somme des valeurs des champs **Montant statistique** et **Montant statistique des frais**.

  ![Détails de l’ordre de transfert sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_overview_4.png)

### <a name="additional-units"></a>Unités supplémentaires

Dans cet exemple, une entreprise en Allemagne doit acheter 10 unités de marchandises à une entreprise en Italie. En plus des codes marchandises, des unités supplémentaires doivent être spécifiées pour ces marchandises. L’exemple montre comment créer de nouvelles unités de mesure, affecter des unités supplémentaires au code marchandise de la déclaration d’échange de biens, valider des transactions qui comportent des unités supplémentaires et examiner le journal de la déclaration d’échange de biens où le champ pour les unités supplémentaires est défini.

#### <a name="preliminary-setup"></a>Paramétrage préliminaire

1. Accédez à **Administration d’organisation** > **Organisation** > **Entités juridiques**, puis sélectionnez **DEMF**.
2. Sur le raccourci **Adresses** vérifiez que le champ **Pays/région** est défini sur **DEU(Allemagne)**.
3. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
4. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code** **transaction**, sélectionnez **11**.
5. Dans le raccourci **Hiérarchie des codes marchandise**, vérifiez que le champ **Hiérarchie des catégories** est défini sur **Déclaration d’échanges de biens**.
6. Accédez à **Comptabilité fournisseur** > **Fournisseurs** > **Tous les fournisseurs**.
7. Dans la grille, sélectionnez **DE-001**.
8. Dans le raccourci **Adresse**, sélectionnez **Modifier**.
9. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **ITA**.
10. Sélectionnez **OK** pour fermer la boîte de dialogue.

#### <a name="create-a-unit-of-measure"></a>Créer une unité de mesure

1. Accédez à **Administration d’organisation** > **Paramétrage** > **Unités** > **Unités**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Unité**, entrez un nom pour l’unité de mesure. Pour cet exemple, entrez **GRM**.
4. Dans le raccourci **Général**, dans la section **Classification**, dans le champ **Classe d’unité**, sélectionnez la propriété que l’unité mesure. Pour cet exemple, sélectionnez **Masse**.
5. Dans le champ **Système d’unités**, sélectionnez le système de mesure auquel appartient l’unité. Par exemple, sélectionnez **Unités métriques**.

#### <a name="set-up-unit-conversions"></a>Configurer la converstion d’unités

1. Accédez à **Administration d’organisation** > **Paramétrage** > **Unités** > **Conversion d’unités**.
2. Dans l’onglet **Conversions inter-classes**, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Conversion d’unité**, dans le champ **Produit**, sélectionnez **F00007**.
4. Dans le champ **Unité d’origine**, sélectionnez **unité**.
5. Dans le champ **Unité de destination**, sélectionnez **GRM**.
6. Vérifiez que le taux de conversion est **1 = 1**.
7. Cliquez sur **OK**.
8. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
9. Dans la grille, sélectionnez **F00007**.
10. Dans le raccourci **Gérer l’inventaire**, dans la section **Stock**, dans le champ **Unité**, entrez **GRM**.
11. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="set-up-product-information"></a>Configurer les informations sur le produit

1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
2. Dans la grille, sélectionnez **F00007**.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **920 20 34**.
4. Dans le volet Actions, sélectionnez **Enregistrer**.

#### <a name="assign-the-additional-unit-to-an-intrastate-commodity-code"></a>Attribuer l’unité supplémentaire à un code marchandise de déclaration d’échanges de biens

1. Accédez à **Gestion des informations sur les produits** > **Paramétrage** > **Catégories et d’attributs** > **Hiérarchies de catégories**.
2. Dans la liste, sélectionnez **Déclaration d’échanges de biens**.
3. Dans la grille, sélectionnez **Haut-parleur**.
4. Dans le raccourci **Commerce extérieur**, dans le champ **Unités supplémentaires**, sélectionnez **GRM**.
5. Dans le volet Actions, sélectionnez **Enregistrer**.

   Pour plus d’informations, voir [Gérer les unités de mesure](../../supply-chain/pim/tasks/manage-unit-measure.md).

#### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Comptabilité fournisseur** > **Commandes fournisseur** > **Toutes les commandes fournisseur**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande fournisseur**, dans le champ **Compte fournisseur**, sélectionnez **DE-001**.
4. Cliquez sur **OK**.
5. Sur l’onglet **En-tête**, sur le raccourci **Commerce** **étranger**, vérifiez que le champ **Code de transaction** est défini sur **11**.
6. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande fournisseur**, dans le champ **Numéro d’article**, sélectionnez **F00007**. Ensuite, dans le champ **Quantité**, entrez **10**.
7. Dans le raccourci **Détails de ligne**, dans l’onglet **Commerce extérieur**, dans la section **Commerce extérieur**, vérifiez que les champs **Code transaction** et **Marchandise** sont définis automatiquement.
8. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer**.
9. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
10. Sur le volet Action, sélectionnez **Par défaut**. Dans le champ **Quantité par défaut pour les lignes**, sélectionnez **Quantité commandée**. Puis sélectionnez **OK**.
11. Sur le raccourci **En-tête de facture fournisseur**, dans la section **Identification de la facture**, dans le champ **Numéro**, entrez **VE-0010**.
12. Dans la section **Dates de facturation**, dans le champ **Date de la facture**, sélectionnez **5/10/2021** (5 octobre 2021).
13. Dans le volet Actions, sélectionnez **Valider** pour valider la facture.

#### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Transférer la facture fournisseur au journal de déclaration d’échange de biens

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture fournisseur** sur **Oui**.
4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

   ![Ligne représentant la commande fournisseur sur la page de déclaration d’échanges de biens](media/intrastat_overview_5.png)

5. Examinez l’onglet **Général** pour la commande fournisseur. Remarquez que les champs **Quantité d’unités supplémentaires** et **Unité supplémentaire** de la section **Unité** sont automatiquement définis.

   ![Détails de la commande fournisseur sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_overview_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
