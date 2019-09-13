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
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873126"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a>Ordre d'exécution de la synchronisation initiale de Finance and Operations et Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Avant d'utiliser l'intégration des données, vous devez créer les données initiales requises pour les clients, les fournisseurs et les contacts. Par exemple, vous souhaitez créer un nouvel élément **Groupe de fournisseurs** et définir la valeur de ses **Conditions de paiement** sur **Net30**. Dans ce cas, avant d'essayer de créer l'élément **Groupe de fournisseurs**, vous devez vous assurer que **Net30** existe bien dans Microsoft Dynamics 365 for Finance and Operations et Common Data Service. (À l'avenir, Microsoft lancera une fonctionnalité de plateforme en double écriture appelée Synchronisation initiale. Elle effectuera une synchronisation unique des données entre Finance and Operations et Common Data Service dans le cadre du paramétrage de la double écriture.)

> [!TIP]
> Microsoft lance une mise en correspondance de la double écriture pour toutes les données de référence notamment les **Conditions de paiement**. Si vous avez déjà les données initiales dans un système, une petite opération de mise à jour sur un enregistrement peut déclencher la double écriture partir de cet enregistrement.

Vous devez suivre l'ordre de priorité suivant et vous assurer que les données initiales sont disponibles sur Finance and Operations et Common Data Service.

## <a name="vendor"></a>Fournisseur

Voici l'ordre d'exécution de l'entité **Fournisseur** :

1. Groupe de fournisseurs

    1. Conditions de paiement

        1. Lignes de jour de paiement
        2. Echéancier de paiement

2. Mode de paiement fournisseur

## <a name="customer-organization"></a>Client (Organisation)

Voici l'ordre d'exécution de l'entité **Client** :

1. Groupe de clients

    1. Conditions de paiement

        1. Lignes de jour de paiement
        2. Paiement 

2. Modes de paiement des clients

## <a name="contact-person"></a>Contact (Personne)

Voici l'ordre d'exécution de l'entité **Contact** :

1. Client 
2. Fournisseur
