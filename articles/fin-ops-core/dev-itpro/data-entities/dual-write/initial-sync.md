---
title: Chaîne de dépendance d'entité (ordre de synchronisation)
description: Cette rubrique spécifie l'ordre de synchronisation à suivre pour créer les données initiales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 4adb2c8d57ad8f67346b8d34212b7a4b0bd052ab
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173129"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Chaîne de dépendance d'entité (ordre de synchronisation)

[!include [banner](../../includes/banner.md)]



Dans les tableaux suivants, les entités sont répertoriées dans l'ordre dans lequel vous devez les activer. Lorsque vous activez une carte pour la synchronisation initiale, la double écriture détecte automatiquement les autres cartes à activer. Vous pouvez utiliser la page **Double écriture** dans les applications Finance and Operations pour sélectionner ou annuler la sélection des entités lors de la synchronisation initiale.

Dans la dernière version de la double écriture, vous ne pouvez activer que certaines entités et les dépendances sont gérées pour vous.

## <a name="dynamics-365-supply-chain-management-entities"></a>Entités Dynamics 365 Supply Chain Management

Les entités suivantes pour Supply Chain Management sont répertoriées dans l'ordre dans lequel vous devez les activer.

| Nom du mappage sur la page Double écriture | Nom des métadonnées d'entité dans Supply Chain Management | Nom des métadonnées d'entité dans Common Data Service | Notes |
|---|---|---|---|
| Unités ... uoms                                                                      | UnitOfMeasureEntity                                    | uom                                          | |
| Conversions d'unités ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Tous les produits ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Groupes de dimensions de produit ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Groupes de dimensions de stockage ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Groupes de dimensions de suivi ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Couleurs ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Tailles ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Styles ... msdyn_productstyles                                                      | EcoResProductStyleEntity                               | msdyn_productstyle                           | |
| Configurations ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Produits lancés V2 ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Produits distincts lancés par Common Data Service ... produits                         | EcoResReleasedDistinctProductCommon Data ServiceEntity | Produit                                      | |
| Code-barres identifié par le numéro de produit ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Paramètres de commande par défaut ... msdyn_productdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Paramètres de commande par défaut du produit V2 ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Conversions d'unités spécifiques au produit ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Sites ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Entrepôts ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Voir [remarque 1](#scm-notes). |
| Couleurs du produit générique ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Tailles du produit générique ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Styles du produit générique ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Configurations du produit générique ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Catégories de produit ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategory                        | Voir [remarque 2](#scm-notes). |
| Affectations de catégorie de produit ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Hiérarchies de catégories de produit ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchy               | |
| Rôles de hiérarchie de catégories de produit ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Allée d'inventaire ... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Zones d'entrepôt ... msdyn_warehousezones                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Groupes de zones d'entrepôt ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Emplacements d'entrepôt ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Voir [remarque 3](#scm-notes). |
| En-têtes de travail d'entrepôt ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Lignes de travail d'entrepôt ... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Voir [remarque 4](#scm-notes). |
| Modes de livraison ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Conditions de livraison ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Codes d'origine des commandes client ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| En-têtes de commande client Common Data Service ... salesorders                             | SalesOrderHeaderCommon Data ServiceEntity              | salesorder                                   | |
| Lignes de commande client Common Data Service ... salesorderdetails                         | SalesOrderLineCommon Data ServiceEntity                | salesorderdetails                            | |
| En-tête de devis de vente Common Data Service ... quotes                               | SalesQuotationHeaderCommon Data ServiceEntity          | devis                                        | |
| Lignes de devis de vente Common Data Service ... quotedetails                          | SalesQuotationLineCommon Data ServiceEntity            | QuoteDetails                                 | |
| En-têtes de facture client V2 ... invoices                                               | SalesInvoiceHeaderV2Entity                             | Facture                                      | |
| Lignes de facture client V2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Notes dédiées au mappage

1. En raison de l'autonomie, vous devrez peut-être exécuter la synchronisation initiale deux fois.
2. Par défaut, la synchronisation initiale est désactivée en raison de la relation parent-enfant (l'ordonnancement « intelligent » n'est pas géré par la plateforme). Par conséquent, les catégories de produits existantes doivent être synchronisées manuellement (par exemple, en mettant à jour la description de la catégorie) dans le bon ordre (catégorie racine d'abord, puis enfants, puis enfants d'enfants). Accédez à **Gestion des informations sur les produits \> Configuration \> Catégories et attributs \> Hiérarchies de catégories**. Sur la page **Hiérarchies de catégories**, vous pouvez sélectionner chaque hiérarchie et y voir les catégories de produits.
3. Le mappage des champs de recherche **ItemNumberInLocation** vides et des première, deuxième et troisième zones d'entrepôt supplémentaires entraîne l'échec de la synchronisation initiale. Par conséquent, ces mappages sont supprimés pour l'instant.
4. Le mappage du champ **CaptureWeight** vide entraîne l'échec de la synchronisation initiale. Par conséquent, ce mappage est supprimé pour l'instant.

### <a name="setup-related-information"></a>Informations liées à la configuration

+ Lorsque les enregistrements sont créés pour la première fois dans l'entité **Produits** des applications pilotées par modèle dans Dynamics 365, ils ont le statut **Brouillon**. Pour définir le statut sur **Actif**, accédez à **Paramètres \> Administration \> Paramètres système \> Ventes** dans l'application pilotée par modèle, puis définissez l'option **Créer des produits à l'état actif** sur **Oui**.
+ Si vous créez des enregistrements dans l'entité **Produits** des applications pilotées par modèle dans Dynamics 365 ou dans Common Data Service avant d'activer la double écriture, ces enregistrements sont mis à jour seulement si l'ensemble de la clé, y compris **Société**, correspond aux données de l'application Finance and Operations.
+ La synchronisation de l'entité **Produits** est unidirectionnelle, des applications Finance and Operations vers Common Data Service. Si un champ mappé dans l'entité **Produits** des applications pilotées par modèle dans Dynamics 365 est mis à jour, la mise à jour est remplacée lors de la prochaine synchronisation à partir de l'application Finance and Operations.

### <a name="known-issues"></a>Problèmes connus

- Une erreur se produit lors de la suppression d'une unité dans une application Finance and Operations. Lorsque les unités de mesure sont synchronisées de l'application Finance and Operations vers Common Data Service, la première unité d'une classe spécifique est créée en tant qu'unité principale et empêche la suppression.

    **Atténuation :** commencez par supprimer l'unité dans Common Data Service. Elle peut ensuite être supprimée dans l'application Finance and Operations.

- Une erreur se produit lors de la suppression d'un site opérationnel dans Common Data Service. Le message d'erreur indique : « Infos : avertissement : l'adresse principale ne peut pas être supprimée. Avertissement : l'enregistrement d'entité n'a pas pu être supprimé en raison de l'échec de la validation pour la source de données suivante : InventSiteLogisticsLocation (InventSiteLogisticsLocation). » Cette erreur est due à un problème dans l'entité de données de l'application Finance and Operations.

    **Atténuation :** vous pouvez supprimer le site dans l'application Finance and Operations. Le site est ensuite supprimé dans Common Data Service si la carte de double écriture correspondante est en cours d'exécution.

## <a name="dynamics-365-finance-entities"></a>Entités Dynamics 365 Finance

Les entités suivantes pour Dynamics 365 Finance sont répertoriées dans l'ordre dans lequel vous devez les activer.

| Nom du mappage sur la page Double écriture | Nom des métadonnées d'entité dans Finance | Nom des métadonnées d'entité dans Common Data Service | Notes |
|---|---|---|---|
| Devises ... transactioncurrencies                                            | CurrencyEntity                              | Devise                                   | |
| Type de taux de change ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Taux de change entre les deux devises ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Taux de change Common Data Service ... msdyn_currencyexchangerates              | ExchangeRateCommon Data ServiceEntity       | msdyn_currencyexchangerate                 | Voir [remarque 1](#fin-notes). |
| Entité Intégration du calendrier fiscal ... msdyn_fiscalcalendars                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Entité Intégration de l'exercice du calendrier fiscal ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Période du calendrier fiscal ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Type de hiérarchie d'organisation ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Voir [remarque 1](#fin-notes). |
| Objectifs de la hiérarchie d'organisation ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Voir [remarque 1](#fin-notes). |
| Entités juridiques ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Voir [remarque 1](#fin-notes). |
| Entités juridiques ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Unité opérationnelle ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Voir [remarque 1](#fin-notes). |
| Hiérarchie d'organisation - publiée ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Voir [remarque 1](#fin-notes). |
| Affixes de nom ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Jours de paiement Common Data Service ... msdyn_paymentdays                          | PaymentDayCommon Data ServiceEntity         | msdyn_paymentday                           | |
| Lignes de jour de paiement Common Data Service V2 ... msdyn_paymentdaylines              | PaymentDayLineCommon Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Échéancier de paiement ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Lignes d'échéancier de paiement ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Conditions de paiement ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Mode de paiement client ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Mode de paiement fournisseur ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Groupes de clients ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Groupes de fournisseurs ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Groupes de taxe ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Groupes de taxe d'article ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Groupes de validation dans la comptabilité des taxes V2 ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Entité Common Data Service Code d'exonération fiscale ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data ServiceEntity      | msdyn_taxexemptcode                        | |
| Administrations fiscales ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Codes taxe ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Voir [remarque 1](#fin-notes). |
| Format de dimension financière ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Dimensions financières ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Groupes de retenue à la source ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Codes de retenue à la source ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Plan comptable ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Comptabilité ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Voir [remarque 1](#fin-notes). |
| Catégories de compte principal ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Compte principal ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Clients V3 ... accounts                                                       | CustCustomerV3Entity                        | Compte                                    | Voir [remarque 2](#fin-notes). |
| Clients V3 ... contacts                                                       | CustCustomerV3Entity                        | Contact                                    | Voir [remarque 3](#fin-notes). |
| Fournisseurs V2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Voir [remarque 2](#fin-notes). |
| Contacts Common Data Service V2 ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | Contact                                    | Voir [remarque 4](#fin-notes). |
| Contacts Common Data Service V2 ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | Contact                                    | Voir [remarque 5](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Notes dédiées au mappage

1. La synchronisation unidirectionnelle se produit à partir des applications Finance and Operations vers Common Data Service.
2. En raison de l'autonomie, vous devrez peut-être exécuter la synchronisation initiale plusieurs fois. Veillez à sélectionner **Client** comme type de relation lorsque vous créez un compte à l'aide de la page **Comptes** dans Common Data Service. Si vous rencontrez des problèmes avec le champ **Contact principal** lors de la synchronisation initiale, supprimez ce champ du mappage, puis réexécutez la synchronisation initiale. Une fois la synchronisation initiale terminée, arrêtez le mappage et rajoutez le champ **Contact principal**. Ensuite, démarrez le mappage, mais ignorez la synchronisation initiale. La valeur du champ **Contact principal** n'est pas incluse dans la synchronisation initiale et vous devez migrer manuellement les valeurs.
3. Veillez à définir l'option **Vendable** sur **Oui** sur la page **Contacts** dans Common Data Service lorsque vous tentez de créer un client du type **Personne**.
4. Ce mappage possède un filtre des deux côtés pour associer les contacts client. Ouvrez les détails du mappage, cliquez sur le bouton de filtre (symbole d'entonnoir) en regard du nom de l'entité **Sales.Contact** et assurez-vous que les critères du fichier contiennent **msdyn_contactforvendor eq true et msdyn_sellable eq false**.
5. Ce mappage possède un filtre des deux côtés pour associer les contacts fournisseur. Ouvrez les détails du mappage, cliquez sur le bouton de filtre (symbole d'entonnoir) en regard du nom de l'entité **Sales.Contact** et assurez-vous que les critères du filtre contiennent **msdyn_contactforvendor eq true et msdyn_sellable eq false**. 

## <a name="dynamics-365-human-resources-entities"></a>Entités Dynamics 365 Human Resources

Les entités suivantes pour Dynamics 365 Human Resources sont répertoriées dans l'ordre dans lequel vous devez les activer.

| Nom du mappage sur la page Double écriture | Nom des métadonnées d'entité dans Human Resources | Nom des métadonnées d'entité dans Common Data Service | Notes |
|---|---|---|---|
| cdm_jobfunction - Fonction                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes - Types de missions                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs - Missions                                               |                                   | cdm_jobs                         | |
| cdm_jobs - Détails de la mission                                        |                                   | cdm_jobs                         | |
| cdm_positiontype - Type de poste                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions - Poste de base                              | HcmPositionBaseEntity             | cdm_jobposition                  | Voir [remarque 1](#hr-notes). |
| cdm_jobposition - Détails du poste                            | HcmPositionDetailEntity           | cdm_jobposition                  | Voir [remarque 1](#hr-notes). |
| cdm_jobposition - Durée du poste                           | HcmPositionDurationEntity         | cdm_jobposition                  | Voir [remarque 1](#hr-notes). |
| cdm_jobposition - Hiérarchies du poste                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Voir [remarque 1](#hr-notes). |
| cdm_veteranstatus - Statut d'ancien combattant                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin - Origine ethnique                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode - Code langue                              |                                   | cdm_languagecode                 | |
| cdm_worker - Collaborateur                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments - Emplois                                 |                                   | cdm_employments                  | |
| cdm_employments - Détails de l'emploi                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps - Affectation du collaborateur au poste | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Voir [remarque 2](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Notes dédiées au mappage

1. Une entité Common Data Service est mappée à plusieurs entités d'application Finance and Operations.
2. Ce mappage a une auto-référence.

## <a name="asset-management-entities"></a>Entités Gestion des actifs

Les entités suivantes pour Gestion des actifs pour Dynamics 365 Supply Chain Management sont répertoriées dans l'ordre dans lequel vous devez les activer.

| Nom du mappage sur la page Double écriture | Nom des métadonnées d'entité dans Gestion des actifs | Nom des métadonnées d'entité dans Common Data Service | Notes |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Gestion des actifs  Actifs  Statuts du cycle de vie               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Gestion des actifs  Actifs  Modèles de cycle de vie               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Gestion des actifs  Postes techniques  Modèles de cycle de vie | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Gestion des actifs  Postes techniques  Statuts du cycle de vie | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Gestion des actifs  Types d'actifs                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Gestion des actifs  Types de postes techniques            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Gestion des actifs  Postes techniques                 | msdyn_functionallocations                | Voir [la remarque](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Gestion des actifs  Actifs                               | msdyn_customerassets                     | Voir [la remarque](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Gestion des actifs  Fabricants                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Modèles de gestion des actifs                               | msdyn_models                             | |
| FO.AssetManagementWarranty--Common Data Service.msdyn_warranties                                                 | Garantie de la gestion des actifs                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Notes dédiées au mappage

- En raison de l'autonomie, vous devrez peut-être exécuter la synchronisation initiale plusieurs fois.
