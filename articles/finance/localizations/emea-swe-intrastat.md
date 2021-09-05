---
title: Déclaration d’échanges de biens suédoise
description: Cette rubrique contient des informations sur la Déclaration d’échanges de biens en Suède.
author: andosip
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 404fb8dff1519aefb2f4af25eb95dfa6fce75b7c
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417080"
---
# <a name="swedish-intrastat"></a>Déclaration d’échanges de biens suédoise

[!include[banner](../includes/banner.md)]

La page **Déclaration d'échanges de biens** sert à générer et rapporter des informations sur le commerce entre pays/régions de l'Union européenne. La déclaration d’échanges de biens suédoise contient des informations sur le commerce de biens à déclarer.

Les champs suivants sont inclus dans la déclaration d’échanges de biens suédoise :

   - Code ISO du pays partenaire
   - Code transaction
   - Code marchandise
   - Unité additionnelle
   - Poids
   - Montant de la facture

## <a name="set-up-intrastat"></a>Configuration de la Déclaration d'échanges de biens

Importer la dernière version des configurations de génération d’états électroniques (ER) :

   - Modèle de déclaration d’échanges de biens
   - État de déclaration d’échanges de biens
   - Déclaration d’échanges de biens (SE)

Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Dans Microsoft Dynamics 365 Finance, accédez à **Taxes** > **Paramétrage** > **Paramètres de commerce extérieur**.
2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **Déclaration d’échanges de biens (SE)**.
3. Dans le champ **Mappage de format d'état**, sélectionnez **Déclaration d'échanges de biens**.
4. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d'échanges de biens**.
5. Dans le champ **Code transaction** sélectionnez le code transaction pour les transferts de propriété. Vous pouvez utiliser ce code pour les transactions qui génèrent des transferts de propriété réels ou prévus contre compensation (financière ou autre). Vous l’utilisez également pour les corrections. Les entreprises suédoises utilisent des codes de transaction à un chiffre.
6. Dans le champ **Avoir**, sélectionnez le code transaction pour le retour des marchandises. Ce code sert pour le retour des marchandises après la transaction enregistrée à l’origine sous le code de transaction. Les entreprises suédoises utilisent des codes de transaction à un chiffre.
7. Dans l’onglet **Propriétés de pays/région**, dans le champ **Pays/région**, répertoriez tous les pays ou régions avec lesquels votre société fait affaire. Pour chaque pays de l’UE, dans le champ **Type de pays/région**, sélectionnez **UE**, afin que le pays apparaisse sur votre déclaration d’échanges de biens.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Paramétrer les paramètres du produit pour la déclaration d’échanges de biens

1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
2. Sélectionnez un produit dans la grille.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez le code de marchandise.
4. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures nettes**, saisissez le poids du produit en kilogrammes.
5. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Compression de déclaration d’échanges de biens**, puis sélectionnez les champs qui doivent être comparés lors de la synthèse des informations de la déclaration d’échanges de biens. Pour la déclaration d’échanges de biens suédoise, sélectionnez les champs suivants :

    - Marchandise
    - Code transaction
    - Direction
    - Pays/région
    - Correction
    - Facture

## <a name="intrastat-transfer"></a>Transfert des déclarations d'échanges de biens

Sur la page **Déclaration d'échanges de biens**, dans le volet Actions, vous pouvez sélectionner **Transférer** pour transférer automatiquement les informations sur le commerce intracommunautaire à partir de vos commandes clients, de vos factures financières, des commandes fournisseur, des factures fournisseurs, des accusés de réception de produits fournisseurs, des factures de projet et des ordres de transfert. Seuls les documents ayant un pays de l'UE comme pays ou région de destination (pour les expéditions) ou de consignation (pour les arrivées) seront transférés.

Vous pouvez également saisir manuellement des transactions en sélectionnant **Nouveau** dans le volet Actions.

### <a name="generate-an-intrastat-report"></a>Génération d'une déclaration d'échanges de biens

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Résultat** > **État**.
3. Dans la boîte de dialogue **Déclaration d'échanges de biens**, définissez les champs suivants :

    | Champ            | Description                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Date de début        | Sélectionnez la date de début de la déclaration.                                                                                               |
    | Au          | Sélectionnez la date de fin de la déclaration.                                                                                                 |
    | Générer un fichier    | Définissez cette option sur **Oui** pour générer un fichier .txt. pour votre rapport de déclaration d’échanges de biens.                                                       |
    | Nom de fichier        | Entrez le nom du fichier .txt.                                                                                                    |
    | Générer un rapport  | Définissez cette option sur **Oui** pour générer un fichier .xlsx pour votre rapport de déclaration d’échanges de biens.                                                     |
    | Nom du fichier d'état | Entrez le nom du fichier .xlsx.                                                                                                   |
    | Direction        | Sélectionnez **Arrivées** pour un rapport sur les arrivées intracommunautaires. Sélectionnez **Expéditions** pour un rapport sur les envois intracommunautaires. |

4. Cliquez sur **OK** et examinez les états générés.

## <a name="example"></a>Exemple

Cet exemple montre comment valider les arrivées et les expéditions pour la déclaration d’échanges de biens. Il utilise l'entité juridique **DEMF**.

### <a name="preliminary-setup"></a>Paramétrage préliminaire

1. Allez dans **Administration d’organisation** > **Organisation** > **Entités juridiques**, puis sélectionnez l’entité juridique **DEMF**.
2. Sur le raccourci **Adresses**, sélectionnez **Modifier**, puis, dans le champ **Pays/région**, sélectionnez **SWE (Suède)**.
3. Importer la dernière version des configurations de génération d’états électroniques (ER) :

    - Modèle de déclaration d’échanges de biens
    - État de déclaration d’échanges de biens
    - Déclaration d’échanges de biens (SE)

### <a name="create-transaction-codes"></a>Créer les codes transactions

1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Codes transaction**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Code** **transaction**, entrez **1**.
4. Dans le champ **Nom**, entrez **Transactions normales**
5. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code** **transaction**, sélectionnez **1**.
3. Dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **Déclaration d’échanges de biens (SE)**.
4. Dans le champ **Mappage de format d’état**, sélectionnez **Déclaration d’échanges de biens**.
5. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, assurez-vous que **Déclaration d’échanges de biens** est sélectionné.
6. Dans l’onglet **Propriétés de pays/région**, sélectionnez **Nouveau**.
7. Dans le champ **Pays/région de la partie**, sélectionnez **SWE**.
8. Dans le champ **Type de pays/région**, sélectionnez **Local**.
9. Dans le champ **Pays/région de la partie**, sélectionnez **DEU** puis, dans le champ **Type de pays/région**, sélectionnez **UE**.

### <a name="set-up-product-information"></a>Configurer les informations sur le produit

1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
2. Dans la grille, sélectionnez **D0001**.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **100 200 30**.
4. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures pondérales**, dans le champ **Poids net**, entrez **5**.
5. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="change-the-site-address"></a>Changer l’adresse du site

1. Accédez à **Gestion des entrepôts** > **Paramétrage** > **Entrepôt** > **Sites**.
2. Dans la grille, sélectionnez **1**.
3. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
4. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **SWE**.
5. Cliquez sur **OK**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Créer une commande client avec un client de l’UE

1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande client**, dans le raccourci **Client**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-015**.
4. Dans le raccourci **Général**, dans la section **Dimensions de stockage**, dans le champ **Site**, sélectionnez **1**.
5. Dans le champ **Entrepôt**, sélectionnez **11**.
6. Cliquez sur **OK**.
7. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande client**, dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité**, entrez **10**.
8. Dans le raccourci **Détails de ligne**, dans l’onglet **Commerce extérieur**, assurez-vous que les champs **Code transaction** et **Marchandise** sont automatiquement définis.
9. Dans le volet Actions, sélectionnez **Enregistrer**.
10. Dans le volet Actions, sous l’onglet **Facture**, dans la section **Générer**, sélectionnez **Facture**.
11. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**.
12. Cliquez sur **OK** pour valider la facture.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transférer la transaction dans le journal de déclaration d’échanges de biens et examiner le résultat

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d'échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l'option **Facture client** sur **Oui**.
4. Sélectionnez **Filtrer**.
5. Dans la boîte de dialogue **Filtre de déclaration d’échanges de biens**, dans l’onglet **Plage**, sélectionnez la première ligne et assurez-vous que le champ **Champ** est défini sur **Date**.
6. Dans le champ **Critères**, sélectionnez la date actuelle.
7. Cliquez sur **OK** pour fermer la boîte de dialogue **Filtre de déclaration d’échanges de biens**.
8. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens (Transfert)** et examinez le résultat. La ligne représente la commande client que vous avez créée précédemment.

    ![Lignes journal de déclaration d’échanges de biens pour la commande client](media/swe_intrastat_journal_sales_order.png)

9. Sélectionnez la ligne de transaction, puis l’onglet **Général** pour afficher plus de détails.

    ![Détails de lignes journal de déclaration d’échanges de biens pour la commande client](media/swe_intrastat_journal_sales_order_line_details.png)

10. Dans le volet Actions, sélectionnez **Résultat** > **État**.
11. Dans la boîte de dialogue **Déclaration d'échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, sélectionnez le mois de la commande client que vous avez créée.
12. Dans la section **Options** **d’exportation**, définissez l’option **Générer un fichier** sur **Oui**. Puis, dans le champ **Nom du fichier**, entrez le nom requis.
13. Définissez l’option **Générer un état** sur **Oui**. Puis, dans le champ **Nom du fichier d’état**, entrez le nom requis.
14. Dans le champ **Direction**, sélectionnez **Répartitions**.
15. Cliquez sur **OK** et examinez l’état généré au format .txt. Le tableau suivant indique les valeurs dans l’exemple d’état.

    | Code ISO du pays partenaire | Code transaction | Code marchandise | Unité additionnelle | Poids | Montant de la facture |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Examinez le fichier généré dans le format Excel.

    ![État de déclaration d’échanges de biens](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Comptabilité fournisseur** > **Commandes fournisseur** > **Toutes les commandes fournisseur**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande fournisseur**, dans le champ **Compte fournisseur**, sélectionnez **DE-001**.
4. Cliquez sur **OK**.
5. Sur l’onglet **En-tête**, sur le raccourci **Commerce** **étranger**, vérifiez que le champ **Code de transaction** est défini sur **1**.
6. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande fournisseur**, dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité**, entrez **6**.
7. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer**.
8. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
9. Sur le volet Action, sélectionnez **Par défaut**. Dans le champ **Quantité par défaut pour les lignes**, sélectionnez **Quantité commandée**. Puis sélectionnez **OK**.
10. Sur le raccourci **En-tête de facture fournisseur**, dans la section **Identification de la facture**, dans le champ **Numéro**, entrez **0001**.
11. Dans le volet Actions, sélectionnez **Valider** pour valider la facture.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Créer une déclaration d’échanges de biens pour les arrivées

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture fournisseur** sur **Oui**.
4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

    ![Journal de déclaration d’échanges de biens pour la commande fournisseur](media/swe_intrastat_journal_purchase_order.png)

5. Examinez l’onglet **Général** pour la commande fournisseur.

    ![Détails de lignes journal de déclaration d’échanges de biens pour la commande fournisseur](media/swe_intrastat_journal_purchase_order_line_details.png)

6. Dans le volet Actions, sélectionnez **Résultat** > **État**.
7. Dans la boîte de dialogue **Déclaration d'échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, sélectionnez le mois de la commande client que vous avez créée.
8. Dans la section **Options** **d’exportation**, définissez l’option **Générer un fichier** sur **Oui**. Puis, dans le champ **Nom du fichier**, entrez le nom requis.
9. Définissez l’option **Générer un état** sur **Oui**. Puis, dans le champ **Nom du fichier d’état**, entrez le nom requis.
10. Dans le champ **Direction**, sélectionnez **Arrivées**.
11. Cliquez sur **OK** et examinez l’état généré au format .txt. Le tableau suivant indique les valeurs dans l’exemple d’état.

    | Code ISO du pays partenaire | Code transaction | Code marchandise | Unité additionnelle | Poids | Montant de la facture |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Examinez le fichier généré dans le format Excel.

    ![Rapport des arrivées de déclaration d’échanges de biens](media/swe_intrastat_arrivals_report.png)
