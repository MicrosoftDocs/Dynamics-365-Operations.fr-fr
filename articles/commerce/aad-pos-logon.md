---
title: Configurer Azure Active Directory pour la connexion au PDV
description: Cet article explique comment configurer Azure Active Directory comme méthode d’authentification dans le point de vente Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 9ef9d79e319b95e6c7f531ed2a5886b3f1e85d27
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277114"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Configurer Azure Active Directory pour la connexion au PDV

[!include [banner](includes/banner.md)]

Cet article explique comment configurer Azure Active Directory (Azure AD) comme méthode d’authentification dans le point de vente (PDV) Microsoft Dynamics 365 Commerce.

Les détaillants qui utilisent Dynamics 365 Commerce avec d’autres services cloud Microsoft tels que Microsoft Azure, Microsoft 365 et Microsoft Teams veulent généralement utiliser Azure AD pour une gestion centralisée des informations d’identification des utilisateurs afin d’offrir une expérience de connexion sécurisée et transparente entre les applications. Pou utiliser l’authentification Azure AD dans l’application PDV de Commerce, vous devez d’abord configurer Azure AD comme méthode d’authentification dans Commerce Headquarters.

## <a name="configure-pos-authentication-method"></a>Configurer la méthode d’authentification PDV

Pour configurer la méthode d’authentification PDV de Commerce Headquarters, procédez comme suit.
    
1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage Point de vente \> Profils Point de vente \> Profils de fonctionnalité** et sélectionnez le profil de fonctionnalité que vous souhaitez modifier.
1. Dans la section **Connexion du personnel au PDV** du raccourci **Fonctions**, sélectionnez l’option de méthode d’authentification souhaitée dans la liste déroulante **Mode d’authentification pour la connexion**.

    Le **Mode d’authentification pour la connexion** a trois options :
    
    - **ID et mot de passe personnels** – Cette option par défaut oblige les utilisateurs du PDV à saisir un ID personnel et un mot de passe pour se connecter au PDV et accéder à la fonctionnalité de remplacement par le responsable.
    - **Azure AD sans authentification unique** – Cette option nécessite que les utilisateurs du point de vente utilisent les informations d’identification Azure AD pour se connecter au PDV et accéder à la fonctionnalité de remplacement par le responsable. Lorsque le client PDV est actualisé ou rouvert, l’utilisateur du PDV doit fournir les informations d’identification Azure AD pour se reconnecter.
    - **Azure AD avec authentification unique** – Lorsque cette option est sélectionnée, les utilisateurs du PDV peuvent se connecter à Cloud POS (CPOS) en utilisant les informations d’identification Azure AD actives qui sont utilisées par d’autres applications Web dans le même navigateur Web, ou se connecter à Modern POS (MPOS) en utilisant les identifiants Azure AD utilisés pour Windows. Les deux méthodes permettent la connexion sans avoir besoin d’entrer les informations d’identification Azure AD sur l’écran de connexion au PDV. Cependant, l’accès à la fonctionnalité de remplacement par le responsable du point de vente nécessitera toujours une connexion à l’aide des identifiants Azure AD.

1. Accédez à **Retail et Commerce> IT Retail et Commerce > Programme de distribution** et exécutez le travail **1070 (configuration des canaux)** pour synchroniser les derniers paramètres de profil de fonctionnalité avec les clients PDV.

> [!NOTE]
> - L’option de méthode d’authentification **Azure AD sans authentification unique** remplace l’option **Azure Active Directory** dans Commerce version 10.0.18 et versions antérieures.
> - L’authentification Azure AD nécessite une connexion Internet active et ne fonctionnera pas si le point de vente est hors ligne.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Associer des comptes Azure AD avec des utilisateurs de point de vente

Pour utiliser Azure AD comme méthode d’authentification au PDV, vous devez associer les comptes Azure AD avec des utilisateurs de point de vente dans Commerce Headquarters. 

Pour associer des comptes Azure AD à des utilisateurs de point de vente dans Commerce Headquarters, procédez comme suit.
    
1. Accédez à **Retail et Commerce > Employés > Collaborateurs** et ouvrez un enregistrement de collaborateur.
1. Sur le volet Actions, sélectionnez l’onglet **Commerce**, puis sous **Identité externe**, cliquez sur **Associer l’identité existante**. 
1. Dans la boîte de dialogue **Utiliser l’identité externe existante**, sélectionnez **Rechercher à l’aide de l’e-mail**, entrez une adresse électronique Azure AD, puis sélectionnez **Rechercher**.
1. Sélectionnez le compte Azure AD renvoyé, puis sélectionnez **OK**.

Après les étapes de configuration ci-dessus, les champs **Alias**, **UPN** et **Sous-identifiant externe** de l’onglet **Commerce** de la page des détails du collaborateur seront remplis.

Vous devez exécuter la tâche **1060 (Personnel)** dans **Retail et Commerce > IT Retail et Commerce > Programme de distribution** pour synchroniser le dernier utilisateur du PDV et les données de compte Azure AD sur le canal.

> [!NOTE]
> En tant que meilleure pratique, après que les informations sur le collaborateur telles que le mot de passe, l’autorisation de point de vente, le compte Azure AD, ou le carnet d’adresses des employés sont mises à jour dans Commerce Headquarters, il est fortement recommandé d’exécuter la tâche **1060 (Personnel)** pour synchroniser les dernières informations sur le collaborateur avec le canal. Le client PDV peut ainsi extraire les données correctes pour l’authentification des utilisateurs et la vérification des autorisations.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Verrouillage de caisse enregistreuse de point de vente et déconnexion via l’authentification Azure AD

Voici ce qui se produit lorsque le PDV est configuré pour utiliser le mode d’authentification Azure AD :

- La fonction **Verrouiller la caisse enregistreuse** ne sera pas disponible dans l’application PDV. 
- La fonction **Verrouiller automatiquement** se comportera de la même manière que la fonction **Déconnecter automatiquement**.
- Si l’utilisateur du PDV sélectionne **Déconnecter**, il sera invité à se connecter avec les informations d’identification Azure AD lors du prochain lancement du PDV, que la connexion unique soit activée ou non.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>Fonctionnalité de remplacement par le responsable avec l’authentification Azure AD

Lorsque le PDV est configuré pour utiliser l’authentification Azure AD, la fonctionnalité de remplacement par le responsable ouvrira une boîte de dialogue qui demande les identifiants Azure AD du responsable. Une fois la connexion du responsable approuvée, les identifiants Azure AD du responsable seront supprimés et les identifiants Azure AD de l’utilisateur précédent seront utilisés pour les opérations de PDV ultérieures.

> [!NOTE]
> - Dans les versions 10.0.18 et antérieures de Commerce, la fonction de remplacement par le responsable ne prend pas en charge Azure AD. Un ID et un mot de passe personnels sont requis même si le PDV est configuré pour utiliser le mode d’authentification Azure AD.
> - Lorsque vous utilisez CPOS avec le navigateur Web Safari sur un appareil Apple iOS, vous devez d’abord désactiver le **bloqueur de fenêtres publicitaires** dans les paramètres de Safari pour que la fonctionnalité de remplacement par le responsable fonctionne avec l’authentification Azure AD. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Meilleures pratiques de sécurité pour l’authentification au PDV basée sur Azure AD sur les appareils partagés

De nombreux détaillants configurent leur environnement de magasin de manière à ce que plusieurs utilisateurs accèdent à l’application de point de vente à partir d’un appareil physique partagé. Dans ce contexte, si la connexion unique offre une expérience d’authentification pratique et transparente, elle peut également créer une faille de sécurité dans laquelle l’utilisateur actuel du PDV peut ne pas savoir si les informations d’identification d’un autre utilisateur sont utilisées pour effectuer des transactions ou des opérations dans le PDV. Avant de configurer le PDV pour utiliser le mode d’authentification Azure AD, il est fortement recommandé de passer en revue votre politique de sécurité et les paramètres de connexion de l’appareil partagé pour décider quelle option convient le mieux.

- Si votre environnement de vente au détail utilise un compte partagé (par exemple, un compte local) pour la connexion à un appareil physique, il est recommandé d’utiliser l’option **Azure AD sans authentification unique**. Cela garantit que chaque utilisateur de point de vente fournit explicitement les informations d’identification Azure AD pour se connecter au PDV.
- Si votre environnement de vente au détail oblige les employés à utiliser leurs propres comptes Azure AD pour se connecter au point de vente et qu’il héberge un appareil physique, il est recommandé d’utiliser l’option **Azure AD avec authentification unique**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un collaborateur](tasks/worker.md)

[Créer un profil de fonctionnalité de vente au détail](retail-functionality-profile.md)


[Paramétrer une fonctionnalité de connexion étendue pour MPOS et CPOS](extended-logon.md)

[Bonnes pratiques de sécurité pour Cloud POS dans les environnements partagés](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
