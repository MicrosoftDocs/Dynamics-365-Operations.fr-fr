---
title: "Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture client directement entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: afbf4a24b737cf7221bac4b688b8801b1bcd839c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synchroniser directement les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales

[!include [banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture client directement entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de facture client entre Finance and Operations et Sales :

- **Nom du modèle dans l'intégration des données :** Factures client (entre Fin and Ops et Sales) - Direct
- **Noms des tâches dans le projet d'intégration de données :**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de factures client puisse avoir lieu :

- Produits (entre Fin and Ops et Sales) - Direct
- Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)
- Contacts (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)
- En-tête et lignes de commande client (entre Fin and Ops et Sales) - Direct

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations                               | Vente          |
|------------------------------------------------------|----------------|
| En-têtes de facture de vente client gérée en externe | Factures       |
| Lignes de facture de vente client gérée en externe   | InvoiceDetails |

## <a name="entity-flow"></a>Flux d'entité

Les factures client sont créées dans Finance and Operations et synchronisées avec Sales.

> [!NOTE]
> Actuellement, la taxe associée aux frais dans l'en-tête de facture client n'est pas incluse dans la synchronisation entre Finance and Operations et Sales. Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête. Toutefois, la taxe associée aux frais au niveau de la ligne est incluse dans la synchronisation.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

- Un champ **Numéro de facture** a été ajouté à l'entité **Facture** et apparaît sur la page.
- Le bouton **Créer une facture** sur la page **Commande client** est masqué car les factures sont créées dans Finance and Operations et synchronisées avec Sales. La page **Facture** ne peut pas être modifiée car les factures sont synchronisées à partir de Finance and Operations.
- La valeur **Statut de la commande client** passe automatiquement à **Facturé** lorsque la facture concernée dans Finance and Operations a été synchronisée avec Sales. En outre, le propriétaire de la commande client pour laquelle la facture a été créée est désigné propriétaire de la facture. Par conséquent, le propriétaire de la commande client peut afficher la facture.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les factures client, il est important de mettre les systèmes à jour avec le paramètre suivant :

### <a name="setup-in-sales"></a>Configuration dans Sales

Allez dans **Paramètres** > **Administration** > **Paramètres système** > **Sales**, et assurez-vous que les paramètres suivants sont utilisés :

- L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.
- Le champ **Mode de calcul de remise** est défini sur **Ligne article**.

### <a name="setup-in-the-data-integration-project"></a>Paramétrage du projet d'intégration des données

#### <a name="salesinvoiceheader-task"></a>Tâche SalesInvoiceHeader

- Assurez-vous que la mise en correspondance nécessaire existe pour **InvoiceCountryRegionId** dans **BillingAddress\_Country**.

    La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance.

- Un tarif est requis pour créer des factures dans Sales. Mettez à jour la mise en correspondance de la valeur pour **pricelevelid.name \[Nom des tarifs\]** sur la liste des prix utilisée dans Sales par devise. Vous pouvez utiliser le tarif par défaut pour une seule devise. Sinon, si vous avez un tarif dans plusieurs devises, vous pouvez utiliser une mise en correspondance des valeurs.

    La valeur de modèle pour **pricelevelid.name \[Nom des tarifs\]** est une mise en correspondance des valeurs basée sur la devise avec USD = CRM Service USA (exemple).  
    
#### <a name="salesinvoiceline-task"></a>Tâche SalesInvoiceLine

- Assurez-vous que la mise en correspondance nécessaire existe pour **Unité de mesure**.
- Assurez-vous que la mise en correspondance des valeurs requise pour **SalesUnitSymbol** dans Finance and Operations existe.

    Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **Quantité\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Mise en correspondance de modèles dans l'intégration de données](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Mise en correspondance de modèles dans l'intégration de données](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping-direct.md)

[Synchroniser directement les produits provenant de Finance and Operations sur les produits du module Sales](products-template-mapping-direct.md)

[Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations](contacts-template-mapping-direct.md)

[Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales](sales-order-template-mapping-direct-two-ways.md)







