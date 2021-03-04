---
title: Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes depuis Dynamics 365 Sales vers Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 8aa03f94e0fb89a6d34ce014dbb6004a1a666327
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529208"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Common Data Service pour applications](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes directement depuis Dynamics 365 Sales vers Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales.  Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrez [Centre d'administrateur Power Apps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

L'exemple et la tâche sous-jacente suivants sont utilisés pour synchroniser les comptes de Sales vers Supply Chain Management :

- Comptes **Nom du modèle dans l'intégration des données :** (Sales à Fin and Ops) - Direct
- **Nom de la tâche dans le projet :** Comptes - Clients

Aucune tâche de synchronisation n'est nécessaire pour que la synchronisation Compte/Client puisse se produire.

## <a name="entity-set"></a>Ensemble d'entités

| Ventes    | Gestion de la chaîne d'approvisionnement |
|----------|------------------------|
| Comptes | Clients V2           |

## <a name="entity-flow"></a>Flux d'entité

Les comptes sont gérés dans Sales et synchronisés sur Supply Chain Management en tant que clients. La propriété **Géré en externe** sur ces clients est définie sur **Oui** pour suivre les clients issus de Sales. Lors de la facturation, ces informations sont utilisées pour filtrer les factures qui sont synchronisées sur Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Le champ **Numéro de compte** est disponible sur la page **Compte**. Une clé naturelle et unique a été créée pour prendre en charge l'intégration. La fonction de clé naturelle de la solution de gestion de la relation client (CRM) peut affecter les clients utilisant déjà le champ **Numéro de compte**, mais qui n'utilisez pas des valeurs **Numéro de compte** uniques par compte. Actuellement, la solution d'intégration ne prend pas en charge ce cas.

Lorsqu'un compte est créé, si une valeur **Numéro de compte** n'existe pas encore, elle est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée d'**ACC**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères. Voici un exemple : **ACC-01000-BVRCPS**

Lorsque la solution d'intégration pour Sales est appliquée, un script de mise à niveau définit le champ **Numéro de compte** sur les comptes existants dans Sales. S'il n'existe aucune valeur **Numéro de compte**, la souche de numéros qui a été mentionnée plus haut est utilisée.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

- Le mappage **CustomerGroupId** doit être mis à jour avec une valeur valide dans Supply Chain Management. Vous pouvez spécifier une valeur par défaut ou vous pouvez définir la valeur à l'aide d'une mise en correspondance des valeurs.

    Le modèle de valeur par défaut est **10**.

- En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Supply Chain Management. Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.

    - **SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Supply Chain Management. Un site par défaut peut être extrait du produit, ou du client de l'en-tête de commande.

        Le modèle de valeur par défaut est **1**.

    - **WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Supply Chain Management. Un entrepôt par défaut peut être extrait du produit, ou du client de l'en-tête de commande dans Supply Chain Management.

        Le modèle de valeur par défaut est **13**.

    - **LanguageId** – Un langage est requis pour générer des lignes de devis et de commande client dans Supply Chain Management. Par défaut, la langue de l'en-tête de commande du client est utilisée.

        Le modèle de valeur par défaut est **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Supply Chain Management.

![Mise en correspondance de modèles dans l'intégration de données](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Rubriques connexes


[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management](accounts-template-mapping-direct.md)

[Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management](contacts-template-mapping-direct.md)

[Synchronisation des commandes client directement entre Sales et Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synchroniser les en-têtes et les lignes de facture client directement entre le module Supply Chain Management et Sales](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]