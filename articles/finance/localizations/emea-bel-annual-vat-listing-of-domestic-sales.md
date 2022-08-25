---
title: Liste annuelle de TVA des ventes intérieures
description: Cet article fournit des informations sur la liste TVA annuelle belge des ventes intérieures ou l’état du chiffre d’affaires des factures.
author: AdamTrukawka
ms.date: 09/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium
ms.author: atrukawk
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 8ab3d28db4d8dafa99a11f5e1fcc3ebaf79d9f40
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275211"
---
# <a name="annual-vat-listing-of-domestic-sales"></a>Liste annuelle de TVA des ventes intérieures

[!include [banner](../includes/banner.md)]

L’état **Chiffre d’affaires des factures** est envoyé aux autorités une fois par an. Il est utilisé pour déclarer le chiffre d’affaires des clients belges assujettis à la TVA, si ce chiffre d’affaires dépasse un certain montant. L’état comprend les factures des transactions des clients pour lesquelles les clients ont un numéro d’entreprise formaté conformément aux directives des autorités belges.

Les champs suivants sont affichés sur l’état **Chiffre d’affaires des factures** :

- Somme TVA
- Somme du chiffre d’affaires
- Référence du déclarant
- Nombre de clients
- Déclaration remplacée (si nécessaire)
- Numéro de TVA de l’entreprise
- Nom de la société
- Code postal de l’entreprise
- Code ISO du pays de l’entreprise
- Période de déclaration
- Numéro de TVA du client
- Mouvement client
- Montant TVA du client

## <a name="setup"></a>Paramétrage

### <a name="preliminary-steps"></a>Étapes préliminaires

Importer la dernière version des configurations de génération d’états électroniques (ER) :

  - Modèle de l’état du chiffre d’affaires des factures
  - État du chiffre d’affaires des factures (BE)

Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="create-registration-types-for-company-codes"></a>Créer des types d’enregistrement pour les codes d’entreprise

Vous devez créer deux types d’enregistrement pour les sociétés : un pour le numéro de TVA et un pour le numéro d’entreprise.

1. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Types d’enregistrement**.
2. Dans le volet Actions, sélectionnez **Nouveau** pour créer le type d’enregistrement pour le n° de TVA.
3. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**. saisissez un nom pour le nouveau type d’enregistrement. Par exemple, entrez **N° de TVA**.
4. Dans le champ **Pays/région**, sélectionnez **BEL**.
5. Cliquez sur **Créer**.
6. Dans le volet Actions, sélectionnez **Nouveau** pour créer le type d’enregistrement pour le numéro d’entreprise.
7. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, entrez un nom pour le nouveau type d’enregistrement. Par exemple, entrez **ENTNUM**.
8. Dans le champ **Pays/région**, sélectionnez **BEL**.
9. Cliquez sur **Créer**.

### <a name="match-the-registration-types-with-registration-categories"></a>Faire correspondre les types d’enregistrement avec les catégories d’enregistrement

1. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Catégories d’enregistrement**.  
2. Pour le type d’enregistrement pour le numéro de TVA, sélectionnez la catégorie d’enregistrement **Numéro de TVA**.
3. Pour le type d’enregistrement pour le numéro d’entreprise, sélectionnez la catégorie d’enregistrement **ID entreprise (COID)**.

### <a name="set-up-a-vat-id-and-enterprise-number-for-your-company"></a>Configurer un numéro de TVA et un numéro d’entreprise pour votre entreprise

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Dans la grille, sélectionnez votre entreprise.
3. Dans le volet Actions, sélectionnez **ID d’enregistrement**.
4. Dans le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
5. Dans le champ **Type d’enregistrement**, sélectionnez l’un des types d’enregistrement créés précédemment.
6. Saisissez le numéro de TVA ou le numéro d’entreprise de votre entreprise, selon le type d’enregistrement que vous avez sélectionné à l’étape précédente.
7. Répétez les étapes 4 à 6 pour l’autre type d’enregistrement que vous avez créé précédemment.

### <a name="set-up-a-vat-id-and-enterprise-number-for-all-your-companys-belgian-customers"></a>Configurer un numéro de TVA et un numéro d’entreprise pour tous les clients belges de votre entreprise

1. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**.
2. Dans le volet Actions, sélectionnez **ID d’enregistrement**.
3. Dans le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
4. Dans le champ **Type d’enregistrement**, sélectionnez l’un des types d’enregistrement créés précédemment.
5. Saisissez le numéro de TVA ou le numéro d’entreprise de votre client, selon le type d’enregistrement que vous avez sélectionné à l’étape précédente.
6. Répétez les étapes 3 à 5 pour l’autre type d’enregistrement que vous avez créé précédemment.

### <a name="create-number-sequence-codes-for-the-invoice-turnover-report"></a>Créer des codes de séquence de numéros pour l’état du chiffre d’affaires des factures

1. Accédez à **Administration d’organisation** > **Séquences de nombres** > **Séquences de nombres**.
2. Créez une de souches de numéros.
3. Sur le raccourci **Segments**, supprimez toutes les lignes, puis sélectionnez **Ajouter**.
4. Dans le champ **Segment**, sélectionnez **Alphanumérique**.
5. Dans le champ **Valeur**, saisissez **\#\#\#\#\#\#\#\#\#**.
6. Sous l’organisateur **Général**, dans la section **Configuration**, définissez l’option **Continue** sur **Oui**.
7. Accédez à **Comptabilité** > **Paramétrage de la comptabilité** > **Paramètres de comptabilité**.
8. Sur l’onglet **Souche de numéros**, dans le champ **Code de souche de numéros** pour la référence **ID liste des ventes annuelles**, sélectionnez la souche de numéros que vous venez de créer.

## <a name="generate-the-invoice-turnover-report"></a>Générer l’état du chiffre d’affaires des factures

1. Accédez à **Taxe** > **Recherche et états** > **États de taxe** > **État du chiffre d’affaires des factures – Belgique**.
2. Dans la boîte de dialogue **État du chiffre d’affaires des factures**, définissez les champs suivants :

    | Champ                                 | Description                                                                                                           |
    |---------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
    | Date de début                             | Permet de sélectionner la date de début de l’état.                                                                                  |
    | Au                               | Permet de sélectionner la date de fin de l’état.                                                                                    |
    | Montant                                | Montant minimum à inclure dans l’état. Ce montant est le montant total facturé par le client, hors TVA. |
    | Générer un fichier                         | Définissez cette option sur **Oui** pour générer un fichier .xml.                                                                  |
    | Nom de fichier                             | Entrer le nom du fichier de génération d’états électroniques.                                                                                  |
    | Générer un rapport                       | Définissez cette option sur **Oui** pour générer un fichier .xlsx.                                                                 |
    | Nom du fichier d’état                      | Entrer le nom du fichier .xlsx.                                                                                      |
    | Déclaration officielle                  | Définissez cette option sur **Oui** pour indiquer que cet état est définitif.                                                     |
    | Remplacement de la déclaration du chiffre d’affaires des factures | Si vous devez remplacer un état, saisissez le numéro de la déclaration remplacée.                                           |
    | Mise en correspondance des formats                        | Sélectionnez **État du chiffre d’affaires des factures (BE)** pour générer l’état **Chiffre d’affaires des factures**.                                  |

## <a name="example"></a>Exemple

1. Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actif partagé, téléchargez la dernière version des configurations ER suivantes :

    - Modèle de l’état du chiffre d’affaires des factures
    - État du chiffre d’affaires des factures (BE)

2. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Types d’enregistrement** et procédez comme suit :

    1. Dans le volet Actions, sélectionnez **Nouveau**.
    2. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, saisissez **N° de TVA**.
    3. Dans le champ **Pays/région**, sélectionnez **BEL**.
    4. Cliquez sur **Créer**.
    5. Dans le volet Actions, sélectionnez **Nouveau**.
    6. Dans la boîte de dialogue **Entrer les détails du type d’enregistrement**, dans le champ **Nom**, saisissez **ENTNUM**.
    7. Dans le champ **Pays/région**, sélectionnez **BEL**.
    8. Cliquez sur **Créer**.

3. Accédez à **Administration d’organisation** > **Carnet d’adresse global** > **Types d’enregistrement** > **Catégories d’enregistrement** et procédez comme suit :

    1. Dans le volet Actions, sélectionnez **Nouveau**.
    2. Dans le champ **Type d’enregistrement**, sélectionnez **N° de TVA**.
    3. Dans le champ **Catégorie d’enregistrement**, sélectionnez **N° de TVA**.
    4. Dans le volet Actions, sélectionnez **Nouveau**.
    5. Dans le champ **Type d’enregistrement**, sélectionnez **ENTNUM**.
    6. Dans le champ **Catégorie d’enregistrement**, sélectionnez **ID entreprise (COID)**.

4. Accédez à **Administration d’organisation** > **Carnet d’adresses global** > **Adresses** > **Configuration de l’adresse** et procédez comme suit :

    1. Sur l’onglet **Codes postaux**, sélectionnez **Nouveau**.
    2. Dans le champ **Pays/région**, sélectionnez **BEL**.
    3. Dans le champ **Code postal**, entrez **B-1014**.
    4. Dans le volet Actions, sélectionnez **Enregistrer**.

5. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques** et procédez comme suit :

    1. Dans la grille, sélectionnez **DEMF**.
    2. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
    3. Dans la boîte de dialogue **Modifier l’adresse**, dans le champ **Pays/région**, sélectionnez **BEL**.
    4. Dans le champ **Code postal**, sélectionnez **B-1014**.
    5. Dans l’organisateur **Immatriculation fiscale**, dans le champ **Numéro d’identification fiscale**, entrez **0466.158.640**.
    6. Dans le volet Actions, sélectionnez **ID d’enregistrement**.
    7. Dans le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
    8. Dans le champ **Type d’enregistrement**, sélectionnez **ENTNUM**.
    9. Dans le champ **Numéro d’enregistrement**, entrez **BTW BE 0466.158.640**.
    10. Sélectionnez **Ajouter**.
    11. Dans le champ **Type d’enregistrement**, sélectionnez **N° de TVA**.
    12. Dans le champ **Numéro d’enregistrement**, entrez **BE 0466.158.640**.

6. Accédez à **Taxe** > **Configurer** > **Taxe de vente** > **Numéros identifiant TVA**, et suivez ces étapes :

    1. Dans le volet Actions, sélectionnez **Nouveau**.
    2. Dans le champ **Pays/région**, sélectionnez **BEL**.
    3. Dans le champ **Numéro identifiant TVA**, entrez **BTW BE 0420.429.375**.

7. Accédez à **Comptabilité client** > **Clients** > **Tous les clients**, et suivez ces étapes :

    1. Dans la grille, sélectionnez **DE-010**.
    2. Dans le raccourci **Adresses**, sélectionnez **Modifier**.
    3. Dans le champ **Pays/région**, sélectionnez **BEL**.
    4. Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, dans le champ **Numéro d’exonération fiscale**, sélectionnez **BTW BE 0420.429.375**.
    5. Dans le volet Actions, sous l’onglet **Client**, dans la section **Enregistrement**, sélectionnez **ID d’enregistrement**.
    6. Dans le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
    7. Dans le champ **Type d’enregistrement**, sélectionnez **N° de TVA**.
    8. Dans le champ **Numéro d’enregistrement**, entrez **BE 0420.429.375**.
    9. Sélectionnez **Ajouter**.
    10. Dans le champ **Type d’enregistrement**, sélectionnez **N° de TVA**.
    11. Dans le champ **Numéro d’enregistrement**, entrez **BTW BE 0420.429.375**.

8. Accédez à **Administration d’organisation** > **Séquences de nombres** > **Séquences de nombres** et procédez comme suit :

    1. Dans le volet Actions, sous l’onglet **Souche de numéros**, dans la section **Nouveau**, sélectionnez **Souche de numéros**.
    2. Sur le raccourci **Identification**, dans le champ **Code de souche de numéros**, sélectionnez **Gene\_BE01**.
    3. Sur le raccourci **Paramètres de portée**, dans le champ **Portée**, sélectionnez **Entreprise**.
    4. Dans le champ **Entreprise**, sélectionnez **DEMF**.
    5. Sur le raccourci **Segments**, supprimez toutes les lignes, puis sélectionnez **Ajouter**.
    6. Dans le champ **Segment**, sélectionnez **Alphanumérique**.
    7. Dans le champ **Valeur**, saisissez **\#\#\#\#\#\#\#\#\#**.
    8. Sur le raccourci **Général**, dans la section **Configurer**. définissez l’option **Continu** sur **Oui**.

9. Accédez à **Comptabilité** > **Paramétrage du journal** > **Journaux de validation**. Dans le volet Actions, sélectionnez **Créer**.
10. Accédez à **Comptabilité** > **Paramétrage de la comptabilité** > **Paramètres de comptabilité**. Sur l’onglet **Souche de numéros**, dans le champ **Code de souche de numéros** pour la référence **ID liste des ventes annuelles**, sélectionnez **Gene\_BE01**.
11. Accédez à **Comptabilité client** > **Factures** > **Toutes factures financières**, puis procédez comme suit :

    1. Dans le volet Actions, sélectionnez **Nouveau**.
    2. Sur le raccourci **En-tête de facture financière**, dans la section **Client**, dans le champ **Compte client**, sélectionnez **DE-010**.
    3. Sur le raccourci **Lignes de facture**, dans le champ **Compte principal**, sélectionnez **110130**.
    4. Veillez à ce que le champ **Groupe de taxe de vente** soit défini sur **AR-DOM**.
    5. Dans le champ **Groupe de taxe de vente d’article**, sélectionnez **FULL**.
    6. Dans le champ **Prix unitaire**, entrez **100**.
    7. Dans le volet Actions, sélectionnez **Valider**.
    8. Dans la boîte de dialogue **Valider une facture financière**, sélectionnez **OK**.

12. Accédez à **Taxe** > **Recherche et états** > **États de taxe** > **État du chiffre d’affaires des factures – Belgique** et procédez comme suit :

    1. Sur le raccourci **Paramètres**, dans la section **Critères**, dans les champs **Date de début** et **Date de fin**, définissez l’intervalle de l’état qui correspond aux dates de la facture en texte libre que vous avez créée précédemment.
    2. Dans la section **Options d’exportation**, définissez l’option **Générer un fichier** sur **Oui**.
    3. Dans la section **Gestion des états électroniques**, dans le champ **Mise en correspondance des formats**, sélectionnez **État sur le chiffre d’affaires des factures (BE)**.
    4. Cliquez sur **OK** et examinez le fichier pour l’état. Le tableau suivant indique les valeurs dans l’exemple d’état.

        | Nom du champ                     | Valeur                                |
        |--------------------------------|--------------------------------------|
        | ClientListingsNbr              | 1                                    |
        | ClientListing VATAmountSum     | 19                                   |
        | TurnOverSum                    | 100                                  |
        | ClientsNbr                     | 1                                    |
        | SequenceNumber                 | 1                                    |
        | common:VATNumber               | 0466158640                           |
        | common:Name                    | Contoso Entertainment System Germany |
        | common:PostCode                | B-1014                               |
        | common:CountryCode             | BE                                   |
        | Client SequenceNumber          | 1                                    |
        | CompanyVATNumber issuedBy="BE" | 0420429375                           |
        | TurnOver                       | 100                                  |
        | VATAmount                      | 19                                   |

5. Examinez l’état généré au format .xlsx.

    ![Description de la table générée automatiquement.](media/emea-bel-turnover-report.png)
    

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
