---
title: Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les Contacts (Contacts) et Contacts (Clients) de Microsoft Dynamics 365 for Sales à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 7a856a9460d092925a34a0733f37f89354c2ddf1
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) de Microsoft Dynamics 365 for Sales (Sales) à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations).

## <a name="templates-and-tasks"></a>Modèles et tâches

Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les Contacts (Contacts) de Sales avec les Contacts (Clients) de Finance and Operations :

- **Nom des modèles :**

    - Contacts vers Contact (Sales vers Fin and Ops)
    - Contacts vers Client (Sales vers Fin and Ops)

- **Noms des tâches du projet :**

    - Contacts
    - ContactToCustomer

La tâche suivante de synchronisation est requise avant la synchronisation de Contact : Comptes (Sales vers Fin and Ops)

## <a name="entity-sets"></a>Ensembles d'entités

| Vente    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Contacts | Contact | Contacts CDS           |
| Contacts | Compte | Clients V2           |

## <a name="entity-flow"></a>Flux d'entité

Les contacts sont gérés dans Sales, et sont synchronisés avec Common Data Service (CDS) et Finance and Operations.

Un contact dans Sales peut devenir un contact dans CDS et Finance and Operations. Sinon, il peut devenir un compte dans CDS et un client dans Finance and Operations. Pour déterminer si un contact doit être collecté rapidement de Sales pour la synchronisation avec CDS et Finance and Operations (par exemple, Contacts dans Sales &gt; Contact dans CDS &gt; Contacts dans Finance and Operations), les système recherche les propriétés suivantes sur le contact dans Sales :

- **Synchronisation avec Compte dans CDS et Client dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Oui**
- **Synchronisation avec Contact dans CDS et Contact dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Non** et **Société** (Compte parent/Contact) pointe vers un Compte (pas un Contact)

## <a name="prospect-to-cash-solution-for-sales"></a>Prospect pour une solution de disponibilités pour Sales 

Un nouveau champ **Client actif** a été ajouté au Contact. Ce champ permet de différencier les contacts qui disposent d'activités commerciales et les contacts qui n'ont pas d'activités commerciales. **Client actif** est défini sur **Oui** uniquement pour les Contacts qui associés à des devis, des commandes, ou des factures. Seuls ces contacts sont synchronisés avec Finance and Operations comme clients.

Un nouveau champ **IsCompanyAnAccount** a été ajouté au Contact. Ce champ permet d'indiquer si le contact est lié à une société parent (Compte parent/Contact) du type **Compte**. Ces informations servent à identifier les contacts qui doivent être synchronisés avec Finance and Operations comme contacts.

Un nouveau champ **Numéro de contact** a été ajouté au contact pour garantir une clé naturelle et unique pour l'intégration. Lorsqu'un nouveau contact est créé, une valeur **Numéro de contact** est automatiquement générée à l'aide d'une souche de numéros. La valeur est composée de **CON**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères. Voici un exemple : **CON-01000-BVRCPS**

Lorsque la solution d'intégration pour Sales est ajoutée à Sales, le script de mise à niveau définit le champ **Numéro de contact** pour des contact existants à l'aide de la souche de numéros qui a été précédemment évoquées. Le script de mise à niveau définit également le champ **Client actif** sur **Oui** pour tous les contacts qui disposent d'activités commerciales.

## <a name="in-finance-and-operations"></a>Dans Finance and Operations 

Les contacts sont étiquetés à l'aide de la propriété **IsContactPersonExternallyMaintained**. Cette propriété indique qu'un contact donné est conservé en externe. Dans ce cas, les contacts tenus à jour en externe sont tenus à jour dans Sales.

## <a name="preconditions-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="contact-to-contact"></a>Contact vers Contact

- Mettez à jour **ID organisation CDS** dans la mise en correspondance **Source &gt; CDS**.

    - La valeur par défaut du modèle pour **Organization_OrganizationId [ID organisation]** est **ORG001**.
    - La valeur par défaut du modèle pour **PrimaryAccount_Organization_OrganizationId [Organization ID]** est **ORG001**.

- **Adresse Pays Région Code** est requis dans Finance and Operations. Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance **CDS &gt; Operations**. Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales. Le modèle de valeur par défaut pour **PrimaryAddressCountryRegionISOCode** est **USA**.
- Assurez-vous qu'une valeur pour le champ suivant existe dans Finance and Operations. Si ces informations ne sont pas obligatoires dans Finance and Operations, vous pouvez supprimer la mise en correspondance de la mise en correspondance **CDS &gt; Destination**.

    - **Nom de champ dans Finance and Operations :** Décision
    - **Mise en correspondance :** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Contact vers Client

- Mettez à jour **ID organisation CDS** dans la mise en correspondance **Source &gt; CDS**. La valeur par défaut du modèle pour **Organization_OrganizationId [ID organisation]** est **ORG001**.
- **Adresse Pays Région Code** est requis dans Finance and Operations. Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance **CDS &gt; Destination**. Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales. Le modèle de valeur par défaut pour **PrimaryAddressCountryRegionISOCode** est **USA**.
- **CustomerGroup** est requis dans Finance and Operations. Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance **CDS &gt; Destination**. Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales. Le modèle de valeur par défaut pour **CustomerGroupId** est **10**.
- En ajoutant les mises en correspondance suivantes de **CDS &gt; Destination**, vous pouvez réduire le nombre de mises à jour manuelles dans Finance and Operations. Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.

    - **SiteId** : Site par défaut qui peut également être défini dans Finance and Operations. Un site est requis pour générer des lignes de devis et de commandes client dans Finance and Operations. Aucun modèle de valeur pour **SiteId** n'est défini.
    - **WarehouseId** : Entrepôt par défaut qui peut également être défini dans Finance and Operations. Un entrepôt est requis pour générer des lignes de devis et de commandes client dans Finance and Operations. Aucun modèle de valeur pour **WarehouseId** n'est défini.
    - **LanguageId** : Une langue est requise pour générer des devis et des commandes client dans Finance and Operations. Le modèle de valeur par défaut pour **LanguageId** est **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Mise en correspondance de modèles dans l'intégrateur de données

Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.

### <a name="contact-to-contact"></a>Contact vers Contact

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-1.png)

![Modèle de mise en correspondance pour les contacts dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Contact vers Client

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-3.png)

![Modèle de mise en correspondance pour les contacts dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Rubriques connexes

[Synchronisez les produits de Finance and Operations sur les produits de Sales](products-template-mapping.md)

[Synchronisez les comptes des ventes aux clients de Finance and Operations](accounts-template-mapping.md)

[Synchronisez les en-têtes de vis de vente et les lignes entre Sales et Finances and Operations](sales-quotation-template-mapping.md)

