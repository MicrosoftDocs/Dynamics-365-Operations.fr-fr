---
title: Installer, configurer et mettre à jour le portail client
description: Cette rubrique fournit des détails sur les licences et les instructions de configuration du portail client.
author: dasani-madipalli
manager: tfehr
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 2153bbca2be7c72e48b9dc51b1f7fdbe2ab89903
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977736"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Installer, configurer et mettre à jour le portail client

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Licences requises préalables

Pour implémenter le portail client, vous devez disposer des licences suivantes :

- **Portails Power Apps** – Cette licence est requise pour héberger le portail client. Les licences de portail sont délivrées selon l'utilisation. Pour plus d'informations, voir [Conditions des licences des portails Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Double écriture** – Vous devez disposer des licences nécessaires pour activer la double écriture pour les tables de Supply Chain Management. Pour plus d'informations, voir [Configuration requise pour la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Dépendances à la double écriture et aux portails Power Apps

Le portail client dépend des portails Power Apps et de la double écriture, comme indiqué dans l'illustration suivante.

![Dépendances du portail client](media/customer-portal-elements.png "Dépendances du portail client")

Contrairement aux autres fonctionnalités de Supply Chain Management, le modèle de portail client réside dans les portails Power Apps. Par conséquent, le portail client est limité par les fonctionnalités et capacités assurées par les portails Power Apps et les tables en double écriture.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Configuration requise pour activer le portail client

Après vous être assuré que vous disposez des licences requises, vous pouvez configurer la double écriture comme décrit dans les [instructions de synchronisation initiale de la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).

Veillez à activer les mappages de table suivants en double écriture :

- En-tête de commande client
- Détails de la commande client
- Comptes
- Contacts
- Produits

Une fois cette configuration terminée, vous pouvez provisionner le modèle de portail client.

## <a name="provision-the-customer-portal"></a>Provisionner le portail client

Avant de commencer, assurez-vous que vous avez déjà terminé la [configuration requise](#required-setup). Suivez ensuite ces étapes pour provisionner le portail client.

1. Accédez à [make.powerapps.com](https://make.powerapps.com/).
2. Assurez-vous que vous utilisez l'environnement dans lequel vous avez activé la double écriture.
3. Dans l'onglet **Créer**, défilez jusqu'à la section **Commencer à partir du modèle** et sélectionnez le modèle nommé **Portail client**.
4. Suivez les instructions à l'écran.

Une fois le provisionnement terminé, vous pouvez accéder au portail client dans la section **Vos applis** de la page **Accueil**.

> [!NOTE]
> Si la solution de double écriture n'est pas installée dans l'environnement dans lequel vous travaillez, vous recevrez un message d'erreur et le portail client ne sera pas provisionné.

## <a name="update-the-customer-portal"></a>Mettre à jour le portail client

D'autres fonctionnalités pourront être ajoutées au portail client ultérieurement. Toute modification apportée par Microsoft aux composants de la solution sous-jacente apparaîtra automatiquement dans votre environnement. Cependant, le site web provisionné dans votre environnement ne reflétera pas automatiquement les modifications apportées aux données de configuration. Vous devrez appliquer manuellement ces modifications en récupérant le code du nouveau modèle et en le fusionnant avec le site web provisionné.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour savoir comment configurer et personnaliser le portail client, vous devez commencer par consulter la documentation suivante concernant les technologies sous-jacentes :

- [Documentation des portails Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Documentation de la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Pour gérer efficacement vos portails, vous devez comprendre les portails Power Apps et le cycle de vie de Microsoft Dataverse. Pour plus d’informations, voir les ressources suivantes (éventuellement en anglais) :

- [À propos du cycle de vie des portails](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Mettre à niveau un portail](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migrer la configuration d'un portail](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Gestion du cycle de vie des solutions : applications Dynamics 365 for Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)
