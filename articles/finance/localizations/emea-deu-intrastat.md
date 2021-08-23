---
title: Déclaration d’échanges de biens allemande
description: Cette rubrique contient des informations sur la déclaration d’échanges de biens en Allemagne.
author: andosip
ms.date: 08/2/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: e1dbf0997417f9f1ad313e6a7b3c2c9cfae41efc6b1cfda60a5500ae0af94709
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759841"
---
# <a name="german-intrastat"></a>Déclaration d’échanges de biens allemande

La page **Déclaration d'échanges de biens** sert à générer et rapporter des informations sur le commerce entre pays/régions de l'Union européenne. La déclaration d’échanges de biens allemande contient des informations sur le commerce de biens à déclarer.

Le tableau suivant présente les champs inclus dans la déclaration d’échanges de biens allemande.

| Champs | Répartitions | Introduction |
|-------------------------|-------------------------|-------------------------|
| Période de référence | O | O |
| Code direction | O | O |
| Devise de la déclaration d’échanges de biens</br>**Remarque :** Cette devise est la <em>devise comptable</em>. | O | O |
| Code marchandise | O | O |
| Nom de la marchandise | O | O |
| Code d’unité supplémentaire | O | O |
| État membre de consignation/destination | O | O |
| Masse nette | O | O |
| Quantité en unités supplémentaires | O | O |
| Pays d'origine |  | O |
| Montant de la facture | O |  |
| Valeur statistique | O | O |
| Nature des transactions | O | O |
| Mode de transport | O | O |
| Code région</br>**Remarque :**</br><ul></br><li>Si le pays ou la région d’origine est l’Allemagne et que la facture concerne des expéditions, un code de déclaration d’échanges de biens pour l’état d’origine est affiché.</li></br><li>Si le pays ou la région d’origine n’est pas l’Allemagne et que la facture concerne des expéditions, le code **99** est affiché.</li></br><li>Si la facture concerne des arrivées, un code de déclaration d’échanges de biens pour l’état est affiché.</li></br></ul> | O | O |
| Code port/aéroport/port intérieur | O | O |
| Conditions de livraison | O | O |


## <a name="set-up-intrastat"></a>Configuration de la Déclaration d'échanges de biens

1. Configurez les codes de la société.

    1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
    2. Dans le raccourci **Commerce extérieur et logistique**, dans la section **Identification**, dans le champ **DVR**, entrez l’ID de l’accord d’échange. Cet ID sera inclus dans la déclaration.
    3. Dans le champ **Exportation de numéro identifiant TVA**, entrez le numéro de taxe sur la valeur ajoutée (TVA) de votre entreprise pour l’exportation.
    4. Dans le champ **Importation de numéro identifiant TVA**, entrez le numéro de taxe sur la valeur ajoutée (TVA) de votre entreprise pour l’importation.
    5. Dans le champ **Code de déclaration d’échanges de biens**, saisissez le code de déclaration d’échanges de biens qui est affecté à l’entité juridique.
    6. Dans le raccourci **Immatriculation fiscale**, dans le champ **Numéro d’immatriculation fiscale**, spécifiez le numéro d'identification fiscale de votre société.

    > [!NOTE]
    > Si vous générez une déclaration d’échanges de biens pour des filiales, dans le champ **Numéro d’immatriculation fiscale**, saisissez le numéro d’identification fiscale de votre société mère.

2. Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations de gestion des états électroniques pour la déclaration d’échanges de biens.

    - Modèle de déclaration d’échanges de biens
    - État de déclaration d’échanges de biens
    - INSTAT XML
    - INSTAT XML (DE)

3. Configurez les paramètres de commerce extérieur :

    1. Dans Dynamics 365 Finance, accédez à **Taxes** > **Paramétrage** > **Paramètres de commerce extérieur**.
    2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **Déclaration d’échanges de biens XML (DE)**.
    3. Dans le champ **Mappage de format d'état**, sélectionnez **Déclaration d'échanges de biens**.
    4. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d'échanges de biens**.
    5. Dans le champ **Code transaction** sélectionnez le code transaction pour les transferts de propriété. Vous pouvez utiliser ce code pour les transactions qui génèrent des transferts de propriété réels ou prévus contre compensation (financière ou autre). Vous l’utilisez également pour les corrections.
    6. Dans le champ **Avoir**, sélectionnez le code transaction pour le retour des marchandises. Ce code sert pour le retour des marchandises après la transaction enregistrée à l’origine sous le code de transaction.
    7. Dans le champ **Administration**, sélectionnez l’administration de déclaration d’échanges de biens.
    8. Accédez à **Taxes** > **Taxes indirectes** > **Taxe de vente** > **Administrations fiscales**, puis entrez les informations suivantes pour l’administration de déclaration d’échanges de biens que vous avez sélectionnée à l’étape précédente :

       - Identification de l’administration
       - Adresse
       - Informations sur le contact

    9. Dans l’onglet **Propriétés de pays/région**, dans le champ **Pays/région**, répertoriez tous les pays ou régions avec lesquels votre société fait affaire. Pour chaque pays ou région, dans le champ **Type de pays/région**, sélectionnez **UE**, afin que le pays ou la région apparaisse sur votre déclaration d’échanges de biens.

4. Configurez les codes régions.

    1. Accédez à **Administration d’organisation** > **Carnet d’adresses global** > **Adresses** > **Configuration de l’adresse**.
    2. Dans l’onglet **État/province**, dans le champ **Pays/région**, sélectionnez **DEU**, puis sélectionnez **Appliquer le filtre**.
    3. Dans la grille, sélectionnez l’état. Ensuitez, dans le champ **Code de déclaration d’échanges de biens**, entrez le code unique de déclaration d’échanges de biens.

5. Configurez l’adresse d’origine d’un produit.

    1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
    2. Sélectionnez le produit dans la grille.
    3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Pays d’origine**, sélectionnez **DEU**.

6. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Compression de déclaration d’échanges de biens**, puis sélectionnez les champs qui doivent être comparés lors de la synthèse des informations de la déclaration d’échanges de biens. Pour la déclaration d’échanges de biens allemande, sélectionnez les champs suivants :

    - Marchandise
    - Pays/région
    - Correction
    - Direction
    - Conditions de livraison
    - Facture
    - Pays/région d'origine
    - Port
    - Pays/région de l'expéditeur
    - État de l'expéditeur
    - Procédure statistique
    - Code transaction
    - Transport
    - Numéro identifiant TVA

### <a name="intrastat-transfer"></a>Transfert des déclarations d'échanges de biens

Sur la page **Déclaration d’échanges de biens**, dans le volet Actions, vous pouvez sélectionner **Transférer** pour transférer automatiquement les informations sur le commerce intracommunautaire à partir de vos commandes clients, de vos factures financières, des commandes fournisseur, des factures fournisseur, des accusés de réception de produits fournisseurs **,** des factures de projet et des ordres de transfert. Seuls les documents ayant un pays de l'UE comme pays ou région de destination (pour les expéditions) ou de consignation (pour les arrivées) seront transférés.

Vous pouvez également saisir manuellement des transactions en sélectionnant **Nouveau** dans le volet Actions.

### <a name="generate-an-intrastat-report"></a>Génération d'une déclaration d'échanges de biens

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Résultat** > **État**.
3. Dans la boîte de dialogue **Déclaration d'échanges de biens**, définissez les champs suivants :

    | Champ | Description |
    |-------------------------|-------------------------|
    | Date de début | Sélectionnez la date de début de la déclaration. |
    | Au | Sélectionnez la date de fin de la déclaration. |
    | Générer un fichier | Définissez cette option sur **Oui** pour générer un fichier .xml. |
    | Nom de fichier | Laissez ce champ vide. Le nom du fichier est généré automatiquement et se compose de la valeur de la balise XML **&lt;envelopeId&gt;** et de l’extension de nom de fichier **.xml**.</br>La valeur **&lt;envelopeId&gt;** est une concaténation des éléments suivants, dans cet ordre :</br><ol type="1"></br><li>La valeur de la balise **&lt;interchangeAgreementId&gt;**,</li></br><li>Un trait d’union (-)</li></br><li>La valeur de la balise **&lt;referencePeriod in YYYYMM&gt;**</li></br><li>Un trait d’union (-)</li></br><li>La valeur de la balise **&lt;Envelope/DateTime/date in YYYYMMDD&gt;**</li></br><li>Un trait d’union (-)</li></br><li>La valeur de la balise **&lt;Envelope/DateTime/time in hhmm&gt;**</li></br></ol> |
    | Direction | <ul></br><li>Sélectionnez **Arrivées** pour créer des états sur les arrivées intracommunautaires.</li></br><li>Sélectionnez **Expéditions** pour créer des états sur les envois intracommunautaires.</li></br><li>Sélectionnez **Les deux** pour créer des états sur les arrivées et les envois.</li></br></ul> |
    | Numéro d’identification fiscale | Saisissez le numéro d’immatriculation à utiliser pour générer le code d’identification de l’expéditeur, si le numéro diffère du numéro d’immatriculation fiscale de l’entité juridique. |


## <a name="example"></a>Exemple

Cet exemple montre comment valider les arrivées et les expéditions pour la déclaration d’échanges de biens. Il utilise l'entité juridique **DEMF**.

1. Dans [LCS](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations de gestion des états électroniques pour le format de déclaration d’échanges de biens :

    - Modèle de déclaration d’échanges de biens
    - État de déclaration d’échanges de biens
    - Déclaration d’échanges de biens XML
    - Déclaration d’échanges de biens XML (DE)

2. Créez les codes transactions.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Codes transaction**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans le champ **Code** **transaction**, entrez **21**.
    4. Dans le champ **Nom**, entrez **Retour de marchandises**.
    5. Dans le volet Actions, sélectionnez **Enregistrer**.

3. Configurez le numéro d’identification de l’administration.

    1. Accédez à **Taxes** > **Taxes indirectes** > **Taxe de vente** > **Administrations fiscales**.
    2. Dans la liste, sélectionnez **TA**.
    3. Dans le champ **Identification de l’administration**, entrez **123**.

4. Configurez les codes régions.

    1. Accédez à **Administration d’organisation** > **Carnet d’adresses global** > **Adresses** > **Configuration de l’adresse**.
    2. Dans l’onglet **État/province**, dans le champ **Pays/région**, sélectionnez **DEU**, puis sélectionnez **Appliquer le filtre**.
    3. Dans la grille, sélectionnez **BE**, puis, dans le champ **Code de déclaration d’échanges de biens**, entrez **11**.
    4. Dans le volet Actions, sélectionnez **Enregistrer**.

5. Configurez les paramètres de commerce extérieur.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
    2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code** **transaction**, sélectionnez **11**.
    3. Dans le champ **Avoir**, sélectionnez **21**.
    4. Dans le champ **Administration**, sélectionnez **TA**.
    5. Dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **INSTAT XML (DE)**.
    6. Dans le champ **Mappage de format d’état**, sélectionnez **Déclaration d’échanges de biens**.
    7. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, assurez-vous que **Déclaration d’échanges de biens** est sélectionné.
    8. Dans l’onglet **Propriétés de pays/région**, sélectionnez **Nouveau**.
    9. Dans le champ **Pays/région de la partie**, sélectionnez **FRA**.
    10. Dans le champ **Type de pays/région**, sélectionnez **UE**.

6. Attribuez un code marchandise à un produit et définissez l’origine du produit. Les champs **Code marchandise**, **Pays/région d’origine** et **État d’origine** seront alors automatiquement définis sur les commandes client et fournisseur lorsque vous sélectionnerez le produit.

    1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
    2. Dans la grille, sélectionnez **D0001**.
    3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **920 20 34**.
    4. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez **DEU**.
    5. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures pondérales**, dans le champ **Poids net**, entrez **12**.
    6. Dans le volet Actions, sélectionnez **Enregistrer**.

7. Affectez le transport à un mode de livraison. Le code de transport sera alors automatiquement défini sur les commandes lorsque vous sélectionnerez le mode de livraison.

    1. Accédez à **Approvisionnements** > **Paramétrage** > **Distribution** > **Modes de livraison**.
    2. Dans la liste, sélectionnez **10**.
    3. Dans le raccourci **Commerce extérieur**, dans le champ **Transport**, sélectionnez **01**.

8. Créez une commande client avec un client de l’UE.

    1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans la boîte de dialogue **Créer une commande client**, dans le raccourci **Client**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-012**.
    4. Dans le raccourci **Général**, dans la section **Dimensions de stockage**, dans le champ **Site**, sélectionnez **1**.
    5. Dans le champ **Entrepôt**, sélectionnez **11**.
    6. Cliquez sur **OK**.
    7. Dans l’onglet **En-tête**, dans le raccourci **Commerce extérieur**, dans le champ **Port**, sélectionnez **53**.
    8. Dans le champ **Procédure statistique**, sélectionnez **31710**.
    9.  Dans l’onglet **Lignes**, dans le raccourci **Lignes de** **commande client**, dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité**, entrez **10**.
    10. Dans le raccourci **Détails de ligne**, dans l’onglet **Commerce extérieur**, assurez-vous que les champs **Code transaction**, **Transport**, **Marchandise** et **Pays/région d’origine** sont automatiquement définis.
    11. Dans le volet Actions, sélectionnez **Enregistrer**.
    12. Dans le volet Actions, sous l’onglet **Facture**, dans la section **Générer**, sélectionnez **Facture**.
    13. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**.
    14. Cliquez sur **OK** pour valider la facture.

9.  Transférez la transaction dans le journal de déclaration d’échanges de biens et examinez le résultat.

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d'échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l'option **Facture client** sur **Oui**.
    4. Sélectionnez **Filtrer**.
    5. Dans la boîte de dialogue **Filtre de déclaration d’échanges de biens**, dans l’onglet **Plage**, sélectionnez la première ligne et assurez-vous que le champ **Champ** est défini sur **Date**.
    6. Dans le champ **Critères**, sélectionnez la date actuelle.
    7. Cliquez sur **OK** pour fermer la boîte de dialogue **Filtre de déclaration d’échanges de biens**.
    8. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens (Transfert)** et examinez le résultat. La ligne représente la commande client que vous avez créée précédemment.

        ![Ligne représentant la commande client sur la page de déclaration d’échanges de biens](media/intrastat_deu_1.png)

10. Sélectionnez la ligne de transaction, puis l’onglet **Général** pour afficher plus de détails.

    ![Détails de la commande client sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_deu_2.png)

11. Créez un avoir en utilisant une commande client.

    1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans la boîte de dialogue **Créer une commande client**, dans le raccourci **Client**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-012**.
    4. Dans le raccourci **Général**, dans la section **Dimensions de stockage**, dans le champ **Site**, sélectionnez **1**.
    5. Dans le champ **Entrepôt**, sélectionnez **11**.
    6. Dans l’onglet **En-tête**, dans le raccourci **Commerce extérieur**, dans le champ **Port**, sélectionnez **53**.
    7. Dans le champ **Procédure statistique**, sélectionnez **31710**.
    8. Dans l’onglet **Lignes**, dans le raccourci **Lignes de** **commande client**, dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité**, entrez **-2**.
    9. Dans le raccourci **Détails de la ligne**, dans l’onglet **Commerce extérieur**, dans le champ **Code transaction**, sélectionnez **21**.
    10. Assurez-vous que les champs **Transport**, **Marchandise** et **Pays/région d’origine** sont automatiquement définis.
    11. Dans le volet Actions, sélectionnez **Enregistrer**.
    12. Dans le volet Actions, sous l’onglet **Facture**, dans la section **Générer**, sélectionnez **Facture**.
    13. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**.
    14. Cliquez sur **OK** pour valider la facture.

12. Transférez la transaction dans le journal de déclaration d’échanges de biens et examinez le résultat.

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d'échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l'option **Facture client** sur **Oui**.
    4. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens (Transfert)** et examinez le résultat. Une nouvelle ligne où le champ **Direction** est défini sur **Arrivées** a été ajoutée.            
        Cette ligne représente le retour physique des marchandises.

        ![Ligne pour le retour physique des marchandises sur la page de déclaration d’échanges de biens](media/intrastat_deu_3.png)

13. Sélectionnez la ligne de transaction, puis l’onglet **Général** pour afficher plus de détails.

    ![Détails du retour physique des marchandises sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_deu_4.png)

14. Créez une correction en utilisant une commande client :

    1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans la boîte de dialogue **Créer une commande client**, dans le raccourci **Client**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-012**.
    4. Dans le raccourci **Général**, dans la section **Dimensions de stockage**, dans le champ **Site**, sélectionnez **1**.
    5. Dans le champ **Entrepôt**, sélectionnez **11**.
    6. Dans l’onglet **En-tête**, dans le raccourci **Commerce extérieur**, dans le champ **Port**, sélectionnez **53**.
    7. Dans le champ **Procédure statistique**, sélectionnez **31710**.
    8. Dans l’onglet **Lignes**, dans le raccourci **Lignes de** **commande client**, dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité**, entrez **-3**.
    9. Dans le raccourci **Détails de la ligne**, dans l’onglet **Commerce extérieur**, dans le champ **Code transaction**, sélectionnez **11**.
    10. Assurez-vous que les champs **Transport**, **Marchandise** et **Pays/région d’origine** sont automatiquement définis.
    11. Dans le volet Actions, sélectionnez **Enregistrer**.
    12. Veillez à ce que le champ **Code transaction** soit défini sur 11.
    13. Dans le volet Actions, sous l’onglet **Facture**, dans la section **Générer**, sélectionnez **Facture**.
    14. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**.
    15. Cliquez sur **OK** pour valider la facture.

15. Transférez la transaction dans le journal de déclaration d’échanges de biens et examinez le résultat :

    1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
    2. Dans le volet Actions, sélectionnez **Transférer**.
    3. Dans la boîte de dialogue **Déclaration d'échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l'option **Facture client** sur **Oui**.
    4. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens (Transfert)** et examinez le résultat. Une nouvelle ligne où une coche apparaît dans la colonne **Correction** a été ajoutée.

        ![Ligne pour la correction sur la page de déclaration d’échanges de biens](media/intrastat_deu_5.png)

16. Sélectionnez la ligne de transaction, puis l’onglet **Général** pour afficher plus de détails.

    ![Détails de la correction sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_deu_6.png)

17. Dans le volet Actions, sélectionnez **Résultat** > **État**.
18. Dans la boîte de dialogue **Déclaration d'échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, sélectionnez le mois de la commande client que vous avez créée.
19. Dans la section **Options** **d’exportation**, définissez l’option **Générer un fichier** sur **Oui**.
20. Dans le champ **Nom du fichier**, entrez le nom requis.
21. Cliquez sur **OK** et examinez l’état généré. Le tableau suivant indique les valeurs dans l’exemple d’état.

    | **Nom**                  | **Facture client**  |   **Correction**   | **Avoir** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | D                  | A                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Speaker            | Speaker            | Speaker         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

