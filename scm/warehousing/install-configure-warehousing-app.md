---
title: "Installation et configuration Microsoft Dynamics 365 pour les opérations &#8211 ; Entreposage"
description: "Cette rubrique décrit la procédure d&quot;installation et de configuration Microsoft Dynamics 365 pour les opérations - entreposant."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Installation et configuration Microsoft Dynamics 365 pour les opérations &#8211 ; Entreposage

Cette rubrique décrit la procédure d'installation et de configuration Microsoft Dynamics 365 pour les opérations - entreposant.

Dynamics 365 pour les opérations - le stockage est une application disponible dans le magasin de jeu de Google et le magasin Windows. Pour la version actuelle de Microsoft Dynamics 365 pour les opérations, cette application est fournie comme composant autonome, l'auto- déploiement des périphériques utilisés pour les tâches d'entrepôt. Pour pouvoir utiliser l'application dans votre Dynamics 365 pour l'environnement d'opérations, vous devez télécharger l'application de chaque périphérique et la configurer pour se connecter à votre Dynamics 365 pour l'environnement d'opérations. Cette rubrique décrit la procédure d'installation l'application de vos périphériques. Elle décrit également comment configurer l'application pour se connecter à votre Dynamics 365 pour l'environnement d'opérations.

## <a name="prerequisites"></a>Conditions préalables
L'application est disponible sous Android et systèmes d'exploitation Windows. Pour utiliser cette candidature, vous devez avoir l'un des systèmes d'exploitation pris en charge suivants installés sur vos périphériques. Vous devez également avoir une des versions prises en charge suivantes de Dynamics 365 pour les opérations. Les informations du tableau suivant pour évaluer si votre matériel et environnement logiciel est prêt à prendre en charge l'installation.

| Plateforme                    | Version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (toutes les versions)                                                                                                                                                   |
| Dynamics 365 pour les opérations | Microsoft Dynamics 365 pour la version 1611 d'opérations version 7.0/7.0.1 - ou de Microsoft dynamics AX Dynamics et mise à jour 2 de plateforme Microsoft Dynamics AX avec la Base de connaissances 3210014 de correctif |

## <a name="get-the-app"></a>Obtenez de l'application
-   Windows (UWP) - [Dynamics 365 pour les opérations - entreposant dans le magasin de Windows (https://www.microsoft.com/store/apps/9p1bffd5tstm)]
-   Android 070- [Dynamics 365 pour les opérations - entreposant dans le magasin de jeu de Google Chrome (https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)]

## <a name="create-a-web-service-application-in-active-directory"></a>Créez une application de service Web dans Active Directory
Pour permettre à l'application d'interagir avec Dynamics spécifique 365 pour les opérations serveur, vous devez enregistrer une application de service Web dans Active Directory azuré pour Dynamics 365 pour le locataire d'opérations. Pour des raisons de sécurité, nous vous recommandons de créer une application de service Web pour chaque périphérique que vous utilisez. Pour créer une candidature de service Web dans Active Directory azuré (ANNONCE azurée), procédez comme suit :

1.  Dans un navigateur Web, passez à https://manage.windowsazure.com>.
2.  Entrez le nom et le mot de passe de l'utilisateur qui a accès à l'abonnement azuré.
3.  Dans le portail azuré, dans le volet gauche de navigation, cliquez sur ** Active Directory **. [] (. /media/wh-01-active-directory-example.png) [![wh-01-active-directory-example] (. /media/wh-01-active-directory-example.png)](. /media/wh-01-active-directory-example.png)
4.  Dans la grille, sélectionnez l'instance d'Active Directory utilisée par Dynamics 365 pour les opérations.
5.  Dans la barre d'outils supérieure, cliquez sur ** applications **. ![wh-02-active-directory-applications [] (. /media/wh-02-active-directory-applications-1024x197.png)](. /media/wh-02-active-directory-applications.png)
6.  Dans le volet inférieur, cliquez sur ** ajoutez **. ** Ajoutez l'application ** de début de l'Assistant.
7.  Entrez un nom pour l'application et sélectionnez ** API d'application Web et/ou Web **. ![wh-03-active-directory-add-application [] (. /media/wh-03-active-directory-add-application.png)](. /media/wh-03-active-directory-add-application.png)
8.  Entrez {{signe-:sign-on}} {{sur:sign-on}} l'URL, qui est l'URL d'application dans votre locataire, l'URL d'opérations racine. {{Signe-:sign-on}} {{sur:sign-on}} L'URL actuel n'est pas activement utilisé lors de l'authentification l'application, mais est un champ obligatoire. Entrez le même URL dans le champ d'URI ID d'application. ![wh-04-ad-add-properties [] (. /media/wh-04-ad-add-properties.png)](. /media/wh-04-ad-add-properties.png)
9.  Allez ** configurez ** à l'onglet. ![wh-05-ad-configure-app [] (. /media/wh-05-ad-configure-app.png)](. /media/wh-05-ad-configure-app.png)
10. Faites défiler l'écran jusqu'à ce que vous puissiez voir ** des autorisations à d'autres applications ** la section. Cliquez sur ** ajoutez l'application **. ![wh-06-ad-app-add-permissions [] (. /media/wh-06-ad-app-add-permissions.png)](. /media/wh-06-ad-app-add-permissions.png)
11. Sélectionnez ** Microsoft Dynamics ERP ** dans la liste. Cliquez sur ** chèque complet ** se dans bouton le coin droit de la page. ![wh-07-ad-select-permissions [] (. /media/wh-07-ad-select-permissions.png)](. /media/wh-07-ad-select-permissions.png)
12. Dans ** des autorisations de délégué ** la liste, sélectionnez les cases à cocher. Click **Save**. ![wh-08-ad-delegate-permissions [] (. /media/wh-08-ad-delegate-permissions.png)](. /media/wh-08-ad-delegate-permissions.png)
13. Notez d'informations suivantes :
    -   ** ID client ** - que vous la faites défiler vers le haut de la page, vous verrez ** ID client ** affiche.
    -   ** La clé ** - Dans ** des clés ** la section, créez une clé en sélectionnant la durée, et copies la clé. Cette clé ultérieurement sont appelés du ** secret de client **.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Créer et configurer un compte d'utilisateur dans Dynamics 365 pour les opérations
Pour permettre à Dynamics 365 pour les opérations à utiliser votre application azurée d'ANNONCE, vous devez effectuer les étapes de configuration suivantes :

1.  Créez un nouveau compte d'utilisateur dans Active Directory azuré pour Dynamics 365 pour le locataire d'opérations. L'objectif de ce compte utilisateur est d'accéder au service personnalisé spécifique de l'application de stockage, que Dynamics 365 pour le serveur d'opérations expose. Après avoir accompli cette étape, vous avez les informations d'identification de l'utilisateur de WMDP, qui se composent d'une adresse e-mail de WMDP et d'un mot de passe de WMDP. Pour connaître sur les étapes de base pour ajouter des utilisateurs à ANNONCE azurée et Dynamics 365 pour les opérations, reportez-vous à ce didacticiel : [Inscription à Microsoft Dynamics 365 pour l'abonnement d'opérations] (/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Créez Dynamics 365 pour l'utilisateur d'opérations qui correspond aux informations d'identification de stockage d'utilisateurs de l'application.
    1.  Dans Dynamics 365 pour les opérations, passez ** Administration du système ** &gt; ** au Courant ** &gt; ** les utilisateurs **.
    2.  Création d'un utilisateur.
    3.  Permet d'affecter l'utilisateur de périphérique mobile d'entrepôt, comme illustré dans le capture d'écran suivant. ![wh-09-add-user-security-role [] (. /media/wh-09-add-user-security-role.png)](. /media/wh-09-add-user-security-role.png)

3.  Associez votre application azurée d'Active Directory avec l'utilisateur de stockage d'application.
    1.  Dans Dynamics 365 pour les opérations, passez ** Administration du système ** &gt; ** au paramétrage ** &gt; ** les applications azurées d'Active Directory **.
    2.  Créez une ligne.
    3.  Entrez ** ID client ** (obtenu en dernière section), attribuez -lui un nom, puis sélectionnez l'utilisateur précédemment créé. Nous vous recommandons que vous référencez tous vos périphériques afin de faciliter supprimer l'accès à Dynamics 365 pour les opérations de cette page au cas où ils seront perdus. ![wh-10-ad-applications-form [] (. /media/wh-10-ad-applications-form.png)](. /media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurent l'application
Vous devez configurer l'application sur le périphérique pour se connecter à Dynamics 365 pour le serveur d'opérations dans l'application azurée d'ANNONCE. Pour ce faire, procédez comme suit.

1.  Dans l'application, allez dans ** les paramètres de connexion **.
2.  Désactivez ** mode de démonstration ** le champ. ![wh-11-app-connection-settings-demo-mode [] (. /media/wh-11-app-connection-settings-demo-mode-169x300.png)](. /media/wh-11-app-connection-settings-demo-mode.png)
3.  Entrez les informations suivantes : - ** ID actif azuré clients de répertoire ** - L'ID client est obtenu en étape 13 de « Création d'une candidature de service Web dans Active Directory. - ** Le secret actif azuré clients de répertoire ** - Le secret de client est obtenu en étape 13 de « Création d'une candidature de service Web dans Active Directory. - ** La ressource active azurée en répertoire ** - la ressource azurée en répertoire d'ANNONCE représente Dynamics 365 pour l'URL racine d'opérations. ** Note ** : Ne terminez pas ce champ avec un caractère en avant à barres Fraction (/). - ** Locataire actif azuré de répertoire ** - Le locataire azuré d'annuaire ANNONCE utilisé avec Dynamics 365 pour le serveur d'opérations : https://login.windows.net/your-AD-tenant-ID&lt;&gt;. Par exemple : https://login.windows.net/contosooperations.onmicrosoft.com. 
** Note ** : Ne terminez pas ce champ avec un caractère en avant à barres Fraction (/). - ** Société ** - Permet d'entrer l'entité juridique dans Dynamics 365 pour les opérations dans lesquelles vous souhaitez que l'application de se connecter. ![wh-12-app-connection-settings [] (. /media/wh-12-app-connection-settings-169x300.png)](. /media/wh-12-app-connection-settings.png)
4.  Sélectionnez ** arrière ** se dans bouton le coin dessus- gauche de l'application. L'application se connectera maintenant à votre Dynamics 365 pour le serveur d'opérations et l'écran de connexion pour le travailleur d'entrepôt s'affiche. ![wh-13-log-in-screen [] (. /media/wh-13-log-in-screen-180x300.png)](. /media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Suppression de l'accès pour un périphérique
En cas de périphérique perdu ou compromis, vous devez supprimer l'accès à Dynamics 365 pour les opérations du périphérique. Les étapes suivantes décrivent le processus recommandé pour supprimer l'accès.

1.  Dans Dynamics 365 pour les opérations, passez ** Administration du système ** &gt; ** au paramétrage ** &gt; ** les applications azurées d'Active Directory **.
2.  Permet de supprimer la ligne correspondant au périphérique auquel vous souhaitez supprimer l'accès. Note vers le bas du ** ID client ** utilisé pour le périphérique supprimé.
3.  Connexion le portail classique azuré adresse<> https://manage.windowsazure.com.
4.  Cliquez sur ** Active Directory ** l'icône dans le menu de gauche, puis cliquez sur le répertoire souhaité.
5.  Dans le menu supérieur, cliquez sur ** applications **, puis sur l'application à configurer. ** Début rapide ** la page s'affichera à l'ouverture de session unique et d'autres données de configuration.
6.  Cliquez sur ** configurez ** l'onglet, faites défiler l'écran et assurez-vous que ** ID client ** de l'application est identique à celle de l'étape 2 de cette section.
7.  Cliquez sur ** Supprimer ** bouton se dans la barre de commande.
8.  Cliquez sur Oui ** ** dans le message de confirmation.



