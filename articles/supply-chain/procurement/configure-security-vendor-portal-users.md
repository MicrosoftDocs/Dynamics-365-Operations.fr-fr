---
title: Sécurité de l'utilisateur du portail fournisseur
description: Cet article détaille la procédure de paramétrage de la sécurité pour les fournisseurs externes qui utilisent le portail Fournisseur. Ces informations ne s'appliquent qu'aux versions de février 2016 &amp; de mai 2016 de Dynamics AX.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 176eeb2ddb145d21f7ff9fd94a9a56e173caee59
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555082"
---
# <a name="vendor-portal-user-security"></a>Sécurité utilisateur du portail fournisseur

[!include [banner](../includes/banner.md)]

Cet article détaille la procédure de paramétrage de la sécurité pour les fournisseurs externes qui utilisent le portail Fournisseur. Ces informations ne s'appliquent qu'aux versions de février 2016 &amp; de mai 2016 de Dynamics AX.

La fonctionnalité de portail fournisseur a été remplacée par la fonctionnalité étendue de collaboration fournisseur dans la version 1611 de Dynamics 365 for Operations. Pour plus d'informations sur le paramétrage de la sécurité pour la collaboration fournisseur, voir [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md). Le portail Fournisseur expose un ensemble limité d'informations sur les commandes fournisseur (CF) aux fournisseurs externes. Il est important de paramétrer correctement des autorisations utilisateur pour le portail Fournisseur dans Microsoft Dynamics AX, de sorte que les fournisseurs n'aient pas un accès involontaire aux informations supplémentaires dans votre installation de Dynamics AX. **Important :** à la différence d'autres utilisateurs, les fournisseurs externes ne doivent pas avoir le rôle **SystemUser**. Le rôle **SystemUser** octroie l'accès à un ensemble de privilèges qui ne sont pas appropriés aux utilisateurs externes.

## <a name="setting-up-a-vendor-portal-user"></a>Paramétrage d'un utilisateur du portail Fournisseur
Avant de créer un compte utilisateur pour une personne qui utilise le portail Fournisseur, vous devez paramétrer le fournisseur pour autoriser sa collaboration au portail Fournisseur. Utilisez le champ **Collaboration de commande fournisseur** sous l'onglet **Général** dans la page **Fournisseurs**. Les fournisseurs externes qui utilisent le portail Fournisseur doivent avoir le paramétrage suivant :

-   Un compte utilisateur de Microsoft Azure Active Directory (AAD) doit être enregistré pour le fournisseur dans la page **Utilisateurs** dans Dynamics AX.
-   Le fournisseur doit avoir le rôle de sécurité **Fournisseur (externe)**, et non le rôle **SystemUser**. **Remarque :** le rôle **SystemUser** est automatiquement octroyé lorsque vous créez un nouveau compte utilisateur dans Dynamics AX. Par conséquent, vous devez supprimer ce rôle et accepter le message d'avertissement reçu.
-   L'utilisateur fournisseur ne doit pas avoir l'autorisation d'ajouter des champs supplémentaires à partir des tables de CF sur leur affichage de la CF. Sous l'onglet **Personnalisation**, sous l'onglet **Utilisateurs**, réglez l'option **Personnalisation explicite autorisée** pour l'utilisateur sur **Non**.
-   Le compte utilisateur doit être associé à une personne à contacter enregistrée. Dans la page **Utilisateurs**, sélectionnez une personne à contacter dans le champ **Nom**. La personne sélectionnée doit avoir le rôle **Contact** pour le fournisseur approprié.

Si la même personne a besoin d'accéder au portail Fournisseur pour plusieurs comptes fournisseur (pour différentes entités juridiques, peut-être), chacun des comptes d'utilisateurs de cette personne doit être associé à la même personne à contacter enregistrée. Le rôle **Fournisseur (externe)** inclut toutes les fonctionnalités de base requises afin d'utiliser la fonctionnalité disponible dans le portail Fournisseur. Ce paramétrage permet de garantir que l'interface utilisateur vue par l'utilisateur externe est concentrée uniquement sur le scénario prévu.

<a name="additional-resources"></a>Ressources supplémentaires
--------

[Collaboration du fournisseur](collaborate-vendors-vendor-portal.md)



