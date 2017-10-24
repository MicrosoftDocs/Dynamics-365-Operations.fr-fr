---
title: "Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 9117b5af3beff7290816586f63091b12e357339c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis entre Microsoft Dynamics 365 for Sales (Sales) et Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations). 

## <a name="template-and-tasks"></a>Modèle et tâches

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de devis entre Sales et Finance and Operations :

- **Nom du modèle :** Devis de vente (Sales vers Fin and Ops)
- **Noms des tâches du projet :**

    - QuoteHeader
    - QuoteLine

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de devis puisse être entreprise :

- Produits (entre Fin and Ops et Sales)
- Comptes (Entre Sales et Fin and Ops) (en cas d'utilisation)
- Contacts vers Clients (Sales vers Fin and Ops) (en cas d'utilisation)

## <a name="entity-set"></a>Ensemble d'entités

| Vente        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Citations       | Devis     | En-têtes de devis de vente   |
| QuoteDetails | QuotationLine | Lignes de devis de vente CDS |

## <a name="entity-flow"></a>Flux d'entité

Les devis sont créés dans Sales et synchronisés avec Finance and Operations.

Les devis sont synchronisés uniquement dans Sales si les conditions suivantes sont réunies :

- Tous les produits sur les lignes de devis sont mis à jour en externe.
- Le devis est actif ou activé.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Le champ **A des produits mis à jour en externe uniquement** a été ajouté à l'entité de devis pour effectuer le suivi uniformément si le devis consiste entièrement en produits mis à jour en externe. Si un devis comporte uniquement des produits mis à jour en externe, les produits sont mis à jour dans Finance and Operations. Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de devis avec des produits qui sont inconnus de Finance and Operations.

Tous les produits et lignes du devis sont mis à jour avec les informations **A des produits mis à jour uniquement en externe** de l'en-tête du devis. Ces informations figurent dans le champ **Le devis a des produits mis à jour uniquement en externe** sur l'entité ligne de devis.

Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations. Ce paramétrage ne prend pas en charge actuellement la mise en correspondance d'intégration. Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont maîtrisé et gérés par Finances and Operations.

Dans Sales, la solution rend les champs suivants en lecture seule, car les valeurs ne sont pas synchronisées avec Finance and Operations :

- **Champs en lecture seule sur l'en-tête de devis :** % de remise, Remise, volume de transport
- **Champs en lecture seule sur les lignes de devis :** Taxe

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Accédez à **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Ventes** et vérifiez que le champ **Mode de calcul de remise** est défini sur **Par unité**. Ce paramètre permet de garantir que la remise de l'article de ligne dans Sales correspond au paramètre de Finance and Operations. Sinon, la remise ne sera pas correcte dans Finance and Operations, car Finance and Operations lira la remise comme une remise par unité, même s'il s'agit d'une remise par ligne dans Sales.

### <a name="setup-in-finance-and-operations"></a>Configuration dans Finance and Operations

- Accédez à **Comptabilité client** &gt; **Configuration** &gt; **Paramètres de la comptabilité client**. Dans l'onglet **Souche de numéros**, sélectionnez la souche de numéros pour les devis, puis cliquez sur **Afficher les détails**. Ensuite, sous **Paramétrage général**, définissez le champ **Manuel** sur **Oui**.
- Accédez à **Comptabilité client** &gt; **Configuration** &gt; **Paramètres de la comptabilité client**. Puis, dans l'onglet **Expéditions**, définissez le champ **Vérification de la date de livraison** sur **Aucun**. Ce paramètre permet d'empêcher la synchronisation d'échouer pour les devis.

### <a name="setup-in-the-data-integration-project"></a>Paramétrage du projet d'intégration des données

#### <a name="quoteheader"></a>QuoteHeader

- Le champ **Date de livraison demandée** est requis dans Finance and Operations, et la synchronisation échoue si le champ est laissé vide. Pour éviter ce problème, si le champ est vide, une date par défaut est issue de **Source &gt; CDS**. La date doit être mise à jour avec une valeur recommandée. Actuellement, vous ne pouvez pas entrer de valeur comme **Aujourd'hui** pour représenter la date du jour. Vous devez entrer une date spécifique. Le modèle de valeur par défaut pour **Date de livraison demandée** est **1/1/2020**.
- Le champ **Adresse Pays Région Code** est requis dans Finance and Operations. Pour empêcher les erreurs de synchronisation, vous pouvez spécifier une valeur par défaut utilisée si le champ est laissé vide dans Sales. Cette valeur par défaut est également utile, car vous ne devez pas entrer manuellement de valeur dans le champ **Pays/Région** pour les adresses locales. Il n'existe aucun modèle de valeur par défaut pour **DeliveryAddressCountryRegionISOCode**.
- Mettez la mise en correspondance à jour pour **ID organisation CDS** dans **Source &gt; CDS** afin qu'elle corresponde à **Organisation CDS** dans l'entité Organisation :

    - Le modèle de valeur par défaut pour **Organization_OrganizationId** est **ORG001**.
    - Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est **ORG001**.
    - Le modèle de valeur par défaut pour **InvoiceAccount_OrganizationId** est **ORG001**.

#### <a name="quoteline"></a>QuoteLine

- Mettez la mise en correspondance à jour pour **ID organisation CDS** dans **Source &gt; CDS** afin qu'elle corresponde à **Organisation CDS** dans l'entité Organisation :

    - Le modèle de valeur par défaut pour **Organization_OrganizationId** est **ORG001**.
    - La valeur par défaut du modèle pour **Product_Organization_Organization_OrganizationId** est **ORG001**.
    - La valeur par défaut du modèle pour **Quotation_Organization_Organization_OrganizationId** est **ORG001**.

- Le champ **Date de livraison demandée** est requis dans Finance and Operations, et la synchronisation échoue si le champ est laissé vide. Pour éviter ce problème, si le champ est vide, une date par défaut est issue de **Source &gt; CDS**. La date doit être mise à jour avec une valeur recommandée. Actuellement, vous ne pouvez pas entrer de valeur comme **Aujourd'hui** pour représenter la date du jour. Vous devez entrer une date spécifique. Le modèle de valeur par défaut pour **Date de livraison demandée** est **1/1/2020**.
- Vous pouvez ajouter les mises en correspondance suivantes de **CDS &gt; Destination** pour vérifier que les lignes de devis sont importées dans Finances and Operations s'il n'existe aucune information par défaut du client ou du produit :

    - **SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations. Il n'existe aucun modèle de valeur par défaut pour **SiteId**.
    - **WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations. Il n'existe aucun modèle de valeur par défaut pour **WarehouseId**.

- Assurez-vous que la mise en correspondance des valeurs requise pour l'unité de mesure de vente (UOM) dans Finance and Operations existe dans la mise en correspondance **CDS &gt; Destination** pour **Quantity_UOM** vers **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

> [!NOTE]
> - Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations. Ce paramétrage ne prend pas en charge actuellement la mise en correspondance d'intégration. Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont gérés par Finances and Operations.
> - Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

### <a name="quoteheader"></a>QuoteHeader

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Rubriques connexes

[Synchronisez les produits de Finance and Operations sur les produits de Sales](products-template-mapping.md)

[Synchroniser les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping.md)

[Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations](contacts-template-mapping.md)



