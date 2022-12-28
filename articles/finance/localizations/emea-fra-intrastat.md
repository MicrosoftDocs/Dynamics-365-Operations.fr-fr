---
title: Déclaration d’échanges de biens (France)
description: Cet article contient des informations sur la Déclaration d’échanges de biens en France.
author: anasyash
ms.date: 11/30/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 2076649c7fff9f47b9c1fda62a103168b19bb973
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831803"
---
# <a name="french-intrastat"></a>Déclaration d’échanges de biens française

[!include[banner](../includes/banner.md)]

Les entreprises en France qui sont immatriculées pour la taxe sur la valeur ajoutée (TVA) et qui commercent avec d’autres pays de l’Union européenne (UE), doivent déclarer l’échange de biens et de services en provenance et à destination de la France. La DEB (Déclaration d’échanges de Biens) est une combinaison de la déclaration de la liste des ventes intracommunautaires (ESL) et de la déclaration d’échanges de biens. Vous devez remettre cette déclaration mensuellement pour toutes les ventes intracommunautaires de biens.

Vous pouvez générer l’état DEB dans l’un des deux formats de fichier texte électronique : SAISUNIC 330 ou INTRACOM.

Le tableau suivant présente les champs inclus dans la déclaration d’échange de biens française au format SAISUNIC 330. La table indique également les niveaux d’état de chaque champ. Un champ peut avoir les niveaux de rapport suivants :

- **4** – Déclaration de taxe.
- **1** – Réponse statistique.
- **5** – Réponse statistique aux expéditions et à la déclaration de taxe et saisie conjointe.

| Champ                       | Niveaux d’états |
|-----------------------------|---------------|
| Période de référence         | 4, 1, 5       |
| Numéro de déclaration       | 4, 1, 5       |
| Numéro de ligne                 | 4, 1, 5       |
| Code ISO de pays (FR)       | 4, 1, 5       |
| Code complémentaire          | 4, 1, 5       |
| Numéro Siren                | 4, 1, 5       |
| Code TVA du client        | 4, 1, 5       |
| Code direction              | 4, 1, 5       |
| Type de transaction            | 4, 1, 5       |
| Niveau d’obligation            | 4, 1, 5       |
| Code marchandise              | 1, 5          |
| NGP National                | 1, 5          |
| Département         | 1, 5          |
| Nature de la transaction       | 1, 5          |
| Pays d’origine      | 1, 5          |
| Pays d’origine - Importations | 1, 5          |
| Destination finale - Exportations | 1, 5          |
| Valeur de la facture               | 4, 1, 5       |
| Valeur statistique           | 1, 5          |
| Poids net                  | 1, 5          |
| Unités supplémentaires            | 1, 5          |
| Code transport              | 1, 5          |

Le tableau suivant présente les champs inclus dans la déclaration d’échange de biens française au format INTRACOM. La table indique également les niveaux d’état de chaque champ. Un champ peut avoir les niveaux de rapport suivants :

- **4** – Déclaration de taxe.
- **1** – Réponse statistique.
- **5** – Réponse statistique aux expéditions et à la déclaration de taxe et saisie conjointe.

| Champ                       | Niveaux d’états |
|-----------------------------|---------------|
| Code direction              | 4, 1, 5       |
| Numéro de déclaration       | 4, 1, 5       |
| Numéro de ligne              | 4, 1, 5       |
| Siren                       | 4, 1, 5       |
| Département         | 1, 5          |
| Code transport              | 1, 5          |
| Pays d’origine           | 1, 5          |
| Nature de la transaction       | 1, 5          |
| Valeur de la facture               | 4, 1, 5       |
| Modes de livraison           | 1, 5          |
| Type de transaction            | 4, 1, 5       |
| Niveau d’obligation            | 4, 1, 5       |
| Code marchandise              | 1, 5          |
| NGP National                | 1, 5          |
| Poids net                  | 1, 5          |
| Valeur statistique           | 1, 5          |
| Unités supplémentaires            | 1, 5          |
| Pays d’origine - Importations | 1, 5          |
| Destination finale - Exportations | 1, 5          |
| Code TVA du client        | 4, 1, 5       |
| Code complémentaire          | 4, 1, 5       |
| Période de référence         | 4, 1, 5       |

## <a name="set-up-intrastat"></a>Configuration de la Déclaration d’échanges de biens

- Dans [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations d’états électroniques pour la déclaration d’échanges de biens :

    - Modèle de déclaration d’échanges de biens
    - État de déclaration d’échanges de biens
    - Format INTRACOM pour la déclaration d’échanges de biens (FR)
    - Format SAISUNIC pour la déclaration d’échanges de biens (FR)

    Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)

### <a name="set-up-vat-ids"></a>Paramétrer les ID de TVA

#### <a name="set-up-vat-codes-for-your-company"></a>Définir les codes TVA pour votre entreprise

1. Allez dans **Taxe** \> **Paramétrage** \> **Taxe** \> **Numéros identifiant TVA**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Pays/région**, sélectionnez **FRA**.
4. Dans le champ **Numéro identifiant TVA**, entrez la clé du numéro de TVA de votre société.
5. Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**, puis sélectionnez votre société.
6. Dans le raccourci **Commerce extérieur et logistique**, dans la section **Déclaration d’échanges de biens**, définissez les champs **Exportation de numéro d’exonération de TVA** et **Importation de numéro d’exonération de TVA** sur le code créé à l’étape 4.
7. Dans le raccourci **Immatriculation fiscale**, dans le champ **Numéro d’immatriculation fiscale**, spécifiez le numéro d’identification fiscale de votre société.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Définir les n° de T.V.A. des partenaires commerciaux

##### <a name="create-a-registration-type-for-the-company-code"></a>Créer un type d’enregistrement pour le code d’entreprise

Vous devez créer des types d’enregistrement de n° de T.V.A. pour tous les pays ou régions avec lesquels votre entreprise fait affaire.

1. Accédez à **Administration d’organisation** \> **Carnet d’adresse global** \> **Types d’enregistrement** \> **Types d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’enregistrement pour le n° de TVA.
3. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, entrez un nom pour le nouveau type d’enregistrement. Par exemple, entrez **N° de TVA**.
4. Dans le champ **Pays/région**, sélectionnez le pays ou la région du partenaire commercial.
5. Cliquez sur **Créer**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Faire correspondre le type d’enregistrement avec une catégorie d’enregistrement

1. Accédez à **Administration d’organisation** \> **Carnet d’adresse global** \> **Types d’enregistrement** \> **Catégories d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un lien entre un type d’inscription et une catégorie d’inscription.
3. Pour le type d’enregistrement pour le numéro de TVA, sélectionnez la catégorie d’enregistrement **Numéro de TVA**.
4. Répétez les étapes 2 et 3 pour les autres types d’enregistrement que vous avez créés pour les pays ou les régions avec lesquels votre entreprise fait affaire.

##### <a name="set-up-the-vat-number-of-a-trading-partner"></a>Configurer le numéro de TVA d’un partenaire commercial

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Sélectionnez un client dans la grille.
3. Dans le volet Actions, sous l’onglet **Client**, dans le groupe **Enregistrement**, sélectionnez **ID d’enregistrement**.
4. Sur le raccourci **ID enregistrement**, sélectionnez **Ajouter** pour créer un ID enregistrement.
5. Dans le champ **Type d’enregistrement**, sélectionnez le type d’enregistrement créé pour le code société.
6. Entrez le n° de T.V.A. de la société dans le champ **Numéro d’enregistrement**.
7. Sur le volet Action, sélectionnez **Enregistrer**, puis fermez la page.

Pour plus d’informations, voir [ID enregistrements](emea-registration-ids.md).

### <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Accédez à **Taxe** \> **Paramétrage** \> **Commerce extérieur** \> **Paramètres de commerce extérieur**.
2. Sur l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Génération d’états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **INTRACOM (FR)** ou **SAISUNIC (FR)**.
3. Dans le champ **Mappage de format d’état**, sélectionnez **Déclaration d’échanges de biens**.
4. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d’échanges de biens**.
5. Dans le raccourci **Général**, dans le champ **Code transaction**, sélectionnez le code qui est utilisé pour les transferts de marchandises.
6. Dans le champ **Avoir**, sélectionnez le code qui est utilisé pour les retours de marchandises.
7. Dans le champ **Collaborateur**, sélectionnez le nom du contact.
8. Dans l’onglet **Contact**, ajoutez des informations sur la personne à contacter :

    - Dans le champ **Téléphone**, saisissez le numéro de téléphone de la personne à contacter.
    - Dans le champ **Télécopie**, saisissez le numéro de télécopie de la personne à contacter.

9. Dans l’onglet **Propriétés de pays/région**, dans le champ **Pays/région**, répertoriez tous les pays ou régions avec lesquels votre société fait affaire. Pour chaque pays de l’UE, dans le champ **Type de pays/région**, sélectionnez **UE**, afin que le pays apparaisse sur votre déclaration d’échanges de biens. Pour la France, sélectionnez **Local** dans le champ **Type de pays/région**.

### <a name="set-up-compression-of-intrastat"></a>Paramétrer la compression de la déclaration d’échanges de biens

- Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Compression de déclaration d’échanges de biens** et sélectionnez les champs qui doivent être comparés lors de la synthèse des informations de la déclaration d’échanges de biens. Pour la déclaration d’échanges de biens française, sélectionnez les champs suivants :
 
    - Régime DEB
    - Pays/région d’origine
    - Transport
    - Correction
    - Pays/Région
    - Département d’origine/de destination
    - Direction
    - Pays/région de l’expéditeur
    - Code transaction
    - Marchandise

### <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Paramétrer les paramètres du produit pour la déclaration d’échanges de biens

1. Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.
2. Sélectionnez un produit dans la grille.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez le code de marchandise. Le nom de la marchandise sera imprimé dans le champ **Description des marchandises** sur le rapport de déclaration d’échanges de biens.
4. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez le pays ou la région d’origine du produit.
5. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures nettes**, saisissez le poids du produit en kilogrammes.

### <a name="ngp-codes"></a>Codes NGP

Sur la déclaration DEB, la codification des produits est constituée des éléments suivants :

- Le code CN8 à huit chiffres qui représente la nomenclature tarifaire et statistique de l’UE.
- Le cas échéant, le code article national à un chiffre de la Nomenclature Générale des Produits (NGP).

En 2022, le NGP ne s’applique qu’à trois types de produits :

- Certains produits issus des vaches, moutons et chèvres
- Les équipements militaires
- Les vins français

Vous devez configurer les codes NGP et les affecter aux produits associés. Le champ **NGP** est alors automatiquement défini sur la page **Journal des déclarations d’échanges de biens**.

#### <a name="set-up-an-ngp-code"></a>Paramétrage d’un code NGP

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Codes NGP**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **NGP**, entrez un code à un chiffre.
4. Dans le champ **Description**, entrez une description pour le code.

#### <a name="assign-an-ngp-code-to-a-product"></a>Affecter un code NGP à un produit

1. Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.
2. Sélectionnez un produit dans la grille.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **NGP**, sélectionnez le code NGP approprié.

### <a name="set-up-warehouse-parameters-for-the-intrastat-declaration"></a>Paramétrer les paramètres d’entrepôt pour la déclaration d’échanges de biens

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Entrepôts**.
2. Sélectionnez un entrepôt, puis, dans l’onglet rapide **Adresses**, sélectionnez **Ajouter** ou **Modifier**.
3. Dans la la boîte de dialogue, dans le champ **Ville**, sélectionnez la ville de l’entrepôt. La région ou la province de la ville sera utilisée comme département pour votre déclaration DEB.

### <a name="set-up-the-transport-method"></a>Paramétrer le mode de transport

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Mode de transport**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Transport**, entrez un code unique. Les entreprises françaises utilisent des codes de transport à un chiffre.

### <a name="intrastat-journal"></a>Journal des déclarations d’échanges de biens

Accédez à **Taxes** \> **Déclarations** \> **Commerce extérieur** \> **Déclaration d’échanges de biens** pour gérer vos transactions applicables au commerce extérieur avec les pays de l’UE. Pour plus d’informations, voir [Vue d’ensemble de la déclaration d’échanges de biens](emea-intrastat.md).

La colonne **NGP** est spécifique à la France et indique le code NGP du produit. Si le code NGP n’est pas applicable à un produit,**0** (zéro) est affiché. Pour ajuster le code NGP, sélectionnez la transaction, puis, sur l’onglet **Général**, dans la section **Codes**, dans le champ **NPG**, sélectionnez le code NGP requis.

#### <a name="intrastat-transfer"></a>Transfert de déclaration d’échanges de biens

Sur la page **Déclaration d’échanges de biens**, dans le volet Actions, vous pouvez sélectionner **Transférer** pour transférer automatiquement les informations sur le commerce intracommunautaire à partir de vos commandes clients, de vos factures financières, des commandes fournisseur, des factures fournisseurs, des accusés de réception de produits fournisseurs, des factures de projet et des ordres de transfert. Seuls les documents ayant un pays de l’UE comme pays ou région de destination (pour les expéditions) ou de consignation (pour les arrivées) seront transférés.

Étant donné que la déclaration DEB est une combinaison de la déclaration de la liste des ventes intracommunautaires (ESL) et de la déclaration d’échanges de biens, elle comprend également des transactions *triangulaires*, où une livraison directe est effectuée d’un pays de l’UE (partie A) vers un autre pays de l’UE (partie C), et une personne morale française (partie B) se trouve au milieu de la transaction triangulaire.

#### <a name="generate-a-deb-intrastat-report"></a>Génération d’une déclaration d’échanges de biens

1. Accédez à **Taxes** \> **Déclarations** \> **Commerce extérieur** \> **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Résultat** \> **Rapport**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens**, définissez les champs suivants :

    | Champ            | Description                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Date de début        | Sélectionnez la date de début de la déclaration.                                                                                               |
    | Au          | Sélectionnez la date de fin de la déclaration.                                                                                                 |
    | Générer un fichier    | Définissez cette option sur **Oui** pour générer un fichier .txt.                                                                                 |
    | Nom de fichier        | Saisissez le nom du fichier .txt pour votre déclaration d’échanges de biens.                                                                          |
    | Générer un rapport  | Définissez cette option sur **Oui** pour générer un fichier .xml.                                                                                |
    | Nom du fichier d’état | Entrez le nom requis.                                                                                                            |
    | Uniquement les corrections | Définissez cette option sur **Oui** pour ne déclarer que les corrections. Définissez-la sur **Non** pour déclarer à la fois les transactions normales et les corrections.         |
    | Direction        | Sélectionnez **Arrivées** pour un rapport sur les arrivées intracommunautaires. Sélectionnez **Expéditions** pour un rapport sur les envois intracommunautaires. |

4. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens**.
5. Dans la boîte de dialogue **Paramètres du rapport électronique**, sur le raccourci **Paramètres**, dans le champ **Niveau de rapport**, sélectionnez le niveau de rapport. Le niveau de rapport peut être **1 – réponse statistique**, **4 – déclaration fiscale**, ou **5 – réponse statistique à l’expédition et à la déclaration fiscale**.

## <a name="example"></a>Exemple :

L’exemple suivant montre comment paramétrer la déclaration d’échanges de biens et et créer l’état DEB. Il utilise l’entité juridique **DEMF**.

### <a name="preliminary-setup"></a>Paramétrage préliminaire

1. Dans [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations d’états électroniques pour le format de déclaration d’échanges de biens :

    - Modèle de déclaration d’échanges de biens
    - État de déclaration d’échanges de biens
    - Format INTRACOM pour la déclaration d’échanges de biens (FR)

2. Paramétrez une hiérarchie de produits :

    1. Accédez à **Gestion des informations sur les produits** \> **Paramétrage** \> **Catégories et attributs** \> **Hiérarchies de catégories**.
    2. Dans la grille, sélectionnez **Déclaration d’échanges de biens**.
    3. Dans le volet Actions, sous l’onglet **Hiérarchies de catégories**, dans le groupe **Tenir à jour**, sélectionnez **Modifier**.
    4. Sélectionnez **Nouveau nœud de catégories** dans le volet Actions.
    5. Dans le champ **Nom**, entrez **Autres Libournais**.
    6. Dans le champ **Code**, entrez **2204 21 42**.
    7. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-vat-ids"></a>Paramétrer les ID de TVA

#### <a name="set-up-vat-codes-for-your-company"></a>Définir les codes TVA pour votre entreprise

1. Allez dans **Taxe** \> **Paramétrage** \> **Taxe** \> **Numéros identifiant TVA**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Pays/région**, sélectionnez **FRA**.
4. Dans le champ **Numéro identifiant TVA**, entrez **MS123456**.
5. Accédez à **Administration d’organisation** \> **Organisation** \> **Entités juridiques**, puis sélectionnez **DEMF**.
6. Dans le raccourci **Commerce extérieur et logistique**, dans la section **Déclaration d’échanges de biens**, définissez les champs **Exportation de numéro d’exonération de TVA** et **Importation de numéro d’exonération de TVA** sur le code créé à l’étape 4.
7. Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, entrez **123456789**.

#### <a name="set-up-the-vat-ids-for-trading-partners"></a>Définir les n° de T.V.A. des partenaires commerciaux

##### <a name="create-a-registration-type-for-the-company-code"></a>Créer un type d’enregistrement pour le code d’entreprise

1. Accédez à **Administration d’organisation** \> **Carnet d’adresse global** \> **Types d’enregistrement** \> **Types d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un type d’enregistrement pour le n° de TVA.
3. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, saisissez **N° de TVA**.
4. Dans le champ **Pays/région**, sélectionnez **DEU**.
5. Cliquez sur **Créer**.

##### <a name="match-the-registration-type-with-a-registration-category"></a>Faire correspondre le type d’enregistrement avec une catégorie d’enregistrement

1. Accédez à **Administration d’organisation** \> **Carnet d’adresse global** \> **Types d’enregistrement** \> **Catégories d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer un lien entre le type d’inscription et la catégorie d’inscription.
3. Pour le type d’enregistrement **N° de T.V.A.** du pays **DEU**, sélectionnez la catégorie d’enregistrement **N° de T.V.A.**.

##### <a name="set-up-the-customers-vat-registration-number"></a>Configurer le numéro d’immatriculation de TVA du client

1. Allez dans **Comptabilité client** \> **Clients** \> **Tous les clients**.
2. Dans la grille, sélectionnez **DE-016**.
3. Dans le volet Actions, sous l’onglet **Client**, dans le groupe **Enregistrement**, sélectionnez **ID d’enregistrement**.
4. Sur le raccourci **ID enregistrement**, sélectionnez **Ajouter** pour créer un ID enregistrement.
5. Dans le champ **Type d’enregistrement**, sélectionnez **N° de TVA**.
6. Dans le champ **Numéro d’enregistrement**, entrez **DE9012**.
7. Sur le volet Action, sélectionnez **Enregistrer**, puis fermez la page.
8. Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, dans le champ **Numéro d’exonération fiscale**, sélectionnez **DE9012**.

### <a name="set-up-foreign-trade-parameters"></a>Définir les paramètres de commerce extérieur

1. Accédez à **Taxe** \> **Paramétrage** \> **Commerce extérieur** \> **Paramètres de commerce extérieur**.
2. Sur l’onglet **Déclaration d’échanges de biens**, dans le raccourci **Général**, dans le champ **Code transaction**, sélectionnez **11**.
3. Dans le raccourci **Génération d’états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **INTRACOM (FR)**.
4. Dans le champ **Mappage de format d’état**, sélectionnez **Déclaration d’échanges de biens**.
5. Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d’échanges de biens**.
6. Dans le champs **Collaborateur**, sélectionnez un enregistrement.
7. Sous l’onglet **Contact**, dans le champ **Téléphone**, saisissez le numéro de téléphone du contact
8. Dans le champ **Télécopie**, saisissez le numéro de télécopie du contact.

### <a name="create-ngp-code"></a>Créer le code NGP

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Codes NGP**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **NGP**, entrez **8**.
4. Dans le champ **Nom de la description**, entrez **NGP 8**.
5. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-product-information"></a>Configurer les informations sur le produit

1. Allez à **Gestion des informations sur les produits** \> **Produits** \> **Produits lancés**.
2. Dans la grille, sélectionnez **D0001**.
3. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **NGP**, sélectionnez **8**.
4. Dans le champ **Marchandise**, sélectionnez **2204 21 42**.
5. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez **FRA**.
6. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures pondérales**, dans le champ **Poids net**, entrez **2**.
7. Sur le volet Action, sélectionnez **Enregistrer**, puis fermez la page.
8. Dans la grille, sélectionnez **D0003**.
9. Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d’échanges de biens**, dans le champ **Marchandise**, sélectionnez **100 200 30**.
10. Dans la section **Origine**, dans le champ **Pays/région**, sélectionnez **DEU**.
11. Dans le raccourci **Gérer l’inventaire**, dans la section **Mesures pondérales**, dans le champ **Poids net**, entrez **5**.
12. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="set-up-regime-codes"></a>Paramétrer les codes régime

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Procédure statistique**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Procédure statistique**, entrez **21**.
4. Dans le champ **Texte 1**, saisissez le **Code régime 21**.

### <a name="change-the-site-address"></a>Changer l’adresse du site

1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Sites**.
2. Dans la grille, sélectionnez **1**.
3. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
4. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **FRA**.
5. Cliquez sur **OK**.
6. Accédez à **Gestion d’entrepôt** \> **Paramétrage** \> **Entrepôt** \> **Entrepôts**, et sélectionnez un entrepôt.
7. Dans le raccourci **Adresses**, sélectionnez **Ajouter**.
8. Dans la boîte de dialogue **Nouvelle adresse**, dans le champ **Pays/région**, sélectionnez **FRA**.
9. Dans le champ **Ville**, sélectionnez **Bordeaux**.
10. Sélectionnez **OK** pour fermer la boîte de dialogue.

### <a name="set-up-a-transport-method"></a>Paramétrer un mode de transport

1. Accédez à **Taxes** \> **Paramétrage** \> **Commerce extérieur** \> **Mode de transport**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Transport**, entrez **3**.
4. Dans le champ **Description**, entrez **Transport routier**.

### <a name="assign-a-transport-mode-to-a-mode-of-delivery"></a>Affectez un moyen de transport à un mode de livraison

1. Accédez à **Approvisionnements** \> **Paramétrage** \> **Distribution** \> **Modes de livraison**.
2. Dans la grille, sélectionnez **50**.
3. Dans le raccourci **Commerce extérieur**, dans le champ **Transport**, sélectionnez **3**.

### <a name="create-a-sales-order-with-an-eu-customer-that-includes-the-new-product"></a>Créer une commande client avec un client UE qui inclut le nouveau produit

1. Allez dans **Comptabilité client** \> **Commandes** \> **Toutes les commandes client**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Créer une commande client**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-016**.
4. Dans la section **Adresse**, dans le champ **Adresse de livraison**, sélectionnez le signe plus (**+**) pour créer une adresse.
5. Dans la boîte de dialogue **Nouvelle adresse**, dans le champ **Nom de la description**, entrez **Allemagne**.
6. Dans le champ **Pays/région**, sélectionnez **DEU**.
7. Cliquez sur **OK**.
8. Dans la boîte de dialogue **Créer une commande client**, sélectionnez **OK**.
9. Dans le raccourci **Lignes de commande client**, dans le champ **Numéro d’article**, sélectionnez **0001**.
10. Dans le raccourci **Détails des lignes**, sous l’onglet **Commerce extérieur**, dans le champ **Procédure statistique**, sélectionnez **21**.
11. Dans le champ **État d’origine**, sélectionnez **AL**.
12. Dans le volet Actions, sélectionnez **Enregistrer**.
13. Dans l’onglet **En-tête**, sur le raccourci **Livraison**, dans le champ **Mode de livraison**, assurez-vous que **50** est sélectionné.
14. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.
15. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**. Sélectionnez ensuite **OK** pour valider la facture.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transférer la transaction dans le journal de déclaration d’échanges de biens et examiner le résultat

1. Accédez à **Taxes** \> **Déclarations** \> **Commerce extérieur** \> **Déclaration d’échanges de biens**.
2. Dans le volet Actions, sélectionnez **Transférer**.
3. Dans la boîte de dialogue **Déclaration d’échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l’option **Facture client** sur **Oui**. Puis sélectionnez **OK**.
4. Triez les transactions selon le champ **Date**. La transaction supérieure est la transaction de résultat.

    ![Ligne représentant la commande client sur la page de déclaration d’échanges de biens.](media/intrastat_fr_1.png)

5. Sélectionnez la ligne de transaction, puis l’onglet **Général** pour afficher plus de détails.

    ![Détails de la commande client sur l’onglet Général de la page de déclaration d’échanges de biens.](media/intrastat_fr_2.png)

6. Dans le volet Actions, sélectionnez **Résultat** \> **Rapport**.
7. Dans la boîte de dialogue **Déclaration d’échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, sélectionnez le mois de la commande client que vous avez créée.
8. Dans la section **Options d’exportation**, définissez l’option **Générer un fichier** sur **Oui**.
9. Dans le champ **Nom du fichier**, entrez le nom requis.
10. Cliquez sur **OK** pour fermer la boîte de dialogue **Déclaration d’échanges de biens**.
11. Dans la boîte de dialogue **Paramètres du rapport électronique**, sur le raccourci **Paramètres**, dans le champ **Niveau de rapport**, sélectionnez **5 – réponse statistique à l’expédition et déclaration de taxe**, et examinez le rapport.

    ![Rapport Intracom de déclaration d’échanges de biens pour les expéditions.](media/intrastat_fr_3.png)

12. Examinez l’état Excel généré.

    ![Rapport de déclaration d’échanges de biens pour les expéditions.](media/intrastat_fr_4.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
