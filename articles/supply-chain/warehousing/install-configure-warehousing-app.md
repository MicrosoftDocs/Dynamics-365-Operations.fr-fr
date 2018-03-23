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
ms.sourcegitcommit: 608543c9cfd93c4772e93089e1d174312d8b23a6
ms.openlocfilehash: 411bb28668f5aa9d07774211814da4e9757ac43c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/06/2018

---

# <a name="install-and-configure-microsoft-dynamics-365-for-finance-and-operations-8211-warehousing"></a>Installation et configuration de Microsoft Dynamics 365 for Finance and Operations &#8211; Entreposage

[!include[banner](../includes/banner.md)]


> [!NOTE]

> Cette rubrique décrit comment configurer l'entreposage pour les déploiements cloud. Si vous souhaitez savoir comment configurer l'entreposage pour les déploiements sur site, consultez [Entreposage pour les déploiements sur site](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


Cette rubrique décrit la procédure d'installation et de configuration de Microsoft Dynamics 365 for Finance and Operations - Entreposage.

Finance and Operations - Entreposage est une application disponible dans le Google Play Store et le Windows Store. Pour la version actuelle de Finance and Operations, cette application est fournie en tant que composant autonome, ce qui signifie un auto-déploiement sur les périphériques utilisés pour les tâches d'entrepôt. Pour utiliser l'application dans votre environnement Finance and Operations, vous devez télécharger l'application sur chaque périphérique et la configurer en vue d'une connexion à votre environnement Finance and Operations. Cette rubrique décrit la procédure d'installation de l'application sur vos périphériques. Elle décrit également comment configurer l'application pour se connecter à votre environnement Finance and Operations.

## <a name="prerequisites"></a>Conditions préalables
L'application est disponible sur les systèmes d'exploitation Android et Windows. Pour utiliser cette application, vous devez avoir l'un des systèmes d'exploitation pris en charge suivants installés sur vos périphériques. Vous devez également avoir une des versions prises en charge suivantes de Finance and Operations. Utilisez les informations contenues dans le tableau suivant pour évaluer si votre environnement matériel et logiciel est prêt à prendre en charge l'installation.

| Plateforme                    | Version                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (toutes les versions)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations, version 1611 <br>- ou - <br>Microsoft Dynamics AX version 7.0/7.0.1 et Microsoft Dynamics AX Platform - Mise à jour 2 avec correctif. Voir l'article de la base de connaissances 3210014 |

## <a name="get-the-app"></a>Obtenir l'application
-   Windows (UWP)
     - [Finance and Operations - Entreposage dans le Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - Windows (UWP) - [Finance and Operations - Entreposage dans le Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)
    - Windows (UWP) - [Finance and Operations - Entreposage dans la Zebra App Gallery](https://appgallery.zebra.com/showcase/apps/146?type=showcase)

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Créer une application de service Web dans Azure Active Directory
Pour permettre à l'application d'interagir avec un serveur Finance and Operations, vous devez enregistrer une application de service Web dans un répertoire Azure Active Directory pour le locataire Finance and Operations. Pour des raisons de sécurité, nous vous recommandons de créer une application de service Web pour chaque périphérique que vous utilisez. Pour créer une application de service Web dans Azure Active Directory (Azure AD), procédez comme suit :

1.  Dans un navigateur Web, accédez à <https://portal.azure.com>.
2.  Entrez le nom et le mot de passe de l'utilisateur qui a accès à l'abonnement Azure.
3.  Dans le portail Azure, dans le volet de navigation gauche, cliquez sur **Azure Active Directory**.[](./media/WMA-01-active-directory-example.png)[![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)
4.  Vérifiez que l'instance Active Directory est celle utilisée par Finance and Operations.
5.  Dans la liste, cliquez sur **Enregistrements d'application**. [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)
6.  Dans le volet supérieur, cliquez sur **Nouvel enregistrement d'application**. L'assistant **Ajouter une application** démarre.
7.  Entrez un nom pour l'application et sélectionnez **Application web/API web**. Entrez l'URL de connexion, qui est une URL d'application Web. Cette URL est identique à votre URL de déploiement, mais oauth est ajouté à la fin. Cliquez sur **Créer**. [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)
8.  Sélectionnez la nouvelle application dans la liste. [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)
9.  Mémorisez l'**ID application**, vous en aurez besoin ultérieurement. L'**ID application** sera appelé par la suite **ID client**.
10. Cliquez sur **Clés** dans le volet **Paramètres**. Créez une clé en entrant une description de la clé et une durée dans la section **Mots de passe**. 
11. Cliquez sur **Enregistrer** et copiez la clé. Cette clé sera par la suite référencée en tant que **Clé secrète client**. [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

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
    + **ID du client Azure Active Directory** - L'ID du client est obtenu à l'étape 9 dans « Créer une application de service Web dans Active Directory ». 
    + **Question secrète du client Azure Active Directory** - La question secrète est obtenue à l'étape 11 dans "Créer une application de service Web dans Active Directory". 
    + **Ressource Azure Active Directory** - la ressource Azure Active Directory représente l'URL racine de Finance and Operations. **Remarque** : ne terminez pas ce champ avec une barre oblique inverse (/). 
    + **Locataire Azure Active Directory** - Le locataire Azure Active Directory représente l'URL racine de Finance and Operations : `https://login.windows.net/your-AD-tenant-ID`. Exemple : `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    <br>**Remarque** : ne terminez pas ce champ avec une barre oblique inverse (/). 
    + **Société** - Accédez à l'entité juridique de Finance and Operations à laquelle vous souhaitez que l'application se connecte. <br>[![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Sélectionnez le bouton **Précédent** dans le coin supérieur gauche de l'application. L'application se connecte maintenant à votre serveur Finance and Operations et l'écran de connexion du collaborateur d'entrepôt s'affiche. <br>[![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Pour plus d'informations sur la configuration de Dynamics 365 for Finance and Operations – Entreposage pour lire des codes-barres à l'aide d'une caméra sur un appareil mobile, consultez [Lire les codes-barres à l'aide d'une caméra dans Dynamics 365 for Finance and Operations – Entreposage](scan-bar-codes-using-a-camera.md)

## <a name="remove-access-for-a-device"></a>Suppression de l'accès pour un périphérique
En cas de périphérique perdu ou compromis, vous devez supprimer l'accès Finance and Operations du périphérique. Les étapes suivantes décrivent le processus recommandé pour supprimer l'accès.

1.  Dans Finance and Operations, accédez à **Administration du système** &gt; **Paramétrage** &gt; **Applications Azure Active Directory**.
2.  Supprimez la ligne correspondant au périphérique auquel vous souhaitez supprimer l'accès. Mémorisez l'**ID client** utilisé pour le périphérique supprimé, vous en aurez besoin ultérieurement.
3.  Connectez-vous au portail Azure à l'adresse suivante : <https://portal.azure.com>.
4.  Cliquez sur l'icône **Active Directory** dans le menu de gauche, puis vérifiez que vous vous trouvez dans le répertoire approprié.
5.  Dans la liste, cliquez sur **Enregistrements d'application**, puis sur l'application à configurer. La page **Paramètres** s'affiche avec les informations de configuration.
6.  Assurez-vous que l'**ID client** de l'application est identique à celui de l'étape 2 de cette section.
7.  Cliquez sur le bouton **Supprimer** dans le volet supérieur.
8.  Cliquez sur **Oui** dans le message de confirmation.

