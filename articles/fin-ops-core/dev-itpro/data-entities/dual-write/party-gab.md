---
title: Carnet d’adresses global et de la partie
description: Cette rubrique décrit la fonctionnalité de carnet d’adresses global et de la partie de la double écriture.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750786"
---
# <a name="party-and-global-address-book"></a>Carnet d’adresses global et de la partie

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Le carnet d’adresses global et de la partie sont des concepts des applications Finance and Operations. Une partie peut être une personne ou une organisation. Il est pratique de stocker et de gérer globalement les propriétés d’une **Partie**, comme le nom, la langue, les contacts et les adresses. Lorsqu’une valeur de propriété change à un endroit, elle est répercutée à tous les endroits où la **Partie** est impliquée.

## <a name="party"></a>Tiers

Une *Partie* est une personne ou une organisation impliquée dans l’entreprise. En utilisant le concept de Partie, une personne ou une organisation peut jouer plusieurs rôles (collaborateur, client, fournisseur ou contact) dans une entreprise. Le rôle est basé sur le contexte et l’objectif. Voici quelques exemples de deux sociétés fictives, Contoso et Fabrikam.

+ **Collaborateur** : un employé. Par exemple, un employé de Contoso.
+ **Fournisseur** : une organisation de fournisseurs ou un propriétaire unique qui fournit des biens ou des services à une entreprise. Par exemple, si Fabrikam vend des fournitures à Contoso, Fabrikam joue le rôle de fournisseur.
+ **Contact** : une personne à contacter. Par exemple, si Contoso achète des fournitures à Fabrikam, un employé de Contoso contactera le contact chez Fabrikam.
+ **Client** : un client est une personne ou une entreprise qui achète des choses à une entreprise. Par exemple, si Contoso achète des fournitures à Fabrikam, Contoso est un client de Fabrikam.

Le modèle de Partie est souvent utilisé pour représenter des relations moyennes à complexes entre des organisations et des personnes, en particulier lorsqu’une partie joue plus d’un rôle. Voici quelques exemples courants :

+ Une partie peut être à la fois un client et un fournisseur. Par exemple, en Amérique du Nord, Fabrikam vend des fils électriques à Contoso et achète des haut-parleurs assemblés à Contoso. En Europe, Fabrikam vend des pièces à Contoso, mais ne lui achète rien.
+ Une partie peut être à la fois un collaborateur et un client. Par exemple, un employé de Contoso achète des appareils électroniques à Contoso pour son usage personnel.
+ Il peut y avoir une relation plusieurs-à-plusieurs entre une personne et une organisation. Par exemple, Fabrikam fournit des services d’expertise et emploie un coordonnateur de placement. Le coordinateur fait correspondre les experts avec les demandes de travail de plusieurs clients de Fabrikam. Contoso est l’un des comptes clients. Lorsque Contoso a besoin d’un expert, Contoso contacte le coordinateur, qui facilite ensuite l’exécution de la demande. Le coordinateur traite les demandes de tous les clients, ce qui crée une relation plusieurs-à-plusieurs.

L’image suivante montre le modèle de données pour la Partie :

![Modèle de données pour la Partie](media/party-gab-image1.png)

> [!Tip]
> Lorsque vous essayez de créer un nouvel enregistrement de compte, utilisez le champ « Partie » pour rechercher l’enregistrement par nom. Si vous trouvez l’enregistrement, il vous suffit de le sélectionner. Le système remplit automatiquement toutes les données à partir de la Partie. Vous n’avez pas besoin de saisir manuellement tous les champs obligatoires. Ce même comportement existe sur les formulaires Compte, Contact et Fournisseur livrés prêts à l’emploi.

La double écriture ne prend pas en charge tous les rôles de Partie des applications Finance and Operations. Pour une liste complète des rôles de partie, voir [Vue d’ensemble du carnet d’adresses global](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Carnet d’adresses global

Le carnet d’adresses global est un répertoire d’adresses postales et électroniques des organisations et des particuliers qui sont parties prenantes d’une entreprise.

Le carnet d’adresses global stocke et gère autant d’adresses postales et d’adresses électroniques que nécessaire. Par exemple, supposons que Fabrikam possède des stations-service dans 50 emplacements. Chaque emplacement a une adresse postale, une adresse e-mail et un numéro de téléphone différents. Tous les achats professionnels sont facturés à la station-service principale, mais les achats sont expédiés directement à la station-service spécifique qui a demandé l’achat. Le carnet d’adresses global stocke la station-service principale comme adresse de facturation, et chaque station-service comme adresse de livraison pour Fabrikam. Les adresses peuvent être stockées une fois et récupérées selon les besoins pour les devis et les commandes.

Une personne ou une organisation peut jouer plusieurs rôles en fonction du contexte commercial. Lorsque c’est le cas, ses adresses postales et électroniques peuvent être les mêmes. Dans ce cas, un changement d’adresse dans un rôle doit apparaître dans l’autre rôle, et vice versa. Le carnet d’adresses global stocke et gère les adresses à l’échelle mondiale.

![Modèle de données pour le carnet d’adresses global](media/party-gab-image2.png)

## <a name="contacts"></a>Contacts

Dans les applications d’engagement client, un *Contact* est une personne. Cependant, la table **Contact** table a été surchargée pour représenter une personne, un utilisateur du portail, un client B2C ou un fournisseur. La représentation est implicite et vous ne pouvez pas faire la différence sans étudier les transactions associées. La table **Contact** a été limitée pour avoir une relation 1 à 1 avec la table **Compte**. Dans le cadre du modèle de carnet d’adresses global et de partie, la double écriture introduit des propriétés explicites pour la classification et la double écriture permet des relations N à N entre une personne **Contact** et une organisation (entité Compte ou entité Fournisseur).

Il existe deux types de ligne **Contact** :

+ Contact agrégé : ligne de contact avec une valeur obligatoire dans le champ **Société**.
+ Contact non agrégé : ligne de contact avec le champ **Société** vide.

La table **Contact** peut stocker ces types de lignes :

Type de ligne | Description
---|---
Une personne qui est un client, par exemple un contact susceptible de vente ou un client B2C. | Un enregistrement de contact agrégé où le champ **Société** n’est pas vide et le champ **Est un client** est défini sur **Oui**.
Une personne qui est un fournisseur, par exemple, un propriétaire unique comme un fournisseur. | Un enregistrement de contact agrégé où le champ **Société** n’est pas vide et le champ **Est un fournisseur** est défini sur **Oui**.
Une personne qui est à la fois un client et un fournisseur. | Un enregistrement de contact agrégé où le champ **Société** n’est pas vide et le champ **Est un client** est défini sur **Oui**, et le champ **Est un fournisseur** est défini sur **Oui**. Une personne peut être à la fois un producteur d’un produit et un consommateur d’un autre produit. Les applications Finance and Operations et la double écriture prennent en charge cette relation.
Une personne qui est une personne de contact pour une organisation, mais qui n’est ni un client ni un fournisseur. | Un enregistrement de contact non agrégé où le champ **Société** n’est pas vide et le champ **Est un client** est défini sur **Non**, et le champ **Est un fournisseur** est défini sur **Non**.

## <a name="contact-for-party"></a>Contact pour la partie

**Contact pour la partie** stocke et gère les relations N à N entre les lignes **Compte** et les lignes **Contact**. Il peut filtrer les lignes **Contact** agrégées par rapport aux lignes non agrégées et n’associer que les lignes **Contact** non agrégées à des lignes **Compte** ou **Fournisseur**.

Par exemple, Natasha Jones et Miguel Reyes sont des vétérinaires qui assurent les soins dans les fermes de leur région. Natasha dessert la région de Seattle et Miguel dessert la région de Kent. Dans l’application d’engagement client, les fermes sont représentées comme des clients et les vétérinaires sont des personnes de contact. Un seul enregistrement **Contact** pour Natasha est associé à toutes les fermes avec lesquelles Natasha travaille. De même, un seul enregistrement **Contact** pour Miguel est associé à toutes les fermes avec lesquelles Miguel travaille.

Ces relations sont stockées dans la table **Contact pour la partie**. Vous pouvez trouver les informations dans les formulaires prêts à l’emploi :

+ Lorsque vous êtes dans le formulaire **Compte**, il y a un onglet nommé **Contacts associés**. Utilisez cet onglet pour associer un ou plusieurs contacts à la ligne **Compte**. Sur ce formulaire, vous affectez une personne de contact pour une organisation. Après avoir attribué des contacts, vous pouvez en choisir un comme contact principal pour ce compte. En utilisant le formulaire **Création rapide**, vous ne pouvez choisir qu’une personne de contact. Le comportement est le même lorsque vous utilisez le formulaire **Fournisseur** et que le type d’enregistrement est **Organisation**.
+ Lorsque vous êtes dans le formulaire **Contact**, et que la ligne est un client ou un fournisseur ou les deux (un contact agrégé), il y a un onglet nommé **Contacts associés**. Utilisez cet onglet pour associer un ou plusieurs contacts. Sur ce formulaire, vous affectez une personne de contact pour un client B2C ou un fournisseur. Après avoir attribué des contacts, vous pouvez en choisir un comme contact principal. En utilisant le formulaire **Création rapide**, vous ne pouvez choisir qu’une personne de contact.
+ Lorsque vous êtes dans le formulaire **Contact**, et que la ligne est une personne de contact (un contact non agrégé), il y a un onglet nommé **Organisations associées**. Utilisez cet onglet pour associer un ou plusieurs clients ou fournisseurs. Sur ce formulaire, vous affectez un client ou un fournisseur à la personne de contact sous-jacente. Le client ou le fournisseur peut être une organisation, une personne ou les deux. Vous ne pouvez choisir qu’une seule valeur parmi les quatre champs à un moment donné.

    ![Onglet Organisations associées](media/party-gab-image3.png)

    + Si vous sélectionnez **ID de partie**, alors le contact sous-jacent est affecté à tous les rôles de la partie choisie.
    + Si vous sélectionnez **Contact associé**, vous sélectionnez alors le contact agrégé qui est de type personne.
    + Si vous sélectionnez **Compte associé** ou **Fournisseur**, alors vous sélectionnez une organisation.

    Quel que soit votre choix, l’association est créée au niveau de la partie et est applicable à tous les rôles de la partie ; elle est stockée dans l’entité « Contact de la partie ».

> [!Note]
> Le nom d’affichage de la table **Contact de la partie** dans l’application d’engagement client est **Contact pour le client/fournisseur**.

Lorsque vous ouvrez une ligne **Contact** où **Est un client** est **Non** et **Est un vendeur** est **Non**, vous voyez l’onglet **Organisations associées**. Utilisez cet onglet pour associer une ou plusieurs organisations client ou fournisseur au contact.

Lorsque vous ouvrez une ligne **Contact** où **Est un client** est **Oui** ou **Est un vendeur** est **Oui**, vous voyez l’onglet **Contacts associés**. Utilisez cet onglet pour associer un ou plusieurs contacts.

## <a name="postal-address"></a>Adresse postale

Un nouvel onglet nommé **Adresses** a été introduit sur les formulaires **Compte**, **Contact** et **Fournisseur**. Le formulaire **Adresses** pour prend en charge N adresses en utilisant une grille, comme indiqué dans cette image :

![Grille d’adresses postales](media/party-gab-image4.png)

+ La colonne **Rôles d’adresse postale** répertorie le but des adresses.
+ La colonne **Est principale** répertorie les adresses principales.
+ La colonne **Numéro d’adresse** répertorie l’ordre des adresses.
+ Le bouton **+ Nouvelle adresse** vous permet de créer une nouvelle adresse. Vous pouvez créer autant d’adresses que vous le souhaitez.

Les champs **Adresse 1** et **Adresse 2** sur l’onglet **Résumé** du formulaire **Compte** correspondent aux adresses **Livraison** et **Facture**, respectivement.

![Onglet Résumé de l’adresse postale](media/party-gab-image5.png)

Les champs **Adresse 1**, **Adresse 2**, and **Adresse 3** sur l’onglet **Résumé** du formulaire **Contact** correspondent aux adresses **Entreprise**, **Livraison** et **Facture**, respectivement.

## <a name="electronic-address"></a>Adresse électronique

Un nouvel onglet nommé **Adresses électroniques** a été introduit sur les formulaires **Compte**, **Contact** et **Fournisseur**. Le formulaire **Adresses** pour prend en charge N adresses en utilisant une grille, comme indiqué dans cette image :

![Grille d’adresses électroniques](media/party-gab-image6.png)

+ La colonne **Type** répertorie les types d’adresse.
+ La colonne **Est principale** répertorie les adresses principales.
+ La colonne **Objectif** répertorie le but des adresses électroniques.
+ Le bouton **+ Nouvelle adresse électronique** vous permet de créer une nouvelle adresse. Vous pouvez créer autant d’adresses que vous le souhaitez.

Les adresses électroniques ne sont disponibles que sur cette grille. Dans les versions futures, tous les champs d’adresse électronique et postale seront supprimés des autres onglets, par exemple des onglets **Résumé** et **Détails**.

## <a name="setup-instructions"></a>Définir des instructions

Si vous êtes déjà client de la double écriture, vous devez suivre les instructions de configuration suivantes. Sinon, vous pouvez sauter cette section.

1. Arrêtez les mappages suivants, car ils ne sont plus nécessaires. À la place, exécutez le mappage Contacts V2 (msdyn_contactforparties).

    + CDS Contacts V2 et Contacts (se rapport aux contacts client)
    + CDS Contacts V2 et Contacts (se rapport aux contacts fournisseur)

2. Les mappages d’entités suivants sont mis à jour pour la fonctionnalité de partie, la dernière version doit donc être appliquée à ces mappages.

Mapper | Mise à jour vers cette version | Modifications
---|---|---
Clients V3 (accounts) | 1.0.0.5 |Suppression du champ PartyNumber et d’autres champs liés à la partie tels que le nom, les détails personnels, les champs d’adresse postale, les champs d’adresse électronique, etc.
Client V3 (contacts) | 1.0.0.5 | Suppression du champ PartyNumber et d’autres champs liés à la partie tels que le nom, les détails personnels, les champs d’adresse postale, les champs d’adresse électronique, etc.
Fournisseurs V2 (msdyn_vendors) | 1.0.0.6 | Suppression du champ PartyNumber et d’autres champs liés à la partie tels que le nom, les détails personnels, les champs d’adresse postale, les champs d’adresse électronique, etc.
CDS En-têtes de devis de vente (quotes) | 1.0.0.6 | Remplacement de la personne de contact par la référence ContactforParty.
En-têtes de facture client V2 (invoices) | 1.0.0.4 | Remplacement de la personne de contact par la référence ContactforParty.
CDS En-têtes de commande client (salesorders) | 1.0.0.5 | Remplacement de la personne de contact par la référence ContactforParty.
Contacts V2 (msdyn_contactforparties) | 1.0.0.2 | Ceci est un nouveau mappage. Si vous disposez d’une version précédente de la solution de partie, assurez-vous de mettre à jour ce mappage à la dernière version mentionnée.
CDS Localisation des adresses postales de la partie (msdyn_partypostaladdresses) | 1.0.0.1  | Il s’agit d’un nouveau mappage ajouté dans le cadre de la précédente version préliminaire de la partie.
CDS Historique des adresses postales V2 (msdyn_postaladdresses) | | Il s’agit d’un nouveau mappage ajouté dans le cadre de la précédente version préliminaire de la partie.
CDS Localisation des adresses postales (msdyn_postaladdresscollections) | | Il s’agit d’un nouveau mappage ajouté dans le cadre de la précédente version préliminaire de la partie.
Contacts de la partie V3 (msdyn_partyelectronicaddresses) | | Il s’agit d’un nouveau mappage ajouté dans le cadre de cette version.

## <a name="templates"></a>Modèles

Un ensemble de mappages de tables fonctionne ensemble pendant l’interaction avec le carnet d’adresses global et de partie, comme indiqué dans le tableau suivant.

Application Finance and Operations | Application Customer Engagement     | Description
----------------------------|-----------------------------|------------
[Titres des contacts](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Clients V3](mapping-reference.md#101) | comptes |
[Clients V3](mapping-reference.md#116) | contacts |
[Parties CDS](mapping-reference.md#220) | msdyn_parties |
[Emplacements d’adresse postale de partie CDS](mapping-reference.md#233) | msdyn_partypostaladdresses |
[Historique des adresses postales CDS V2](mapping-reference.md#235) | msdyn_postaladdresses |
[Emplacements d’adresse postale CDS](mapping-reference.md#234) | msdyn_postaladdresscollections |
[En-tête de devis de vente CDS](mapping-reference.md#215) | devis |
[En-têtes de commande client CDS](mapping-reference.md#217) | salesorders |
[Politesses](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Contacts V2](mapping-reference.md#221) | msdyn_contactforparties |
[Rôles de prise de décision](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Fonctions d’emploi](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Niveaux de fidélité](mapping-reference.md#226) | msdyn_loyaltylevels |
[Contacts de partie V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Type de caractère personnel](mapping-reference.md#227) | msdyn_personalcharactertypes |
[En-têtes de facture client V2](mapping-reference.md#118) | factures |
[Salutations](mapping-reference.md#228) | msdyn_salutations |
[Fournisseurs V2](mapping-reference.md#202) | msdyn_vendors |

Pour plus d’informations, voir [Référence de mappage en double écriture](mapping-reference.md).
