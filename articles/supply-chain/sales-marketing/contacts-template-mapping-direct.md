---
title: Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) de Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 021a43c78cec83b23aff5dcc40db1a4be81aefc3
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations

[!INCLUDE [banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître l'[intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) directement de Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales. L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.

[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les entités Contacts (Contacts) de Sales avec les entités Contacts (Clients) de Finance and Operations :

- **Noms des modèles dans l'intégration des données :**

    - Contacts (Sales et Fin and Ops) - Direct
    - Contacts vers Client (Sales vers Fin and Ops) - Direct

- **Noms des tâches dans le projet d'intégration de données :**

    - Contacts
    - ContactToCustomer

La tâche suivante de synchronisation est requise avant que la synchronisation du contact puisse avoir lieu : Comptes (Sales vers Fin and Ops)

## <a name="entity-sets"></a>Ensembles d'entités

| Vente    | Finance and Operations |
|----------|------------------------|
| Contacts | Contacts CDS           |
| Contacts | Clients V2           |

## <a name="entity-flow"></a>Flux d'entité

Les contacts sont gérés dans Sales et synchronisés avec Finance and Operations.

Un contact dans Sales peut devenir un contact ou un client dans Finance and Operations. Pour déterminer si un contact dans Sales doit être synchronisé avec Finance and Operations en tant que contact ou client, le système recherche les propriétés suivantes sur le contact dans Sales :

- **Synchronisation avec un client dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Oui**
- **Synchronisation avec un contact dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Non** et **Société** (compte parent/contact) pointe vers un compte (pas un contact)

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Un nouveau champ **Client actif** a été ajouté au contact. Ce champ permet de différencier les contacts qui disposent d'activités commerciales et les contacts qui n'ont pas d'activités commerciales. **Client actif** est défini sur **Oui** uniquement pour les contacts qui associés à des devis, des commandes, ou des factures. Seuls ces contacts sont synchronisés avec Finance and Operations comme clients.

Un nouveau champ **IsCompanyAnAccount** a été ajouté au contact. Ce champ indique si un contact est lié à une société (compte parent/contact) du type **Compte**. Ces informations servent à identifier les contacts qui doivent être synchronisés avec Finance and Operations comme contacts.

Un nouveau champ **Numéro de contact** a été ajouté au contact pour garantir une clé naturelle et unique pour l'intégration. Lorsqu'un nouveau contact est créé, une valeur **Numéro de contact** est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée de **CON**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères. Voici un exemple : **CON-01000-BVRCPS**

Lorsque la solution d'intégration pour Sales est appliquée, un script de mise à niveau définit le champ **Numéro de contact** pour des contact existants à l'aide de la souche de numéros qui a été précédemment mentionnée. Le script de mise à niveau définit également le champ **Client actif** sur **Oui** pour tous les contacts qui disposent d'activités commerciales.

## <a name="in-finance-and-operations"></a>Dans Finance and Operations

Les contacts sont étiquetés à l'aide de la propriété **IsContactPersonExternallyMaintained**. Cette propriété indique qu'un contact donné est conservé en externe. Dans ce cas, les contacts tenus à jour en externe sont tenus à jour dans Sales.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="contact-to-customer"></a>Contact vers client

- **CustomerGroup** est requis dans Finance and Operations. Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance. Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.

    Le modèle de valeur par défaut est **10**.

- En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Finance and Operations. Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.

    - **SiteId** – Site par défaut qui peut également être défini dans Finance and Operations. Un site est requis pour générer des lignes de devis et de commandes client dans Finance and Operations.

        Aucun modèle de valeur pour **SiteId** n'est défini.

    - **WarehouseId** – Entrepôt par défaut qui peut également être défini dans Finance and Operations. Un entrepôt est requis pour générer des lignes de devis et de commandes client dans Finance and Operations.

        Aucun modèle de valeur pour **WarehouseId** n'est défini.

    - **LanguageId** – Une langue est requise pour générer des devis et des commandes client dans Finance and Operations.
    
        Le modèle de valeur par défaut **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.

### <a name="contact-to-contact"></a>Contact vers contact

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Contact vers client

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations](accounts-template-mapping-direct.md)

[Synchroniser les produits directement de Finance and Operations sur les produits du module Sales](products-template-mapping-direct.md)

[Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales](sales-order-template-mapping-direct-two-ways.md)

[Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales](sales-invoice-template-mapping-direct.md)



