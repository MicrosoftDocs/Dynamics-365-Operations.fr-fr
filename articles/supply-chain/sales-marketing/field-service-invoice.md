---
title: Synchroniser des factures d'accord de Field Service sur des factures financières dans Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les factures d'accord de Dynamics 365 Field Service sur les factures financières dans Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
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
ms.openlocfilehash: c2d0f671d4b824cb5d38a5d11c4b06b2e97bd0c8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528243"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Synchroniser des factures d'accord de Field Service sur des factures financières dans Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les factures d'accord de Dynamics 365 Field Service sur les factures financières dans Dynamics 365 Supply Chain Management.

## <a name="templates-and-tasks"></a>Modèles et tâches

Le modèle et les tâches sous-jacentes suivants sont utilisés pour exécuter la synchronisation des factures d'accord de Field Service sur les factures financières de Supply Chain Management.

**Nom du modèle dans l'intégration des données**

- Factures d'accord (Field Service vers Supply Chain Management)

**Noms des tâches dans le projet d'intégration de données**

- En-têtes de facture
- Lignes de facture

La synchronisation suivante est requise avant que la synchronisation des factures d'accord puisse avoir lieu :

- Comptes (Sales vers Supply Chain Management) - Direct

## <a name="entity-set"></a>Ensemble d'entités

| Field Service  | Gestion de la chaîne d'approvisionnement                 |
|----------------|----------------------------------------|
| factures       | En-têtes de facture financière client CDS |
| invoicedetails | Lignes de facture financière client CDS   |

## <a name="entity-flow"></a>Flux d'entité

Les factures qui sont créées à partir d'un accord dans Field Service peuvent être synchronisées sur Supply Chain Management via un projet d'intégration de données Common Data Service. Les mises à jour à ces factures sont synchronisées sur les factures financières dans Supply Chain Management si le statut comptable des factures financières est **En cours**. Une fois les factures financières validées dans Supply Chain Management, et que le statut comptable est mis jour sur **Terminé**, vous ne pouvez plus synchroniser les mises à jour dans Field Service.

## <a name="field-service-crm-solution"></a>Solution Field Service CRM

Le champ **A des lignes provenant d'un accord** a été ajouté à l'entité **Facture**. Ce champ permet de garantir que seules les factures créées à partir d'un accord sont synchronisées. La valeur est **vrai** si la facture contient au moins une ligne de facture qui provient d'un accord.

Le champ **Provient d'un accord** a été ajouté à l'entité **Ligne de facture**. Ce champ permet de garantir que seules les lignes de facture créées à partir d'un accord sont synchronisées. La valeur est **vrai** si la ligne de facture provient d'un accord.

**Date de facture** est un champ obligatoire dans Supply Chain Management. Par conséquent, le champ doit spécifier une valeur dans Field Service avant que la synchronisation se produise. Pour répondre à cette exigence, la logique suivante est ajoutée :

- Si le champ **Date de facture** est vide sur l'entité **Facture** (c'est-à-dire qu'il n'a pas de valeur), il est défini sur la date actuelle lorsqu'une une ligne de facture provenant d'un accord est ajoutée.
- L'utilisateur peut modifier le champ **Date de facture**. Toutefois, lorsque l'utilisateur essaie d'enregistrer une facture qui provient d'un accord, il reçoit une erreur du processus d'entreprise si le champ **Date de facture** est vide sur la facture.

## <a name="prerequisites-and-mapping-setup"></a>Conditions préalables et paramétrage de mise en correspondance

### <a name="in-supply-chain-management"></a>Dans Supply Chain Management

Une origine de facture doit être paramétrée pour l'intégration, afin de distinguer les factures financières de Supply Chain Management créées à partir de factures d'accord dans Field Service. Lorsqu'une facture a une origine de facture de type **Intégration de la facture à l'accord**, le champ **Numéro de facture externe** s'affiche dans l'en-tête **Facture client**.

En plus de s'afficher dans l'en-tête de facture, l'information **Numéro de facture externe** peut être utilisée pour garantir que les factures qui sont créées à partir de factures d'accord de Field Service sont ignorées lors de la synchronisation de facture entre Supply Chain Management et Field Service.

1. Accédez à **Comptabilité client** \> **Paramétrage** \> **Codes d'origine de la facture**.
2. Sélectionnez **Nouveau** pour créer une origine de facture.
3. Dans le champ **Origine de la facture**, entrez un nom pour l'origine de la facture, par exemple **FS**.
4. Dans le champ **Description**, entrez une description, comme **Facture d'accord Field Service**.
5. Activez la case à cocher **Affectation du type d'origine**.
6. Définissez le champ **Type d'origine de la facture** sur **Intégration de la facture à l'accord**.
7. Sélectionnez **Enregistrer**.

### <a name="in-the-data-integration-project"></a>Dans le projet d'intégration des données

Tâche : **Lignes de facture**  

Assurez-vous que la valeur par défaut du champ Supply Chain Management **Valeur d'affichage du compte principal** est mise à jour pour correspondre à la valeur souhaitée.

Le modèle de valeur par défaut est **401100**.

## <a name="template-mapping-in-data-integration"></a>Mise en correspondance de modèles dans l'intégration de données

Les illustrations suivantes présentent la mise en correspondance de modèles dans le module Intégration des données.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Factures d'accord (Field Service vers Supply Chain Management) : En-têtes de facture

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Factures d'accord (Field Service vers Supply Chain Management) : Lignes de facture

[![Mise en correspondance de modèles dans l'intégration de données](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)
