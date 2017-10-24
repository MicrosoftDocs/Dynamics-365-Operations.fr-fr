---
title: Synchroniser les produits provenant de Finance and Operations sur les produits du module Sales
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, édition Entreprise et Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: 063a20f133a00620bdf389b0a52a90bc61e2f7d4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>Synchroniser les produits provenant de Finance and Operations sur les produits du module Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, édition Entreprise et Microsoft Dynamics 365 for Sales.

## <a name="template-and-task"></a>Modèle et tâche

Les modèles et les tâches sous-jacentes suivants sont utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) et Microsoft Dynamics 365 for Sales (Sales).

-   Nom du modèle : Produits (Fin and Ops vers Sales)

-   Nom de la tâche dans le projet : Produits

Tâches de synchronisation requises avant la synchronisation Produit/client : aucune

## <a name="entity-set"></a>Ensemble d'entités

| **Finance and Operations** | **CDS** | **Ventes**  |
|----------------------------|---------|------------|
| Produits lancés vendables | Produit | Produits   |

## <a name="entity-flow"></a>Flux d'entité

Les produits sont gérés dans Finance and Operations et synchronisés avec Sales. L'entité de données **Produits lancés vendables** dans Finance and Operations exporte uniquement les produits vendables, ce qui signifie que les produits ont les informations obligatoires pour être utilisés sur une commande client. Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produit lancé**.

Le **Numéro de produit** est utilisé comme clé, ce qui signifie que les variantes de produit sont synchronisées sur CDS et Sales avec des **ID produits** individuels par **Variante de produit**.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Dans Sales, un nouveau champ sur les produits, **Géré en externe**, est ajouté pour indiquer qu'un produit donné est conservé en externe. La valeur est définie sur **Oui** par défaut lors de l'importation dans Sales.

-   **Géré en externe = Oui** : Le produit provient de Finance and Operations et n'est pas modifiable dans Sales.

-   **Géré en externe = Non** : Le produit est entré directement dans Sales.

-   **Géré en externe = Vide** : Le produit existe dans Sales avant d'activer la solution de prospect en disponibilités.

L'information **Géré en externe** est utilisée pour vous assurer que seuls **Devis** et **Commandes client** avec **Produits mis à jour en externe** se synchroniseront avec Finance and Operations.

Les **Produits mis à jour en externe** sont automatiquement ajoutés à la première **Liste des prix** valide avec la même devise. Notez que la liste est organisée alphabétiquement par **Nom**. Le prix de vente du produit de Finance and Operations est utilisé comme prix sur **Liste des prix**. Cela signifie qu'il doit y avoir une **Liste des prix** dans Sales pour chaque **Devise de vente de produit** dans Finance and Operations. La devise des produits vendables lancés est définie sur la devise comptable de l'entité juridique, depuis laquelle le produit est exporté.

> [!NOTE]
> La synchronisation de produit ne réussira pas sans **Liste des prix** dans la devise correspondante.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

-   Avant d'exécuter la toute première synchronisation, vous devez renseigner la **Table des produits distincts** pour les produits existants dans Finance and Operations. Les produits existants ne seront pas synchronisés tant que cette tâche ne sera pas terminée.

    -   Dans Finance and Operations, utilisez la fonction de recherche pour **Compléter la table des produits distincts**.

    -   Cliquez sur **Compléter la table des produits distincts** pour exécuter la tâche. Cette tâche doit être exécutée une seule fois.

-   Assurez-vous que la **ValueMap** nécessaire pour la vente d'**Unité de mesure** (UM) dans Finance and Operations existe dans **Source -\> Mise en correspondance CDS SalesUnitSymbol / DefaultSellingUnitOfMeasure**.

-   Mettez à jour l'**ID d'organisation CDS Organization_OrganizationId** dans **Source -\> CDS**.

    -   Le modèle de valeur par défaut est ORG001.

-   Mettez à jour **ValueMap** pour **Groupe d'unités** (**defaultuomscheduleid.name**) dans **CDS -\> Destination** pour correspondre au **Groupes d'unités** de Sales.

    -   Le modèle de valeur par défaut est **Unité par défaut**.

-   Assurez-vous que les UM de vente de produits de Finance and Operations existent dans Sales avec la valeur **Listes de prélèvements CDS**.

-   Assurez-vous que **Liste des prix** figurent dans Sales pour chaque devise de vente de produit dans Finance and Operations.

-   Les produits peuvent être créés dans Sales avec le statut **Brouillon** ou **Actif**. Cette opération est contrôlée dans **Paramètres système** sous **Sales** dans Sales.

    -   Les produits créés avec le statut de brouillon doivent être activés avant de pouvoir être ajoutés à **Devis** ou **Commande client**.

## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

![modèle de mise en correspondance dans l'intégrateur de données](./media/products-template-mapping-data-integrator-1.png)

![modèle de mise en correspondance pour les produits dans l'intégrateur de données](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Rubriques connexes

[Synchronisez les comptes des ventes aux clients de Finance and Operations](accounts-template-mapping.md)

[Synchroniser les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations](contacts-template-mapping.md)

[Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations](sales-quotation-template-mapping.md)

[Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales](sales-order-template-mapping.md)

[Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales](sales-invoice-template-mapping.md)


