---
title: Synchroniser les produits directement de Finance and Operations sur les produits du module Sales
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.sourcegitcommit: 0d409b3b7f19ca31d9c720bca191f1ddba81caa3
ms.openlocfilehash: def88c291538e3ef278c51e4b87462782e222de2
ms.contentlocale: fr-fr
ms.lasthandoff: 03/13/2018

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>Synchroniser les produits directement de Finance and Operations sur les produits du module Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître l'[intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits directement entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Le modèle et tâches sous-jacentes suivants sont utilisés pour synchroniser les produits de Finance and Operations vers Sales.

- Produits **Nom du modèle dans l'intégration des données :** (Fin and Ops to Sales) - Direct
- **Nom de la tâche dans le projet d'intégration de données :** Produits

Aucune tâche de synchronisation n'est nécessaire pour que la synchronisation des produits puisse se produire.

## <a name="entity-set"></a>Ensemble d'entités

| Finance and Operations     | Vente    |
|----------------------------|----------|
| Produits lancés vendables | Produits |

## <a name="entity-flow"></a>Flux d'entité

Les produits sont gérés dans Finance and Operations et synchronisés avec Sales. L'entité de données **Produits lancés vendables** dans Finance and Operations exporte uniquement les produits qui sont *vendables*. Les produits vendables sont des produits ayant toutes les informations requises pour être utilisés dans une commande client. Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produit lancé**.

Le numéro de produit est utilisé comme clé. Par conséquent, lorsque des variantes de produit sont synchronisées avec Sales, chaque variante de produit a un ID de produit individuel.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Dans Sales, un nouveau champ **Géré en externe** est ajouté sur les produits pour indiquer qu'un produit donné est conservé en externe. Par défaut, la valeur est définie sur **Oui** lors de l'importation dans Sales. Les valeurs disponibles sont les suivantes :

- **Oui** – Le produit provient de Finance and Operations et n'est pas modifiable dans Sales.
- **Non** – Le produit est entré directement dans Sales.
- **(Vide)** – Le produit existe dans Sales avant d'activer la solution de prospect en disponibilités.

Le champ **Géré en externe** aide à garantir que seuls les devis et les commandes client ayant des produits gérés en externes seront synchronisés avec Finance and Operations.

Les produits mis à jour en externe sont automatiquement ajoutés au premier tarif valide avec la même devise. Les tarifs sont organisés alphabétiquement par nom. Le prix de vente du produit de Finance and Operations est utilisé comme prix sur le tarif. Par conséquent, un tarif doit figurer dans Sales pour chaque devise de vente de produit dans Finance and Operations. La devise des produits vendables lancés est définie sur la devise comptable de l'entité juridique, depuis laquelle le produit est exporté.

> [!NOTE]
> La synchronisation de produits ne réussira pas si un tarif n'a pas de devise correspondante.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

- Avant d'exécuter la toute première synchronisation, vous devez renseigner la Table des produits distincts pour les produits existants dans Finance and Operations. Les produits existants ne seront pas synchronisés tant que cette tâche ne sera pas terminée.

    1. Dans Finance and Operations, utilisez la fonction de recherche pour **Compléter la table des produits distincts**.
    2. Cliquez sur **Compléter la table des produits distincts** pour exécuter la tâche. Cette tâche ne doit être exécutée qu'une seule fois.

- Assurez-vous que la mise en correspondance des valeurs requise pour l'unité de mesure de vente (UOM) entre Finance and Operations et Sales existe bien dans la mise en correspondance **SalesUnitSymbol** vers **DefaultUnit (Name)**.
- Mettez à jour la mise en correspondance de la valeur pour **Groupe d'unités** (**defaultuomscheduleid.name**) pour qu'il corresponde au  **Groupes d'unité** dans Sales.

    Le modèle de valeur par défaut est **Unité par défaut**.

- Assurez-vous que les UM de vente pour tous les produits de Finance and Operations existent dans Sales.
- Assurez-vous que les tarifs figurent dans Sales pour chaque devise de vente de produit dans Finance and Operations.
- Lorsque les produits sont créés dans Sales, ils peuvent avoir un statut **Brouillon** ou **Actif**. Le comportement est contrôlé dans **Paramètres** > **Administration** > **Paramètres système** > **Ventes** dans Sales.

    Les produits qui ont l'état **Brouillon** lors de leur création doivent être activés pour pouvoir être ajoutés aux devis ou aux commandes client.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de modèle de mise en correspondance dans l'intégration des données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.

![Mise en correspondance de modèles dans l'intégrateur de données](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping-direct.md)

[Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations](contacts-template-mapping-direct.md)

[Synchroniser directement les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales](sales-order-template-mapping-direct-two-ways.md)

[Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales](sales-invoice-template-mapping-direct.md)




