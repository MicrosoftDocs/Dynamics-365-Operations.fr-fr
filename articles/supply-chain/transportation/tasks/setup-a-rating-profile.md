---
title: Profils de classement
description: Cette rubrique décrit le paramétrage des données de profils de classement.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f754a8b86b0d369af03812a831d77a8a6fa8154
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233509"
---
# <a name="rating-profiles"></a>Profils de classement

Un profil de classement ressemble à un contrat logistique (mais pas à un contrat légal). Il sert à déterminer les tarifs de transport des charges. 

Chaque profil de classement est propre à un transporteur. Dans le profil, vous associer le transporteur à une table maître des taux. La table maître des taux définit l’affectation de base de taux et la base de taux. La base de taux détermine le taux du transporteur.

Vous pouvez paramétrer un profil de classement à l’aide d’une page générique qui affiche une vue d’ensemble de tous les profils de classement existants. Sinon, vous pouvez paramétrer le profil de classement directement à partir du transporteur. Dans les deux cas, les informations que vous définissez pour le profil de classement sont les mêmes.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Créer ou modifier un profil de classement sur la page Profils de classement

Sur la page **Profils de classement**, vous pouvez consulter tous les profils de classement disponibles. Vous pouvez également modifier les profils existants et créer des profils.

1. Accédez à **Gestion du transport \> Configurer \> Taux \> Données principales de taux**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter un nouveau profil de classement à la grille, ou sélectionnez **Modifier** pour modifier un profil existant.
1. Dans la ligne du profil de notation nouveau ou existant, définissez les champs suivants :

    - **Profils de classement** – Entrez un identificateur (ID) unique pour le profil de classement.
    - **Nom** – Entrez un nom descriptif pour le profil de classement.
    - **Transporteur** – Sélectionnez un transporteur. Le profil de classement que vous configurez sera également affiché sur la page **Transporteurs** pour le transporteur sélectionné.
    - **Site** et **Entrepôt** – Sélectionnez un site et un entrepôt.
    - **Moteur de taux** – Sélectionnez le moteur de taux pour le profil de classement.
    - **Maître de taux** – Sélectionnez le maître de taux pour le profil de classement. Vous pouvez utiliser le maître des taux pour définir un type de base de taux et une base de taux. Pour plus d’informations, voir [Paramétrage des maîtres de taux](set-up-rate-masters.md).
    - **Moteur de temps de transit** – Sélectionnez le moteur de temps de transit pour le profils de classement.
    - **Indice de carburant du transporteur** – Sélectionnez l’indice de carburant du transporteur pour le profil de classement.
    - **Date et heure de début effectives** et **Date et heure de fin effectives** – Définissez la période pendant laquelle le profil de classement doit être actif.

1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Créer ou modifier un profil de classement directement sur la page Transporteurs

1. Allez dans **Gestion du transport \> Configuration \> Transporteurs \> Transporteurs**.
1. Sélectionnez un transporteur dans la liste.
1. Dans l’organisateur **profils de classement**, cliquez sur **Nouveau** pour créer un profil de classement.
1. Définissez les champs du nouveau profils de classement. Ces champs correspondent aux champs de la page **profils de classement**, comme décrit dans la section précédente de cette rubrique.

> [!NOTE]
> Les profils créés sur la page **Transporteurs** sont également affichés sur la page **profils de classement**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]