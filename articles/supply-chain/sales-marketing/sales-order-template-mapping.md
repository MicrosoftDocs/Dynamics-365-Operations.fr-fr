---
title: "Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 707efc97afc0679ed1fc22539789e98cbabcb581
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales

[!include[banner](../includes/banner.md)]

La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales. 

## <a name="template-and-tasks"></a>Modèle et tâches

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de commande client entre Finance and Operations et Sales :

- **Nom du modèle dans l'intégration des données** 

    - Commandes client (entre Fin and Ops et Sales)
    
- **Noms des tâches du projet d'intégration de données**

    - OrderHeader
    - OrderLine

Tâches de synchronisation requises avant l'en-tête et les lignes synchronisation de facture client :

- Produits (entre Fin and Ops et Sales)
- Comptes (Entre Sales et Fin and Ops) (en cas d'utilisation)
- Contacts vers Clients (Sales vers Fin and Ops) (en cas d'utilisation)

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations |    Common Data Service (CDS)         |     Vente      |
|------------------------|----------------|----------------|
| En-têtes de commande client CDS| SalesOrder     | SalesOrders |
| Lignes de commande client CDS  | SalesOrderLine | SalesOrderDetails|

## <a name="entity-flow"></a>Flux d'entité

Les commandes client sont créées dans Finance and Operations et synchronisées avec Sales.

Les filtres dans le modèle garantissent que seules les commandes client appropriées sont incluses dans la synchronisation :

- La commande et la facturation client sur la commande client provenant de Sales seront incluses dans la synchronisation. Dans Finance and Operations, les champs **OrderingCustomerIsExternallyMaintained** et **InvoiceCustomerIsExternallyMaintained** permettent de suivre la synchronisation dans les entités de données.

- La **commande client** dans Finance and Operations doit être confirmée. Seules les commandes client confirmées ou les commandes client dont le statut de traitement le plus élevé, par exemple, Livré ou Facturé, sont synchronisées avec Sales.

- Après avoir créé ou modifié une commande client, le traitement par lots **Calcule les totaux de vente** dans Finance and Operations doit être exécuté. Seules les commandes client avec des totaux de vente calculés seront synchronisés avec CDS et Sales.

> [!NOTE]
> La taxe associée aux frais dans **En-tête de commande client** n'est actuellement pas incluse dans la synchronisation entre Finance and Operations et Sales. En effet, Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête. La taxe associée aux frais au niveau de la ligne est incluse.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

De nouveaux champs sont ajoutés à l'entité **Commande** et s'affichent sur la page :

- **Est conservé en externe** - Défini sur **Oui** lorsque la commande provient de Finance and Operations.

- **Statut de traitement** - Utilisé pour afficher le statut de traitement de la commande dans Finance and Operations. Les valeurs sont les suivantes :

    - Active
    - Confirmée
    - Bon de livraison
    - Facturé
    - Prélevé
    - Partiellement prélevé
    - Partiellement emballé
    - Expédié
    - Partiellement expédié
    - Partiellement facturé
    - Annulé

Le paramètre **Le devis a des produits mis à jour uniquement en externe** est utilisé dans d'autres scénarios de commande client (synchronisation entre Sales et Finance and Operation) pour gérer de façon cohérente si la commande client comprend entièrement les **Produits mis à jour en externe**, dans le cas présent les produits sont gérés dans Finance and Operations. Cela permet de garantir que vous ne tenterez pas de synchroniser les lignes de commande avec des produits qui sont inconnus de Finance and Operations.
 
Les boutons **Créer une facture**, **Annuler la commande**, **Recalculer**, **Obtenir des produits** et **Adresse de recherche** sur la page **Commande client** sont masqués pour les commandes gérées en externe car les factures sont créées dans Finance and Operations et synchronisées avec Sales. La page de commande ne peut pas être modifiée car les informations de commande client sont synchronisées à partir de Finance and Operations.
 
Le **Statut de la commande client** restera actif pour garantir que les modifications effectuées dans Finance and Operations peuvent être répercutées dans la **Commande client** avec Sales. Cette opération est contrôlée en définissant le paramètre par défaut **Statecode [Statut]** sur **Actif** dans le projet d'intégration de données.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance 

Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Vérifiez les autorisations de l'équipe à laquelle l'utilisateur est affecté (à partir des **paramètres de connexion** dans Sales). Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe. Sans cela vous obtiendrez une erreur disant que l'équipe principale est manquante lors de l'exécution du projet depuis l'intégrateur de données. 

    - Sous **Paramètres** > **Sécurité** > **Équipes**, sélectionnez l'équipe appropriée, cliquez sur **Gestion des rôles**, puis sélectionnez un rôle avec les autorisations souhaitées, par exemple, celles d'administrateur système.

- Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que le paramètre **Utiliser le système de calcul du prix du système** est défini sur **Oui**. 

- Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que **Mode de calcul de remise** est défini sur **Ligne**. 

### <a name="setup-in-finance-and-operations"></a>Configuration dans Finance and Operations

Définissez **Ventes et marketing** > **Tâches périodiques** > **Calcule les totaux de vente** pour une exécution en tant que traitement par lots, avec **Calculer les totaux des commandes client** définie sur **Oui**. Cela est important car seules les commandes client avec des totaux de vente calculés seront synchronisés avec CDS et Sales. La fréquence du traitement par lots doit être alignée avec la fréquence de la synchronisation des commandes client.

### <a name="setup-in-the-data-integration-project"></a>Paramétrage du projet d'intégration des données

#### <a name="salesheader-task"></a>Tâche SalesHeader

- Mettez à jour la **Mise en correspondance pour l'ID organisation CDS dans Source** > **CDS**.

    - Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est ORG001.
    - La valeur du modèle par défaut pour **InvoiceAccount_Organization_OrganizationId** est ORG001.
    - Le modèle de valeur par défaut pour **Organization_OrganizationId** est ORG001.

- Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS pour InvoiceCountryRegionId à BillingAddress_Country** et **DeliveryCountryRegionId à DeliveryAddress_Country**.

    - La valeur du modèle est **ValueMap** avec un numéro de pays mis en correspondance.

- La **Liste des prix** est requise pour créer des commandes dans Sales. Mettez à jour **ValueMap** dans **CDS** > **Destination** pour **pricelevelid.name [Nom des tarifs]** dans la **Liste des prix** utilisée dans Sales par devise. Vous pouvez utiliser la **Liste des prix** par défaut pour une seule devise ou utiliser **ValueMap** si vous avez des **Listes de prix** dans plusieurs devises.
    
    - La valeur de modèle par défaut pour **pricelevelid.name [Nom des tarifs]** est le service CRM USA (exemple). 

#### <a name="salesline-task"></a>Tâche SalesLine

- Mettez à jour la **Mise en correspondance pour l'ID organisation CDS dans Source** > **CDS**. 
    
    - La valeur du modèle par défaut pour **SalesOrder_Organization_OrganizationId** est ORG001.
    - Le modèle de valeur par défaut pour **Product_Organization_OrganizationId** est ORG001.

- Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS** pour **DeliveryCountryRegionId** dans **DeliveryAddress_Country**.

    - La valeur du modèle est **ValueMap** avec un numéro de pays mis en correspondance.
    
- Assurez-vous que **ValueMap** nécessaire pour **SalesUnitSymbol** dans Finance and Operations existe dans **Source** > **Mise en correspondance CDS**.

    - La valeur du modèle avec **ValueMap** est définie sur **SalesUnitSymbol à Quantity_UOM**.

## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

### <a name="orderheader"></a>OrderHeader

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>OrderLine

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Rubriques connexes

[Synchronisez les produits de Finance and Operations sur les produits de Sales](products-template-mapping.md)

[Synchroniser les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping.md)

[Synchroniser les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations](contacts-template-mapping.md)

[Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations](sales-quotation-template-mapping.md)

[Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales](sales-invoice-template-mapping.md)


