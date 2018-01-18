---
title: "Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales."
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
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fb5ba099911deda5308daf92d82cd6b3489995bf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales

[!include[banner](../includes/banner.md)]

La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales. 

## <a name="templates-and-tasks"></a>Modèles et tâches

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de facture client entre Finance and Operations et Sales :

- **Nom du modèle dans l'intégration des données** 

     - Factures client (entre Fin and Ops et Sales)

- **Noms des tâches dans le projet d'intégration de données**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Tâches de synchronisation requises avant l'en-tête et les lignes synchronisation de facture client :
-   Produits (entre Fin and Ops et Sales)
-   Comptes (Entre Sales et Fin and Ops) (en cas d'utilisation)
-   Contacts (Entre Sales et Fin and Ops) (en cas d'utilisation)
-   En-tête et lignes de commande client (Entre Fin and Ops et Sales)

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations                               | Common Data Service (CDS)              | Vente          |
|------------------------------------------------------|------------------|----------------|
| En-têtes de facture de vente client gérée en externe | SalesInvoice     | Factures       |
| Lignes de facture de vente client gérée en externe   | SalesInvoiceLine | InvoiceDetails |

## <a name="entity-flow"></a>Flux d'entité

Les factures client sont créées dans Finance and Operations et synchronisées avec Sales.

> [!NOTE]
> La taxe associée aux frais dans **En-têtes de facture client** n'est actuellement pas incluse dans la synchronisation entre Finance and Operations et Sales. En effet, Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête. La taxe associée aux frais au niveau de la ligne est incluse.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

-  Un **Champ de numéro de facture** est ajouté à l'entité **Facture** et apparaît sur la page.
 
-  Le bouton **Créer une facture** sur la page **Commande client** est masqué car les factures sont créées dans Finance and Operations et synchronisées avec Sales. La page **Facture** ne peut pas être modifiée car les factures sont synchronisées à partir de Finance and Operations.
 
-  Le **Statut de la commande client** passe automatiquement à **Facturé** lorsque la facture concernée dans Finance and Operations a été synchronisée avec Sales. En outre, le propriétaire de la commande client pour laquelle la facture a été créée est désigné propriétaire de la facture. Cela donne au propriétaire de la commande client la capacité d'afficher la facture.
 
## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les factures client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que le paramètre **Utiliser le système de calcul du prix du système** est défini sur **Oui**. 

- Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que **Mode de calcul de remise** est défini sur **Ligne**. 

### <a name="setup-in-the-data-integration-project"></a>Paramétrage du projet d'intégration des données

#### <a name="salesinvoiceheader-task"></a>Tâche SalesInvoiceHeader

- Mettez à jour la mise en correspondance pour **ID organisation CDS** dans **Source** > **CDS**. 

    -  La valeur du modèle par défaut pour **SalesOrder_Organization_OrganizationId** est ORG001.
    -  Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est ORG001.
    -  Le modèle de valeur par défaut pour **Organization_OrganizationId** est ORG001.

- Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS pour InvoiceCountryRegionId** dans **BillingAddress_Country**.

    -  La valeur du modèle est **ValueMap** avec un numéro de pays mis en correspondance.

- La **Liste des prix** est requise pour créer des factures dans Sales. Mettez à jour **ValueMap** dans **CDS** > **Destination pour pricelevelid.name [Nom des tarifs]** dans la **Liste des prix** utilisée dans Sales par devise. Vous pouvez utiliser la **Liste des prix** par défaut pour une seule devise ou utiliser **ValueMap** si vous avez des **Listes de prix** dans plusieurs devises.

    -  La valeur de modèle pour **pricelevelid.name [Nom des tarifs]** est **ValueMap** en fonction de la **Devise**.
    -  usd: CRM Service USA (exemple). 

#### <a name="salesinvoiceline-task"></a>Tâche SalesInvoiceLine

- Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS pour l'unité de mesure**.

- Assurez-vous que **ValueMap** nécessaire pour **SalesUnitSymbol** dans Finance and Operations existe dans **Source** > **Mise en correspondance CDS**. 
    
    - La valeur du modèle avec **ValueMap** est définie sur **SalesUnitSymbol à Quantity_UOM**.
    
-  Mettez à jour la **Mise en correspondance pour l'ID organisation CDS dans Source** > **CDS**. 

    -  La valeur du modèle par défaut pour **SalesInvoicer_Organization_OrganizationId** est ORG001.
    -  Le modèle de valeur par défaut pour **Product_Organization_OrganizationId** est ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. La mise en correspondance de ces champs nécessite la mise en place d'un mappage de valeurs, spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Rubriques connexes

[Synchronisez les produits de Finance and Operations sur les produits de Sales](products-template-mapping.md)

[Synchroniser les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping.md)

[Synchroniser les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations](contacts-template-mapping.md)

[Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations](sales-quotation-template-mapping.md)

[Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales](sales-order-template-mapping.md)


