---
title: Zones d’emplacement supplémentaires
description: Cet article fournit une vue d’ensemble des nouvelles zones d’emplacement qui ont été ajoutées à Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 819330e0f6e6cd419da441f919d68ff996b6475c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336513"
---
# <a name="additional-location-zones"></a>Zones d’emplacement supplémentaires

[!include [banner](../includes/banner.md)]

Trois nouveaux champs de zone sont disponibles dans Microsoft Dynamics 365 Supply Chain Management. Les responsables d’entrepôt peuvent les utiliser pour définir des organisations ou des dispositions d’entrepôt supplémentaires. Les nouveaux champs de zone peuvent être définis manuellement ou en utilisant l’Assistant **Paramétrage d’emplacement**. Ils peuvent être utilisés dans toute requête ou tout filtrage qui utilise la table Emplacements.

Aucune configuration supplémentaire n’est requise pour utiliser les champs de zone.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Activer ou désactiver la fonctionnalité Zone d’emplacement supplémentaire

Pour pouvoir utiliser cette fonctionnalité, il doit être activé pour votre système. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est activée par défaut. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée. Si vous exécutez une version antérieure à 10.0.29, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Zone d'emplacement supplémentaire* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="use-location-zones"></a>Utiliser les zones d’emplacement

1. Allez dans **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Assistant Paramétrage d’emplacement**.
2. Définissez les valeurs suivantes :

    - Dans le champ **Entrepôt**, sélectionnez _62_.
    - Dans le champ **ID zone**, sélectionnez _FLOOR_.
    - Dans le champ **Zone supplémentaire 1**, sélectionnez _PICKZONE1_.
    - Dans le champ **Zone supplémentaire 2**, sélectionnez _WEBSHOP1_.
    - Dans le champ **ID profil d’emplacement**, sélectionnez _FLOOR_.

3. Sélectionnez la ligne **Sol**.
4. Dans le champ **Numéro de départ**, entrez _1_. Dans le champ **Numéro d’arrivée**, entrez _3_.
5. Sélectionnez la ligne **Allée**.
6. Dans le champ **Numéro de départ**, entrez _1_. Dans le champ **Numéro d’arrivée**, entrez _5_.
7. Sélectionnez **Créer**.
8. Vous recevez des messages indiquant que de nouveaux emplacements ont été ajoutés. Sélectionnez le bouton **Afficher les messages** pour afficher les messages.
9. Accédez à **Gestion des entrepôts \> Paramétrage \> Entrepôt \> Emplacements**. Les nouveaux emplacements s’affichent dans la liste et tous les champs de zone sont disponibles (c’est-à-dire le champ de zone existant et les nouveaux champs de zone supplémentaires).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]