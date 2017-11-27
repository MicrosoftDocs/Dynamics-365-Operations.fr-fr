---
title: Installation et configuration de Microsoft Dynamics 365 for Finance and Operations &#8211; Entreposage
description: "Cette rubrique décrit la procédure d'installation et de configuration de Microsoft Dynamics 365 for Finance and Operations - Entreposage."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4b3d068ddbf6f0b28c97618f5fa10fa486f3af51
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>Installation et configuration de Microsoft Dynamics 365 for Finance and Operations &#8211; Entreposage

[!include[banner](../includes/banner.md)]


Cette rubrique décrit la procédure d'installation et de configuration de Microsoft Dynamics 365 for Finance and Operations - Entreposage.

Finance and Operations - Entreposage est une application disponible dans le Google Play Store et le Windows Store. Pour la version actuelle de Finance and Operations, cette application est fournie en tant que composant autonome, ce qui signifie un auto-déploiement sur les périphériques utilisés pour les tâches d'entrepôt. Pour utiliser l'application dans votre environnement Finance and Operations, vous devez télécharger l'application sur chaque périphérique et la configurer en vue d'une connexion à votre environnement Finance and Operations. Cette rubrique décrit la procédure d'installation de l'application sur vos périphériques. Elle décrit également comment configurer l'application pour se connecter à votre environnement Finance and Operations.

## <a name="prerequisites"></a>Conditions préalables
L'application est disponible sur les systèmes d'exploitation Android et Windows. Pour utiliser cette application, vous devez avoir l'un des systèmes d'exploitation pris en charge suivants installés sur vos périphériques. Vous devez également avoir une des versions prises en charge suivantes de Finance and Operations. Utilisez les informations contenues dans le tableau suivant pour évaluer si votre environnement matériel et logiciel est prêt à prendre en charge l'installation.

| Plateforme                    | Version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (toutes les versions)                                                                                                                                                   |
| Finance and Operations | Microsoft Finance and Operations version 1611 <br>- ou - <br>Microsoft Dynamics AX version 7.0/7.0.1 et Microsoft Dynamics AX Platform - Mise à jour 2 avec correctif. Voir l'article de la base de connaissances 3210014 |

## <a name="get-the-app"></a>Obtenir l'application
-   Windows (UWP) - [Finance and Operations - Entreposage dans le Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android :
    - Windows (UWP) - [Finance and Operations - Entreposage dans le Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - Windows (UWP) - [Finance and Operations - Entreposage dans la Zebra App Gallery](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-active-directory"></a>Créer une application de service Web dans Active Directory
Pour permettre à l'application d'interagir avec un serveur Finance and Operations, vous devez enregistrer une application de service Web dans un répertoire Azure Active Directory pour le locataire Finance and Operations. Pour des raisons de sécurité, nous vous recommandons de créer une application de service Web pour chaque périphérique que vous utilisez. Pour créer une application de service Web dans Azure Active Directory (Azure AD), procédez comme suit :

1.  Dans un navigateur Web, accédez à <https://manage.windowsazure.com>.
2.  Entrez le nom et le mot de passe de l'utilisateur qui a accès à l'abonnement Azure.
3.  Dans le portail Azure, dans le volet de navigation gauche, cliquez sur **Active Directory**.[](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-example](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  Dans la grille, sélectionnez l'instance Active Directory utilisée par Finance and Operations.
5.  Dans la barre d'outils supérieure, cliquez sur **Applications**. [![wh-02-active-directory-applications](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  Dans le volet inférieur, cliquez sur **Ajouter**. L'assistant **Ajouter une application** démarre.
7.  Entrez un nom pour l'application et sélectionnez **Application web et/ou API web**. [![wh-03-active-directory-add-application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Entrez l'URL de connexion, qui est une URL d'application Web. Cette URL est identique à votre URL de déploiement, mais oauth est ajouté à la fin. Entrez l'URI d'ID d'application, cette valeur est obligatoire, mais n'est pas nécessaire pour l'authentification. Assurez-vous que l'URI d'ID d'application est un URI d'imitation comme https://contosooperations/wmapp, car l'utilisation de l'URL de votre déploiement peut entraîner des problèmes de connexion dans d'autres applications AAD comme le module complémentaire Excel. [![WH-04-AD-add-properties3](./media/WH-04-AD-add-properties3.png)](./media/WH-04-AD-add-properties3.png)
9.  Sélectionnez l'onglet **Configurer**. [![wh-05-ad-configure-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Faites défiler l'écran jusqu'à ce que vous puissiez voir la section **Autorisations pour d'autres applications**. Cliquez sur **Ajouter une application**. [![wh-06-ad-app-add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Sélectionnez **Microsoft Dynamics ERP** dans la liste. Cliquez sur le bouton **Vérification complète** dans le coin droit de la page. [![wh-07-ad-select-permissions](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. Dans la liste **Autorisations accordées aux délégués**, sélectionnez toutes les cases à cocher. Cliquez sur **Enregistrer**. [![wh-08-ad-delegate-permissions](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Relevez les informations suivantes :
    -   **ID client** - En faisant défiler la page vers le haut, vous pouvez voir apparaître l'**ID client**.
    -   **Clé** - Dans la section **Clés**, créez une clé en sélectionnant la durée, et copiez la clé. Cette clé sera par la suite référencée en tant que **Clé secrète client**.

## <a name="create-and-configure-a-user-account-in-finance-and-operations"></a>Créer et configurer un compte d'utilisateur dans Finance and Operations
Pour permettre à Finance and Operations d'utiliser votre application Azure AD, vous devez effectuer les étapes de configuration suivantes :

1.  Créez un nouveau compte d'utilisateur dans Azure Active Directory pour le locataire Finance and Operations. L'objectif de ce compte utilisateur est d'accéder au service personnalisé spécifique de l'application Entreposage, que le serveur Finance and Operations expose. Après avoir accompli cette étape, vous avez les informations d'identification de l'utilisateur WMDP, qui se composent d'une adresse e-mail WMDP et d'un mot de passe WMDP. Pour connaître les étapes de base permettant d'ajouter des utilisateurs à Azure AD et Finance and Operations, reportez-vous à ce didacticiel : [Inscription à Finance and Operations](../../dev-itpro/dev-tools/sign-up-preview-subscription.md).
2.  Créez un utilisateur Finance and Operations qui correspond aux informations d'identification de l'utilisateur de l'application Entreposage.
    1.  Dans Finance and Operations, accédez à **Administration du système** &gt; **Commun** &gt; **Utilisateurs**.
    2.  Créez un nouvel utilisateur.
    3.  Affectez l'utilisateur d'appareil mobile d'entrepôt, comme illustré dans la capture d'écran suivante. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Associez votre application Azure Active Directory à l'utilisateur de l'application Entreposage.
    1.  Dans Finance and Operations, accédez à **Administration du système** &gt; **Paramétrage** &gt; **Applications Azure Active Directory**.
    2.  Créez une ligne.
    3.  Entrez l'**ID client** (obtenu en dernière section), attribuez-lui un nom, puis sélectionnez l'utilisateur précédemment créé. Nous vous recommandons de référencer tous vos périphériques afin de faciliter la suppression de l'accès à Finance and Operations à partir de cette page en cas de perte. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurer l'application
Vous devez configurer l'application sur le périphérique pour vous connecter au serveur Finance and Operations via l'application Azure AD. Pour ce faire, procédez comme suit.

1.  Dans l'application, accédez à **Paramètres de connexion**.
2.  Désactivez le champ **Mode démonstration**. <br>[![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Entrez les informations suivantes : 
    + **ID du client Azure Active Directory** - L'ID du client est obtenu à l'étape 13 dans « Créer une application de service Web dans Active Directory ». 
    + **Question secrète du client Azure Active Directory** - La question secrète est obtenue à l'étape 13 dans "Créer une application de service Web dans Active Directory". 
    + **Ressource Azure Active Directory** - la ressource Azure Active Directory représente l'URL racine de Finance and Operations. **Remarque** : ne terminez pas ce champ avec une barre oblique inverse (/). 
    + **Locataire Azure Active Directory** - Le locataire Azure Active Directory représente l'URL racine de Finance and Operations : https://login.windows.net/your-AD-tenant-ID. Par exemple : https://login.windows.net/contosooperations.onmicrosoft.com.
    <br>**Remarque** : ne terminez pas ce champ avec une barre oblique inverse (/). 
    + **Société** - Accédez à l'entité juridique de Finance and Operations à laquelle vous souhaitez que l'application se connecte. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Sélectionnez le bouton **Précédent** dans le coin supérieur gauche de l'application. L'application se connecte maintenant à votre serveur Finance and Operations et l'écran de connexion du collaborateur d'entrepôt s'affiche. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Suppression de l'accès pour un périphérique
En cas de périphérique perdu ou compromis, vous devez supprimer l'accès Finance and Operations du périphérique. Les étapes suivantes décrivent le processus recommandé pour supprimer l'accès.

1.  Dans Finance and Operations, accédez à **Administration du système** &gt; **Paramétrage** &gt; **Applications Azure Active Directory**.
2.  Supprimez la ligne correspondant au périphérique auquel vous souhaitez supprimer l'accès. Relevez l'**ID client** utilisé pour le périphérique supprimé.
3.  Connectez-vous au portail classique Azure à l'adresse <https://manage.windowsazure.com>.
4.  Cliquez sur l'icône **Active Directory** dans le menu de gauche, puis cliquez sur le répertoire souhaité.
5.  Dans le menu supérieur, cliquez sur **Applications**, puis sur l'application à configurer. La page **Démarrage rapide** s'affichera à l'ouverture de session unique avec d'autres données de configuration.
6.  Cliquez sur l'onglet **Configurer**, faites défiler l'écran et assurez-vous que l'**ID client** de l'application est identique à celle de l'étape 2 dans cette section.
7.  Cliquez sur le bouton **Supprimer** dans la barre de commandes.
8.  Cliquez sur **Oui** dans le message de confirmation.





