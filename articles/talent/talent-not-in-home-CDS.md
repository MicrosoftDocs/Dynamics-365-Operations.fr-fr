---
title: "Talent n'apparaît pas parmi les applications Microsoft Dynamics 365 (CDS1.0)"
description: "Cette rubrique explique comment procéder si le client ne voit pas l'application Microsoft Dynamics 365 for Talent parmi les applications Microsoft Dynamics 365."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: fr-fr
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>Talent n'apparaît pas parmi les applications Microsoft Dynamics 365 (CDS1.0)

[!include [banner](includes/banner.md)]

**Problème**

Le client ne voit pas l'application Microsoft Dynamics 365 for Talent parmi les applications Microsoft Dynamics 365.

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

