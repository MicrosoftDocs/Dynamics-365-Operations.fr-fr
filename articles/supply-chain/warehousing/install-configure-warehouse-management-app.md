---
title: Installer et connecter l’application mobile Gestion des entrepôts
description: Cette rubrique explique comment installer l’application mobile Gestion des entrepôts sur chacun de vos appareils mobiles et la configurer pour se connecter à votre environnement Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f46c5d4ec78a1e5ed708687e8da6eb379697d5f4
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908950"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Installer et connecter l’application mobile Gestion des entrepôts

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Cette rubrique décrit comment configurer la nouvelle application mobile Gestion des entrepôts. Si vous recherchez des informations sur la configuration de l’ancienne application d’entrepôt (désormais obsolète), voir [Installer et connecter l’application d’entrepôt](../../supply-chain/warehousing/install-configure-warehousing-app.md).

Cette rubrique explique comment télécharger et installer l’application mobile Gestion des entrepôts sur chacun de vos appareils mobiles et configurer l’application pour se connecter à votre environnement Supply Chain Management. Vous pouvez configurer chaque appareil manuellement, ou vous pouvez importer les paramètres de connexion via un fichier ou en scannant un code QR.

## <a name="system-requirements"></a>Configuration requise

L’application mobile Gestion des entrepôts est disponible pour les systèmes d’exploitation Windows et Google Android. Pour utiliser l’application, l’un des systèmes d’exploitation suivants doit être installé sur vos appareils mobiles :

- Windows 10 (Plateforme Windows universelle \[UWP\]), mise à jour 1809 d’octobre 2018 (build 10.0.17763) ou version ultérieure
- Android 4.4 ou version ultérieure

## <a name="turn-on-the-feature"></a>Activer la fonctionnalité

Avant de pouvoir utiliser l’application, une fonctionnalité associée doit être activée dans votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Là, la fonctionnalité est répertoriée de la manière suivante :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Paramètres utilisateur, icônes et titres des étapes de la nouvelle application d’entrepôt*

## <a name="get-the-warehouse-management-mobile-app"></a>Obtenir l’application mobile Gestion des entrepôts

Pour les déploiements plus petits, vous pouvez souhaiter installer l’application sur chaque appareil à partir du magasin approprié, puis configurer manuellement la connexion aux environnements que vous utilisez.

Pour les déploiements plus importants, vous pouvez automatiser le déploiement et / ou la configuration des applications, ce qui peut être plus pratique si vous gérez de nombreux appareils. Par exemple, vous pouvez utiliser une solution de gestion des appareils mobiles et de gestion des applications mobiles telle que [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Pour plus d’informations sur l’utilisation d’Intune pour ajouter des applications, consultez [Ajouter des applications à Microsoft Intune](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Installez l’application à partir d’un App Store

Le moyen le plus simple d’installer l’application sur un seul appareil est de l’installer à partir d’un magasin d’applications, qui fournit toujours la dernière version généralement disponible. Microsoft Intune peut également récupérer des applications dans les App Stores. Utilisez l’un des liens suivants pour installer l’application à partir d’un App Store :

- **Windows (UWP) :** [Gestion des entrepôts sur Microsoft Store](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android :** [Gestion des entrepôt sur Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Téléchargez l’application à partir de Microsoft App Center

Au lieu d’installer à partir d’un App Store, vous pouvez à la place télécharger l’application à partir du Microsoft App Center. L’App Center fournit des packages installables que vous pouvez charger de manière indépendante. En plus de la version actuelle, l’App Center vous permet également de télécharger des versions précédentes et peut fournir des versions préliminaires avec des fonctionnalités à venir que vous pouvez essayer. Pour télécharger les versions actuelles, précédentes ou en préversion de l’application mobile Gestion des entrepôts à partir de Microsoft App Center, utilisez l’un des liens suivants :

- **Windows (UWP) :** [Gestion des entrepôts (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    Pour savoir comment installer un package téléchargé sur un appareil Windows, puis configurer les certificats requis, voir [Installer une version depuis App Center](/appcenter/distribution/installation).

- **Android :** [Gestion des entrepôts (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Si vous téléchargez une version préliminaire, quelques étapes supplémentaires sont nécessaires pour l’installer. Pour plus d’informations, voir [Tester des applications Android](/appcenter/distribution/testers/testing-android).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Créer une application de service Web dans Azure Active Directory

Pour permettre à l’application mobile Gestion des entrepôts d’interagir avec un serveur Supply Chain Management spécifique, vous devez enregistrer une application de service web pour le client Supply Chain Management dans Azure Active Directory (Azure AD). La procédure suivante montre comment effectuer cette tâche. Pour des informations détaillées et des alternatives, consultez les liens après la procédure.

1. Dans un navigateur Web, accédez à [https://portal.azure.com](https://portal.azure.com/).
1. Entrez le nom et le mot de passe de l’utilisateur qui a accès à l’abonnement Azure.
1. Dans le portail Azure, dans le volet gauche de navigation, cliquez sur **Azure Active Directory**.

    ![Azure Active Directory](media/app-connect-azure-aad.png "Azure Active Directory")

1. Assurez-vous que vous utilisez l’instance Azure AD utilisée par Supply Chain Management.
1. Dans la liste **Gérer**, cliquez sur **Enregistrements d’application**.

    ![Enregistrements d’application](media/app-connect-azure-register.png "Enregistrements d’application")

1. Dans la barre d’outils, sélectionnez **Nouvelle inscription** pour ouvrir l’assistant **Enregistrer une application**.
1. Entrez un nom pour l’application et sélectionnez l’option **Comptes dans ce répertoire organisationnel uniquement**, puis **Enregistrer**.

    ![Enregistrer un assistant d’application](media/app-connect-azure-register-wizard.png "Enregistrer un assistant d’application")

1. Votre nouvel enregistrement d’application s’ouvre. Notez la valeur dans le champ **ID d’application (client)**, car vous en aurez besoin ultérieurement. Cet ID sera appelé *ID client* plus loin dans cette rubrique.

    ![ID application (client)](media/app-connect-azure-app-id.png "ID application (client)")

1. Dans la liste **Gérer**, cliquez sur **Certificat et secrets**. Sélectionnez ensuite l’un des boutons suivants, selon la façon dont vous souhaitez configurer l’application pour l’authentification. (Pour plus d’informations, consultez la section [Authentification à l’aide d’un certificat ou un secret client](#authenticate) plus loin dans cette rubrique.)

    - **Télécharger le certificat** : Téléchargez un certificat à utiliser comme secret. Nous recommandons cette approche, car elle est plus sécurisée et peut également être automatisée plus complètement. Si vous exécutez l’application mobile Gestion des entrepôts sur des appareils Windows, notez la valeur **Empreinte** affichée après le chargement du certificat. Vous aurez besoin de cette valeur lorsque vous configurerez le certificat sur les appareils Windows.
    - **Nouveau secret client** : Créez une clé en saisissant une description et une durée dans la section **Mot de passe**, puis sélectionnez **Ajouter**. Faites une copie de la clé et conservez-la en lieu sûr.

    ![Certificat et secrets](media/app-connect-azure-authentication.png "Certificat et secrets")

Pour plus d’informations sur la configuration des applications de service Web dans Azure AD, consultez les ressources suivantes :

- Pour obtenir des instructions qui montrent comment utiliser Windows PowerShell pour configurer des applications de service Web dans Azure AD, voir [Comment : Utiliser Azure PowerShell pour créer un principal de service avec un certificat](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Pour plus de détails sur la création manuelle d’une application de service Web dans Azure AD, consultez les rubriques suivantes :

    - [Démarrage rapide : Enregistrer une application avec la plateforme d’identités Microsoft](/azure/active-directory/develop/quickstart-register-app)
    - [Comment : Utiliser le portail pour créer une application Azure AD et un principal de service qui peut accéder aux ressources](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Créer et configurer un compte d’utilisateur dans Supply Chain Management

Pour permettre à Supply Chain Management d’utiliser votre application Azure AD, procédez comme suit.

1. Créez un utilisateur qui correspond aux informations d’identification de l’utilisateur pour l’application mobile Gestion des entrepôts :

    1. Dans Supply Chain Management, accédez à **Administration du système \> Utilisateurs \> Utilisateurs**.
    1. Créez un utilisateur.
    1. Attribuez l’utilisateur de l’appareil mobile d’entreposage.

    ![Attribuer l’utilisateur de l’appareil mobile d’entreposage](media/app-connect-app-users.png "Attribuer l’utilisateur de l’appareil mobile d’entreposage")

1. Associez votre application Azure AD à l’utilisateur de l’application mobile Gestion des entrepôts :

    1. Accédez à **Administration système \> Paramétrage \> Applications Azure Active Directory**.
    1. Créez une ligne.
    1. Entrez l’ID client que vous avez noté dans la section précédente, donnez-lui un nom et sélectionnez l’utilisateur que vous venez de créer. Nous vous recommandons de marquer tous vos appareils. Ensuite, si un appareil est perdu, vous pouvez facilement supprimer son accès à Supply Chain Management à partir de cette page.

    ![Applications Azure Active Directory](media/app-connect-aad-apps.png "Applications Azure Active Directory")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Authentifiez-vous en utilisant un certificat ou un secret client

L’authentification avec Azure AD fournit un moyen sécurisé de connecter un appareil mobile à Supply Chain Management. Vous pouvez vous authentifier en utilisant un certificat ou un secret client. Si vous importez des paramètres de connexion, nous vous recommandons d’utiliser un certificat au lieu d’un secret client. Étant donné que le secret client doit toujours être stocké en toute sécurité, vous ne pouvez pas l’importer à partir d’un fichier de paramètres de connexion ou d’un code QR, comme décrit plus loin dans cette rubrique.

Les certificats peuvent être utilisés comme secrets pour prouver l’identité de l’application lorsqu’un jeton est demandé. La partie publique du certificat est chargée dans l’inscription de l’application dans le portail Azure, tandis que le certificat complet doit être déployé sur chaque appareil sur lequel l’application mobile Gestion des entrepôts est installée. Votre organisation est responsable de la gestion du certificat en termes de rotation, etc. Vous pouvez utiliser des certificats auto-signés, mais vous devez toujours utiliser des certificats non exportables.

Vous devez rendre le certificat disponible localement sur chaque appareil sur lequel vous exécutez l’application mobile Gestion des entrepôts. Pour plus d’informations sur la gestion des certificats pour les appareils contrôlés par Intune si vous utilisez Intune, consultez [Utiliser des certificats pour l’authentification dans Microsoft Intune](/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Configurer l’application en important des paramètres de connexion

Pour faciliter la maintenance et le déploiement de l’application sur de nombreux appareils mobiles, vous pouvez importer les paramètres de connexion au lieu de les saisir manuellement sur chaque appareil. Cette section explique comment créer et importer des paramètres.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Créer un fichier de paramètres de connexion ou un code QR

Vous pouvez importer les paramètres de connexion à partir d’un fichier ou d’un code QR. Pour les deux approches, vous devez d’abord créer un fichier de paramètres qui utilise le format et la syntaxe JSON (JavaScript Object Notation). Le fichier doit inclure une liste de connexions contenant les connexions individuelles à ajouter. Le tableau suivant résume les paramètres que vous devez spécifier dans le fichier de paramètres de connexion.

| Paramètre | Description |
|---|---|
| ConnectionName | Permet d’indiquer le nom du paramètre de connexion. La longueur maximale est de 20 caractères. Étant donné que cette valeur est l’identificateur unique d’un paramètre de connexion, assurez-vous qu’il est unique dans la liste. Si une connexion portant le même nom existe déjà sur l’appareil, elle sera remplacée par les paramètres du fichier importé. |
| ActiveDirectoryClientAppId | Spécifiez l’ID client que vous avez noté lors de la configuration Azure AD dans la section [Créer une application de service Web dans Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Spécifiez l’URL racine de Supply Chain Management. |
| ActiveDirectoryTenant | Spécifie le client Azure AD que vous utilisez avec le serveur Supply Chain Management. Cette valeur a la forme `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Voici un exemple : `https://login.windows.net/contosooperations.onmicrosoft.com`. |
| Société | Spécifiez l’entité juridique de Supply Chain Management à laquelle vous souhaitez que l’application se connecte. |
| ConnectionType | (Facultatif) Spécifiez si le paramètre de connexion doit utiliser un certificat ou un secret client pour se connecter à un environnement. Les valeurs valides sont *certificat* et *clientsecret*. La valeur par défaut est *certificat*.<p>**Remarque :** Les secrets client ne peuvent pas être importés.</p> |
| IsEditable | (Facultatif) Spécifiez si l’utilisateur de l’application doit pouvoir modifier le paramètre de connexion. Les valeurs valides sont *true* et *false*. La valeur par défaut est *true*. |
| IsDefault | (Facultatif) Spécifiez si la connexion est celle par défaut. Une connexion définie comme celle par défaut sera automatiquement présélectionnée à l’ouverture de l’application. Une seul connexion peut être définie comme celle par défaut. Les valeurs valides sont *true* et *false*. La valeur par défaut est *false*. |
| CertificateThumbprint | (Facultatif) Pour les appareils Windows, vous pouvez spécifier l’empreinte numérique du certificat pour la connexion. Pour les appareils Android, l’utilisateur de l’application doit sélectionner le certificat la première fois qu’une connexion est utilisée. |

L’exemple suivant montre un fichier de paramètres de connexion valide qui contient deux connexions. Comme vous pouvez le voir, la liste des connexions (nommée *ConnectionList* dans le fichier) est un objet qui a un tableau qui stocke chaque connexion en tant qu’objet. Chaque objet doit être placé entre accolades ({}) et séparé par des virgules, et le tableau doit être placé entre crochets (\[\]).

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Vous pouvez soit enregistrer les informations sous forme de fichier JSON, soit générer un code QR ayant le même contenu. Si vous enregistrez les informations dans un fichier, nous vous recommandons de le faire en utilisant le nom par défaut, *connections.json*, surtout si vous le stockez à l’emplacement par défaut sur chaque appareil mobile.

### <a name="save-the-connection-settings-file-on-each-device"></a>Enregistrer le fichier des paramètres de connexion sur chaque appareil

En règle générale, vous utiliserez un outil ou un script de gestion des périphériques pour distribuer les fichiers de paramètres de connexion à chaque périphérique que vous gérez. Si vous utilisez le nom et l’emplacement par défaut lorsque vous enregistrez le fichier de paramètres de connexion sur chaque appareil, l’application mobile Gestion des entrepôts l’importera automatiquement, même lors de la première exécution après l’installation de l’application. Si vous utilisez un nom ou un emplacement personnalisé pour le fichier, l’utilisateur de l’application doit spécifier les valeurs lors de la première exécution. Cependant, l’application continuera à utiliser le nom et l’emplacement spécifiés par la suite.

Chaque fois que l’application est lancée, elle réimporte les paramètres de connexion depuis leur emplacement précédent pour déterminer s’il y a eu des modifications. L’application ne mettra à jour que les connexions portant les mêmes noms que les connexions du fichier de paramètres de connexion. Les connexions créées par l’utilisateur qui utilisent d’autres noms ne seront pas mises à jour.

Vous ne pouvez pas supprimer une connexion en utilisant le fichier de paramètres de connexion.

Comme cela a été mentionné, le nom de fichier par défaut est *connections.json*. L’emplacement de fichier par défaut varie selon que vous utilisez un appareil Windows ou Android :

- **Windows :** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android :** `Android\data\com.Microsoft.WarehouseManagement\files`

Habituellement, les chemins sont créés automatiquement après la première exécution de l’application. Cependant, vous pouvez les créer manuellement si vous devez transférer le fichier des paramètres de connexion sur l’appareil avant l’installation.

> [!NOTE]
> Si l’application est désinstallée, le chemin par défaut et son contenu sont supprimés.

### <a name="import-the-connection-settings"></a>Importer les paramètres de connexion

Suivez ces étapes pour importer les paramètres de connexion à partir d’un fichier ou d’un code QR.

1. Démarrez l’application mobile Gestion des entrepôts sur votre appareil mobile. La première fois que vous démarrez l’application, un message de bienvenue s’affiche. Sélectionnez **Sélectionner une connexion**.

    ![Message de bienvenue](media/app-configure-welcome-screen.png "Message de bienvenue")

1. Si vous importez les paramètres de connexion à partir d’un fichier et si le nom et l’emplacement par défaut ont été utilisés lors de l’enregistrement du fichier, l’application a peut-être déjà trouvé le fichier. Dans ce cas, passez à l’étape 4. Sinon, sélectionnez **Configurer la connexion**, puis passez à l’étape 3.

    ![Configurer la connexion](media/app-configure-set-up-connection.png "Configurer la connexion")

1. Dans la boîte de dialogue **Configuration de la connexion**, sélectionnez **Ajouter à partir d’un fichier** ou **Ajouter à partir du code QR**, selon la manière dont vous souhaitez importer les paramètres :

    - Si vous importez les paramètres de connexion à partir d’un fichier, sélectionnez **Ajouter à partir d’un fichier**, recherchez le fichier sur votre appareil local et sélectionnez-le. Si vous sélectionnez un emplacement personnalisé, l’application le stockera et l’utilisera automatiquement la prochaine fois.
    - Si vous importez les paramètres de connexion en scannant un code QR, sélectionnez **Ajouter à partir du code QR**. L’application vous demande l’autorisation d’utiliser l’appareil photo de l’appareil. Une fois que vous avez donné votre autorisation, l’appareil photo démarre, afin que vous puissiez l’utiliser pour la numérisation. Selon la qualité de l’appareil photo de l’appareil et la complexité du code QR, il peut être difficile d’obtenir une analyse correcte. Dans ce cas, essayez de réduire la complexité du code QR en générant une seule connexion par code QR. (Actuellement, vous ne pouvez utiliser que l’appareil photo de l’appareil pour numériser le code QR.)

    ![Menu de configuration de la connexion](media/app-configure-connection-setup-flyout.png "Menu de configuration de la connexion")

1. Lorsque les paramètres de connexion sont correctement chargés, la connexion sélectionnée s’affiche.

    ![Paramètres de connexion chargés](media/app-configure-select-connection.png "Paramètres de connexion chargés")

1. Si vous utilisez un appareil Android et un certificat pour l’authentification, l’appareil vous invite à sélectionner le certificat.

    ![Invite de sélection du certificat sur un appareil Android](media/app-configure-select-certificate.png "Invite de sélection du certificat sur un appareil Android")

1. L’application se connecte à votre serveur Supply Chain Management et affiche la page de connexion.

    ![Page de connexion](media/app-configure-sign-in-page.png "Page de connexion")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Configurer manuellement l’application

Si vous n’avez pas de fichier ou de code QR, vous pouvez configurer manuellement l’application sur l’appareil pour qu’elle se connecte au serveur Supply Chain Management via l’application Azure AD.

1. Démarrez l’application mobile Gestion des entrepôts sur votre appareil mobile.
1. Si l’application est démarrée en **Mode démonstration**, sélectionnez **Paramètres de connexion**. Si la page **Connexion** apparaît au démarrage de l’application, sélectionnez **Changer de connexion**.
1. Sélectionnez **Configurer la connexion**.

    ![Configurer la connexion](media/app-configure-set-up-connection.png "Configurer la connexion")

1. Sélectionnez **Saisie manuelle**.

    ![Menu de configuration de la connexion](media/app-configure-connection-setup-flyout.png "Menu de configuration de la connexion")

    La page **Nouvelle connexion** apparaît et affiche les paramètres nécessaires pour entrer manuellement les détails de la connexion.

    ![Champs de connexion manuelle](media/app-configure-input-manually.png "Champs de connexion manuelle")

1. Entrez les informations suivantes :

    - **Utiliser le secret client** : Définissez cette option sur _Oui_ pour utiliser un secret client pour vous authentifier auprès de Supply Chain Management. Définissez-le sur _Non_ pour utiliser un certificat pour l’authentification. (Pour plus d’informations, voir la section [Créer une application de service web dans Azure Active Directory](#create-service) plus haut dans cette rubrique.)
    - **Nom de la connexion** : Saisissez un nom pour la nouvelle connexion. Ce nom apparaîtra dans le champ **Sélectionner la connexion** la prochaine fois que vous ouvrirez les paramètres de connexion. Le nom que vous entrez doit être unique. (En d’autres termes, il doit différer de tous les autres noms de connexion stockés sur votre appareil, le cas échéant.)
    - **ID du client Azure Active Directory** : Spécifiez l’ID client que vous avez noté lors de la configuration Azure AD dans la section [Créer une application de service Web dans Azure Active Directory](#create-service).
    - **Secret client Active Directory** : Ce champ n’est disponible que lorsque l’option **Utiliser le secret client** est définie sur _Oui_. Entrez le secret client que vous avez noté lors de la configuration Azure AD dans la section [Créer une application de service Web dans Azure Active Directory](#create-service).
    - **Empreinte de certificat Active Directory** : ce champ n’est disponible que pour les appareils Windows et uniquement si l’option **Utiliser la clé secrète client** est définie sur _Non_. Entrez les informations d’empreinte de certificat que vous avez notées lors de la configuration Azure AD dans la section [Créer une application de service Web dans Azure Active Directory](#create-service).
    - **Ressource Active Directory** : Spécifiez l’URL racine de Supply Chain Management.

        > [!IMPORTANT]
        > Ne terminez pas cette valeur par une barre oblique (/).

    - **Client Active Directory** : Entrez le client Azure AD que vous utilisez avec le serveur Supply Chain Management. Cette valeur a la forme `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Voici un exemple : `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!IMPORTANT]
        > Ne terminez pas cette valeur par une barre oblique (/).

    - **Société** : accédez à l’entité juridique (société) de Supply Chain Management à laquelle vous souhaitez que l’application se connecte.

1. Sélectionnez le bouton **Enregistrer** dans le coin supérieur droit de la page.
1. Si vous utilisez un appareil Android et un certificat pour l’authentification, l’appareil vous invite à sélectionner le certificat.
1. L’application se connecte à votre serveur Supply Chain Management et affiche la page de connexion.

## <a name="remove-access-for-a-device"></a>Suppression de l’accès pour un périphérique

Si un appareil est perdu ou compromis, vous devez supprimer son accès à Supply Chain Management. Les étapes suivantes décrivent le processus recommandé pour supprimer l’accès.

1. Accédez à **Administration système \> Paramétrage \> Applications Azure Active Directory**.
1. Supprimez la ligne correspondant au périphérique auquel vous souhaitez supprimer l’accès. Notez l’ID client utilisé pour l’appareil, car vous en aurez besoin plus tard.

    Si vous n’avez enregistré qu’un seul ID client et que plusieurs appareils utilisent le même ID client, vous devez pousser de nouveaux paramètres de connexion vers ces appareils. Sinon, ils perdront l’accès.

1. Connectez-vous au portail Azure à l’adresse suivante : [https://portal.azure.com](https://portal.azure.com/).
1. Dans le volet de navigation de gauche, sélectionnez **Active Directory** et assurez-vous que vous êtes dans le bon répertoire.
1. Dans la liste **Gérer**, cliquez sur **Enregistrements d’application**, puis sur l’application à configurer. La page **Paramètres** s’affiche avec les informations de configuration.
1. Assurez-vous que l’ID client de l’application correspond à l’ID client que vous avez noté à l’étape 2.
1. Sélectionnez **Supprimer** dans la barre d’outils.
1. Dans la boîte de message de confirmation qui apparaît, sélectionnez **Oui**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]