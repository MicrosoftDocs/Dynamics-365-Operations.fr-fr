---
title: Package d’orchestration d’application à double écriture séparé
description: Le package d’orchestration d’applications à double écriture n’est plus un package unique mais a été séparé en packages plus petits. Cet article explique les solutions et les mappages que chaque package contient, ainsi que sa dépendance vis-à-vis d’autres packages.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: 28c321ee2815b2886c07bfb0996870e536458145
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111658"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Package d’orchestration d’application à double écriture séparé

[!include [banner](../../includes/banner.md)]



Auparavant, le package d’orchestration d’applications à double écriture était un package unique qui contenait les solutions suivantes :

- Notes Dynamics 365
- Ancre commune Dynamics 365 de finances et d’opérations
- Cartes d’entité à double écriture des applications de finances et d’opérations Dynamics 365
- Application de gestion des actifs Dynamics 365
- Gestion des actifs Dynamics 365
- Éléments communs de HCM
- Dynamics 365 Supply Chain Extended
- Dynamics 365 Finance Extended
- Éléments communs des applications de finances et d’opérations de Dynamics 365
- Dynamics 365 Company
- Taux de change des devises
- Field Service Common

Parce qu’il s’agissait d’un package unique, ce package a créé une situation de "tout ou rien" pour les clients. Cependant, Microsoft l’a maintenant séparé en packages plus petits. Par conséquent, les clients peuvent sélectionner uniquement les packages pour les solutions dont il a besoin. Par exemple, si vous êtes un client Microsoft Dynamics 365 Supply Chain Management, et ne nécessitez pas d’intégration avec Dynamics 365 Human Resources, notes et gestion des actifs, vous pouvez exclure ces solutions des solutions installées. Étant donné que les noms de solution sous-jacents, l’éditeur et les versions de carte restent les mêmes, ce changement est ininterrompu. Les installations existantes doivent être mises à niveau.

![Package séparé.](media/separated-package-1.png)

Cet article explique les solutions et les mappages que chaque package contient, ainsi que sa dépendance vis-à-vis d’autres packages.

## <a name="dual-write-application-core"></a>Base d’application à double écriture

Le package Base d’application à double écriture permet aux utilisateurs d’installer et de configurer la double écriture sans aucune application d’engagement client. Elle contient les cinq solutions suivantes :

| Nom unique                           | Nom d’affichage                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 Company                       |
| Dynamics365FinanceAndOperationsCommon | Éléments communs des applications de finances et d’opérations de Dynamics 365 |
| CurrencyExchangeRates                 | Taux de change des devises                    |
| msdyn_DualWriteAppCoreMaps            | Cartes d’entités principales des applications à double écriture   |
| msdyn_DualWriteAppCoreAnchor          | Ancre de base des applications à double écriture        |

Les cartes suivantes sont disponibles dans ce package.

| Applications de finances et d'opérations     | Applications Customer Engagement                    |
|---------------------------------|---------------------------------------------|
| Unité opérationnelle                  | msdyn_internalorganizations                 |
| Hiérarchie d’organisation          | msdyn_internalorganizationhierarchies       |
| Entités juridiques                  | msdyn_internalorganizations                 |
| Entités juridiques                  | cdm_companies                               |
| Objectifs de la hiérarchie d’organisation | msdyn_internalorganizationhierarchypurposes |
| Taux de change entre les deux devises     | msdyn_currencyexchangeratepairs             |
| Affixes de nom                    | msdyn_nameaffixes                           |
| Type de taux de change              | msdyn_exchangeratetypes                     |
| Taux de change CDS              | msdyn_currencyexchangerates                 |
| Type de la hiérarchie d’organisation     | msdyn_internalorganizationhierarchytypes    |
| Devises                      | transactioncurrencies                       |
| Entité Guides de réalité mixte     | msmrw_guides                                |

**Informations sur les dépendances**

Le package de base d’application à double écriture n’a aucune dépendance vis-à-vis d’autres packages.

## <a name="dual-write-human-resources"></a>Human Resources en double écriture

Le package Human Resources à double écriture contient les solutions et les cartes nécessaires pour synchroniser les données de Human Resources. Elle contient les trois solutions suivantes :

| Nom unique                | Nom d’affichage                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | Éléments communs de HCM                               |
| msdyn_Dynamics365HCMMaps   | Cartes d’entité Dynamics 365 Human Resources |
| msdyn_Dynamics365HCMAnchor | Ancre Dynamics 365 Human Resources      |

Les cartes suivantes sont disponibles dans ce package.

| Applications de finances et d'opérations | Applications Customer Engagement         |
|-----------------------------|----------------------------------|
| Origines ethniques              | cdm_ethnicorigins                |
| Fonction de tâche de rémunération   | cdm_jobfunctions                 |
| Positions V2                | cdm_jobpositions                 |
| Emplois                        | cdm_jobs                         |
| Type de tâche de rémunération       | cdm_jobtypes                     |
| Codes langue              | cdm_languages                    |
| Type de poste               | cdm_positiontypes                |
| Affectations des collaborateurs aux postes | cdm_positionworkerassignmentmaps |
| Statut de vétéran              | cdm_veteranstatuses              |
| Collaborateur                      | cdm_workers                      |
| Emploi par société      | cdm_employments                  |

**Informations sur les dépendances**

Le package Human Resources en double écriture dépend du package de base d’application en double écriture. Par conséquent, vous devez installer le package de base d’application à double écriture avant d’installer le package de Human Resources à double écriture.

## <a name="dual-write-supply-chain"></a>Supply Chain à double écriture

Le package Supply Chain à double écriture contient les solutions et les cartes nécessaires pour synchroniser les données de Supply Chain Management. Elle contient les trois solutions suivantes :

| Nom unique                                | Nom d’affichage                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain Extended                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Cartes d’entités étendues Dynamics 365 Supply Chain Management |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Ancre étendue Dynamics 365 Supply Chain Management      |

Les cartes suivantes sont disponibles dans ce package.

| Applications de finances et d'opérations                 | Applications Customer Engagement                      |
|---------------------------------------------|-----------------------------------------------|
| Unités                                       | UM                                          |
| En-têtes de commande client CDS                     | salesorders                                   |
| Lignes de commande client CDS                       | salesorderdetails                             |
| En-tête de devis de vente CDS                  | devis                                        |
| Lignes de devis de vente CDS                   | quotedetails                                  |
| Produits distincts lancés pour CDS              | produits                                      |
| Zones d’entrepôt                             | msdyn_warehousezones                          |
| Groupes de zones d’entrepôt                       | msdyn_warehousezonegroups                     |
| Afficher les ligne de travail d’entrepôt                        | msdyn_warehouseworklines                      |
| En-têtes de travail d’entrepôt                      | msdyn_warehouseworkheaders                    |
| Entrepôts                                  | msdyn_warehouses                              |
| Allée de stockage                             | msdyn_warehouseaisles                         |
| Conversion d’unités                            | msdyn_unitofmeasureconversions                |
| Conditions de livraison                           | msdyn_termsofdeliveries                       |
| Modes de livraison                           | msdyn_shipvias                                |
| Styles de produit générique                       | msdyn_sharedproductstyles                     |
| Lignes de facture client V2                      | invoicedetails                                |
| En-têtes de facture client V2                    | factures                                      |
| Tailles de produit générique                        | msdyn_sharedproductsizes                      |
| Produits lancés V2                        | msdyn_sharedproductdetails                    |
| Configurations de produit générique               | msdyn_sharedproductconfigurations             |
| Couleurs de produit générique                       | msdyn_sharedproductcolors                     |
| Codes d’origine des commandes client                    | msdyn_salesorderorigins                       |
| En-tête d’accusé de réception des marchandises                      | msdyn_purchaseorderreceipts                   |
| Lignes d’accusé de réception des marchandises                        | msdyn_purchaseorderreceiptproducts            |
| En-têtes de commande fournisseur V2                   | msdyn_purchaseorders                          |
| Entité supprimée de la ligne de commande fournisseur CDS | msdyn_purchaseorderproducts                   |
| Entité de ligne de commande fournisseur CDS              | msdyn_purchaseorderproducts                   |
| Groupes de dimension de suivi                   | msdyn_producttrackingdimensiongroups          |
| Styles                                      | msdyn_productstyles                           |
| Groupes de dimension de stockage                    | msdyn_productstoragedimensiongroups           |
| Conversions d’unités spécifiques à un produit           | msdyn_productspecificunitofmeasureconversions |
| Paramètres de commande par défaut du produit V2           | msdyn_productspecificdefaultordersettings     |
| Tailles                                       | msdyn_productsizes                            |
| Groupes de dimensions de produit                    | msdyn_productdimensiongroups                  |
| Paramètres de commande par défaut                      | msdyn_productdefaultordersettings             |
| Configurations                              | msdyn_productconfigurations                   |
| Tous les produits                                | msdyn_globalproducts                          |
| Couleurs                                      | msdyn_productcolors                           |
| Rôles de hiérarchie de catégories de produit            | msdyn_productcategoryhierarchyroles           |
| Hiérarchie de catégories de produit                | msdyn_productcategoryhierarchies              |
| Affectations de catégorie de produit                | msdyn_productcategoryassignments              |
| Catégories de produits                          | msdyn_productcategories                       |
| Emplacements d’entrepôts                         | msdyn_inventorylocations                      |
| Stock CDS le                            | msdyn_inventoryonhandentries                  |
| Catégories de produits                          | msdyn_productcategories                       |
| Stock CDS le                            | msdyn_inventoryonhandrequests                 |
| Numéro de produit identifié par code-barres           | msdyn_productbarcodes                         |
| Carte de fidélité                                | msdyn_loyaltycards                            |
| Points de récompense de fidélité                       | msdyn_loyaltyrewardpoints                     |
| Groupes de clients prix                       | msdyn_pricecustomergroups                     |
| Sites                                       | msdyn_operationalsites                        |
| Lignes de devis de vente CDS                   | quotedetails                                  |
| Lignes de commande client CDS                       | salesorderdetails                             |

**Informations sur les dépendances**

Le package Supply Chain à double écriture dépend des trois packages suivants. Par conséquent, vous devez installer ces packages avant d’installer le package Supply Chain à double écriture.

- Package de Base d’application à double écriture
- Package de Finance à double écriture
- Package de Human Resources en double écriture

## <a name="dual-write-finance"></a>Finance à double écriture

Le package Finance à double écriture contient les solutions et les cartes nécessaires pour synchroniser les données de Dynamics 365 Finance. Elle contient les quatre solutions suivantes :

| Nom unique                            | Nom d’affichage                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Mappages d’entités étendues Dynamics 365 Finance |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Ancrage étendu de Dynamics 365 Finance      |

Les cartes suivantes sont disponibles dans ce package.

| Applications de finances et d'opérations             | Applications Customer Engagement        |
|-----------------------------------------|---------------------------------|
| Groupes de retenue à la source                  | msdyn_withholdingtaxgroups      |
| CDS Contacts V2 (client)              | contacts                        |
| CDS Contacts V2 (fournisseur)                | contacts                        |
| Clients V3                            | contacts                        |
| Codes de retenue à la source                   | msdyn_withholdingtaxcodes       |
| Fournisseurs V2                              | msdyn_vendors                   |
| Mode de paiement fournisseur                   | msdyn_vendorpaymentmethods      |
| Groupes de fournisseurs                           | msdyn_vendorgroups              |
| Plan comptable                       | msdyn_chartofaccountses         |
| Groupes de validation dans la comptabilité des taxes V2      | msdyn_taxpostinggroups          |
| Groupe de taxe d’article                    | msdyn_taxitemgroups             |
| Groupes de taxe                        | msdyn_taxgroups                 |
| Entité Code d’exonération fiscale pour CDS        | msdyn_taxexemptcodes            |
| Groupes de clients                         | msdyn_customergroups            |
| Modes de paiement des clients                 | msdyn_customerpaymentmethods    |
| Dimensions financières                    | msdyn_dimensionattributes       |
| Administrations fiscales                   | msdyn_taxauthorities            |
| Format de dimension financière              | msdyn_financialdimensionformats |
| Période de calendrier fiscal                  | msdyn_fiscalcalendarperiods     |
| Entité Intégration du calendrier fiscal      | msdyn_fiscalcalendars           |
| Entité Intégration de l’exercice de calendrier fiscal | msdyn_fiscalcalendaryears       |
| Conditions de paiement                        | msdyn_paymentterms              |
| Échéancier de paiement                        | msdyn_paymentschedules          |
| Lignes d’échéancier de paiement                  | msdyn_paymentschedulelines      |
| Jours de paiement CDS                        | msdyn_paymentdays               |
| Lignes de jour de paiement CDS V2                | msdyn_paymentdaylines           |
| Compte principal                            | msdyn_mainaccounts              |
| Catégories de compte principal                 | msdyn_mainaccountcategories     |
| Registre                                  | msdyn_ledgers                   |
| Clients V3                            | comptes                        |

**Informations sur les dépendances**

Le package Finance en double écriture dépend du package de base d’application en double écriture. Par conséquent, vous devez installer le package de base d’application à double écriture avant d’installer le package de Finance à double écriture.

## <a name="dual-write-notes"></a>Notes en double écriture

Le package Notes à double écriture contient les solutions et les cartes nécessaires pour synchroniser les données de notes ou d’annotations. Elle contient les quatre solutions suivantes :

| Nom unique                  | Nom d’affichage                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Notes Dynamics 365             |
| Dynamics365NotesExtended     | Dynamics 365 notes extended    |
| msdyn_Dynamics365NotesMaps   | Cartes d’entité de notes Dynamics 365 |
| msdyn_Dynamics365NotesAnchor | Ancre de notes Dynamics 365      |

Les cartes suivantes sont disponibles dans ce package.

| Finances et opérations                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Pièces jointes des documents d’en-tête de commande client    | annotations         |
| Pièces jointes clients                       | annotations         |
| Pièces jointes de document fournisseur                | annotations         |
| Pièces jointes des documents d’en-tête de commande fournisseur | annotations         |

**Informations sur les dépendances**

Le package Notes à double écriture dépend des deux packages suivants. Par conséquent, vous devez installer ces packages avant d’installer le package Notes à double écriture.

- Package de Base d’application à double écriture
- Package de Finance à double écriture

## <a name="dual-write-asset-management"></a>Gestion des actifs à double écriture

Le package Gestion des actifs à double écriture contient les solutions et les cartes nécessaires pour synchroniser les données d’actifs de Supply Chain Management ou Dynamics 365 Field Service. Elle contient les quatre solutions suivantes :

| Nom unique                          | Nom d’affichage                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Gestion des actifs Dynamics 365             |
| Dynamics365AssetManagementApp        | Application de gestion des actifs Dynamics365          |
| msdyn_DualWriteAssetManagementMaps   | Cartes d’entité de gestion des actifs Dynamics 365 |
| msdyn_DualWriteAssetManagementAnchor | Ancre de gestion des actifs Dynamics 365      |

Les cartes suivantes sont disponibles dans ce package.

| Applications de finances et d'opérations                           | Applications Customer Engagement                |
|-------------------------------------------------------|-----------------------------------------|
| Garantie de la gestion des actifs                             | msdyn_warranties                        |
| Modèles de gestion des actifs                               | msdyn_models                            |
| Gestion des actifs Fabricants                        | msdyn_manufacturers                     |
| Gestion des actifs Types de postes techniques            | msdyn_functionallocationtypes           |
| Gestion des actifs Postes techniques                 | msdyn_functionallocations               |
| Gestion des actifs Postes techniques Statuts du cycle de vie | msdyn_functionallocationlifecyclestates |
| Gestion des actifs Postes techniques Modèles de cycle de vie | msdyn_functionallocationlifecyclemodels |
| Gestion des actifs Actifs                               | msdyn_customerassets                    |
| Gestion des actifs Types d’actifs                          | msdyn_customerassetcategories           |
| Gestion des actifs Actifs Statuts du cycle de vie               | msdyn_assetlifecyclestates              |
| Gestion des actifs Actifs Modèles de cycle de vie               | msdyn_assetlifecyclemodels              |

**Informations sur les dépendances**

Le package Gestion des actifs en double écriture dépend du package de base d’application en double écriture. Par conséquent, vous devez installer le package de base d’application à double écriture avant d’installer le package de Gestion des actifs à double écriture.

## <a name="packages-required-for-project-operations"></a>Packages requis pour Project Operations
Project Operations dépendent des packages suivants. Par conséquent, vous devez installer ces packages avant d’installer Project Operations.

- Package de Base d’application à double écriture
- Package de Finance à double écriture
- Package Supply Chain à double écriture
- Package Gestion des actifs à double écriture
- Package de Human Resources en double écriture

## <a name="dual-write-party-and-global-address-book-solutions"></a>Solutions à double écriture et carnet d’adresses global

Le package de partie à double écriture et de carnet d’adresses global contient les solutions et cartes suivantes qui sont nécessaires pour synchroniser les données de partie et de carnet d’adresses global. 

| Nom unique                       | Nom d’affichage                            |
|-----------------------------------|-----------------------------------------|
| Tiers                             | Tiers                                   |
| Dynamics365GABExtended            | Carnet d’adresses global étendu Dynamics 365               |
| Dynamics365GABDualWriteEntityMaps | Mappages d’entités à double écriture avec carnet d’adresses global étendu Dynamics 365 |
| Dynamics365GABParty_Anchor        | Carnet d’adresses global étendu Dynamics 365 et Tiers              |

Les cartes suivantes sont disponibles dans ce package.

| Applications de finances et d’opérations | Applications Customer Engagement | 
|-----------------------------|--------------------------|
| Parties CDS | msdyn_parties | 
| Emplacements d’adresse postale CDS | msdyn_postaladdresscollections | 
| Historique des adresses postales CDS V2 | msdyn_postaladdresses | 
| Emplacements d’adresse postale de partie CDS | msdyn_partypostaladdresses | 
| Contacts de partie V3 | msdyn_partyelectronicaddresses | 
| Clients V3 | comptes | 
| Clients V3 | contacts | 
| Fournisseurs V2 | msdyn_vendors | 
| Titres des contacts | msdyn_salescontactpersontitles | 
| Politesses | msdyn_complimentaryclosings | 
| Salutations | msdyn_salutations | 
| Rôles de prise de décision | msdyn_decisionmakingroles | 
| Fonctions d’emploi | msdyn_employmentjobfunctions | 
| Niveaux de fidélité | msdyn_loyaltylevels | 
| Type de caractère personnel | msdyn_personalcharactertypes | 
| Contacts V2 | msdyn_contactforparties | 
| En-tête de devis de vente CDS | devis | 
| En-têtes de commande client CDS | salesorders | 
| En-têtes de facture client V2 | factures | 
| Rôle d’adresse CDS | msdyn_addressroles |

**Informations sur les dépendances**

Les solutions de partie à double écriture et de carnet d’adresses global dépendent des trois packages suivants. Par conséquent, vous devez installer ces packages avant d’installer le package de solutions de partie à double écriture et de carnet d’adresses global.

- Package de Base d’application à double écriture
- Package de Finance à double écriture
- Package Supply Chain à double écriture

