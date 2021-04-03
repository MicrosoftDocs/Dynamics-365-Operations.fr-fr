---
title: Human Resources n’apparaît pas dans les applications Microsoft Dynamics 365
description: Cet article explique comment procéder si le client ne voit pas l’application Microsoft Dynamics 365 Human Resources parmi les applications Microsoft Dynamics 365.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9be1c2b862a01d6f14ad98dbcb01e061649c6af0
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463982"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>Human Resources n’apparaît pas dans les applications Microsoft Dynamics 365

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Sortie**

Le client ne voit pas Dynamics 365 Human Resources parmi les applications Microsoft Dynamics 365.

**Résolution**

L’utilisateur doit être ajouté au rôle Créateur d’environnement pour l’environnement dans Microsoft Power Apps.

1. L’utilisateur administrateur disposant d’une licence Power Apps Plan 2 doit ouvrir le [Portail d’administration Power Apps](https://preview.admin.powerapps.com/).

2. Sélectionnez **Environnements**, puis sélectionnez l’environnement approprié pour Human Resources.

3. Sous l’onglet **Sécurité**, sous l’onglet **Rôles d’environnement**, sélectionnez **Créateur d’environnement**.

    ![Onglet Rôles d’environnement](media/environment-roles.png)

4. Sous l’onglet **Utilisateurs**, ajoutez l’utilisateur ou votre organisation.

    ![Onglet Utilisateurs](media/environment-maker.png)

5. Sélectionnez **Enregistrer**.

6. L’utilisateur doit à présent se connecter à [Microsoft Dynamics 365](https://home.dynamics.com/).

7. Sélectionnez **synchroniser** pour mettre à jour les applications de l’utilisateur.

    ![Bouton Synchroniser](media/get-more.png)

    Une fois la synchronisation terminée, Human Resources apparaît sur la page d’accueil.


[!INCLUDE[footer-include](../includes/footer-banner.md)]