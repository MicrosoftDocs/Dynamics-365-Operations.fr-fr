---
title: Déclaration d'échanges de biens française
description: Cette rubrique contient des informations sur la Déclaration d'échanges de biens en France.
author: andosip
ms.date: 07/9/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: a0f418aa18db99088db0b75df41f950e67160e3f
ms.sourcegitcommit: 8fb79920bea14746a71551a4456236a6386bfcea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "6538876"
---
# <a name="french-intrastat"></a>Déclaration d'échanges de biens française

[!include[banner](../includes/banner.md)]

Les entreprises en France qui sont immatriculées pour la taxe sur la valeur ajoutée (TVA) et qui commercent avec d'autres pays de l'Union européenne (UE), doivent déclarer l'échange de biens et de services en provenance et à destination de la France. La DEB (Déclaration d'échanges de Biens) est une combinaison de la déclaration de la liste des ventes intracommunautaires (ESL) et de la déclaration d'échanges de biens. Vous devez remettre cette déclaration mensuellement pour toutes les ventes intracommunautaires de biens.

Vous pouvez générer l'état DEB dans l'un des deux formats de fichier texte électronique : SAISUNIC 330 ou INTRACOM.

Le tableau suivant présente les champs inclus dans la déclaration d'échange de biens française au format SAISUNIC 330.

| **Champ**                   | **Niveau de l'état**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (Simplifié)** | **1 (Complet)** |
| Période de référence         | O                  | O            |
| Numéro de déclaration       | O                  | O            |
| Numéro de ligne                 | O                  | O            |
| Code ISO de pays (FR)       | O                  | O            |
| Code complémentaire          | O                  | O            |
| Numéro Siren                | O                  | O            |
| Code TVA du client        | O                  | O            |
| Code direction              | O                  | O            |
| Type de transaction            | O                  | O            |
| Niveau d'obligation            | O                  | O            |
| Code marchandise              |                    | O            |
| NGP National                |                    | O            |
| Département         |                    | O            |
| Nature de la transaction       |                    | O            |
| Pays d’origine      |                    | O            |
| Pays d'origine - Importations |                    | O            |
| Destination finale - Exportations |                    | O            |
| Valeur de la facture               | O                  | O            |
| Valeur statistique           |                    | O            |
| Poids net                  |                    | O            |
| Unités supplémentaires            |                    | O            |
| Code transport              |                    | O            |

Le tableau suivant présente les champs inclus dans la déclaration d'échange de biens française au format INTRACOM.

| **Champ**                   | **Niveau de l'état**   |              |
|-----------------------------|--------------------|--------------|
|                             | **4 (Simplifié)** | **1 (Complet)** |
| Code                        | O                  | O            |
| Numéro de déclaration       | O                  | O            |
| Numéro de ligne              | O                  | O            |
| Siren                       | O                  | O            |
| Département         |                    | O            |
| Code transport              |                    | O            |
| Pays d’origine           |                    | O            |
| Nature de la transaction       |                    | O            |
| Valeur de la facture               | O                  | O            |
| Modes de livraison           |                    | O            |
| Type de transaction            | O                  | O            |
| Niveau d'obligation            | O                  | O            |
| Code marchandise              |                    | O            |
| NGP National                |                    | O            |
| Poids net                  |                    | O            |
| Valeur statistique           |                    | O            |
| Unités supplémentaires            |                    | O            |
| Pays d'origine - Importations |                    | O            |
| Destination finale - Exportations |                    | O            |
| Code TVA du client        | O                  | O            |
| Code complémentaire          | O                  | O            |
| Période de référence         | O                  | O            |

### <a name="set-up-intrastat"></a>Configuration de la Déclaration d'échanges de biens

1.  Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations d’états électroniques pour la déclaration d'échanges de biens :

-   Modèle de déclaration d’échanges de biens

-   État de déclaration d’échanges de biens

-   Format INTRACOM pour la déclaration d’échanges de biens (FR)

-   Format SAISUNIC pour la déclaration d’échanges de biens (FR)

Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)

2.  Dans Dynamics 365 Finance, accédez à **Taxes** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Paramètres du commerce extérieur**, et suivez ces étapes :

    1.  Sur l'onglet **Déclaration d'échanges de biens**, dans le raccourci **Génération d'états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **INTRACOM (FR)** ou **SAISUNIC (FR)**.

    2.  Dans le champ **Mappage de format d'état**, sélectionnez **Déclaration d'échanges de biens**.

    3.  Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d'échanges de biens**.

    4.  Dans le raccourci **Général**, dans le champ **Code transaction**, sélectionnez le code qui est utilisé pour les transferts de marchandises.

    5.  Dans le champ **Avoir**, sélectionnez le code qui est utilisé pour les retours de marchandises.

    6.  Dans le champ **Niveau d'obligation pour l'exportation**, entrez le niveau de détail de la déclaration d'exportation. Le niveau que vous sélectionnez affecte les lignes qui sont affichées sur la déclaration. Pour plus d'informations, voir les tables au début de la rubrique.

3.  Accédez à **Administration d’organisation** &gt; **Organisations** &gt; **Entités juridiques**, sélectionnez votre entreprise puis procédez comme suit :

    1.  Dans le raccourci **Numéros d'enregistrement**, dans le champ **Code NAF**, entrez votre code NAF. Pour plus d'informations, voir [Codes NAF FR-00003 et numéros Siret](tasks/fr-00003-naf-codes-siret-numbers.md).

    2.  Dans le raccourci **Commerce extérieur et logistique**, dans la section **Déclaration d'échanges de biens**, définissez les champs **Exportation de numéro d'exonération de TVA** et **Importation de numéro d'exonération de TVA**.

    3.  Dans le raccourci **Immatriculation fiscale**, dans le champ **Numéro d’immatriculation fiscale**, spécifiez le numéro d'identification fiscale de votre société.

4.  Pour spécifier les codes NAF et les numéros d'exonération fiscale pour les clients, accédez à **Comptabilité client** &gt; **Clients** &gt; **Tous les clients**, et suivez ces étapes :

    1.  Sélectionnez un client.

    2.  Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, dans le champ **Numéro d'exonération fiscale**, saisissez le numéro d'exonération fiscale du client.

    3.  Dans le raccourci **Démographie de vente**, dans le champ **Siret français**, saisissez le numéro Siret de l'entreprise.

    4.  Dans le champ **Code NAF**, entrez le code NAF de l'entreprise.

    5.  Répétez ces étapes pour les autres clients.

5.  Pour spécifier les codes NAF et les numéros d'exonération fiscale pour les fournisseurs, accédez à **Comptabilité fournisseur** &gt; **Fournisseurs** &gt; **Tous les fournisseurs**, et suivez ces étapes :

    1.  Sélectionnez un fournisseur.

    2.  Dans le raccourci **Facture et livraison**, dans la section **Taxe de vente**, dans le champ **Numéro d'exonération fiscale**, saisissez le numéro d'exonération fiscale du fournisseur.

    3.  Dans le raccourci **Démographie d'achat**, dans le champ **Siret français**, saisissez le numéro Siret de l'entreprise.

    4.  Dans le champ **Code NAF**, entrez le code NAF de l'entreprise.

    5.  Répétez ces étapes pour les autres fournisseurs.

6.  Accédez à **Taxes** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Compression de déclaration d'échanges de biens** et sélectionnez les champs qui doivent être comparés lors de la synthèse des informations de la déclaration d'échanges de biens. Pour la déclaration d'échange de biens française, sélectionnez **Procédure statistique**, **État d'origine**, **Pays/région d'origine**, **Conditions de livraison**, **Transport**, **Correction**, **Pays/région**, **Département d'origine/destination**, **Direction**, **Pays/région de l'expéditeur**, **État de l'expéditeur**, **État**, **Code transaction** et **Marchandise**.

7.  Accédez à **Gestion d'entrepôt** &gt; **Paramétrage** &gt; **Entrepôt** &gt; **Entrepôts**, sélectionnez un entrepôt, puis procédez comme suit :

    1.  Dans le raccourci **Adresses**, sélectionnez **Ajouter** ou **Modifier**.

    2.  Dans la la boîte de dialogue, dans le champ **Ville**, sélectionnez la ville de l'entrepôt. L'état de la ville sera utilisé comme département pour votre déclaration DEB.

### <a name="ngp-codes"></a>Codes NGP

Sur la déclaration DEB, la codification des produits est constituée des éléments suivants :

1.  Le code CN8 à huit chiffres qui représente la nomenclature tarifaire et statistique de l'UE.

2.  Le cas échéant, le code article national à un chiffre de la Nomenclature Générale des Produits (NGP).

En 2021, le NGP ne s'applique qu'à trois types de produits :

-   Certains produits issus des vaches, moutons et chèvres

-   Les équipements militaires

-   Les vins français

Vous devez configurer les codes NGP et les affecter aux produits associés. Le champ **NGP** est alors automatiquement défini sur la page **Journal des déclarations d'échanges de biens**.

#### <a name="set-up-an-ngp-code"></a>Paramétrage d’un code NGP

1.  Accédez à **Taxes** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Codes NGP**.

2.  Dans le volet Actions, sélectionnez **Nouveau** pour créer un code NGP.

3.  Dans le champ **NGP**, entrez un code à un chiffre.

4.  Dans le champ **Description**, entrez une description pour le code.

#### <a name="assign-an-ngp-code-to-a-product"></a>Affecter un code NGP à un produit

1.  Allez à **Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits lancés**.

2.  Sélectionnez un produit dans la grille.

3.  Dans le raccourci **Commerce extérieur**, dans la section **Déclaration d'échanges de biens**, dans le champ **NGP**, sélectionnez le code NGP approprié.

## <a name="intrastat-journal"></a>Journal des déclarations d'échanges de biens

Accédez à **Taxes** &gt; **Déclarations** &gt; **Commerce** **extérieur** &gt; **Déclaration d'échanges de biens** pour gérer vos transactions applicables au commerce extérieur avec les pays de l'UE. Pour plus d'informations, voir [Vue d'ensemble de la déclaration d'échanges de biens](emea-intrastat.md).

La colonne **NGP** colonne est spécifique à la France. Elle affiche le code NGP du produit. Si le code NGP n'est pas applicable à un produit,**0** (zéro) est affiché. Vous pouvez ajuster le code NGP. Sélectionnez la transaction, puis, sur l'onglet **Général**, dans la section **Codes**, dans le champ **NPG**, sélectionnez le code NGP requis.

### <a name="intrastat-transfer"></a>Transfert de déclaration d'échanges de biens

Sur la page **Déclaration d'échanges de biens**, dans le volet Actions, vous pouvez sélectionner **Transférer** pour transférer automatiquement les informations sur le commerce intracommunautaire à partir de vos commandes clients, de vos factures financières, des commandes fournisseur, des factures fournisseurs, des accusés de réception de produits fournisseurs, des factures de projet et des ordres de transfert. Seuls les documents ayant un pays de l'UE comme pays ou région de destination (pour les expéditions) ou de consignation (pour les arrivées) seront transférés.

Étant donné que la déclaration DEB est une combinaison de la déclaration de la liste des ventes intracommunautaires (ESL) et de la déclaration d'échanges de biens, elle comprend également des transactions *triangulaires*, où une livraison directe est effectuée d'un pays de l'UE (partie A) vers un autre pays de l'UE (partie C), et une personne morale française (partie B) se trouve au milieu de la transaction triangulaire.

### <a name="generate-a-deb-intrastat-report"></a>Génération d'une déclaration d'échanges de biens

1.  Accédez à **Taxes** &gt; **Déclarations** &gt; **Commerce extérieur** &gt; **Déclaration d'échanges de biens**.

2.  Dans le volet Actions, sélectionnez **Résultat** &gt; **Rapport**.

3.  Dans la boîte de dialogue **Déclaration d'échanges de biens**, définissez les champs suivants :

| Champ            | Description                                                                                                                         |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Date de début        | Sélectionnez la date de début de la déclaration.                                                                                               |
| Au          | Sélectionnez la date de fin de la déclaration.                                                                                                 |
| Générer un fichier    | Définissez cette option sur **Oui** pour générer un fichier .txt.                                                                                 |
| Nom de fichier        | Saisissez le nom du fichier .txt pour votre déclaration d'échanges de biens.                                                                          |
| Générer un rapport  | Définissez cette option sur **Oui** pour générer un fichier .xml.                                                                                |
| Nom du fichier d'état | Entrez le nom requis.                                                                                                            |
| Uniquement les corrections | Définissez cette option sur **Oui** pour ne déclarer que les corrections. Définissez-la sur **Non** pour déclarer à la fois les transactions normales et les corrections.         |
| Direction        | Sélectionnez **Arrivées** pour un rapport sur les arrivées intracommunautaires. Sélectionnez **Expéditions** pour un rapport sur les envois intracommunautaires. |

## <a name="example"></a>Exemple

L'exemple suivant montre comment configurer et utiliser les codes NGP. Il utilise l'entité juridique **DEMF**.

1.  Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), dans la bibliothèque d’actifs partagés, téléchargez les dernières versions des configurations d’états électroniques pour le format de déclaration d'échanges de biens :

-   Modèle de déclaration d’échanges de biens

-   État de déclaration d’échanges de biens

-   Format INTRACOM pour la déclaration d’échanges de biens (FR)

2.  Dans Finance, configurez un code de transaction :

    1.  Accédez à **Taxes** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Codes transaction**.

    2.  Dans le volet Actions, sélectionnez **Nouveau**.

    3.  Dans le champ **Code transaction code**, entrez **11**.

    4.  Dans le champ **Nom**, entrez **Achat ou vente**.

    5.  Dans le volet Actions, sélectionnez **Enregistrer**.

3.  Paramétrez une hiérarchie de produits :

    1.  Accédez à **Gestion des informations sur les produits** &gt; **Paramétrage** &gt; **Catégories et attributs** &gt; **Hiérarchies de catégories**.

    2.  Dans la grille, sélectionnez **Déclaration d’échanges de biens**. Ensuite, dans le volet Actions, sous l'onglet **Hiérarchies de catégories**, dans le groupe **Tenir à jour**, sélectionnez **Modifier**.

    3.  Sélectionnez **Nouveau nœud de catégories** dans le volet Actions.

    4.  Dans le champ **Nom**, entrez **Autres Libournais**.

    5.  Dans le champ **Code**, entrez **2204 21 42**

    6.  Dans le volet Actions, sélectionnez **Enregistrer**.

4.  Accédez à **Taxes** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Paramètres du commerce extérieur**, et suivez ces étapes :

    1.  Sur l'onglet **Déclaration d'échanges de biens**, dans le raccourci **Général**, dans le champ **Code transaction**, sélectionnez **11**.

    2.  Dans le raccourci **Génération d'états électroniques**, dans le champ **Mappage de format de fichier**, sélectionnez **INTRACOM (FR)**.

    3.  Dans le champ **Mappage de format d'état**, sélectionnez **Déclaration d'échanges de biens**.

    4.  Dans le raccourci **Hiérarchie des codes marchandise**, dans le champ **Hiérarchie des catégories**, sélectionnez **Déclaration d'échanges de biens**.

5.  Paramétrez un code NGP :

    1.  Accédez à **Taxes** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Codes NGP**.

    2.  Dans le volet Actions, sélectionnez **Nouveau**.

    3.  Dans le champ **NGP**, entrez **8**.

    4.  Dans le champ **Nom de la description**, entrez **NGP 8**.

    5.  Dans le volet Actions, sélectionnez **Enregistrer**.

6.  Affectez le code NGP à un produit :

    1.  Allez à **Gestion des informations sur les produits** &gt; **Produits** &gt; **Produits lancés**.

    2.  Dans la grille, sélectionnez **0001**.

    3.  Dans le raccourci **Commerce extérieur**, dans le champ **NGP**, sélectionnez **8**.

    4.  Dans le champ **Marchandise**, sélectionnez **2204 21 42**.

    5.  Dans le volet Actions, sélectionnez **Enregistrer**.

7.  Créez une commande client qui inclut le nouveau produit :

    1.  Allez dans **Comptabilité client** &gt; **Commandes** &gt; **Toutes les commandes client**.

    2.  Dans le volet Actions, sélectionnez **Nouveau**.

    3.  Dans la boîte de dialogue **Créer** **une commande** **client**, dans la section **Client**, dans le champ **Compte** **client**, sélectionnez **100001**.

    4.  Dans la section **Adresse**, dans le champ **Adresse de livraison**, sélectionnez le signe plus (**+**) pour créer une adresse.

    5.  Dans la boîte de dialogue **Nouvelle adresse**, dans le champ **Nom de la description**, entrez **Allemagne**.

    6.  Dans le champ **Pays/région**, sélectionnez **DEU**.

    7.  Cliquez sur **OK**.

    8.  Dans la boîte de dialogue **Créer une commande client**, sélectionnez **OK**.

    9.  Dans le raccourci **Lignes de** **commande client**, dans le champ **Numéro d'article**, sélectionnez **0001**.

    10. Dans le volet Actions, sélectionnez **Enregistrer**.

    11. Dans le volet Actions, sous l’onglet **Facture**, dans le groupe **Générer**, sélectionnez **Facture**.

    12. Dans la boîte de dialogue **Validation de la facture**, dans le raccourci **Paramètres**, dans la section **Paramètre**, dans le champ **Quantité**, sélectionnez **Tous**. Sélectionnez ensuite **OK** pour valider la facture.

8.  Créez la déclaration DEB :

    1.  Accédez à **Taxes** &gt; **Déclarations** &gt; **Commerce extérieur** &gt; **Déclaration d'échanges de biens** :

    2.  Dans le volet Actions, sélectionnez **Transférer**.

    3.  Dans la boîte de dialogue **Déclaration d'échanges de biens (Transfert)**, dans la section **Paramètres**, définissez l'option **Facture client** sur **Oui**. Puis sélectionnez **OK**.

    4.  Triez les transactions selon le champ **Date**. La transaction supérieure est la transaction de résultat. Le champ **NGP** est automatiquement défini.

    5.  Dans le volet Actions, sélectionnez **Résultat** &gt; **Rapport**.

    6.  Dans la boîte de dialogue **Déclaration d'échanges de biens**, dans le raccourci **Paramètres**, dans la section **Date**, sélectionnez le mois de la commande client que vous avez créée.

    7.  Dans la section **Options d'exportation**, définissez l'option **Générer un fichier** sur **Oui**.

    8.  Dans le champ **Nom du fichier**, entrez le nom requis.

    9.  Sélectionnez **OK** et passez en revue la déclaration.

