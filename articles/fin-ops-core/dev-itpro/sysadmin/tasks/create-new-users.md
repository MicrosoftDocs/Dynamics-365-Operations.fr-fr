---
title: Création de nouveaux utilisateurs
description: Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180942"
---
# <a name="create-new-users"></a>Création de nouveaux utilisateurs

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Associer un utilisateur avec une licence (nouveaux types de licence uniquement)
Pour les clients qui se trouvent sur un des nouveaux types de licence qui ont été ajoutés en octobre 2019, les utilisateurs doivent être associés avec une licence. Les utilisateurs associés à une licence sont automatiquement ajoutés comme utilisateurs système sans rôle lors de leur première connexion. Les utilisateurs qui ne sont pas associés à une licence reçoivent un message d'avertissement.

Les administrateurs système peuvent [attribuer des licences aux utilisateurs](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) dans le [Centre d'administration Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-a-new-user"></a>Ajout d'un nouvel utilisateur
1. Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **ID d'utilisateur**, entrez un identificateur unique pour l'utilisateur. Un ID utilisateur est requis.  
4. Dans le champ **Nom d'utilisateur**, saisissez le nom de l'utilisateur.  
5. Dans le champ **Domaine**, entrez le domaine AD DS de l'utilisateur.  
6. Dans le champ **Alias**, entrez l'alias utilisateur.  
7. Sélectionnez la société souhaitée dans le champ **Société**. 
8. Dans l'organisateur **Rôles de l'utilisateur**, sélectionnez **Affecter des rôles** sur [affecter des rôles de sécurité aux utilisateurs](assign-users-security-roles.md)
9. Cliquez sur **OK**.
10. Sélectionnez **Enregistrer**.

## <a name="import-users"></a>Importer des utilisateurs
1. Dans la volet Actions, sélectionnez **Importer les utilisateurs**.
2. Dans la liste, marquer la ligne sélectionnée.
3. Sélectionnez **Importer les utilisateurs**.
4. Sélectionnez **Fermer**.

