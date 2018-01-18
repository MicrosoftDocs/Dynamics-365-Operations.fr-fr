---
title: Synchronisez les comptes des ventes aux clients de Finance and Operations
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes Microsoft Dynamics 365 for Sales à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
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
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: f322c5b273c29d863c059092bf1a41c424c19a7d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>Synchronisez les comptes des ventes aux clients de Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes Microsoft Dynamics 365 for Sales (Sales) à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations).

## <a name="template-and-task"></a>Modèle et tâche

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les comptes de Sales vers Finance and Operations :

- **Nom du modèle :** Comptes (Sales vers Fin and Ops)
- **Nom de la tâche dans le projet :** Comptes - compte - clients

Tâches de synchronisation requises avant la synchronisation Compte/client : aucune

## <a name="entity-set"></a>Ensemble d'entités

| Vente    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Comptes | Compte | Clients              |

## <a name="entity-flow"></a>Flux d'entité

Les comptes sont gérés dans Sales et synchronisés sur Finance and Operations en tant que clients. La propriété **Géré en externe** sur ces clients est définie sur **Activé** pour suivre les clients issus de Sales. Lors de la facturation, ces informations sont utilisées pour filtrer les factures qui sont synchronisées sur Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Le champ **Numéro de compte** est disponible sur la page **Compte**. Une clé naturelle et unique a été créée pour prendre en charge l'intégration. La fonction de clé naturelle de la solution de gestion de la relation client (CRM) peut affecter les clients utilisant déjà le champ **Numéro de compte**, mais qui n'utilisez pas des valeurs **Numéro de compte** uniques par compte. Actuellement, la solution d'intégration ne prend pas en charge ce cas.

Lorsqu'un compte est créé, si une valeur **Numéro de compte** n'existe pas encore, elle est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée d'**ACC**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères. Voici un exemple : **ACC-01000-BVRCPS**

Lorsque la solution d'intégration pour Sales est appliquée, un script de mise à niveau définit le champ **Numéro de compte** sur les comptes existants dans Sales. S'il n'existe aucune valeur **Numéro de compte**, la souche de numéros qui a été décrite plus haut est utilisée.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

- La mise en correspondance **CustomerGroupId** à partir de **CDS &gt; Destination** doit être mise à jour avec une valeur valide dans Finance and Operations. Vous pouvez spécifier une valeur par défaut ou vous pouvez définir la valeur à l'aide d'une mise en correspondance des valeurs. Le modèle de valeur par défaut est **10**.
- **Adresse Pays Région Code** est requis dans Finance and Operations. Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance à partir de **CDS &gt; Destination**. Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.

    - Le modèle de valeur par défaut pour **AddressCountryRegionISOCode** est **USA**.
    - Le modèle de valeur par défaut pour **DeliveryAddressCountryRegionISOCode** est **USA**.

- En ajoutant les mises en correspondance suivantes de **CDS &gt; Destination**, vous pouvez réduire le nombre de mises à jour manuelles requises dans Finance and Operations. Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.

    - **SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations. Un site par défaut peut être extrait du produit, ou du client de l'en-tête de commande. Le modèle de valeur par défaut pour **SiteId** est **1**.
    - **WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations. Un entrepôt par défaut peut être extrait du produit, ou du client de l'en-tête de commande dans Finance and Operations. Le modèle de valeur par défaut pour **WarehouseId** est **13**.
    - **LanguageId** – Une langue est requise pour générer des devis et des commandes client dans Finance and Operations. Par défaut, la langue de l'en-tête de commande du client est utilisée. Le modèle de valeur par défaut pour **LanguageId** est **en-us**.

- Mettez à jour l'ID d'organisation CDS (**Organization_OrganizationId**) dans la mise en correspondance **Source &gt; CDS**. Le modèle de valeur par défaut est **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

> [!NOTE]
> Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut. Pour mettre ces champs en correspondance, vous devez paramétrer une mise en correspondance de valeurs. Les mises en correspondance de valeurs sont spécifiques aux données des organisations entre lesquelles l'entité est synchronisée.

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

![Mise en correspondance de modèles dans l'intégrateur de données](./media/accounts-template-mapping-data-integrator-1.png)

![Modèle de mise en correspondance pour les comptes dans l'intégrateur de données](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Rubriques connexes

[Synchronisez les produits de Finance and Operations sur les produits de Sales](products-template-mapping.md)

[Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations](contacts-template-mapping.md)

[Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations](sales-quotation-template-mapping.md)

[Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales](sales-order-template-mapping.md)

[Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales](sales-invoice-template-mapping.md)




