---
title: Synchroniser les en-têtes et les lignes de devis de vente directement entre Sales et Finance and Operations
description: La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis de vente directement depuis Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: efe943f5c874ed041ce7984272ebc19f57cca6ef
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313794"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a>Synchroniser directement les en-têtes et les lignes de devis provenant du module Sales sur Finance and Operations

[!include [banner](../includes/banner.md)]

La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis de vente directement depuis Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Common Data Service pour applications](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales. Les modèles Prospect en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données pour les comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Modèle et tâches

Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de devis directement entre Sales et Finance and Operations :

- **Nom du modèle dans l'intégration des données :** Devis de vente (entre Sales et Fin and Ops) - Direct
- **Noms des tâches dans le projet d'intégration de données :**

    - QuoteHeader
    - QuoteLine

Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de devis puisse être entreprise :

- Produits (entre Fin and Ops et Sales) - Direct
- Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)
- Contacts vers Clients (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)

## <a name="entity-set"></a>Ensemble d'entités

| Vente        | Finance and Operations     |
|--------------|----------------------------|
| Citations       | En-tête de devis de vente CDS |
| QuoteDetails | Lignes de devis de vente CDS  |

## <a name="entity-flow"></a>Flux d'entité

Les devis sont créés dans Sales et synchronisés avec Finance and Operations.

Les devis sont synchronisés uniquement dans Sales si les conditions suivantes sont réunies :

- Tous les produits sur les devis de vente sont mis à jour en externe.
- Une fois que vous avez cliqué sur **Activer le devis**, le devis de vente est actif.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Le champ **A des produits mis à jour en externe uniquement** a été ajouté à l'entité **Devis** pour effectuer le suivi uniformément si le devis consiste entièrement en produits mis à jour en externe. Si un devis comporte uniquement des produits mis à jour en externe, les produits sont mis à jour dans Finance and Operations. Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de devis ayant des produits qui sont inconnus de Finance and Operations.

Tous les produits du devis de vente sont mis à jour avec les informations **A des produits mis à jour uniquement en externe** de l'en-tête du devis de vente. Ces informations figurent dans le champ **Le devis a des produits mis à jour uniquement en externe** sur l'entité **QuoteDetails** .

Une remise peut être ajoutée au produit du devis et sera synchronisée avec Finance and Operations Les champs **Remise**, **Frais** et **Taxe** sont de l'en-tête sont contrôlés par un paramétrage complexe dans Finance and Operations. Actuellement, ce paramétrage ne prend pas en charge la mise en correspondance d'intégration. Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont mis à jour et gérés dans Finance and Operations.

Dans Sales, la solution rend les champs suivants en lecture seule, car les valeurs ne sont pas synchronisées avec Finance and Operations :

- Champs en lecture seule sur l'en-tête de devis : **% de remise**, **Remise** et **Volume de transport**
- Champs en lecture seule sur les produits du devis : **Taxe**

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

Avant de synchroniser les devis de vente, il est important de mettre les systèmes à jour avec les paramètres suivants :

### <a name="setup-in-sales"></a>Configuration dans Sales

- Vérifiez que les autorisations sont bien définies pour l'équipe à laquelle l'utilisateur est affecté (à partir de votre connexion dans Sales). Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe. Si l'équipe n'a pas accès d'administrateur lors de l'exécution du projet à partir de l'intégrateur de données, vous recevrez un message d'erreur indiquant que l'équipe principale est manquante.

    Pour définir les autorisations pour l'équipe, allez dans &gt; **Paramètres** **Sécurité** &gt; **Équipes**, puis sélectionnez l'équipe appropriée. Sélectionnez **Gestion des rôles**, puis sélectionnez un rôle qui a les autorisations souhaitées, tel que **Administrateur système**.

- Allez dans **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Sales**, et assurez-vous que les paramètres suivants sont utilisés :

    - L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.
    - Le champ **Mode de calcul de remise** est défini sur **Ligne article**.

### <a name="setup-in-the-data-integration-project"></a>Paramétrage du projet d'intégration des données

#### <a name="quoteheader"></a>QuoteHeader

- Assurez-vous que la mise en correspondance nécessaire existe pour **Shipto\_country** avec **DeliveryAddressCountryRegionISOCode**. Dans la mise en correspondance des valeurs, vous pouvez définir une valeur par défaut qui est utilisée si la valeur reste vide. Laissez le côté gauche vide, puis définissez le côté droit sur le pays ou la région souhaité(e). Ainsi, vous n'avez pas à entrer le pays ou la région pour des commandes nationales.

    La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance et où une valeur nulle correspond à une valeur **US**.

#### <a name="quoteline"></a>QuoteLine

- Assurez-vous que la mise en correspondance des valeurs requise existe pour **SalesUnitSymbol** dans Finance and Operations.
- Vérifiez que les unités nécessaires sont définies dans Sales.

    Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **oumid.name** sur **SalesUnitSymbol**.

- Facultatif : Vous pouvez ajouter les mises en correspondance suivantes pour vérifier que les lignes de devis de vente sont importées dans Finance and Operations s'il n'existe aucune information par défaut du client ou du produit :

    - **SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations. Il n'existe aucun modèle de valeur par défaut pour **SiteId**.
    - **WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations. Il n'existe aucun modèle de valeur par défaut pour **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

> [!NOTE]
> - Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations. Actuellement, ce paramétrage ne prend pas en charge la mise en correspondance d'intégration. Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont gérés par Finances and Operations.
> - Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut. Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

### <a name="quoteheader"></a>QuoteHeader

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

