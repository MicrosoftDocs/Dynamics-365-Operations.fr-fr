---
title: Carnet d’adresses global et de la partie
description: Cette rubrique décrit la fonctionnalité de carnet d’adresses global et de la partie de la double écriture.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 2e0d16b29a71da23acc925c09c87f0bb4776759c
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407763"
---
# <a name="party-and-global-address-book"></a>Partie et carnet d’adresses global

[!include [banner](../../includes/banner.md)]



Le *carnet d’adresses global* et de la *partie* sont des concepts des applications de finances et d’opérations. Une partie peut être une personne ou une organisation. Il est pratique de stocker et de gérer globalement les propriétés d’une partie, comme le nom, la langue, les contacts et les adresses. Ensuite, lorsque la valeur d’une propriété change à un endroit, le changement est répercuté à tous les endroits où la partie est impliquée.

## <a name="party"></a>Tiers

Une partie est une personne ou une organisation impliquée dans une entreprise. Lorsque le concept de partie est utilisé, une personne ou une organisation peut jouer plusieurs rôles (collaborateur, client, fournisseur ou contact) dans une entreprise. Le rôle est basé sur le contexte et l’objectif. Voici quelques exemples de rôles de deux sociétés fictives, Contoso et Fabrikam :

+ **Collaborateur** : un employé. Un employé de Contoso par exemple.
+ **Fournisseur** : une organisation de fournisseurs ou un propriétaire unique qui fournit des biens ou des services à une entreprise. Par exemple, si Fabrikam vend des fournitures à Contoso, Fabrikam est fournisseur de Contoso.
+ **Contact** : une personne à contacter. Par exemple, si Contoso achète des fournitures à Fabrikam, les employés de Contoso contacteront le contact chez Fabrikam.
+ **Client** : une personne ou une entreprise qui achète des choses à une entreprise. Par exemple, si Contoso achète des fournitures à Fabrikam, Contoso est donc un client de Fabrikam.

Le modèle de partie est souvent utilisé pour représenter des relations moyennes à complexes entre des organisations et des personnes, en particulier lorsqu’une partie joue plus d’un rôle. Voici quelques exemples courants :

+ Une partie peut être à la fois un client et un fournisseur. Par exemple, en Amérique du Nord, Fabrikam vend des fils électriques à Contoso et achète des haut-parleurs assemblés à Contoso. En Europe, Fabrikam vend des pièces à Contoso, mais n’achète rien à Contoso.
+ Une partie peut être à la fois un collaborateur et un client. Par exemple, un employé de Contoso achète des appareils électroniques à Contoso pour son usage personnel.
+ Il peut y avoir une relation plusieurs-à-plusieurs entre une personne et une organisation. Par exemple, Fabrikam offre des services d’expertise et emploie un coordonnateur de placement. Le coordinateur de placement fait correspondre les experts avec les demandes de travail de plusieurs clients de Fabrikam. Contoso est l’un des clients de Fabrikam. Lorsque Contoso a besoin d’un expert, il contacte le coordinateur de placement, qui facilite ensuite l’exécution de la demande. Étant donné que le coordinateur de placement gère les demandes de tous les clients, une relation N : N est impliquée.

L’illustration suivante montre le modèle de données pour la partie :

![Modèle de données pour la partie.](media/party-gab-image1.png)

> [!TIP]
> Lorsque vous essayez de créer un nouvel enregistrement de compte, utilisez le champ **Partie** pour rechercher l’enregistrement par nom. De cette façon, si vous trouvez l’enregistrement, il vous suffit de le sélectionner. Le système remplit ensuite automatiquement toutes les données à partir de la partie. Vous n’avez pas besoin de saisir manuellement tous les champs obligatoires. Ce même comportement existe sur les pages **Compte**, **Contact** et **Fournisseur** prêtes à l’emploi.

La double écriture ne prend pas en charge tous les rôles de partie des applications de finances et d’opérations. Pour une liste complète des rôles de partie, voir [Vue d’ensemble du carnet d’adresses global](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Carnet d’adresses global

Le carnet d’adresses global est un répertoire d’adresses postales et électroniques des organisations et des particuliers qui participent à une entreprise.

Le carnet d’adresses global stocke et gère autant d’adresses postales et d’adresses électroniques que nécessaire. Par exemple, Fabrikam possède des stations-service dans 50 emplacements. Chaque emplacement a une adresse postale, une adresse e-mail et un numéro de téléphone différents. Tous les achats professionnels sont facturés à la station-service principale, mais expédiés directement à la station-service spécifique qui a demandé l’achat. Le carnet d’adresses global enregistre la station-service principale comme adresse de facturation pour Fabrikam et enregistre chaque station-service comme adresse de livraison. Les adresses peuvent être enregistrées une fois et récupérées selon les besoins pour les devis et les commandes.

Selon le contexte commercial, une personne ou une organisation peut jouer plusieurs rôles et la même adresse postale et électronique peut être utilisée pour tous les rôles. Dans ce cas, un changement d’adresse dans un rôle doit apparaître dans tous les autres rôles. Le carnet d’adresses global stocke et gère les adresses à l’échelle mondiale.

L’illustration suivante présente le modèle de données pour le carnet d’adresses global.

![Modèle de données pour le carnet d’adresses global.](media/party-gab-image2.png)

## <a name="contact"></a>Contact

Dans les applications d’engagement client, un contact est une personne. Cependant, la table **Contact** a été surchargée pour représenter une personne, un utilisateur du portail, un client B2C ou un fournisseur. La représentation est implicite et vous ne pouvez pas faire la différence sans examiner les transactions associées. La table **Contact** a été limitée pour avoir une relation 1 à 1 avec la table **Compte**. Dans le cadre du modèle de carnet d’adresses global et de partie, la double écriture introduit des propriétés explicites pour la classification et la double écriture permet des relations N à N entre un contact qui est une personne et une organisation (entité **Compte** ou **Fournisseur**).

Il existe deux types de ligne **Contact** :

+ **Contact agrégé** – Ligne de **Contact** où le champ **Société** contient une valeur obligatoire.
+ **Contact non agrégé** – Ligne de **Contact** où le champ **Société** est vide.

La table **Contact** peut stocker les types de ligne suivants :

| Type de ligne | Description |
|----------|-------------|
| Une personne qui est un client (par exemple un contact commercialisable ou un client B2C). | Un enregistrement de contact agrégé où le champ **Société** n’est pas vide et le champ **Est un client** est défini sur **Oui**. |
| Une personne qui est un fournisseur (par exemple, un propriétaire unique comme un fournisseur). | Un enregistrement de contact agrégé où le champ **Société** n’est pas vide et le champ **Est un fournisseur** est défini sur **Oui**. |
| Une personne qui est à la fois un client et un fournisseur | Un enregistrement de contact agrégé où le champ **Société** n’est pas vide et le champ **Est un client** est défini sur **Oui**, et le champ **Est un fournisseur** est défini sur **Oui**. Une personne peut être à la fois un producteur d’un produit et un consommateur d’un autre produit. Les applications de finances et d’opérations et la double écriture prennent en charge cette relation. |
| Une personne qui est une personne de contact pour une organisation, mais qui n’est ni un client ni un fournisseur. | Un enregistrement de contact non agrégé où le champ **Société** n’est pas vide et le champ **Est un client** est défini sur **Non**, et le champ **Est un fournisseur** est défini sur **Non**. |

## <a name="contact-for-party-table"></a>Contact pour la table Partie

La table **Contact pour la partie** stocke et gère les relations N à N entre les lignes **Compte** et les lignes **Contact**. Il peut filtrer les lignes **Contact** agrégées par rapport aux lignes non agrégées et n’associer que les lignes **Contact** non agrégées avec les lignes **Compte** ou **Fournisseur**.

Par exemple, Natasha Jones et Miguel Reyes sont des vétérinaires qui assurent les soins dans les fermes de leur région. Natasha dessert la région de Seattle et Miguel dessert la région de Kent. Dans l’application d’engagement client, les fermes sont représentées comme des clients et les vétérinaires comme des personnes de contact. Un seul enregistrement **Contact** pour Natasha est associé à toutes les fermes avec lesquelles Natasha travaille. De même, un seul enregistrement **Contact** pour Miguel est associé à toutes les fermes avec lesquelles Miguel travaille.

Ces relations sont stockées dans la table **Contact pour la partie**. Vous pouvez trouver les informations sur les pages **Compte**, **Contact** et **Fournisseur** prêtes à l’emploi :

+ Sur la page **Compte**, vous pouvez utiliser l’onglet **Contacts associés** pour associer un ou plusieurs contacts à la ligne du **Compte**. Vous pouvez ainsi affecter des personnes de contact pour une organisation. Vous pouvez ensuite sélectionner un contact comme contact principal pour le compte. Si vous utilisez la page **Création rapide**, vous ne pouvez sélectionner qu’une personne de contact. Le comportement est le même lorsque vous utilisez la page **Fournisseur** et que le type d’enregistrement est **Organisation**.
+ Sur la page **Contact**, lorsque la ligne est un client, un fournisseur ou les deux (un contact agrégé), vous pouvez utiliser l’onglet **Contacts associés** pour associer un ou plusieurs contacts. Vous pouvez ainsi affecter des personnes de contact pour un client B2C ou un fournisseur. Vous pouvez ensuite sélectionner un contact comme contact principal. Si vous utilisez la page **Création rapide**, vous ne pouvez sélectionner qu’une personne de contact.
+ Sur la page **Contact**, lorsque la ligne est une personne de contact (un contact non agrégé), vous pouvez utiliser l’onglet **Organisations associées** pour associer un ou plusieurs clients ou fournisseurs. Vous pouvez ainsi affecter des clients ou des fournisseurs à la personne de contact sous-jacente. Le client ou le fournisseur peut être une organisation, une personne ou les deux. Vous ne pouvez choisir une valeur que dans l’un des quatre champs à la fois :

    + Si vous sélectionnez une valeur dans le champ **ID de partie**, alors le contact sous-jacent est affecté à tous les rôles de la partie sélectionnée.
    + Si vous sélectionnez une valeur dans le champ **Contact associé**, vous sélectionnez alors le contact agrégé qui est de type **Personne**.
    + Si vous sélectionnez une valeur dans le champ **Compte associé** ou **Fournisseur associé**, vous sélectionnez une organisation.

    ![Onglet Organisations associées sur la page Contact.](media/party-gab-image3.png)

    Quel que soit votre sélection, l’association est créée au niveau de la partie et s’applique à tous les rôles de la partie ; elle est stockée dans l’entité **Contact de la partie**.

> [!NOTE]
> Le nom d’affichage de la table **Contact de la partie** dans l’application d’engagement client est **Contact pour le client/fournisseur**.

Lorsque vous ouvrez une ligne de **Contact** où le champ **Est un client** et le champ **Est un fournisseur** sont définis sur **Non**, l’onglet **Organisations associées** est affiché. Utilisez cet onglet pour associer une ou plusieurs organisations client ou fournisseur au contact.

Lorsque vous ouvrez une ligne de **Contact** où le champ **Est un client** ou **Est un fournisseur** est défini sur **Oui**, l’onglet **Contacts associées** est affiché. Utilisez cet onglet pour associer un ou plusieurs contacts.

## <a name="postal-addresses"></a>Adresses postales

Un nouvel onglet nommé **Adresses** a été introduit sur les pages **Compte**, **Contact** et **Fournisseur**. Cet onglet prend en charge plusieurs adresses postales à l’aide d’une grille, comme indiqué dans l’illustration suivante.

![Grille d’adresses postales.](media/party-gab-image4.png)

La grille comprend les colonnes suivantes :

+ **Rôles d’adresse postale** – Le but de l’adresse postale.
+ **Est principal** – Valeur qui indique si l’adresse est l’adresse principale.
+ **Numéro d’adresse** – L’ordre des adresses.

Vous pouvez utiliser le bouton **Nouvelle adresse** au-dessus de la grille pour créer autant d’adresses postales que vous le souhaitez.

Les champs **Adresse 1** et **Adresse 2** sur la page **Résumé** du formulaire **Compte** correspondent aux adresses **Livraison** et **Facture**, respectivement.

![Onglet Résumé des adresses postales.](media/party-gab-image5.png)

Les champs **Adresse 1**, **Adresse 2**, and **Adresse 3** sur la page **Résumé** du formulaire **Contact** correspondent aux adresses **Entreprise**, **Livraison** et **Facture**, respectivement.

## <a name="electronic-addresses"></a>Adresses électroniques

Un nouvel onglet nommé **Adresses électroniques** a été introduit sur les pages **Compte**, **Contact** et **Fournisseur**. Cet onglet prend en charge plusieurs adresses électroniques à l’aide d’une grille, comme indiqué dans l’illustration suivante.

![Grille d’adresses électroniques.](media/party-gab-image6.png)

La grille comprend les colonnes suivantes :

+ **Type** – Type de l’adresse électronique.
+ **Est principal** Valeur qui indique si l’adresse est l’adresse principale.
+ **Objectif** – Objectif de l’adresse électronique.

Vous pouvez utiliser le bouton **Nouvelle adresse électronique** au-dessus de la grille pour créer autant d’adresses que vous le souhaitez.

Les adresses électroniques ne sont disponibles que sur cette grille. Dans les versions futures, tous les champs d’adresse électronique et postale seront supprimés des autres onglets, par exemple des onglets **Résumé** et **Détails**. Les coordonnées affichées sur l’onglet **Détails** sont des copies en lecture seule de l’adresse électronique principale, comme le téléphone principal, l’e-mail principal, le téléphone principal, le télécopieur principal et l’identifiant Twitter principal. Au cours du processus de qualification des prospects, vous pouvez fournir un numéro de téléphone professionnel et un numéro de téléphone mobile. Le numéro de téléphone professionnel est considéré comme téléphone principal si **IsMobile=No** et le numéro de téléphone mobile est considéré comme téléphone secondaire si **IsMobile=Yes**.

> [!TIP]
> Utilisez les onglets **Adresses** et **Adresses électroniques** sur les formulaires **Compte** et **Contact** pour gérer les adresses postales et électroniques. Cela garantit que les données d’adresse se synchronisent avec les applications de finances et d’opérations.

## <a name="setup"></a>Paramétrage

1. Ouvrez votre environnement d’application d’engagement client.

2. Installez la dernière version (2.2.2.60 ou ultérieure) de la [solution d’orchestration de l’application de double écriture](https://aka.ms/dual-write-app).

3. Installez la [solution d’orchestration de l’application de double écriture](https://aka.ms/dual-write-gab).

4. Ouvrez l’application Finances et Opérations. Accédez au module Gestion des données et sélectionnez l’onglet Double écriture. La page d’administration de la double écriture s’ouvre.

5. Appliquez les deux solutions installées aux étapes 2 et 3 à l’aide de la fonction [Appliquer la solution](link-your-environment.md).

6. Arrêtez les mappages suivants, car ils ne sont plus nécessaires. À la place, exécutez le mappage `Contacts V2 (msdyn_contactforparties)`.

    + CDS Contacts V2 et Contacts (se rapport aux contacts client)
    + CDS Contacts V2 et Contacts (se rapport aux contacts fournisseur)

7. Les mappages d’entités suivants sont mis à jour pour la fonctionnalité de partie, la dernière version doit donc être appliquée à ces mappages.

    Mapper | Mise à jour vers cette version | Modifications
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.5 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Customers V3 (accounts)` | 1.0.0.5 |Suppression du champ `PartyNumber` et d’autres champs liés à la partie tels que le nom, les détails personnels, les champs d’adresse postale, les champs d’adresse électronique, etc.
    `Customer V3 (contacts)` | 1.0.0.5 | Suppression du champ `PartyNumber` et d’autres champs liés à la partie tels que le nom, les détails personnels, les champs d’adresse postale, les champs d’adresse électronique, etc.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Suppression du champ `PartyNumber` et d’autres champs liés à la partie tels que le nom, les détails personnels, les champs d’adresse postale, les champs d’adresse électronique, etc.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Remplacement de la personne de contact par la référence `ContactforParty`.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Remplacement de la personne de contact par la référence `ContactforParty`.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Remplacement de la personne de contact par la référence `ContactforParty`.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.1 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Complimentary Closings ( msdyn_compliemntaryclosings)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.

8. Avant d’exécuter les mappages ci-dessus, vous devez mettre à jour les clés d’intégration manuellement comme décrit dans les étapes suivantes. Sélectionnez ensuite **Enregistrer**.

    | Mapper | Clés |
    |-----|------|
    | Compte |  accountnumber [Numéro de compte]<br>msdyn_company.cdm_companycode [Société (Code société)] |
    | Contact | msdyn_contactpersonid [Numéro de compte / ID de la personne de contact]<br>msdyn_company.cdm_companycode [Société (Code société)] |
    | Contact pour le client/fournisseur | msdyn_contactforpartynumber [Contact pour le numéro tiers]<br>msdyn_associatedcompanyid.cdm_companycode [Société associée (Code société)] |
    | Fournisseur | msdyn_vendoraccountnumber [Numéro de compte fournisseur]<br>msdyn_company.cdm_companycode [Société (Code société)]|

9. Dans Dataverse, les limites de caractères des règles de détection en double sont passées de 450 à 700 caractères. Cette limite vous permet d’ajouter une ou plusieurs clés aux règles de détection des doublons. Développez la règle de détection des doublons pour la table **Comptes** en définissant les champs suivants.

    | Champ | Valeur |
    |-------|-------|
    | Nom | Comptes avec le même nom de compte. |
    | Description | Détecte les enregistrements de compte qui ont la même valeur dans l’attribut Nom du compte. |
    | Type d’enregistrement de base | Compte |
    | Type d’enregistrement correspondant | Compte |
    | Nom du compte (champ) | Correspondance parfaite |
    | Entreprise (champ) | Correspondance parfaite |
    | Types de relations (champ) | Correspondance parfaite |
    | Identifiant de partie (champ) | Correspondance parfaite |
    | Sélection (champ) | (vide) |

    ![Règle en double pour les comptes.](media/duplicate-rule-1.PNG)

10. Développez la règle de détection des doublons pour la table **Contacts** en définissant les champs suivants.

    | Champ | Valeur |
    |-------|-------|
    | Nom | Contacts avec le même prénom et le même nom. |
    | Description | Détecte les enregistrements de contact qui ont les mêmes valeurs dans les champs Prénom et Nom. |
    | Type d’enregistrement de base | Contact |
    | Type d’enregistrement correspondant | Contact |
    | Prénom (champ) | Correspondance parfaite |
    | Nom (champ) | Correspondance parfaite |
    | Entreprise (champ) | Correspondance parfaite |
    | Identifiant de partie (champ) | Correspondance parfaite |
    | Sélection (champ) | (vide) |

    ![Règle en double pour les contacts.](media/duplicate-rule-2.PNG)

11. Si vous êtes déjà un utilisateur à double écriture, suivez les instructions de la section [Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global](upgrade-party-gab.md) et mettez à jour vos données. **Ne passez pas à l’étape 12 sans avoir terminé cette étape.** Si vous êtes un nouvel utilisateur à double écriture, passez à l’étape 12.

12. Si vous êtes déjà un utilisateur à double écriture, effectuez l’étape 11, puis vous pourrez exécuter les cartes dans l’ordre suivant. Si vous êtes un nouveau client à double écriture, vous pouvez procéder directement. Si vous obtenez un message d’erreur indiquant « La validation du projet a échoué. Champ de destination manquant ... », ouvrez le mappage et sélectionnez **Actualiser les tables**, puis exécutez le mappage.

    Application de finances et d’opérations | Application Customer Engagement  
    ----------------------------|------------------------
    [Parties CDS](mapping-reference.md#220) | msdyn_parties
    [Emplacements d’adresse postale CDS](mapping-reference.md#234) | msdyn_postaladdresscollections
    [Historique des adresses postales CDS V2](mapping-reference.md#235) | msdyn_postaladdresses
    [Emplacements d’adresse postale de partie CDS](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Contacts de partie V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Clients V3](mapping-reference.md#101) | comptes
    [Clients V3](mapping-reference.md#116) | contacts
    [Fournisseurs V2](mapping-reference.md#202) | msdyn_vendors
    [Titres des contacts](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Politesses](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Salutations](mapping-reference.md#228) | msdyn_salutations
    [Rôles de prise de décision](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Fonctions d’emploi](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Niveaux de fidélité](mapping-reference.md#226) | msdyn_loyaltylevels
    [Type de caractère personnel](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Contacts V2](mapping-reference.md#221) | msdyn_contactforparties
    [En-tête de devis de vente CDS](mapping-reference.md#215) | devis
    [En-têtes de commande client CDS](mapping-reference.md#217) | salesorders
    [En-têtes de facture client V2](mapping-reference.md#118) | factures

> [!NOTE]
> Le mappage `CDS Contacts V2 (contacts)` est celui que vous aviez interrompu à l’étape 1. Lorsque vous essayez d’exécuter d’autres mappages, ces 2 mappages peuvent apparaître dans la liste des personnes à charge. N’exécutez pas ces mappages.
>
> Si la solution du carnet d’adresses global et de partie est installée, vous devez désactiver le plugin nommé `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`. Si vous désinstallez la solution du carnet d’adresses global et de partie, vous devez alors activer à nouveau le plugin.
>
> Le champ `msdyn_*partynumber` (un champ de texte sur une seule ligne) qui est inclus dans les tables **Compte**, **Contact** et **Fournisseur** ne doit plus être utilisé à l’avenir. Le nom de l’étiquette contient un préfixe **(Obsolète)** pour plus de clarté. Au lieu de cela, utilisez le champ **msdyn_partyid**. Ce champ effectue une recherche vers la table **msdyn_party**.

> Nom de la table | Ancien champ | Nouveau champ
> --------|-------|--------
> Compte | `msdyn_partynumber` | `msdyn_partyid`
> Contact | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Modèles

Un ensemble de mappages de tables fonctionne ensemble pendant l’interaction avec le carnet d’adresses global et de partie, comme indiqué dans le tableau suivant.

| Application de finances et d’opérations | Application Customer Engagement | Description |
|----------------------------|-------------------------|-------------|
| [Titres des contacts](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Clients V3](mapping-reference.md#101) | comptes |
| [Clients V3](mapping-reference.md#116) | contacts |
| [Parties CDS](mapping-reference.md#220) | msdyn\_parties |
| [Emplacements d’adresse postale de partie CDS](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [Historique des adresses postales CDS V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [Emplacements d’adresse postale CDS](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [En-tête de devis de vente CDS](mapping-reference.md#215) | devis |
| [En-têtes de commande client CDS](mapping-reference.md#217) | salesorders |
| [Politesses](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Contacts V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Rôles de prise de décision](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Fonctions d’emploi](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Niveaux de fidélité](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Contacts de partie V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Type de caractère personnel](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [En-têtes de facture client V2](mapping-reference.md#118) | factures |
| [Salutations](mapping-reference.md#228) | msdyn\_salutations |
| [Fournisseurs V2](mapping-reference.md#202) | msdyn\_vendors |

Pour plus d’informations, voir [Référence de mappage en double écriture](mapping-reference.md).

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

+ Dans les applications de finances et d’opérations lorsque vous créez un client avec l’adresse et que vous l’enregistrez, il est possible que l’adresse ne se synchronise pas avec la table **Adresse**. Cela est dû à un problème de séquençage de plateforme à double écriture. Pour contourner le problème, créez d’abord le client et enregistrez-le. Ajoutez ensuite l’adresse.
+ Dans les applications de finances et d’opérations, lorsqu’un enregistrement client a une adresse principale et que vous créez un nouveau contact pour ce client, l’enregistrement hérite d’une adresse principale de l’enregistrement client associé. Cela se produit également pour le contact fournisseur. Dataverse ne prend actuellement pas en charge ce comportement. Si la double écriture est activée, un client contact hérité d’une adresse principale de l’application de finances et d’opérations est synchronisé avec Dataverse avec son adresse.
+ Les adresses électroniques définies sur l’onglet Adresses électroniques des formulaires **Compte**, **Contact** et **Fournisseur** proviennent de la table `msdyn_partyelectronicaddress`. Ces informations ne sont pas transmises aux transactions associées telles que la commande client, le devis et la commande fournisseur. Nous prévoyons de résoudre ce problème dans une version incrémentielle. Les données existantes sur les champs d’adresse électronique sur les enregistrements de compte et de contact continueront à fonctionner sur les transactions telles que la commande client, le devis et le bon de commande.
+ Dans les applications de finances et d’opérations, vous pouvez créer un enregistrement de contact à partir du formulaire **Ajouter des contacts**. Lorsque vous essayez de créer un nouveau contact à partir du formulaire **Afficher les contacts**, l’action échoue. Il s’agit d’un problème connu.

    ![Problème connu avec Ajouter des contacts.](media/party-gab-contact-issue.png)

+ La **Synchronisation initiale** ne prend pas en charge les champs horaires **Disponible à partir de** et **Disponible jusqu’au** sur **ContactForParty**, car DIXF convertit la valeur en une chaîne au lieu d’un entier. La conversion déclenche l’erreur `Cannot convert the literal '<say 08:00:00>’ to the expected type edm.int32`.
+ Lorsqu’une adresse postale est utilisée pour plusieurs raisons, par exemple, l’adresse de communication professionnelle et l’adresse de facturation, elle doit apparaître sous la forme `Business;Invoice` comme indiqué dans l’image suivante. Si vous ajoutez un espace entre les valeurs, vous obtiendrez une erreur.

    ![Problème connu avec Adresse.](media/party-gab-address-issue.png)

+ Vous ne pouvez pas saisir une adresse postale postdatée à l’aide d’une application de finances et d’opérations avec la double écriture, car Dataverse ne prend pas en charge la validité de la date. Si vous saisissez une adresse postale postdatée à l’aide d’une application de finances et d’opérations, elle se synchronise complètement avec Dataverse et vous verrez l’adresse sur l’interface utilisateur immédiatement. Toute mise à jour de cet enregistrement entraînera une erreur car il est postdaté et n’est pas présent dans l’application de finances et d’opérations.
