---
title: ID enregistrement
description: Cet article fournit des informations sur le paramétrage et l’utilisation des ID d’enregistrement.
author: kfend
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 264824
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
ms.openlocfilehash: 380cb1d2b52d5d0debffdbe73183be2f5e783f21
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274549"
---
# <a name="registration-ids"></a>ID enregistrement

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur le paramétrage et l’utilisation des ID d’enregistrement.

De nombreux pays et régions ont différentes réglementations et exigences pour l’enregistrement des numéros ou ID d’enregistrement. Cet article donne une vue d’ensemble des paramètres requis et du traitement des types d’enregistrement pris en charge pour les parties dans différents pays/régions européens. Tous les pays/régions ont leurs exigences de prise en charge des différentes fonctionnalités spécifiques au pays relatives aux numéros d’enregistrement fournis par les différents bureaux publics. Parmi les exemples de numéros d’enregistrement, on peut citer le numéro de sécurité sociale (SSN), le numéro d’identification de taxe (TIN) et l’identification de TVA européenne (ID de TVA européen). Cette fonctionnalité fournit un cadre unifié pour tous les pays de toutes les régions en tenant compte des exigences spécifiques au pays de certains pays européens. Les sections suivantes décrivent le flux global d’informations utilisé pour le paramétrage et le traitement des ID d’enregistrement.

## <a name="registration-type-creation"></a>Création d’un type d’enregistrement
Avant de pouvoir entrer des ID d’enregistrement, vous devez paramétrer des types d’enregistrement pour les différents types de numéros d’enregistrement auxquels chaque partie est soumise. Accédez à **Administration d’organisation** &gt; **Carnet d’adresses global** &gt; **Types d’enregistrements** &gt; **Types d’enregistrements** pour créer et gérer les types d’enregistrement pour les fournisseurs, les clients, les collaborateurs et les entités juridiques dans différents pays/régions.

|Champ                 |description ;      |
|------------------------------|----------------------------|                                                                           
| Nom                | Nom du type d’enregistrement. |                                                                           
| description ;         | Description du type d’enregistrement. |
| Pays/région      | Identificateur unique du pays ou de la région.|
| Administration fiscale       | Administration fiscale associée au type d’enregistrement.|
| Limité à       | Type de restriction qui s’applique au type d’enregistrement de taxe : Aucun, Personne, Organisation.|
| Formats              | Format de validation du type d’enregistrement.|
| Peut être mis à jour      | Définit si le numéro d’enregistrement pour le type d’enregistrement peut être mis à jour après sa saisie.|
| Unique              | Détermine si le numéro d’enregistrement pour le type d’enregistrement est unique. |
| Principal pour le pays | Si une partie est associée à une ou plusieurs adresses dans un pays particulier et l’ID d’enregistrement est valide pour toutes ces adresses, vous devez désigner une adresse principale pour le pays. Vous ne pouvez enregistrer qu’un ID principal. Définit si le numéro d’enregistrement peut être entré uniquement pour l’adresse principale du pays. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Affecter un type d’enregistrement à une catégorie d’enregistrement
Une catégorie d’enregistrement est un identificateur d’enregistrement de pays/région approuvé pour être utilisé dans un pays/région particulier à des fins de taxe, de douane et autres. Cette catégorie définit les règles de contrôle d’ID d’enregistrement particulier (y compris les chiffres de contrôle, etc.) et d’ID d’enregistrement d’inclusion dans différentes états. Utilisez la page **Administration d’organisation** &gt; **Carnet d’adresses global** &gt; **Types d’enregistrements** &gt; **Catégories d’enregistrement** pour affecter le type d’enregistrement d’un pays particulier à la catégorie d’enregistrement prise en charge.

| Champ            | description ;|
|-----------------------|----------------|
| Type d’enregistrement     | Type d’enregistrement dans un pays/région particulier.|
| Limité à         | Le type de restriction s’applique au type d’enregistrement de taxe : Aucun, Personne, Organisation.|
| Catégorie d’enregistrement | Identificateur d’enregistrement unique approuvé pour être utilisé dans le pays. La liste complète des catégories prises en charge apparaît plus loin dans cet article. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Entrer les ID d’enregistrement pour les enregistrements de carnet d’adresses global

Le Carnet d’adresses global (GAB) contient les informations d’adresse consolidées pour les clients, les fournisseurs, les contacts, les relations commerciales et les entités juridiques. Pour plus d’informations, voir [Vue d’ensemble du carnet d’adresses global](../../fin-ops-core/fin-ops/organization-administration/overview-global-address-book.md). Les enregistrements de partie qui sont enregistrés dans le carnet d’adresses global peuvent contenir un ou plusieurs enregistrements d’adresse. Ces adresses sont utilisées à des fins différentes, comme la facturation ou la livraison. Vous pouvez paramétrer des ID d’enregistrement pour les informations d’adresse des clients, des fournisseurs, des collaborateurs et des entités juridiques. Recherchez l’enregistrement de partie (entité juridique, fournisseur, client, collaborateur) pour lequel vous souhaitez entrer l’ID d’enregistrement, puis cliquez sur **ID d’enregistrement** dans les écrans associés à la partie, à l’entité juridique, au fournisseur, au client ou au collaborateur pour ouvrir la page **Gérer les adresses**. Sous l’onglet **Enregistrement de taxe**, cliquez sur **Ajouter** et entrez les informations concernant l’ID d’enregistrement.


|Champ                |description ;                                                |
|---------------------|-----------------------------------------------------------|
| Type d’enregistrement   | Type d’enregistrement dans le pays ou la région sélectionné.     |
| Numéro d’enregistrement | ID d’enregistrement de la partie.                                |
| description ;         | Description du numéro d’enregistrement.               |
| Section             | Informations supplémentaires sur le numéro d’enregistrement. |
| Agence émettrice      | Autorité qui a émis le numéro d’enregistrement.        |
| Date d’émission         | Date d’émission du numéro d’enregistrement.              |
| Date d’effet           | Date d’effet du numéro d’enregistrement.           |
| Expiration          | Date d’expiration du numéro d’enregistrement.          |

> [!NOTE]
> Le numéro identifiant TVA de l’entité juridique, du fournisseur ou du client peut être sélectionné dans les ID d’enregistrement associés à l’ID de TVA et entré pour la partie.

## <a name="search-for-records-by-registration-id"></a>Rechercher des enregistrements par ID d’enregistrement
La recherche d’enregistrements de partie basée sur un ID d’enregistrement est disponible dans les écrans associés à la partie, à l’entité juridique, au fournisseur, au client et au collaborateur. Cliquez sur **Recherche d’ID d’enregistrement** pour ouvrir la page **Critères de recherche d’ID d’enregistrement**. Spécifiez les critères de recherche et cliquez sur **Rechercher**. Le système affiche les enregistrements sélectionnés dans le carnet d’adresses global et les types associés d’enregistrement de partie.

## <a name="supported-registration-categories"></a>Catégories d’enregistrement prises en charge
Le tableau suivant répertorie les types d’enregistrements pris en charge. Si vous connaissez les champs Microsoft Dynamics AX 2012 pour les ID d’enregistrement, ce tableau met également en correspondance ces champs avec les catégories d’enregistrement de Dynamics 365 Finance.

| Catégorie d’enregistrement de Finance         |Pays/région  | Terme/champ Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| ID TVA                                                        | Tous les pays de l’Union européenne (UE)|  Numéro identifiant TVA (ID de taxe de type législatif dans AX 2012 R3)|
| ID entreprise (COID)                                          | Belgique, République tchèque, Estonie, Hongrie, Lettonie, Lituanie, Pologne, Suisse | Numéro d’entreprise (EnterpriseNumber) Numéro d’enregistrement (RegNum\_W) Numéro d’enregistrement (RegNum\_W) Numéro d’enregistrement (RegNum\_W) Numéro d’enregistrement (RegNum\_W) Code d’entreprise (EnterpriseCode) Numéro d’enregistrement (RegNum\_W) UID (UID de type législatif dans AX 2012 R3) |
| ID agence                                                     | Belgique            | Numéro d’agence (BranchNumber)|
| Spisová značka (numéro d’enregistrement, agence émettrice, section) | République tchèque     | Numéro Inset (CommercialRegisterInsetNumber) Conservé au registre commercial (CommercialRegister) Section du registre commercial (CommercialRegisterSection)|
| Personnalise l’ID client                                           | Finlande | Numéro de client des services douaniers (CustomsCustomerNumber\_FI)|
| INN                                                           | Fédération de Russie| INN (INN de type législatif dans AX 2012 R3)|
| RRC                                                           | Fédération de Russie| RRC (RRC de type législatif dans AX 2012 R3)|
| OKDP                                                          | Fédération de Russie| OKDP (OKDP de type législatif dans AX 2012 R3)|
| OKPO                                                          | Fédération de Russie| OKPO (OKPO de type législatif dans AX 2012 R3)|
| RCOAD                                                         | Fédération de Russie| RCOAD (RCOAD de type législatif dans AX 2012 R3)|
| OGRN                                                          | Fédération de Russie| OGRN (OGRN de type législatif dans AX 2012 R3) |
| SNILS                                                         | Fédération de Russie| SNILS (SNILS de type législatif dans AX 2012 R3)|
| CIFTS                                                         | Fédération de Russie| CIFTS (CIFTS de type législatif dans AX 2012 R3)|
| Passeport                                                      | Espagne             | Passeport|
| Document d’identification officiel                              | Espagne             | Document d’identification officiel|
| Certificat de résidence                                         | Espagne             | Certificat de résidence|
| Autre document d’identification                                 | Espagne             | Autre document d’identification|
| Non recensé                                                  | Espagne             | Non disponible dans AX 2012 R3|


Pour plus d’informations sur le traitement des ID d’enregistrement, notamment les conditions préalables requises, consultez les enregistrements de tâche suivants pour l’ID de TVA dans Lifecycle Services (LCS) :

-   Paramétrer l’ID de TVA
-   Enregistrement de l’ID de TVA du fournisseur
-   Recherche de partie à l’aide de l’ID de TVA






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
