---
title: Activer l'authentification Azure Active Directory pour la connexion au PDV
description: Cette rubrique explique comment configurer l'expérience de connexion pour le point de vente (PDV) Microsoft Dynamics 365 Commerce afin d'utiliser l'authentification Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 4f5a02348e8cef44424ae5d6a49de02d762ba245
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410033"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Activer l'authentification Azure Active Directory pour la connexion au PDV
[!include [banner](includes/banner.md)]


De nombreux clients qui utilisent Microsoft Dynamics 365 Commerce utilisent également d'autres services cloud Microsoft, et ils peuvent utiliser Azure Active Directory (Azure AD) pour gérer les informations d'identification de l'utilisateur pour ces services. Dans ces cas, les clients peuvent souhaiter utiliser le même compte Azure AD dans toutes les applications. Cette rubrique explique comment configurer l'expérience de connexion pour le point de vente (PDV) Commerce afin d'utiliser l'authentification Azure AD.

## <a name="configure-azure-ad-authentication"></a>Configurer l'authentification Azure AD

Pour mettre Azure AD à disposition en tant que mode d'authentification pour la connexion au PDV pour un magasin, vous devez configurer les paramètres du profil de fonctionnalité du magasin, puis appliquer ces paramètres aux clients du PDV.

Pour configurer un profil de fonctionnalité, procédez comme suit :

1. Accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Paramétrage du PDV** \> **Profils POS** \> **Profils de fonctionnalité**.
1. Sélectionnez le profil de fonctionnalité à modifier.
1. Sur le raccourci **Fonctions**, dans la section **Connexion du personnel au PDV**, modifiez la valeur du champ **Mode d'authentification pour la connexion** de **ID et mot de passe personnels** vers **Azure Active Directory**.

Par défaut, tous les profils de fonctionnalité utilisent **ID et mot de passe personnels** en tant que mode d'authentification au PDV. Par conséquent, vous devez modifier la valeur du champ **Mode d'authentification pour la connexion** si vous souhaitez utiliser Azure AD. Chaque magasin de vente au détail lié au profil de fonctionnalité sélectionné sera affecté par cette modification.

Pour appliquer les paramètres aux clients du PDV, procédez comme suit.

1. Accédez à **Retail et Commerce** \> **Informatique Retail et Commerce** \> **Programme de distribution**.
1. Exécutez le programme de distribution **1070** (**Configuration du canal**).

> [!NOTE]
> L'authentification Azure AD nécessite une connexion Internet. Cela ne fonctionne pas si le PDV est en mode Hors connexion.
> 
> Actuellement, la fonction **remplacement par le responsable** ne prend pas en charge Azure AD comme méthode d'authentification. Un ID opérateur et un mot de passe sont requis même si Azure AD est configuré comme méthode d'authentification pour la connexion de PDV.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Associer un compte Azure AD à un collaborateur

Avant qu'un employé de magasin puisse utiliser un compte Azure AD pour se connecter à l'application de PDV, le compte Azure AD doit être associé à ce collaborateur.

Pour associer un compte Azure AD à un collaborateur, procédez comme suit.

1. Accédez à **Retail et Commerce** \> **Employés** \> **Collaborateurs**.
1. Ouvrez la page des détails pour un collaborateur.
1. Sur le volet Actions, sous l'onglet **Commerce**, dans le groupe **Identité externe**, cliquez sur **Associer l'identité existante**.
1. Dans la boîte de dialogue **Utiliser l'identité externe existante**, sélectionnez **Rechercher à l'aide de l'e-mail**, entrez une adresse électronique Azure AD, puis sélectionnez **Rechercher**.
1. Sélectionnez le compte Azure AD renvoyé, puis sélectionnez **OK**.

Les champs **Alias**, **UPN** et **Sous-identifiant externe** de l'onglet **Commerce** de la page des détails du collaborateur seront remplis.

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrer une fonctionnalité de connexion étendue pour MPOS et PDV Cloud](extended-logon.md)

[Créer un profil de fonctionnalité de vente au détail](retail-functionality-profile.md)

[Configurer un collaborateur](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
