---
title: Regulatory Configuration Service (RCS) – Supprimer un environnement RCS
description: Cet article explique comment un administrateur système de Regulatory Configuration Service (RCS) peut supprimer un environnement RCS et les données associées.
author: kfend
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, System Admin
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.custom: 97423
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
ms.openlocfilehash: bdcb6820ead72fce0f89bf80cc5e474cb3942724
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277237"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS) – Supprimer un environnement RCS

[!include [banner](../includes/banner.md)]

Cet article explique comment un administrateur système de Regulatory Configuration Service (RCS) peut supprimer un environnement RCS et les données associées.

Avant de pouvoir effectuer la procédure de cet article, les conditions préalables suivantes doivent être remplies :

- Vous devez disposer du rôle **Administrateur système** pour l’environnement RCS.
- Le rôle **Administrateur système** doit disposer du rôle **RCSDeleteEnvironmentDuty**.

## <a name="delete-an-rcs-environment"></a>Supprimer un environnement RCS

1. Ouvrez RCS et sélectionnez la vignette de l’espace de travail **Gestion des états électroniques**.
2. Dans la section **Liens connexes**, sélectionnez **Supprimer l’environnement RCS**.

    ![Lien Supprimer l’environnement RCS dans la section Liens connexes.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. Dans la boîte de dialogue qui s’affiche, passez en revue les messages concernant l’étendue de la suppression de l’environnement.

    ![Messages dans la boîte de dialogue Supprimer l’environnement RCS.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > La suppression d’un environnement RCS est irréversible.
    >
    > L’opération supprime l’environnement RCS sélectionné et toutes les données associées, y compris les fonctionnalités et les configurations qui sont stockées dans le référentiel global. Les fonctionnalités et configurations partagées avec d’autres organisations ne seront plus partagées et seront supprimées si elles n’ont pas de dépendances. Les fonctionnalités et configurations qui ont des dépendances seront marquées comme abandonnées.

4. Dans le champ indiqué, saisissez l’identifiant global unique (GUID) de l’environnement RCS pour confirmer que vous souhaitez le supprimer. Le GUID de l’environnement est inclus dans le message de suppression.
5. Sélectionnez **Supprimer l’environnement**.
    
Votre environnement RCS et toutes les données associées sont désormais supprimés.

> [!IMPORTANT]
> Après avoir supprimé un environnement RCS, il n’y a aucun moyen de récupérer les données. Un nouvel environnement RCS peut être créé dans n’importe quelle région RCS disponible.
