---
title: Déclaration d’échanges de biens (Pologne)
description: Cet article contient des informations sur la Déclaration d’échanges de biens en Pologne.
author: andosip
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: ''
ms.openlocfilehash: 45bd1d3c90d0a8a8ad5db6d0b80c5eed0aa489e8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871099"
---
# <a name="polish-intrastat"></a>Déclaration d’échanges de biens (Pologne)

[!include[banner](../includes/banner.md)]

La page **Déclaration d’échanges de biens** sert à générer et rapporter des informations sur le commerce entre pays/régions de l’Union européenne. La déclaration d’échanges de biens polonaise contient des informations sur le commerce de biens à déclarer.

Les champs suivants sont inclus dans la déclaration d’échanges de biens polonaise. Tous les champs sont inclus sur les arrivées et les expéditions sauf pour **RodzajTransportu** (le mode de transport) et **KrajPochodzenia** (le pays ou la région d’origine) qui ne figurent pas sur les envois, et **IdKontrahenta** (le numéro de TVA étrangère du client) qui n’est pas inclus à l’arrivée.

| Nom du champ | Description |
|-------------------------|-------------------------|
| Données de Deklaracja | Date de création du document. |
| Miesiac | Mois de référence de la déclaration. |
| Rok | Année de référence de la déclaration. |
| Numer | Numéro de déclaration dans la période de référence. |
| Wersja | Numéro de version de la déclaration. |
| NrWlasny | Identificateur de la déclaration. La valeur est générée automatiquement. |
| Typ | Direction de la déclaration.</br><li>Pour les arrivées, « P » est imprimé.</li><li>Pour les expéditions, « W » est imprimé.</li> |
| Rodzaj | Type de déclaration. La valeur indique si le rapport est la déclaration d’origine ou une déclaration de correction. |
| UC | Code unité auquel la déclaration d’échanges de biens est adressée. La valeur est indiquée dans le champ **Numéro d’exonération fiscale** dans la section **Taxe de vente** sur l’onglet **Agent** de la page **Paramètres du commerce extérieur**. |
| Nazwa | Nom de la société. |
| Miejscowosc, UlicaNumer, KodPocztowy | Adresse complète de l’entité juridique. |
| Nip | Le numéro d’identification fiscale polonais (ID de taxe sur la valeur ajoutée [TVA]). |
| Regon | Numéro d’identification statistique polonais (numéro d’entreprise). |
| LacznaWartoscFaktur | Somme des valeurs de la facture. |
| LacznaWartoscStatystyczna | Somme des valeurs statistiques. |
| LacznaLiczbaPozycji | Nombre total d’articles de marchandises. |
| PozId | Numéro consécutif d’un article de marchandise donné. |
| Opis Towaru | Nom commercial de la marchandise. |
| KrajPochodzeniaWysylki | Code pour le pays ou la région de la contrepartie de l’Organisation internationale de normalisation (ISO). |
| WarunkiDostawy | Code de déclaration d’échanges de biens pour les conditions de livraison. |
| RodzajTransakcji | Code qui indique la nature de la transaction. Les entreprises polonaises utilisent des codes de transaction à deux chiffres. |
| KodTowarowy | Code de marchandise à huit chiffres selon la nomenclature combinée. |
| RodzajTransportu | Code de déclaration d’échanges de biens pour le mode de transport. |
| KrajPochodzenia | Code ISO du pays ou de la région où les marchandises ont été produites ou fabriquées. |
| MasaNetto | Masse nette en kilogrammes complets. |
| IloscUzupelniajacaJm | Quantité dans l’unité supplémentaire, en nombres entiers. |
| WartoscFaktury | Valeur de la facture de toutes les transactions couvertes par un article. |
| WartoscStatystyczna | Valeur statistique. |
| Wypelniajacy: NazwiskoImie, Telefon, Faks, Email | Le nom, le prénom, le numéro de téléphone, le numéro de télécopie et l’adresse e-mail de la personne qui soumet la déclaration. |
| IdKontrahenta | Le numéro de TVA étrangère du client dans un État membre de l’UE. |


## <a name="set-up-intrastat"></a>Configuration de la Déclaration d’échanges de biens

Depuis le référentiel global, importez les dernières versions des configurations de rapports électroniques (ER) :

   - Modèle de déclaration d’échanges de biens
   - État de déclaration d’échanges de biens
   - Déclaration d’échanges de biens (PL)

Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configurer un numéro de TVA et un numéro d’entreprise pour votre entreprise

### <a name="create-registration-types-for-company-codes"></a>Créer des types d’enregistrement pour les codes d’entreprise

Vous devez créer deux types d’enregistrement pour les sociétés : un pour le numéro de TVA (Code PIN) et un pour le numéro d’entreprise (code Regon).

1. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Types d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’enregistrement pour le n° de TVA.
3. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, entrez un nom pour le nouveau type d’enregistrement. Par exemple, entrez **PIN**.
4. Dans le champ **Pays/région**, sélectionnez **POL**.
5. Cliquez sur **Créer**.
6. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’enregistrement pour le numéro d’entreprise.
7. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, entrez un nom pour le nouveau type d’enregistrement. Entrez **Regon**, par exemple.
8. Dans le champ **Pays/région**, sélectionnez **POL**.
9. Cliquez sur **Créer**.

### <a name="match-the-registration-types-with-registration-categories"></a>Faire correspondre les types d’enregistrement avec les catégories d’enregistrement

1. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Catégories d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un lien entre chaque type d’inscription que vous avez créé et une catégorie d’inscription.

    - Pour le type d’enregistrement pour le numéro de TVA (code NIP), sélectionnez la catégorie d’enregistrement **Numéro de TVA**.
    - Pour le type d’enregistrement pour le numéro d’entreprise (code Regon), sélectionnez la catégorie d’enregistrement **ID entreprise (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configurer un numéro de TVA et un numéro d’entreprise pour votre entreprise

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Dans la grille, sélectionnez votre entreprise.
3. Dans le volet Actions, sélectionnez **ID d’enregistrement**.
4. Dans le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
5. Dans le champ **Type d’enregistrement**, sélectionnez l’un des types d’enregistrement créés précédemment.
6. Saisissez le numéro de TVA (code NIP) ou le numéro d’entreprise (code Regon) de votre entreprise, selon le type d’enregistrement que vous avez sélectionné à l’étape précédente.
7. Répétez les étapes 4 à 6 pour l’autre type d’enregistrement que vous avez créé précédemment.

## <a name="set-up-a-company-address"></a>Configurer une adresse de l’entreprise

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Dans la grille, sélectionnez votre entreprise.
3. Dans l’onglet **Adresses**, sélectionnez **Modifier**.
4. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Code postal**, sélectionnez le code postal de votre entreprise.
5. Dans le champ **Rue**, saisissez votre adresse.
6. Dans le champ **Ville**, sélectionnez votre ville.

## <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Accédez à **Taxes** > **Paramétrage** > **Paramètres de commerce extérieur**.
2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **Déclaration d’échanges de biens (PL)**.
3. Dans le champ **Mappage de format d’état**, sélectionnez **Déclaration d’échanges de biens**.
4. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d’échanges de biens**.
5. Dans le champ **Code transaction** sélectionnez le code transaction pour les transferts de propriété. Vous pouvez utiliser ce code pour les transactions qui génèrent des transferts de propriété réels ou prévus contre compensation (financière ou autre). Vous l’utilisez également pour les corrections. Les entreprises de Pologne utilisent des codes de transaction à deux chiffres.
6. Dans le champ **Avoir**, sélectionnez le code transaction pour le retour des marchandises.
7. Dans l’onglet **Propriétés de pays/région**, dans le champ **Pays/région**, répertoriez tous les pays ou régions avec lesquels votre société fait affaire. Pour chaque pays de l’UE, dans le champ **Type de pays/région**, sélectionnez **UE**, afin que le pays apparaisse sur votre déclaration d’échanges de biens. Pour la Pologne, sélectionnez **Local** dans le champ **Type de pays/région**.
8. Sur l’onglet **Agent**, sur le raccourci **Agent**, dans la section **Taxe de vente**, dans le champ **Numéro d’exonération fiscale**, entrez **420000** pour indiquer le code unité auquel la déclaration d’échanges de biens est adressée.
9. Sur l’onglet **Contact**, entrez le nom, le numéro de téléphone, le numéro de télécopie et l’adresse e-mail de la personne qui soumet la déclaration.
10. Sur l’onglet **Souches de numéros**, dans le champ **Code de souche de numéros** de la référence **Numéro de fichier XML**, spécifiez une souche de numéros non continue avec un maximum de neuf caractères. Ce champ est utilisé pour générer automatiquement une valeur pour le champ **Identificateur de déclaration** sur le rapport de déclaration d’échanges de biens.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Paramétrer les paramètres du produit pour la déclaration d’échanges de biens

1. Accédez à **Gestion des informations sur les produits** > **Produits** > **Produits lancés**.
2. Sélectionnez un produit dans la grille.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez le code de marchandise. Le nom de la marchandise sera imprimé dans le champ **Description des marchandises** sur le rapport de déclaration d’échanges de biens.
4. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez le pays ou la région d’origine du produit.
5. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures nettes**, saisissez le poids du produit en kilogrammes.

## <a name="set-up-compression-of-intrastat"></a>Paramétrer la compression de la déclaration d’échanges de biens

-   Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Compression de déclaration d’échanges de biens**, puis sélectionnez les champs qui doivent être comparés lors de la synthèse des informations de la déclaration d’échanges de biens. Pour la déclaration d’échanges de biens polonaise, sélectionnez les champs suivants :

    - Marchandise
    - Code transaction
    - Pays/région d’origine
    - Transport
    - Conditions de livraison
    - Pays/région de l’expéditeur
    - Pays/Région
    - Correction
    - Numéro identifiant TVA
    - Direction
    - Facture

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Paramétrer le mode de transport et les conditions de livraison

1.  Paramétrer des codes de transport.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Mode de transport**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans le champ **Transport**, entrez un code unique. Les entreprises polonaises utilisent des codes de transport à un chiffre.

2.  Paramétrer le mode de livraison des codes de déclaration d’échanges de biens.

    1. Accédez à **Approvisionnements** > **Paramétrage** > **Distribution** > **Conditions de livraison**.
    2. Dans la grille, sélectionnez un ensemble de conditions de livraison.
    3. Dans le raccourci **Général**, dans le champ **Code de déclaration d’échanges de biens**, saisissez le code unique.

## <a name="intrastat-transfer"></a>Transfert des déclarations d’échanges de biens

Sur la page **Déclaration d’échanges de biens**, dans le volet Actions, vous pouvez sélectionner **Transférer** pour transférer automatiquement les informations sur le commerce intracommunautaire à partir de vos commandes clients, de vos factures financières, des commandes fournisseur, des factures fournisseurs, des accusés de réception de produits fournisseurs, des factures de projet et des ordres de transfert. Seuls les documents ayant un pays de l’UE comme pays ou région de destination ou de consignation seront transférés.

Vous pouvez également saisir manuellement des transactions en cliquant sur **Nouveau** dans le volet Actions.

### <a name="generate-an-intrastat-report"></a>Génération d’une déclaration d’échanges de biens

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Résultat** &gt; **Rapport**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens**, définissez les champs suivants :

    | Champ | Description |
    |-------------------------|-------------------------|
    | Date de début | Sélectionnez la date de début de la déclaration. |
    | Générer un fichier | Définissez cette option sur **Oui** pour générer un fichier .xml pour votre rapport de déclaration d’échanges de biens. |
    | Nom de fichier | Entrez le nom du fichier .xml. |
    | Générer un rapport | Définissez cette option sur **Oui** pour générer un fichier .xlsx pour votre rapport de déclaration d’échanges de biens. |
    | Nom du fichier d’état | Entrez le nom du fichier .xlsx. |
    | Direction | Sélectionnez **Arrivées** pour un rapport sur les arrivées intracommunautaires.</br>Sélectionnez **Expéditions** pour un rapport sur les envois intracommunautaires. |
    | Identificateur de la déclaration | L’ID du document est généré automatiquement et peut être mis à jour. |
    | Type de déclaration | Sélectionnez **Déclaration** pour une déclaration originale.</br>Sélectionnez **Correction de déclaration – remplacement** pour une déclaration rectificative destinée à remplacer intégralement une déclaration d’origine ou rectificative existante déjà soumise. |
    | Ville de création du document | Entrez la valeur qui doit être imprimée dans le champ **Miejscowosc** dans la déclaration d’échanges de biens. |
    | Date de création du document | Entrez la valeur qui doit être imprimée dans le champ **Deklaracja Data** dans la déclaration d’échanges de biens. |
    | N° de document | Entrez la valeur qui doit être imprimée dans le champ **Numer** dans la déclaration d’échanges de biens. |
    | Version du document | Entrez la valeur qui doit être imprimée dans le champ **Wersja** dans la déclaration d’échanges de biens. |

4. Cliquez sur **OK** et examinez les états générés.

## <a name="example"></a>Exemple

Cet exemple montre comment valider les arrivées et les expéditions pour la déclaration d’échanges de biens à l’aide de l’entité juridique **DEMF**.

### <a name="preliminary-setup"></a>Paramétrage préliminaire

Importer la dernière version des configurations de génération d’états électroniques (ER) :

   - Modèle de déclaration d’échanges de biens
   - État de déclaration d’échanges de biens
   - Déclaration d’échanges de biens (PL)

### <a name="set-up-a-company-address"></a>Configurer une adresse de l’entreprise

1. Accédez à **Administration d’organisation** > **Carnet d’adresses global** > **Adresses** > **Configuration de l’adresse**.
2. Dans l’onglet **Ville**, sélectionnez **Nouveau**.
3. Dans le champ **Pays/région**, sélectionnez **POL**.
4. Dans le champ **Ville**, entrez **Varsovie**.
5. Sur l’onglet **Code postal**, sélectionnez **Nouveau**.
6. Dans le champ **Pays/région**, sélectionnez **POL**.
7. Dans le champ **Ville**, sélectionnez **Varsovie**.
8. Dans le champ **Code postal**, entrez **00-844**.
9. Allez dans **Administration d’organisation** > **Organisation** > **Entités juridiques**, puis sélectionnez l’entité juridique **DEMF**.
10. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
11. Dans le champ **Pays/région**, sélectionnez **POL**.
12. Dans le champ **Code postal**, sélectionnez **31-111**.
13. Dans le champ **Rue**, saisissez **Statystyczna 22/1**.
14. Dans le champ **Ville**, sélectionnez **Varsovie**.
15. Cliquez sur **OK**.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Configurer un numéro de TVA et un code de numéro d’entreprise pour votre entreprise

### <a name="create-registration-types-for-company-codes"></a>Créer des types d’enregistrement pour les codes d’entreprise

1. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Types d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’enregistrement pour le n° de TVA (code PIN).
3. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, saisissez **PIN**.
4. Dans le champ **Pays/région**, sélectionnez **POL**.
5. Cliquez sur **Créer**.
6. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’enregistrement pour le numéro d’entreprise (code Région).
7. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, saisissez **Région**.
8. Dans le champ **Pays/région**, sélectionnez **POL**.
9. Cliquez sur **Créer**.

### <a name="match-the-registration-types-with-registration-categories"></a>Faire correspondre les types d’enregistrement avec les catégories d’enregistrement

1. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Catégories d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un lien entre chaque type d’inscription que vous avez créé et une catégorie d’inscription.

    - Pour le type d’enregistrement **NIP**, sélectionnez la catégorie d’enregistrement **Numéro de TVA**.
    - Pour le type d’enregistrement **Regon**, sélectionnez la catégorie d’enregistrement **ID entreprise (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configurer un numéro de TVA et un numéro d’entreprise pour votre entreprise

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Dans la grille, sélectionnez **DEMF**.
3. Dans le volet Actions, sélectionnez **ID d’enregistrement**.
4. Dans le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
5. Dans le champ **Type d’enregistrement**, sélectionnez **NIP**.
6. Dans le champ **Numéro d’enregistrement**, entrez **1234567890**.
7. Sélectionnez **Ajouter**.
8. Dans le champ **Type d’enregistrement**, sélectionnez **Regon**.
9. Dans le champ **Numéro d’enregistrement**, entrez **12345678901234**.

### <a name="set-up-a-number-sequence-code"></a>Paramétrez un code de souche de numéros

1. Accédez à **Administration d’organisation** > **Séquences de nombres** > **Séquences de nombres**.
2. Dans le volet Actions, sous l’onglet **Souche de numéros**, dans le groupe **Nouveau**, sélectionnez **Souche de numéros**.
3. Sur le raccourci **Identification**, dans le champ **Code de souche de numéros**, sélectionnez **XML\_fichier**.
4. Sur le raccourci **Paramètres de portée**, dans le champ **Portée**, sélectionnez **Entreprise**.
5. Dans le champ **Entreprise**, sélectionnez **DEMF**.
6. Sur le raccourci **Segments**, dans le champ **Longueur** pour le segment **Alphanumérique**, entrez **4**.
7. Sous le raccourci **Général**, dans la section **Configuration**, définissez l’option **Continue** sur **Non**.
8. Dans la section **Attribution des numéros**, dans le champ **Maximum**, entrez **9999**.

### <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Paramètres de commerce extérieur**.
2. Dans l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code** **transaction**, sélectionnez **11**.
3. Dans le raccourci **Gestion des états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **Déclaration d’échanges de biens (PL)**.
4. Dans le champ **Mappage de format d’état**, sélectionnez **Déclaration d’échanges de biens**.
5. Dans le raccourci **Hiérarchie des codes marchandise**, vérifiez que le champ **Hiérarchie des catégories** est défini sur **Déclaration d’échanges de biens**.
6. Dans l’onglet **Propriétés de pays/région**, sélectionnez **Nouveau**.
7. Dans le champ **Pays/région de la partie**, sélectionnez **POL**. Ensuite, dans le champ **Type de pays/région**, sélectionnez **Local**.
8. Dans le champ **Pays/région de la partie**, sélectionnez **DEU**. Ensuite, dans le champ **Type de pays/région**, sélectionnez **UE**.
9. Sur l’onglet **Agent**, sur le raccourci **Agent**, dans la section **Taxe de vente**, dans le champ **Numéro d’exonération fiscale**, entrez **420000**.
10. Sur l’onglet **Contact**, dans le champ **Nom**, saisissez **Manish Chopra**.
11. Dans le champ **Téléphone**, entrez **425-555-5068**.
12. Dans le champ **Numéro de télécopie**, entrez **425-555-5049**.
13. Dans le champ **Adresse e-mail**, entrez **manishc@contoso.com**.
14. Sur l’onglet **Souches de numéros**, dans le champ **Code de souche de numéros** pour la référence **Numéro de fichier XML**, sélectionnez **XML\_fichier**.

### <a name="set-up-product-information"></a>Configurer les informations sur le produit

1. Allez à **Gestion des informations sur les produits** > **Produits** > **Produits** **lancés**.
2. Dans la grille, sélectionnez **D0001**.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **100 200 30**.
4. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures pondérales**, dans le champ **Poids net**, entrez **2**.
5. Dans le volet Actions, sélectionnez **Enregistrer**.
6. Dans la grille, sélectionnez **D0003**.
7. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **100 200 30**.
8. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez **DEU**.
9. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures pondérales**, dans le champ **Poids net**, entrez **5**.
10. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="change-the-site-address"></a>Changer l’adresse du site

1. Accédez à **Gestion des entrepôts** > **Paramétrage** > **Entrepôt** > **Sites**.
2. Dans la grille, sélectionnez **1**.
3. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
4. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **POL**.
5. Cliquez sur **OK**.

### <a name="set-up-a-transport-method"></a>Paramétrer un mode de transport

1. Créer un mode de transport.

    1. Accédez à **Taxes** > **Paramétrage** > **Commerce extérieur** > **Mode de transport**.
    2. Dans le volet Actions, sélectionnez **Nouveau**.
    3. Dans le champ **Transport**, entrez **3**.
    4. Dans le champ **Description**, entrez **Transport routier**.

2. Affectez le nouveau mode de transport à un mode de livraison. De cette façon, vous configurez les valeurs par défaut qui sont utilisées pour le mode de transport lorsque le mode de livraison correspondant est sélectionné.

    1. Accédez à **Approvisionnements** > **Paramétrage** > **Distribution** > **Modes de livraison**.
    2. Dans la grille, sélectionnez **10**.
    3. Dans le raccourci **Commerce extérieur**, dans le champ **Transport**, sélectionnez **3**.

3. Sélectionnez le mode de livraison par défaut pour un client.

    1. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**.
    2. Dans la grille, sélectionnez **DE-016**.
    3. Dans le raccourci **Facturation et livraison**, dans le champ **Mode de livraison**, sélectionnez **10**.

4. Sélectionnez le mode de livraison par défaut pour un fournisseur.

    1. Accédez à **Comptabilité fournisseur** > **Fournisseurs** > **Tous les fournisseurs**.
    2. Dans la grille, sélectionnez **DE-001**.
    3. Dans le raccourci **Facturation et livraison**, dans le champ **Mode de livraison**, sélectionnez **10**.

### <a name="set-up-codes-for-terms-of-delivery"></a>Paramétrez les codes des conditions de livraison

1. Paramétrez un code de déclaration d’échanges de biens pour les conditions de livraison.

    1. Accédez à **Approvisionnements** > **Paramétrage** > **Distribution** > **Conditions de livraison**.
    2. Dans la grille, sélectionnez **CIF**.
    3. Dans le raccourci **Général**, dans le champ **Code de déclaration d’échanges de biens**, saisissez **CIF**.

2. Sélectionnez les conditions de livraison par défaut pour un client.

    1. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**.
    2. Dans la grille, sélectionnez **DE-016**.
    3. Dans le raccourci **Facturation et livraison**, dans le champ **Conditions de livraison**, sélectionnez **CIF**.

3. Sélectionnez les conditions de livraison par défaut pour un fournisseur.

    1. Accédez à **Comptabilité fournisseur** > **Fournisseurs** > **Tous les fournisseurs**.
    2. Dans la grille, sélectionnez **DE-001**.
    3. Dans le raccourci **Facturation et livraison**, dans le champ **Conditions de livraison**, sélectionnez **CIF**.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Vérifier le code de numéro d’exonération fiscale d’un client de l’UE

1. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**.
2. Dans la grille, sélectionnez **DE-016**.
3. Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, vérifiez que le champ **Numéro d’exonération fiscale** est défini sur **DE9012**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Créer une commande client avec un client de l’UE

1. Accédez à **Comptabilité client** > **Commandes** > **Toutes les commandes client**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande client**, dans le raccourci **Client**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-016**.
4. Dans le raccourci **Général**, dans la section **Dimensions de stockage**, dans le champ **Site**, sélectionnez **1**.
5. Dans le champ **Entrepôt**, sélectionnez **11**.
6. Sur l’onglet **Adresse**, vérifiez que le champ **Adresse** est défini sur **Teichgasse 12, Kiel, 24103, DEU**, car le client vient d’Allemagne.
7. Cliquez sur **OK**.
8. Sur l’onglet **En-tête**, sur le raccourci **Livraison**, vérifiez que le champ **Conditions de livraison** est défini sur **CIF** et le champ **Mode de livraison** sur **10**.
9. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande client**, dans le champ **Numéro d’article**, sélectionnez **D0001**. Ensuite, dans le champ **Quantité**, entrez **8**.
10. Sur le raccourci **Détails de la ligne**, sur l’onglet **Commerce extérieur**, vérifiez que le champ **Code de transaction** est défini sur **11**, que le champ **Marchandises** est défini sur **100 200 30**, et que le champ **Pays/région d’origine** est défini sur **POL**.
11. Dans le volet Actions, sélectionnez **Enregistrer**.
12. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
13. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**.
14. Dans le raccourci **Configuration**, dans le champ **Date de vente**, sélectionnez **18/10/2021** (18 octobre 2021).
15. Cliquez sur **OK** pour valider la facture.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transférer la transaction dans le journal de déclaration d’échanges de biens et examiner le résultat

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l’option **Facture client** sur **Oui**.
4. Sélectionnez **Filtrer**.
5. Dans la boîte de dialogue **Filtre de déclaration d’échanges de biens**, dans l’onglet **Plage**, sélectionnez la première ligne et vérifiez que le champ **Champ** est défini sur **Date**.
6. Dans le champ **Critères**, sélectionnez la date actuelle.
7. Cliquez sur **OK** pour fermer la boîte de dialogue **Filtre de déclaration d’échanges de biens**.
8. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens (Transfert)** et examinez le résultat. La ligne représente la commande client que vous avez créée précédemment.

    ![Ligne représentant la commande client sur la page de déclaration d’échanges de biens](media/intrastat_pl_1.png)

9. Sélectionnez la ligne de transaction, puis l’onglet **Général** pour afficher plus de détails.

    ![Détails de la commande client sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_pl_2.png)

10. Dans le volet Actions, sélectionnez **Résultat** > **État**.
11. Dans la boîte de dialogue **Déclaration d’échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, dans le champ **Date de début**, sélectionnez le premier jour du mois actuel.
12. Dans la section **Options** **d’exportation**, définissez l’option **Générer un fichier** sur **Oui**. Puis, dans le champ **Nom du fichier**, entrez le nom requis.
13. Définissez l’option **Générer un état** sur **Oui**. Puis, dans le champ **Nom du fichier d’état**, entrez le nom requis.
14. Dans le champ **Direction**, sélectionnez **Répartitions**.
15. Dans la section **Mappage de format de fichier**, vérifiez que le champ **Type de déclaration** est défini sur **Déclaration**.
16. Dans le champ **Ville de création du document**, entrez **Cracovie**.
17. Dans le champ **Date de création du document**, sélectionnez **10/19/2021** (19 octobre 2021).
18. Dans le champ **Numéro de document**, entrez **11**.
19. Dans le champ **Version du document**, entrez **22**.
20. Cliquez sur **OK** et examinez l’état généré au format XML. Le tableau suivant indique les valeurs dans l’exemple d’état.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nom de champ</strong></p>
    </td>
    <td>
    <p><strong>Description du champ</strong></p>
    </td>
    <td>
    <p><strong>Valeur</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informations sur le document</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Données de Deklaracja</p>
    </td>
    <td>
    <p>Date de création du document.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Ville de création du document.</p>
    </td>
    <td>
    <p>Cracovie</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Nombre total d’articles.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Valeur statistique totale.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Valeur totale de la facture.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Code unitaire.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Type de déclaration.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Version du document.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>Numéro du document.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>Mois de référence.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>Année de référence.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>Direction de la déclaration.</p>
    </td>
    <td>
    <p>W</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>Identificateur de la déclaration.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informations sur la société</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>Ville dans laquelle la société se trouve.</p>
    </td>
    <td>
    <p>Varsovie</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>Code Regon de la société.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Pin</p>
    </td>
    <td>
    <p>Code PIN de l’entreprise.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Code postal de la société.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Rue dans laquelle la société se trouve.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Nom de la société.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informations sur la marchandise</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Valeur statistique.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Valeur de la facture.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Masse nette.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>Numéro de TVA du client.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Code marchandise.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Code transaction.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Conditions du mode de livraison.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Code du pays ou de la région d’expédition/destination.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Opis Towaru</p>
    </td>
    <td>
    <p>Description des marchandises.</p>
    </td>
    <td>
    <p>Matériel</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Numéro d’article.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informations sur le contact</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>E-mail</p>
    </td>
    <td>
    <p>Adresse e-mail de l’expéditeur.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Numéro de télécopie de l’expéditeur.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Numéro de téléphone de l’expéditeur.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Nom de l’expéditeur.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Examinez le fichier généré dans le format Excel.

    ![Rapport de déclaration d’échanges de biens pour les expéditions](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Créer une commande fournisseur

1. Accédez à **Comptabilité fournisseur** > **Commandes fournisseur** > **Toutes les commandes fournisseur**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande fournisseur**, dans le champ **Compte fournisseur**, sélectionnez **DE-001**.
4. Dans le champ **Site**, sélectionnez **1**.
5. Dans le champ **Entrepôt**, sélectionnez **11**.
6. Cliquez sur **OK**.
7. Sur l’onglet **En-tête**, sur le raccourci **Livraison**, vérifiez que le champ **Mode de livraison** est défini sur **10** et que le champ **Conditions de livraison** est défini sur **CIF**.
8. Dans l’onglet **Lignes**, dans le raccourci **Lignes de commande fournisseur**, dans le champ **Numéro d’article**, sélectionnez **D0003**. Ensuite, dans le champ **Quantité**, entrez **6**.
9. Sur le raccourci **Détails de la ligne**, sur l’onglet **Commerce extérieur**, vérifiez que le champ **Code de transaction** est défini sur **11**, que le champ **Transport** est défini sur **3**, que le champ **Marchandises** est défini sur **100 200 30**, et que le champ **Pays/région d’origine** est défini sur **DEU**.
10. Dans le volet Actions, sous l’onglet **Achats**, dans le groupe **Actions**, cliquez sur **Confirmer**.
11. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
12. Sur le volet Action, sélectionnez **Par défaut**, puis dans le champ **Quantité par défaut pour les lignes**, sélectionnez **Quantité commandée**. Puis sélectionnez **OK**.
13. Sur le raccourci **En-tête de facture fournisseur**, dans la section **Identification de la facture**, dans le champ **Numéro**, entrez **00010**.
14. Dans la rubrique **Dates de facturation**, dans le champ **Date de la facture**, sélectionnez la date actuelle. Cette date sera utilisée pour le virement de la déclaration d’échanges de biens.
15. Dans le champ **Date de réception du document**, sélectionnez **10/18/2021** (18 octobre 2021).
16. Dans le volet Actions, sélectionnez **Valider** pour valider la facture.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Créer une déclaration d’échanges de biens pour les arrivées

1. Accédez à **Taxes** > **Déclarations** > **Commerce extérieur** > **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, définissez l’option **Facture fournisseur** sur **Oui**.
4. Sélectionnez **OK** pour transférer les transactions et examinez le journal de déclaration d’échanges de biens.

    ![Ligne représentant la commande fournisseur sur la page de déclaration d’échanges de biens](media/intrastat_pl_4.png)

5. Passez en revue les informations sur l’onglet **Général** pour la commande fournisseur.

    ![Détails de la commande fournisseur sur l’onglet Général de la page de déclaration d’échanges de biens](media/intrastat_pl_5.png)

6. Dans le volet Actions, sélectionnez **Résultat** > **État**.
7. Dans la boîte de dialogue **Déclaration d’échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, dans le champ **Date de début**, sélectionnez le premier jour du mois actuel.
8. Dans la section **Options** **d’exportation**, définissez l’option **Générer un fichier** sur **Oui**. Puis, dans le champ **Nom du fichier**, entrez le nom requis.
9. Définissez l’option **Générer un état** sur **Oui**. Puis, dans le champ **Nom du fichier d’état**, entrez le nom requis.
10. Dans le champ **Direction**, sélectionnez **Arrivées**.
11. Dans la section **Mappage de format de fichier**, vérifiez que le champ **Type de déclaration** est défini sur **Déclaration**.
12. Dans le champ **Ville de création du document**, entrez **Cracovie**.
13. Dans le champ **Date de création du document**, sélectionnez **10/19/2021** (19 octobre 2021).
14. Dans le champ **Numéro de document**, entrez **11**.
15. Dans le champ **Version du document**, entrez **22**.
16. Cliquez sur **OK** et examinez l’état généré au format XML. Le tableau suivant indique les valeurs dans l’exemple d’état.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nom de champ</strong></p>
    </td>
    <td>
    <p><strong>Description du champ</strong></p>
    </td>
    <td>
    <p><strong>Valeur</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informations sur le document</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Données de Deklaracja</p>
    </td>
    <td>
    <p>Date de création du document.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>Ville de création du document.</p>
    </td>
    <td>
    <p>Cracovie</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>Nombre total d’articles.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>Valeur statistique totale.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>Valeur totale de la facture.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Code unitaire.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>Type de déclaration.</p>
    </td>
    <td>
    <p>D</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>Version du document.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>Numéro du document.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>Mois de référence.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>Année de référence.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>Direction de la déclaration.</p>
    </td>
    <td>
    <p>P</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>Identificateur de la déclaration.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informations sur la société</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>Ville dans laquelle la société se trouve.</p>
    </td>
    <td>
    <p>Varsovie</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>Code Regon de la société.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Pin</p>
    </td>
    <td>
    <p>Code PIN de l’entreprise.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>Code postal de la société.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>Rue dans laquelle la société se trouve.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>Nom de la société.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informations sur la marchandise</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>Valeur statistique.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>Valeur de la facture.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>Masse nette.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>Code du pays ou de la région d’origine.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>Code du mode de transport.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>Code marchandise.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>Code transaction.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>Conditions du mode de livraison.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>Code du pays ou de la région d’expédition/destination.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Opis Towaru</p>
    </td>
    <td>
    <p>Description des marchandises.</p>
    </td>
    <td>
    <p>Matériel</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>Numéro d’article.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p align=center><strong>Informations sur le contact</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>E-mail</p>
    </td>
    <td>
    <p>Adresse e-mail de l’expéditeur.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>Numéro de télécopie de l’expéditeur.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>Numéro de téléphone de l’expéditeur.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>Nom de l’expéditeur.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Examinez le fichier généré dans le format Excel.

    ![Rapport de déclaration d’échanges de biens des arrivées](media/intrastat_pl_6.png)
