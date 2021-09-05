---
title: Human Resources n’apparaît pas dans les applications Microsoft Dynamics 365
description: Cette rubrique explique comment procéder si Microsoft Dynamics 365 Human Resources ne figure pas parmi les applications Microsoft Dynamics 365.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dfed82463eece882bed66c7b2dac1dd30e04720e
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413399"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>L’application Human Resources ne s’affiche pas dans les applications Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problème**

Le client ne voit pas Dynamics 365 Human Resources parmi les applications Microsoft Dynamics 365.

**Résolution**

L’utilisateur doit être ajouté au rôle Créateur d’environnement pour l’environnement dans Microsoft Power Apps.

1. L’utilisateur administrateur disposant d’une licence Power Apps Plan 2 doit ouvrir le [Portail d’administration Power Apps](https://preview.admin.powerapps.com/).

2. Sélectionnez **Environnements**, puis sélectionnez l’environnement approprié pour Human Resources.

3. Sous l’onglet **Sécurité**, sous l’onglet **Rôles d’environnement**, sélectionnez **Créateur d’environnement**.

    ![Onglet Rôles d’environnement.](media/environment-roles.png)

4. Sous l’onglet **Utilisateurs**, ajoutez l’utilisateur ou votre organisation.

    ![Onglet Utilisateurs.](media/environment-maker.png)

5. Sélectionnez **Enregistrer**.

6. L’utilisateur doit à présent se connecter à [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Sélectionnez **synchroniser** pour mettre à jour les applications de l’utilisateur.

    ![Bouton Synchroniser.](media/get-more.png)

    Une fois la synchronisation terminée, Human Resources apparaît sur la page d’accueil.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
