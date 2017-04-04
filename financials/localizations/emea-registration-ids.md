---
title: ID enregistrement
description: "Cette rubrique fournit des informations sur le paramétrage et l&quot;utilisation des ID enregistrement."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>ID enregistrement

Cette rubrique fournit des informations sur le paramétrage et l'utilisation des ID enregistrement.

De nombreux pays/régions ont des réglementations et demandes pour enregistrer les numéros d'enregistrement ou des ID. Cette rubrique fournit une vue d'ensemble des paramètres et de traitement requis les types d'enregistrements pris en charge pour les parties de différents pays européens/régions. Tous les pays/régions ont des conditions requises pour prendre en charge des différentes fonctionnalité au pays spécifiques relatives aux numéros d'enregistrement fournis par des bureaux d'état. Exemples de numéros d'enregistrement comprennent, numéro de Sécurité sociale (SSN), le numéro d'identification (TIN) de taxe, puis identification européenne de TVA (ID de TVA intracommunautaire). Cette fonction permet la zone unifié pour tous les pays dans toutes les régions prise en compte des besoins spécifiques au pays de certains pays européens. Les sections suivantes décrivent le flux d'informations général utilisée pour paramétrer et traiter les ID enregistrement.

## <a name="registration-type-creation"></a>Création de type d'enregistrement
Avant de pouvoir entrer l'ID enregistrement, vous devez paramétrer les types d'enregistrements pour les différents types de numéros d'enregistrement auquel chaque partie est soumise. Allez ** Administration d'organisation ** &gt; ** au carnet d'adresses global ** &gt; ** les types d'enregistrements ** &gt; ** les types d'enregistrements ** page permet de créer et de gérer des types d'enregistrement des fournisseurs, des clients, des travailleurs, et les entités juridiques dans différents pays/régions.

|Champ                 |description ;      |
|------------------------------|----------------------------|                                                                           
| Nom                | Le nom du type d'enregistrement. |                                                                           
| description ;         | Description du type d'enregistrement. |
| Pays/région      | Identificateur unique du pays/de la région.|
| Administration fiscale       | L'administration fiscale associée au type d'enregistrement.|
| Limité à       | Le type de restriction qui s'applique au type d'enregistrement de taxe : Aucun, personne, organisation.|
| Formats              | Le format de contrôle du type d'enregistrement.|
| Peut être mis à jour      | Détermine si le numéro d'enregistrement du type d'enregistrement peut être mis à jour après avoir été entré.|
| Seul              | Détermine si le numéro d'enregistrement du type d'enregistrement est unique. |
| Principal pour le pays | Si une partie est associée au pays d'un ou plusieurs adresses en particulier et l'ID d'enregistrement est valide pour toutes les adresses, vous devez indiquer une adresse comme principale du pays. Vous ne pouvez enregistrer un ID comme principal. Détermine si le numéro d'enregistrement peut être entré que pour principal pour l'adresse de pays. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Affectation d'un type d'enregistrement à une catégorie d'enregistrement
Catégorie d'enregistrement est identificateur d'enregistrement de pays/régions approuvé pour l'utilisation en particulier du pays/de la région de la taxe, les Douanes et tout autre fin. Cette catégorie définit les règles de contrôle ID particulier d'enregistrement (chiffres de contrôle y compris la suite.) et d'ID enregistrement d'inclusion dans différentes régions. La page ** Administration d'organisation ** &gt; ** carnet d'adresses global ** &gt; ** les types d'enregistrements ** &gt; ** des catégories d'enregistrement ** pour affecter le type d'enregistrement de pays particulier dans la catégorie prise en charge d'enregistrement.

| Champ            | description ;|
|-----------------------|----------------|
| Type d'enregistrement     | Pays/région du type d'enregistrement en particulier.|
| Limité à         | Le type de restriction s'applique au type d'enregistrement de taxe : Aucun, personne, organisation.|
| Catégorie d'enregistrement | Le identificateur d'enregistrement approuvé pour l'utilisation du pays. La liste complète de prendre en charge dans les catégories AX7.1 est ci-dessous. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Entrez les ID enregistrement pour les enregistrements de carnet d'adresses global
Le Carnet d'adresses global (GAB) dans Microsoft Dynamics 365 pour les opérations contient les informations d'adresse consolidées pour les clients, des fournisseurs, des contacts, des relations commerciales, et les entités juridiques. Pour plus d'informations, voir [vue d'ensemble du carnet d'adresses global] (/dynamics365/operations/organization-administration/overview-global-address-book). Les enregistrements de partie enregistrés dans le carnet d'adresses global qui peuvent contenir un ou plusieurs enregistrements d'adresse. Ces adresses sont utilisées à des fins différentes, comme la facturation ou la livraison. Vous pouvez paramétrer les ID enregistrement pour les informations d'adresse pour les clients, les fournisseurs, les travailleurs, et les entités juridiques. Rechercher une partie (l'entité juridique, fournisseur, client, travailleur) que l'enregistrement pour laquelle vous souhaitez entrer l'ID du registre, puis sur ** les ID enregistrement ** sur les écrans liés à la portion, l'entité juridique, fournisseur, client, un travailleur pour ouvrir ** de gérer les adresses ** la page. Sous ** enregistrement de taxe ** l'onglet, cliquez sur ** ajoutez **, puis entrez toutes les informations concernant l'ID enregistrement.

|Champ                |description ;                                                |
|---------------------|-----------------------------------------------------------|
| Type d'enregistrement   | Type d'enregistrement du pays/de la région sélectionné.     |
| Numéro d'enregistrement | ID de l'enregistrement de partie.                                |
| description ;         | Description du numéro d'enregistrement.               |
| Section             | Les informations supplémentaires sur le numéro d'enregistrement. |
| Agence émettrice      | L'autorité ayant émis le numéro d'enregistrement.        |
| Date d'émission         | Date émise pour le numéro d'enregistrement.              |
| Date d'effet           | Date d'effet pour le numéro d'enregistrement.           |
| Expiration          | Date d'expiration pour le numéro d'enregistrement.          |

> [!NOTE]
> Le numéro identifiant TVA d'entité juridique, fournisseur, client peut être sélectionné les ID enregistrement liés à l'ID de la TVA et entrés pour la partie.

## <a name="search-for-records-by-registration-id"></a>Recherche des enregistrements de l'ID enregistrement
La recherche des enregistrements de parties basée sur un ID enregistrement est disponible dans les écrans liés à la partie, dans l'entité juridique, au fournisseur, au client, et au travailleur. Cliquez sur ** recherche d'ID enregistrement ** pour ouvrir ** critères de recherche d'ID enregistrement ** la page. Permet de spécifier les critères de recherche et cliquez sur Rechercher ** **. Le système affiche les enregistrements sélectionnés du carnet d'adresses global et les types associés d'enregistrement de partie.

## <a name="supported-registration-categories"></a>Catégories prises en charge d'enregistrement
Le tableau suivant répertorie les types d'enregistrements pris en charge dans Dynamics 365 pour les opérations. Si vous connaissez les champs Microsoft Dynamics AX 2012 pour les ID enregistrement, cette table mappe également ces champs à Dynamics 365 pour les catégories d'enregistrement des opérations.

| Dynamics 365 pour la catégorie d'enregistrement d'opérations         |Pays/région  | Condition/Champ de Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| ID TVA                                                        | Tous les pays de l'Union européenne (EU)|  Numéro identifiant TVA (ID TAXE législatif de type dans AX2012 R3)|
| ID entreprise (COID)                                          | République tchèque Estonie Hongrie Lettonie Pologne Lithuanie Suisse Belgique | Numéro d'identification de numéro d'entreprise (EnterpriseNumber) (numéro d'enregistrement de RegNum\_W) (numéro d'enregistrement de RegNum\_W) (numéro d'enregistrement de RegNum\_W) numéro d'enregistrement de code de RegNum\_W) ((EnterpriseCode) (RegNum\_W) UID type législatif (UID dans AX2012 R3) |
| ID agence                                                     | Belgique            | Numéro de branches (BranchNumber)|
| Značka de Spisová (numéro d'enregistrement, de publication de l'agence, la section) | République tchèque     | Numéro d'encart (CommercialRegisterInsetNumber) donné à la section du registre de vente (CommercialRegister) du registre de vente (CommercialRegisterSection)|
| Personnalise l'ID client                                           | Finlande | Numéro de client de douane (CustomsCustomerNumber\_FI)|
| INN                                                           | Fédération de Russie| AUBERGE (AUBERGE législative de type dans AX2012 R3)|
| RRC                                                           | Fédération de Russie| RRC (type législatif dans RRC AX2012 R3)|
| OKDP                                                          | Fédération de Russie| OKDP (type législatif dans OKDP AX2012 R3)|
| OKPO                                                          | Fédération de Russie| OKPO (type législatif dans OKPO AX2012 R3)|
| RCOAD                                                         | Fédération de Russie| RCOAD (type législatif dans RCOAD AX2012 R3)|
| OGRN                                                          | Fédération de Russie| OGRN (type législatif dans OGRN AX2012 R3) |
| SNILS                                                         | Fédération de Russie| SNILS (type législatif dans SNILS AX2012 R3)|
| CIFTS                                                         | Fédération de Russie| CIFTS (type législatif dans CIFTS AX2012 R3)|

Pour plus d'informations sur les ID enregistrement de traitement, notamment les conditions préalables requises, voir les enregistrements suivants de la tâche pour l'ID de TVA aux Lifecycle Services (LCS) :

-   Paramétrer l'ID de TVA
-   Enregistrement d'ID de TVA du fournisseur
-    Recherche de partie à l'aide de l'ID de TVA



