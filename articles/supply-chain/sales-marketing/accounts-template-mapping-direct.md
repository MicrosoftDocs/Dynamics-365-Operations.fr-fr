---
title: Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes Microsoft Dynamics 365 for Sales à Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 16bbca2d9eb8c3d9c33752404ebecbe4415517a2
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a>Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître l'[intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes directement entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales.  Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

L'exemple et la tâche sous-jacente suivants sont utilisés pour synchroniser les comptes de Sales vers Finance and Operations :

- Comptes **Nom du modèle dans l'intégration des données :** (Sales à Fin and Ops) - Direct
- **Nom de la tâche dans le projet :** Comptes - Clients

Aucune tâche de synchronisation n'est nécessaire pour que la synchronisation Compte/Client puisse se produire.

## <a name="entity-set"></a>Ensemble d'entités

| Vente    | Finance and Operations |
|----------|------------------------|
| Comptes | Clients V2           |

## <a name="entity-flow"></a>Flux d'entité

Les comptes sont gérés dans Sales et synchronisés sur Finance and Operations en tant que clients. La propriété **Géré en externe** sur ces clients est définie sur **Oui** pour suivre les clients issus de Sales. Lors de la facturation, ces informations sont utilisées pour filtrer les factures qui sont synchronisées sur Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Le champ **Numéro de compte** est disponible sur la page **Compte**. Une clé naturelle et unique a été créée pour prendre en charge l'intégration. La fonction de clé naturelle de la solution de gestion de la relation client (CRM) peut affecter les clients utilisant déjà le champ **Numéro de compte**, mais qui n'utilisez pas des valeurs **Numéro de compte** uniques par compte. Actuellement, la solution d'intégration ne prend pas en charge ce cas.

Lorsqu'un compte est créé, si une valeur **Numéro de compte** n'existe pas encore, elle est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée d'**ACC**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères. Voici un exemple : **ACC-01000-BVRCPS**

Lorsque la solution d'intégration pour Sales est appliquée, un script de mise à niveau définit le champ **Numéro de compte** sur les comptes existants dans Sales. S'il n'existe aucune valeur **Numéro de compte**, la souche de numéros qui a été mentionnée plus haut est utilisée.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

- Le mappage **CustomerGroupId** doit être mis à jour avec une valeur valide dans Finance and Operations. Vous pouvez spécifier une valeur par défaut ou vous pouvez définir la valeur à l'aide d'une mise en correspondance des valeurs.

    Le modèle de valeur par défaut est **10**.

- En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Finance and Operations. Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.

    - **SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations. Un site par défaut peut être extrait du produit, ou du client de l'en-tête de commande.

        Le modèle de valeur par défaut est **1**.

    - **WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations. Un entrepôt par défaut peut être extrait du produit, ou du client de l'en-tête de commande dans Finance and Operations.

        Le modèle de valeur par défaut est **13**.

    - **LanguageId** – Une langue est requise pour générer des devis et des commandes client dans Finance and Operations. Par défaut, la langue de l'en-tête de commande du client est utilisée.

        Le modèle de valeur par défaut est **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.

![Mise en correspondance de modèles dans l'intégration de données](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Rubriques connexes


[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping-direct.md)

[Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations](contacts-template-mapping-direct.md)

[Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales](sales-order-template-mapping-direct.md)

[Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales](sales-invoice-template-mapping-direct.md)


