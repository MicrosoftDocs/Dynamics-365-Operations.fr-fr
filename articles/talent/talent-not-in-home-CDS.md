---
title: Talent ne figure pas dans les applications Microsoft Dynamics 365 (Common Data Service 1.0)
description: Cette rubrique explique comment procéder si le client ne voit pas l'application Microsoft Dynamics 365 for Talent parmi les applications Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ad5add2b572ccb6bff175806b965f63b53986152
ms.sourcegitcommit: 45b79d1e587e03f5cde2766cdec4eaa7a2a897a3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "949780"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>Talent ne figure pas dans les applications Microsoft Dynamics 365 (Common Data Service 1.0)

[!include [banner](includes/banner.md)]

**Sortie**

Le client ne voit pas à l'application Microsoft Dynamics 365 for Talent parmi les applications Microsoft Dynamics 365.

**Résolution**

L'utilisateur doit être ajouté au rôle Créateur d'environnement pour l'environnement dans Microsoft PowerApps.

1. L'utilisateur administrateur disposant d'une licence PowerApps Plan 2 doit ouvrir le [Portail d'administration PowerApps](https://preview.admin.powerapps.com/).
2. Sélectionnez **Environnements**, puis sélectionnez l'environnement approprié pour Talent.
3. Sous l'onglet **Sécurité**, sous l'onglet **Rôles d'environnement**, sélectionnez **Créateur d'environnement**.

    ![Onglet Rôles d'environnement](media/environment-roles.png)

4. Sous l'onglet **Utilisateurs**, ajoutez l'utilisateur ou votre organisation.

    ![Onglet Utilisateurs](media/environment-maker.png)

5. Sélectionnez **Enregistrer**.
6. L'utilisateur doit à présent se connecter à [Microsoft Dynamics 365](https://home.dynamics.com/).
7. Sélectionnez **synchroniser** pour mettre à jour les applications de l'utilisateur.

    ![Bouton Synchroniser](media/get-more.png)

    Une fois la synchronisation terminée, Talent apparaît sur la page d'accueil.
