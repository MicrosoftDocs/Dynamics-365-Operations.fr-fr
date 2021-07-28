---
title: Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) directement depuis Dynamics 365 Sales vers Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a16006a18e552c00fbed5eda7579fbcb77c315ea
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355923"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Avant d’utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Microsoft Dataverse pour applications](/powerapps/administrator/data-integrator).

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les tables Contact (Contacts) et Contact (Clients) directement depuis Dynamics 365 Sales vers Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Flux de données dans Prospect en disponibilités

La solution Prospect en disponibilités utilise la fonction d’intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales. Les modèles de prospects en disponibilités disponibles avec la fonction d’intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales. L’illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.

[![Flux de données dans Prospect en disponibilités.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modèles et tâches

Pour accéder à des modèles disponibles, ouvrez [Centre d’administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration). Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les tables Contacts (Contacts) de Sales avec les tables Contacts (Clients) de Supply Chain Management :

- **Noms des modèles dans l’intégration des données**

    - Contacts (Sales vers Supply Chain Management) - Direct
    - Contacts vers Customer (Sales vers Supply Chain Management) - Direct

- **Noms des tâches dans le projet d’intégration de données**

    - Contacts
    - ContactToCustomer

La tâche suivante de synchronisation est requise avant que la synchronisation du contact puisse avoir lieu : Comptes (Sales vers Supply Chain Management)

## <a name="entity-sets"></a>Ensembles d’entités

| Vente    | Gestion de la chaîne d’approvisionnement |
|----------|------------------------|
| Contacts | Contacts Dataverse           |
| Contacts | Clients V2           |

## <a name="entity-flow"></a>Flux d’entité

Les contacts sont gérés dans Sales et synchronisés sur Supply Chain Management.

Un contact dans Sales peut devenir un contact ou un client dans Supply Chain Management. Pour déterminer si un contact dans Sales doit être synchronisé avec Supply Chain Management en tant que contact ou client, le système recherche les propriétés suivantes sur le contact dans Sales :

- **Synchronisation avec un client dans Supply Chain Management :** Contacts là où **Client actif** est défini sur **Oui**
- **Synchronisation avec un contact dans Supply Chain Management :** Contacts là où **Client actif** est défini sur **Non** et **Société** (compte parent/contact) pointe vers un compte (pas un contact)

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales

Une nouvelle colonne **Client actif** a été ajoutée au contact. Cette colonne permet de différencier les contacts qui disposent d’activités commerciales et les contacts qui n’ont pas d’activités commerciales. **Client actif** est défini sur **Oui** uniquement pour les contacts qui associés à des devis, des commandes, ou des factures. Seuls ces contacts sont synchronisés avec Supply Chain Management comme clients.

Une nouvelle colonne **IsCompanyAnAccount** a été ajoutée au contact. Cette colonne indique si un contact est lié à une société (compte parent/contact) du type **Compte**. Ces informations servent à identifier les contacts qui doivent être synchronisés avec Supply Chain Management comme contacts.

Une nouvelle colonne **Numéro de contact** a été ajoutée au contact pour garantir une clé naturelle et unique pour l’intégration. Lorsqu’un nouveau contact est créé, une valeur **Numéro de contact** est automatiquement générée à l’aide d’une souche de numéros. La valeur est composée de **CON**, suivi d’une souche de numéros croissante et d’un suffixe de six caractères. Voici un exemple : **CON-01000-BVRCPS**

Lorsque la solution d’intégration pour Sales est appliquée, un script de mise à niveau définit la colonne **Numéro de contact** pour des contact existants à l’aide de la souche de numéros qui a été précédemment mentionnée. Le script de mise à niveau définit également la colonne **Client actif** sur **Oui** pour tous les contacts qui disposent d’activités commerciales.

## <a name="in-supply-chain-management"></a>Dans Supply Chain Management

Les contacts sont étiquetés à l’aide de la propriété **IsContactPersonExternallyMaintained**. Cette propriété indique qu’un contact donné est conservé en externe. Dans ce cas, les contacts tenus à jour en externe sont tenus à jour dans Sales.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="contact-to-customer"></a>Contact vers client

- **CustomerGroup** est obligatoire dans Supply Chain Management. Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance. Cette valeur par défaut est alors utilisée si la colonne est laissée vide dans Sales.

    Le modèle de valeur par défaut est **10**.

- En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Supply Chain Management. Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.

    - **SiteId** – Site par défaut qui peut également être défini dans Supply Chain Management. Un site est requis pour générer des lignes de devis et de commandes client dans Supply Chain Management.

        Aucun modèle de valeur pour **SiteId** n’est défini.

    - **WarehouseId** – Entrepôt par défaut qui peut également être défini dans Supply Chain Management. Un entrepôt est requis pour générer des lignes de devis et de commandes client dans Supply Chain Management.

        Aucun modèle de valeur pour **WarehouseId** n’est défini.

    - **LanguageId** – Un langage est requis pour générer des lignes de devis et de commande client dans Supply Chain Management.
    
        Le modèle de valeur par défaut **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l’intégration de données

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l’intégration de données. 

> [!NOTE]
> La mise en correspondance indique quelles informations de la colonne sont synchronisées entre Sales et Supply Chain Management.

### <a name="contact-to-contact"></a>Contact vers contact

![Mise en correspondance de modèles dans l’intégrateur de données.](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Contact vers client

![Mise en correspondance de modèles dans l’intégrateur de données.](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Rubriques connexes

[Prospect en disponibilités](prospect-to-cash.md)

[Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management](accounts-template-mapping-direct.md)

[Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Sales](products-template-mapping-direct.md)

[Synchronisation des commandes client directement entre Sales et Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synchroniser les en-têtes et les lignes de facture client directement entre le module Supply Chain Management et Sales](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]