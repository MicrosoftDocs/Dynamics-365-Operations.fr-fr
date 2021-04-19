---
title: Création de nouveaux utilisateurs
description: Les utilisateurs sont des employés internes de votre organisation, ou des clients et fournisseurs externes, qui doivent avoir accès au système pour effectuer leurs tâches.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b994473b4535c255f87551a6d97e197516fc2a9c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745835"
---
# <a name="create-new-users"></a>Créer de nouveaux utilisateurs

[!include [banner](../../includes/banner.md)]

Avant de pouvoir accéder aux applications Finance and Operations, vous devez d’abord être ajouté à la page **Utilisateurs** (**Administration système \> Utilisateurs \> Utilisateurs**). Les utilisateurs incluent les employés internes de votre organisation ou les clients et fournisseurs externes. Les utilisateurs peuvent être importés ou ajoutés manuellement. Tous les utilisateurs doivent disposer d’une licence correcte pour une utilisation conforme.

Pour plus d’informations sur l’achat et la licence pour les applications Finance and Operations, voir [Guide des licences Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Attribuer une licence à un utilisateur
Les administrateurs système peuvent [attribuer des licences aux utilisateurs](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) dans le [Centre d’administration Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Ajouter un utilisateur externe à Azure AD et attribuer une licence 
Les utilisateurs externes doivent être représentés dans votre répertoire de locataires (Azure Active Directory (Azure AD)) pour leur attribuer des licences. Ces utilisateurs externes doivent être ajoutés au client dans Azure AD en tant qu’utilisateurs invités, puis se voir attribuer les licences appropriées. Obligation concernant les applications Finance and Operations : l’entreprise de l’utilisateur invité doit utiliser Azure AD. Pour plus d’informations, voir [Ajouter utilisateurs de collaboration B2B Azure Active Directory dans le portail Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Importer de nouveaux utilisateurs depuis Azure AD 
1. Accédez à **Administration système** \> **Utilisateurs** \> **Utilisateurs**.
2. Dans la volet Actions, sélectionnez **Importer les utilisateurs**.
3. Sélectionnez les utilisateurs à importer. La liste comprend les utilisateurs Azure AD qui ne sont actuellement pas des utilisateurs dans cet environnement.
4. Sélectionnez **Importer les utilisateurs**.
5. Sélectionnez **Fermer**.

> [!NOTE]
> La valeur du champ **Société** sera définie en fonction de la société de session actuelle pour l’administrateur. Après l’importation, vous devez attribuer des rôles et des organisations selon le cas. Pour plus d’informations, voir [Affecter des utilisateurs à des rôles de sécurité](assign-users-security-roles.md). Sous certaines conditions, il pourrait également être nécessaire d’associer l’utilisateur à une **Personne** et de mettre à jour les options utilisateur telles que la langue.

## <a name="manually-add-a-new-user"></a>Ajouter manuellement un nouvel utilisateur
1. Accédez à **Administration système** \> **Utilisateurs** \> **Utilisateurs**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **ID d’utilisateur**, entrez un identificateur unique pour l’utilisateur.   
4. Dans le champ **Nom d’utilisateur**, saisissez le nom de l’utilisateur.  
5. Dans le champ **Fournisseur** :
 - Pour les utilisateurs internes, utilisez la valeur par défaut. Par exemple, votre locataire Azure AD commençant par le préfixe https://sts.windows.net/.  
 - Pour les utilisateurs non-Azure AD, tels que les comptes Service-2-Service, saisissez une valeur textuelle de base. Par exemple, NA. Cette valeur aidera à éviter les appels d’authentification incorrects qui pourraient entraîner des erreurs si une valeur de fournisseur d’identité valide est utilisée.  
 - Pour les utilisateurs externes ou invités, ajoutez leur nom de locataire Azure AD après https://sts.windows.net/.
6. Dans le champ **E-mail**, saisissez le nom de principe d’e-mail/utilisateur complet de l’utilisateur.  
7. Dans le champ **Société**, sélectionnez la société de début par défaut pour l’utilisateur. 
8. Sélectionnez **Enregistrer**.

Les valeurs du fournisseur d’identité et de l’identifiant de télémétrie seront mises à jour en fonction d’un appel [Graphique Microsoft](https://docs.microsoft.com/graph/overview), lorsque l’enregistrement utilisateur est enregistré. L’identifiant de télémétrie est basé sur l’identifiant d’objet/l’identificateur de sécurité (SID) de l’utilisateur dans Azure AD.

> [!NOTE]
> Après avoir ajouté un utilisateur, vous devez attribuer des rôles et des organisations selon le cas. Pour plus d’informations, voir [Affecter des utilisateurs à des rôles de sécurité](assign-users-security-roles.md). Sous certaines conditions, il pourrait également être nécessaire d’associer l’utilisateur à une **Personne** et de mettre à jour les **Options utilisateur** telles que la langue.

## <a name="change-a-user-id"></a>Modifier un identifiant utilisateur
Pour modifier un identifiant utilisateur, vous devez renommer la clé dans la base de données. Lorsque vous modifiez un identifiant utilisateur à l’aide de cette procédure, tous les paramètres utilisateur associés sont modifiés pour utiliser le nouvel identifiant utilisateur. Par exemple, les informations d’utilisation dans la table **SysLastValue** sont mises à jour pour référencer le nouvel identifiant utilisateur.

> [!NOTE]
> L’identifiant utilisateur est la clé primaire de la table d’informations utilisateur. Renommer la clé primaire peut prendre un certain temps pour les utilisateurs existants, car toutes les références à la clé sont également mises à jour dans la base de données. 

1. Accédez à **Administration système \> Utilisateurs \> Utilisateurs**.
2. Sélectionnez un utilisateur dans la liste et sélectionnez **Options\> Enregistrer les informations**.
3. Sélectionnez **Renommer**.
4. Entrez une nouvelle valeur unique pour l’identifiant utilisateur et sélectionnez **OK**. 
5. Sélectionnez **Oui** pour confirmer.

## <a name="additional-resources"></a>Ressources supplémentaires

Pour plus d’options pour implémenter les utilisateurs B2B, voir [Exporter les utilisateurs B2B vers Azure AD](../implement-b2b.md).

Pour plus d’informations sur les comptes système préconfigurés, voir [Comptes système préconfigurés](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]