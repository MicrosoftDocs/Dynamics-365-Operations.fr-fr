---
title: Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Sales
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
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
ms.openlocfilehash: ecee843b6c09c86b4e40ab34cc113e5a7e7c76f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977686"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Sales

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Microsoft Dataverse pour applications](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits directement depuis Dynamics 365 Supply Chain Management vers Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrez [Centre d'administrateur Power Apps](https://admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

L'exemple suivant et les tâches sous-jacentes sont utilisés pour synchroniser les produits de Supply Chain Management vers Sales.

- Produits **Nom du modèle dans l'intégration des données :** (Supply Chain Management vers Sales) - Direct
- **Nom de la tâche dans le projet d'intégration de données :** Produits

Aucune tâche de synchronisation n'est nécessaire pour que la synchronisation des produits puisse se produire.

## <a name="entity-set"></a>Ensemble d'entités

| Gestion de la chaîne d'approvisionnement    | Ventes    |
|----------------------------|----------|
| Produits lancés vendables | Produits |

## <a name="entity-flow"></a>Flux d'entité

Les produits sont gérés dans Supply Chain Management et synchronisés vers Sales. L'entité de données **Produits lancés vendables** dans Supply Chain Management exporte uniquement les produits qui sont *vendables*. Les produits vendables sont des produits ayant toutes les informations requises pour être utilisés dans une commande client. Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produit lancé**.

Le numéro de produit est utilisé comme clé. Par conséquent, lorsque des variantes de produit sont synchronisées avec Sales, chaque variante de produit a un ID de produit individuel.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Dans Sales, un nouveau champ **Géré en externe** est ajouté sur les produits pour indiquer qu'un produit donné est conservé en externe. Par défaut, la valeur est définie sur **Oui** lors de l'importation dans Sales. Les valeurs disponibles sont les suivantes :

- **Oui** – Le produit provient de Supply Chain Management et n'est pas modifiable dans Sales.
- **Non** – Le produit est entré directement dans Sales.
- **(Vide)** – Le produit existe dans Sales avant d'activer la solution de prospect en disponibilités.

Le champ **Géré en externe** aide à garantir que seuls les devis et les commandes client ayant des produits gérés en externes seront synchronisés avec Supply Chain Management.

Les produits mis à jour en externe sont automatiquement ajoutés au premier tarif valide avec la même devise. Les tarifs sont organisés alphabétiquement par nom. Le prix de vente du produit de Supply Chain Management est utilisé comme prix sur le tarif. Par conséquent, un tarif doit figurer dans Sales pour chaque devise de vente de produit dans Supply Chain Management. La devise des produits vendables lancés est définie sur la devise comptable de l'entité juridique, depuis laquelle le produit est exporté.

> [!NOTE]
> - La synchronisation des produits ne réussit pas si une liste de prix n'a pas de devise correspondante.
> - Vous pouvez contrôler la liste de prix utilisée avec l'intégration en mettant en correspondance le pricelevelid.name [Liste de prix par défaut (nom)] dans le projet d'intégration de données. La saisie doit être effectuée en lettres minuscules. Par exemple, la valeur par défaut pour une liste de prix dans Sales nommée « Standard » est : Champ de destination : pricelevelid.name [Liste de prix par défaut (nom)] et Type de carte : [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

- Avant d'exécuter la toute première synchronisation, vous devez renseigner la Table des produits distincts pour les produits existants dans Supply Chain Management. Les produits existants ne seront pas synchronisés tant que cette tâche ne sera pas terminée.

    1. Dans Supply Chain Management, utilisez la fonction de recherche pour **Compléter la table des produits distincts**.
    2. Cliquez sur **Compléter la table des produits distincts** pour exécuter la tâche. Cette tâche ne doit être exécutée qu'une seule fois.

- Assurez-vous que la mise en correspondance des valeurs requise pour l'unité de mesure de vente (UOM) entre Supply Chain Management et Sales existe bien dans la mise en correspondance **SalesUnitSymbol** vers **DefaultUnit (Name)**.
- Mettez à jour la mise en correspondance de la valeur pour **Groupe d'unités** (**defaultuomscheduleid.name**) pour qu'il corresponde au  **Groupes d'unité** dans Sales.

    Le modèle de valeur par défaut est **Unité par défaut**.

- Assurez-vous que les UM de vente pour tous les produits de Supply Chain Management existent dans Sales.
- Assurez-vous que les tarifs figurent dans Sales pour chaque devise de vente de produit dans Supply Chain Management.
- Lorsque les produits sont créés dans Sales, ils peuvent avoir un statut **Brouillon** ou **Actif**. Le comportement est contrôlé dans **Paramètres** > **Administration** > **Paramètres système** > **Ventes** dans Sales.

    Les produits qui ont l'état **Brouillon** lors de leur création doivent être activés pour pouvoir être ajoutés aux devis ou aux commandes client.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

L'illustration suivante présente un exemple de modèle de mise en correspondance dans l'intégration des données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Supply Chain Management.

![Mise en correspondance de modèles dans l'intégrateur de données](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management](accounts-template-mapping-direct.md)

[Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management](contacts-template-mapping-direct.md)

[Synchronisation des commandes client directement entre Sales et Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synchroniser les en-têtes et les lignes de facture client directement entre le module Supply Chain Management et Sales](sales-invoice-template-mapping-direct.md)



