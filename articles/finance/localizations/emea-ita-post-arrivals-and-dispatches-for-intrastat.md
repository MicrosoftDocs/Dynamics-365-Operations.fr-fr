---
title: Valider les arrivées et les expéditions dans le cadre de la déclaration d’échanges de biens
description: Cette rubrique offre un exemple présentant comment valider les arrivées et les expéditions pour la déclaration d’échanges de biens.
author: anasyash
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4ab4402740d199043519773b18732bdde9a0fb2f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724781"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Valider les arrivées et les expéditions dans le cadre de la déclaration d’échanges de biens

[!include [banner](../includes/banner.md)]

Cette rubrique offre un exemple présentant comment valider les arrivées et les expéditions pour la déclaration d’échanges de biens. L’exemple utilise l’entité juridique **ITCO**.

## <a name="setup"></a>Paramétrage

1. Importer la dernière version des configurations de génération d’états électroniques (ER) :

    - Modèle de déclaration d’échanges de biens
    - État de déclaration d’échanges de biens
    - Déclaration d'échanges de biens (IT)

    Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

2. Dans Microsoft Dynamics 365 Finance, définissez les séquences de nombres suivantes comme continues : **Gene\_397**, **Acco\_16403**, **Gene\_407** et **PUR\_EU**.

    1. Accédez à **Administration d’organisation** > **Séquences de nombres** > **Séquences de nombres**.
    2. Dans la grille, sélectionnez l’un des codes de séquence de numéros.
    3. Dans le volet Actions, sélectionnez **Modifier**.
    4. Sous l’organisateur **Général**, dans la section **Configuration**, définissez l’option **Continue** sur **Oui**.
    5. Dans le volet Actions, sélectionnez **Enregistrer**.

3. Définissez une adresse d’entrepôt.

    1. Accédez à **Gestion des entrepôts** &gt; **Paramétrage** &gt; **Entrepôt** &gt; **Entrepôts**.
    2. Sélectionnez un entrepôt dans la liste **11**.
    3. Dans le raccourci **Adresse**, sélectionnez **Ajouter**.
    4. Dans la boîte de dialogue **Nouvelle** **adresse**, dans le champ **Nom** **ou** **description**, entrez **Principale**.
    5. Dans le champ **Pays/région**, sélectionnez **ITA (Italie)**.
    6. Dans le champ **Ville**, sélectionnez **Aprilia**.
    7. Cliquez sur **OK**.

4. Définissez des codes transaction.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Codes transaction**.
    2. Sélectionnez **Nouveau**, et mettez en place un code de transaction pour les transferts de propriété.

        - Dans le champ **Code transaction code**, entrez **1**.
        - Dans le champ **Nom**, entrez **Transfert de propriété**.

    3. Sélectionnez **Nouveau**, et mettez en place un code de transaction pour les retours.

        - Dans le champ **Code** **transaction**, entrez **2**.
        - Dans le champ **Nom**, entrez **Retour de marchandises**.

5.  Configurez les paramètres de commerce extérieur.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
    2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code** **transaction**, sélectionnez **1**.
    3. Dans le champ **Avoir**, sélectionnez **2**.
    4. Dans le champ **Période de reporting de vente**, sélectionnez **Mois**.
    5. Dans le champ **Période de reporting d’achat**, sélectionnez **Mois**.
    6. Dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **Déclaration d’échanges de biens (IT)**.
    7. Dans le champ **Mappage de format de reporting**, sélectionnez **État de déclaration d’échanges de biens**.
    8. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d’échanges de biens**.
    9. Dans le raccourci **Valeur statistique**, définissez l’option **Imprimer et exporter des données statistiques** sur **Oui**.
    10. Sur l’onglet **Propriétés de pays/régions**, vérifiez que les lignes suivantes existent.

        | **Partie/Pays/Région** | **Code déclaration d'échanges de biens** | **Devise** | **Type de pays/région** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | IT                 | EUR          | Local                |
        | SMR                      | SM                 | EUR          | Local spécial        |

    11. Dans la barre d’outils, sélectionnez **Nouveau** pour créer la ligne suivante.

        | **Partie/Pays/Région** | **Code déclaration d'échanges de biens** | **Devise** | **Type de pays/région** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | DKK          | UE                      |

6. Paramétrez les numéros exempts de TVA.

    1. Accédez à **Taxe** > **Paramétrage** > **Taxe** > **Numéros d’exonération fiscale**.
    2. Dans le volet Actions, sélectionnez **Nouveau** pour créer les lignes suivantes.

        | **Pays/région** | **Numéro identifiant TVA** | **Nom de la société** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | FOURNISSEUR UE        |
        | DNK                | DK0987654321          | Client ER      |

7. Définissez l’adresse du fournisseur.

    1. Accédez à **Comptabilité fournisseur** &gt; **Fournisseurs** &gt; **Tous les fournisseurs**.
    2. Dans la grille, sélectionnez **Fournisseur de l’UE**.
    3. Dans le raccourci **Adresses**, sélectionnez **Ajouter**.
    4. Dans la boîte de dialogue **Nouvelle adresse**, dans le champ **Nom ou description**, entrez **Allemagne**.
    5. Dans le champ **Pays/région**, sélectionnez **DEU**.
    6. Sélectionnez **OK** pour créer l’adresse.
    7. Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, dans le champ **Numéro d’exonération fiscale**, sélectionnez **Tous**, puis sélectionnez **DE1234567890**.
    8. Dans le volet Actions, sélectionnez **Enregistrer**.

8. Définissez les adresses des clients.

    1. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**.
    2. Dans la grille, sélectionnez **ITCO-000001**.
    3. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
    4. Dans la boîte de dialogue **Nouvelle adresse**, dans le champ **Nom ou description**, entrez **Saint-Marin**.
    5. Dans le champ **Pays/région**, sélectionnez **SMR**.
    6. Sélectionnez **OK** pour créer l’adresse.
    7. Sur le raccourci **Facture et livraison**, dans la section **Facture**, dans le champ **Compte de facturation**, sélectionnez **ITCO-000001**.
    8. Dans le champ **Groupe de séquences de numéros**, sélectionnez **IT\_VENDOM**.
    9. Sur le volet Action, sélectionnez **Enregistrer** et fermez la page.
    10. Sur la page **Tous les clients**, dans la grille, sélectionnez **ITCO-000002**.
    11. Dans le raccourci **Adresses**, sélectionnez **Ajouter**.
    12. Dans la boîte de dialogue **Nouvelle adresse**, dans le champ **Nom ou description**, entrez **Danemark**.
    13. Dans le champ **Pays/région**, sélectionnez **DNK**.
    14. Sélectionnez **OK** pour créer l’adresse.
    15. Sur le raccourci **Démographie de vente**, dans le champ **Devise**, sélectionnez **DKK**.
    16. Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, dans le champ **Groupe de taxe de vente**, sélectionnez **IT\_PUREU**.
    17. Dans le champ **Numéro d’exonération fiscale**, sélectionnez **Tous**, puis sélectionnez **DK0987654321**.
    18. Dans le volet Actions, sélectionnez **Enregistrer**.

9. Paramétrez la hiérarchie de catégories.

    1. Accédez à **Gestion des informations sur les produits** > **Paramétrage** > **Catégories et d’attributs** > **Hiérarchies de catégories**.
    2. Dans la grille, sélectionnez **Déclaration d’échanges de biens**.
    3. Sélectionnez **Nouveau nœud de catégories** dans le volet Actions.
    4. Dans le champ **Nom**, entrez **Service**.
    5. Dans le champ **Code**, entrez **123456**.
    6. Dans le volet Actions, sélectionnez **Enregistrer**.

10. Paramétrez les produits.

    1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
    2. Dans la grille, sélectionnez **ITEM**.
    3. Sur le raccourci **Achat**, dans la section **Administration**, dans le champ **Fournisseur**, sélectionnez **ITCO-000001**.
    4. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **\[100 200 30\] Haut-parleur**.
    5. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez **DEU**.
    6. Dans le champ **État/province**, sélectionnez **BE**.
    7. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures nettes**, dans le champ **Poids net**, entrez **5**.
    8. Dans le volet Actions, sélectionnez **Enregistrer**.
    9. Sur la page **Produits lancés**, dans la grille, sélectionnez **Article de service**.
    10. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **\[123456\] Service**.
    11. Dans le volet Actions, sélectionnez **Enregistrer**.

11. Paramétrez les modes de transport.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Mode de transport**.
    2. Dans le volet Actions, sélectionnez **Nouveau** pour créer les modes de transport suivants.

        | **Transport** | **Description** |
        |---------------|-----------------|
        | 1             | Route            |
        | 2             | Air             |

12. Paramétrez un mode de livraison.

    1. Accédez à **Approvisionnements** > **Paramétrage** > **Distribution** > **Modes de livraison**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans le champ **Mode de livraison**, entrez **1**.
    4. Dans le champ **Description**, entrez **Camion**.
    5. Dans le raccourci **Commerce extérieur**, dans le champ **Transport**, sélectionnez **1 Route**.
    6. Dans le volet Actions, sélectionnez **Enregistrer**.

13. Paramétrez des conditions de livraison.

    1. Accédez à **Comptabilité fournisseur** > **Paramétrage** > **Conditions de livraison**.
    2. Dans la liste, sélectionnez **CFR**.
    3. Dans l’organisateur **Général**, dans le champ **Code de déclaration d’échanges de biens**, saisissez **1**.

## <a name="post-arrivals-for-intrastat"></a>Valider les arrivées pour la déclaration d’échanges de biens

### <a name="purchase-goods-by-using-a-purchase-order"></a>Acheter des marchandises à l’aide d’une commande fournisseur

Cette partie de l’exemple montre comment utiliser une commande fournisseur pour acheter des marchandises (articles) dans les pays de l’Union européenne (UE).

1. Accédez à **Comptabilité fournisseur** > **Commandes fournisseur** > **Toutes les commandes fournisseur**.
2.  Dans le volet Actions, sélectionnez **Nouveau**.
3.  Dans la boîte de dialogue **Créer une commande fournisseur**, dans le champ **Compte fournisseur**, sélectionnez **Fournisseur UE**.
4.  Sur le raccourci **Administration**, dans le champ **Langue**, sélectionnez **it**.
5.  Cliquez sur **OK**.
6.  Sur la vue **En-tête**, sur le raccourci **Commerce** **étranger**, vérifiez que le champ **Code de transaction** est défini sur **1**.
7.  Vérifiez que le champ **Comté d’origine/destination** est défini sur **RM**.
8.  Dans le raccourci **Livraison**, dans la section **Livraison**, dans le champ **Mode de livraison**, sélectionnez **1**.
9.  Dans le champ **Conditions de livraison**, sélectionnez **CFR**.
10. Dans la vue **Lignes**, dans le raccourci **Lignes de commande fournisseur**, dans le champ **Numéro d’article**, sélectionnez **Article**.
11. Dans le champ **Site**, sélectionnez **1**.
12. Dans le champ **Entrepôt**, sélectionnez **11**.
13. Dans le champ **Quantité**, entrez **10**.
14. Dans le champ **Prix unitaire**, entrez **100**.
15. Dans l’onglet **Configuration**, dans la section **Taxe de vente**, dans le champ **Groupe de taxe d’article**, sélectionnez **22 % UE**.
16. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer**.
17. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
18. Sur le volet Action, sélectionnez **Par défaut**.
19. Dans le champ **Quantité par défaut pour les lignes**, sélectionnez **Quantité commandée**, puis **OK**.
20. Sur le raccourci **En-tête de facture fournisseur**, dans la section **Identification de la facture**, dans le champ **Numéro**, entrez **0001**.
21. Dans la rubrique **Dates de facturation**, dans le champ **Date de la facture**, sélectionnez **09/07/2021**.
22. Dans le volet Actions, sélectionnez **Valider** pour valider la facture.

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Acheter des services à l’aide d’une facture fournisseur

Cette partie de l’exemple montre comment utiliser une facture fournisseur pour acheter des services dans les pays de l’Union européenne (UE).

1. Accédez à **Comptabilité fournisseur** > **Factures** > **Journal des factures**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Nom**, sélectionnez **VEND\_EUINV**.
4. Dans le volet Action, sélectionnez **Lignes**.
5. Dans le champ **Date**, entrez **09/07/2021**.
6. Dans le champ **Type de compte**, sélectionnez **Fournisseur**.
7. Dans le champ **Type de compte**, sélectionnez **Fournisseur de l’UE**.
8. Dans le champ **Date de facture**, sélectionnez **09/07/2021**.
9. Dans le champ **Facture**, entrez **ITA-0004**.
10. Dans le champ **Crédit**, entrez **120000**.
11. Dans le champ **Type** **de compte de contrepartie**, sélectionnez **Comptabilité**.
12. Dans le champ **Compte de contrepartie**, sélectionnez **110130**.
13. Dans le champ **Groupe de taxe de vente**, sélectionnez **IT\_PUREU**.
14. Dans le champ **Groupe de taxe de vente d’article**, sélectionnez **22 % UE**.
15. Sur l’onglet **Commerce extérieur**, suivez une des étapes suivantes :

    1. Dans le champ **Code transaction code**, sélectionnez **1**.
    2. Dans le champ **Transport**, sélectionnez **2 Air**.
    3. Dans le champ **Marchandise**, sélectionnez **\[123456\] Service**.
    4. Dans le champ **Pays/région**, sélectionnez **ITA**.
    5. Dans le champ **État/province**, sélectionnez **LAZ**.
    6. Dans le champ **Département d’origine/destination**, sélectionnez **LT**.


16. Dans le volet Actions, sélectionnez **Valider**.
17. Créez une déclaration d’échanges de biens pour les arrivées.

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture fournisseur** sur **Oui**.
    4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

   ![Page du journal de déclaration d’échanges de biens, onglet Aperçu.](media/ita_intrastat_journal_vendor_invoice.png)

18. Examinez l’onglet **Général** pour la commande fournisseur.

    ![Détails de lignes journal de déclaration d’échanges de biens pour la commande fournisseur](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Examinez l’onglet **Général** pour la facture fournisseur.

    ![Détails de lignes journal de déclaration d’échanges de biens pour la facture fournisseur](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Générer l’état de déclaration d’échanges de biens pour les arrivées.

    1. Dans le volet Actions, sélectionnez **Résultat** > **État**.
    2. Dans la boîte de dialogue **État de déclaration d’échanges de biens**, dans la section **Date**, dans le champ **Date de début**, sélectionnez **07/01/2021**.
    3. Dans le champ **Date de fin**, sélectionnez **31/07/2021**.
    4. Dans la section **Options d’exportation**, définissez les options **Générer un fichier** et **Générer un état** sur **Oui**.
    5. Dans le champ **Nom de fichier**, entrez **Fichier des arrivées**.
    6. Dans le champ **Nom de fichier d’état**, entrez **État des arrivées**.
    7. Dans le champ **Direction**, sélectionnez **Arrivées**.
    8. Dans le champ **N° de référence**, saisissez **123456**.
    9. Sélectionnez **OK** pour générer le rapport de déclaration d’échanges de biens et le fichier de déclaration d’échanges de biens et les examiner.

    L’illustration suivante présente un exemple d’état de déclaration d’échanges de biens.

    ![Rapport des arrivées de déclaration d’échanges de biens.](media/ita_intrastat_arrivals_report.png)

    L’illustration suivante présente un exemple de fichier de déclaration d’échanges de biens.

    ![Fichier des arrivées de déclaration d’échanges de biens.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Valider les expéditions pour la déclaration des échanges de biens

### <a name="sell-goods-by-using-a-sales-order"></a>Vendre des marchandises à l’aide d’une commande client

Cette partie de l’exemple montre comment utiliser une commande client pour vendre des marchandises (articles) dans les pays de l’Union européenne (UE).

1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez **ITCO-000002**.
4. Cliquez sur **OK**.
5. Dans la vue **En-tête**, sur le raccourci **Livraison**, dans la section **Diverses infos de livraison**, dans le champ **Mode de livraison**, sélectionnez **1 Camion**.
6. Dans le champ **Conditions de livraison**, sélectionnez **CFR**.
7. Dans la vue **Lignes**, dans le raccourci **Lignes de commande client**, dans le champ **Numéro d’article**, sélectionnez **ITEM**.
8. Dans le champ **Quantité**, entrez **50**.
9. Dans le champ **Site**, sélectionnez **1**.
10. Dans le champ **Entrepôt**, sélectionnez **11**.
11. Dans le champ **Prix unitaire**, entrez **250**.
12. Dans le raccourci **Détails de ligne**, sur l’onglet **Configuration**, dans la section **Taxe de vente**, dans le champs **Groupe de taxe d’article**, sélectionnez **22 % UE**.
13. Dans le volet Actions, sélectionnez **Enregistrer**.
14. Dans le volet Actions, sur l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture** pour créer la facture pour la commande.
15. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**.
16. Dans le raccourci **Configuration**, dans le champ **Date** **de facture**, sélectionnez **09/07/2021**.
17. Cliquez sur **OK**.
18. Examinez les lignes de journal dans le journal de déclaration d’échanges de biens.

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture client** sur **Oui**.
    4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens. La transaction de note de crédit est marquée comme une correction et a un montant de facture négatif.

        ![Page du journal des déclarations d’échanges de biens](media/ita_intrastat_journal_sales_order.png)

        ![Détails de lignes journal de déclaration d’échanges de biens pour la commande client](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Retourner les marchandises en utilisant une note de crédit

Cette partie de l’exemple montre comment utiliser une note de crédit pour renvoyer des marchandises (articles) dans les pays de l’Union européenne (UE).

1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez **ITCO-000002**.
4. Cliquez sur **OK**.
5. Dans la vue **En-tête**, sur le raccourci **Livraison**, dans la section **Diverses infos de livraison**, dans le champ **Mode de livraison**, sélectionnez **1 Camion**.
6. Dans le champ **Conditions de livraison**, sélectionnez **CFR**.
7. Dans le raccourci **Commerce extérieur**, dans le champ **Code de transaction**, sélectionnez **2**.
8. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande client**, dans le champ **Numéro d’article**, sélectionnez **ITEM**.
9. Dans le champ **Quantité**, saisissez **-10**.
10. Dans le champ **Site**, sélectionnez **1**.
11. Dans le champ **Entrepôt**, sélectionnez **11**.
12. Dans le champ **Prix unitaire**, entrez **250**.
13. Dans le raccourci **Détails de ligne**, sur l’onglet **Configuration**, dans la section **Taxe de vente**, dans le champs **Groupe de taxe d’article**, sélectionnez **22 % UE**.
14. Dans la section **Commande retournée**, dans le champ **N° de traitement de retours**, sélectionnez le lot que vous avez créé précédemment.
15. Dans le volet Actions, sélectionnez **Enregistrer**.
16. Dans le volet Actions, sur l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture** pour créer la facture pour la commande.
17. Sur le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tout**.
18. Dans la boîte de dialogue **Validation de la facture**, sur le raccourci **Configuration**, dans le champ **Date** **de la facture**, sélectionnez **09/07/2021**.
19. Cliquez sur **OK** pour valider la facture.
20. Examinez les lignes de journal dans le journal de déclaration d’échanges de biens.

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture client** sur **Oui**.
    4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens. La transaction de note de crédit est marquée comme une correction et a un montant de facture négatif.

    ![Note de crédit du journal de déclaration d’échanges de biens](media/ita_intrastat_journal_credit_note.png)

    ![Détails de lignes journal de déclaration d’échanges de biens pour la note de crédit](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Vendre des marchandises à Saint-Marin à l’aide d’une commande client

Cette partie de l’exemple montre comment utiliser une commande client pour acheter des marchandises (articles) à Saint-Marin.

1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande client**, dans le champ **Compte client**, sélectionnez **ITCO-000001**.
4. Cliquez sur **OK**.
5. Dans la vue **En-tête**, sur le raccourci **Livraison**, dans la section **Diverses infos de livraison**, dans le champ **Mode de livraison**, sélectionnez **1**.
6. Dans le champ **Conditions de livraison**, sélectionnez **CFR**.
7. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande client**, dans le champ **Numéro d’article**, sélectionnez **ITEM**.
8. Dans le champ **Quantité**, entrez **30**.
9. Dans le champ **Site**, sélectionnez **1**.
10. Dans le champ **Entrepôt**, sélectionnez **11**.
11. Dans le champ **Prix unitaire**, entrez **200**.
12. Dans le volet Actions, sélectionnez **Enregistrer**.
13. Dans le volet Actions, sur l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture** pour créer la facture pour la commande.
14. Sur le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tout**.
15. Dans la boîte de dialogue **Validation de la facture**, sur le raccourci **Configuration**, dans le champ **Date** **de la facture**, sélectionnez **09/07/2021**.
16. Cliquez sur **OK** pour valider la facture.
17. Examinez les lignes de journal dans le journal de déclaration d’échanges de biens.

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture client** sur **Oui**.
    4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

   ![Journal de déclaration d’échanges de biens pour Saint-Marin](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Détails de lignes journal de déclaration d’échanges de biens pour Saint-Marin](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Créez une déclaration d’échanges de biens pour les expéditions.

    1. Accédez à **Taxes** &gt; **Déclarations** &gt; **Commerce extérieur** &gt; **Déclaration d'échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Résultat** &gt; **Rapport**.
    3. Dans la boîte de dialogue **État de déclaration d’échanges de biens**, dans la section **Date**, dans le champ **Date de début**, sélectionnez **07/01/2021**.
    4. Dans le champ **Date de fin**, sélectionnez **31/07/2021**.
    5. Dans la section **Options d’exportation**, définissez les options **Générer un fichier** et **Générer un état** sur **Oui**.
    6. Dans le champ **Nom de fichier**, entrez **Fichier des expéditions**.
    7. Dans le champ **Nom de fichier d’état**, entrez **État des expéditions**.
    8. Dans le champ **Direction**, sélectionnez **Répartitions**.
    9. Dans le champ **N° de référence**, saisissez **98754**.
    10. Sélectionnez **OK** pour générer le rapport de déclaration d’échanges de biens et le fichier de déclaration d’échanges de biens.

        L’illustration suivante présente un exemple d’état de déclaration d’échanges de biens imprimé.

        ![État de déclaration d’échanges de biens](media/ita_intrastat_report_for_dispatches.png)

        L’illustration suivante présente un exemple de fichier de déclaration d’échanges de biens imprimé.

        ![Fichier de déclaration d’échanges de biens pour les expéditions](media/ita_intrastat_file_for_dispatches.png)
