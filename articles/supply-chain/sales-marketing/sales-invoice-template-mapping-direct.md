---
title: Synchroniser les en-têtes et les lignes de facture client directement entre le module Supply Chain Management et Sales
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture directement depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d7f104b3f2e132b5b517443577a020fda7fa9af3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975008"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Synchroniser les en-têtes et les lignes de facture client directement entre Finance and Operations et Sales

[!include [banner](../includes/banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture directement depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrez [Centre d'administrateur Power Apps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de facture entre Supply Chain Management et Sales :

- **Nom du modèle dans l'intégration des données :** Factures client (entre Fin and Ops et Sales) - Direct
- **Noms des tâches dans le projet d'intégration de données :**

    - SalesInvoiceHeader
    - SalesInvoiceLine

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de factures client puisse avoir lieu :

- Produits (Supply Chain Management vers Sales) - Direct
- Comptes (Sales vers Supply Chain Management) - Direct (si utilisé)
- Contacts (Sales vers Supply Chain Management) - Direct (si utilisé)
- En-têtes et lignes de commande client (Supply Chain Management vers Sales) - Direct

## <a name="entity-set"></a>Ensemble d'entités

| Gestion de la chaîne d'approvisionnement                              | Ventes          |
|------------------------------------------------------|----------------|
| En-têtes de facture de vente client gérée en externe | Factures       |
| Lignes de facture de vente client gérée en externe   | InvoiceDetails |

## <a name="entity-flow"></a>Flux d'entité

Les factures sont créées dans Supply Chain Management et synchronisées vers Sales.

> [!NOTE]
> Actuellement, la taxe associée aux frais dans l'en-tête de facture client n'est pas incluse dans la synchronisation entre Supply Chain Management et Sales. Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête. Toutefois, la taxe associée aux frais au niveau de la ligne est incluse dans la synchronisation.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

- Un champ **Numéro de facture** a été ajouté à l'entité **Facture** et apparaît sur la page.
- Le bouton **Créer une facture** sur la page **Commande client** est masqué car les factures sont créées dans Supply Chain Management et synchronisées avec Sales. La page **Facture** ne peut pas être modifiée car les factures sont synchronisées à partir de Supply Chain Management.
- La valeur **Statut de la commande client** passe automatiquement à **Facturé** lorsque la facture concernée dans Supply Chain Management a été synchronisée avec Sales. En outre, le propriétaire de la commande client pour laquelle la facture a été créée est désigné propriétaire de la facture. Par conséquent, le propriétaire de la commande client peut afficher la facture.

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
- Assurez-vous que la mise en correspondance des valeurs requise existe pour **SalesUnitSymbol** dans Supply Chain Management.

    Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **Quantité\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Supply Chain Management.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Mise en correspondance de modèles dans l'intégration de données](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Mise en correspondance de modèles dans l'intégration de données](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management](accounts-template-mapping-direct.md)

[Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Sales](products-template-mapping-direct.md)

[Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management](contacts-template-mapping-direct.md)

[Synchronisation des commandes client directement entre Sales et Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]