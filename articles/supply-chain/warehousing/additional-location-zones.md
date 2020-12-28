---
title: Zones d'emplacement supplémentaires
description: Cette rubrique fournit une vue d'ensemble des nouvelles zones d'emplacement qui ont été ajoutées à Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 6cf81939989b8faffcda51bbbd5bc6b27aec7eea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428254"
---
# <a name="additional-location-zones"></a>Zones d'emplacement supplémentaires

[!include [banner](../includes/banner.md)]

Trois nouveaux champs de zone sont disponibles dans Microsoft Dynamics 365 Supply Chain Management. Les responsables d'entrepôt peuvent les utiliser pour définir des organisations ou des dispositions d'entrepôt supplémentaires. Les nouveaux champs de zone peuvent être définis manuellement ou en utilisant l'Assistant **Paramétrage d'emplacement**. Ils peuvent être utilisés dans toute requête ou tout filtrage qui utilise la table Emplacements.

Aucune configuration supplémentaire n'est requise pour utiliser les champs de zone.

## <a name="turn-on-the-additional-location-zone-feature"></a>Activer la fonctionnalité Zone d'emplacement supplémentaire

Avant de pouvoir utiliser la fonctionnalité *Zone d'emplacement supplémentaire*, celle-ci doit être activée dans votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Zone d'emplacement supplémentaire*

## <a name="use-location-zones"></a>Utiliser les zones d'emplacement

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Assistant Paramétrage d'emplacement**.
2. Définissez les valeurs suivantes :

    - Dans le champ **Entrepôt**, sélectionnez _62_.
    - Dans le champ **ID zone**, sélectionnez _FLOOR_.
    - Dans le champ **Zone supplémentaire 1**, sélectionnez _PICKZONE1_.
    - Dans le champ **Zone supplémentaire 2**, sélectionnez _WEBSHOP1_.
    - Dans le champ **ID profil d'emplacement**, sélectionnez _FLOOR_.

3. Sélectionnez la ligne **Sol**.
4. Dans le champ **Numéro de départ**, entrez _1_. Dans le champ **Numéro d'arrivée**, entrez _3_.
5. Sélectionnez la ligne **Allée**.
6. Dans le champ **Numéro de départ**, entrez _1_. Dans le champ **Numéro d'arrivée**, entrez _5_.
7. Sélectionnez **Créer**.
8. Vous recevez des messages indiquant que de nouveaux emplacements ont été ajoutés. Sélectionnez le bouton **Afficher les messages** pour afficher les messages.
9. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**. Les nouveaux emplacements s'affichent dans la liste et tous les champs de zone sont disponibles (c'est-à-dire le champ de zone existant et les nouveaux champs de zone supplémentaires).
