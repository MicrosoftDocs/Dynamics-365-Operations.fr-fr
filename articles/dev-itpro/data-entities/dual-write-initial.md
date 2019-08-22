---
title: Ordre d'exécution de la synchronisation initiale de Finance and Operations et Common Data Service
description: Cette rubrique spécifie l'ordre de synchronisation à suivre pour créer les données initiales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797296"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Ordre d'exécution de la synchronisation initiale de Finance and Operations et Common Data Service

Avant d'utiliser l'intégration des données, vous devez créer les données initiales requises pour les clients, les fournisseurs et les contacts. Par exemple, si vous souhaitez créer un élément **Groupe de fournisseurs** et définir ses **Conditions de paiement** comme **Net30**, avant de tenter de créer l'élément **Groupe de fournisseurs**, vous devez vous assurer que **Net30** existe dans Finance and Operations et Common Data Service. (À l'avenir, nous lancerons une fonctionnalité de plateforme en double écriture appelée **Synchronisation initiale**. Elle effectuera une synchronisation unique des données entre Finance and Operations et Common Data Service dans le cadre du paramétrage de la double écriture.)

Conseils : Nous lançons une mise en correspondance de la double écriture pour toutes les données de référence notamment les **Conditions de paiement**. Si vous avez déjà les données initiales dans un système, une petite opération de mise à jour sur un enregistrement peut déclencher la double écriture partir de cet enregistrement. 

Vous devez suivre l'ordre de priorité suivant et vous assurer que les données initiales sont disponibles sur Finance and Operations et Common Data Service.   

## <a name="vendor"></a>Fournisseur

L'ordre d'exécution pour le fournisseur est :

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Client (Organisation)

L'ordre d'exécution pour le client est :

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Contact (Personne)

L'ordre d'exécution pour le contact est :

```
Customer
Vendor               
```
