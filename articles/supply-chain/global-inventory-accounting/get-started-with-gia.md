---
title: Premiers pas avec la comptabilité globale des stocks
description: Cette rubrique décrit comment démarrer avec la comptabilité globale des stocks.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 07d3222680d9d9bff639f34eca5fea64d753ffd1
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336977"
---
# <a name="get-started-with-global-inventory-accounting"></a>Premiers pas avec la comptabilité globale des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

La comptabilité globale des stocks vous permet d’effectuer plusieurs comptabilités de stock dans les différents registres de comptabilité globale des stocks que vous avez configurés. Vous devez associer chaque registre de comptabilité globale des stocks à une *convention*. Une convention est un ensemble des types de stratégies comptables suivants :

- Objet de coût
- Base de la mesure en entrée
- Hypothèse de flux de coût
- Élément de coût

> [!NOTE]
> Même après avoir activé la comptabilité globale des stocks, vous pouvez toujours effectuer la comptabilité de stock dans Microsoft Dynamics 365 Supply Chain Management de la manière habituelle.

Le service de comptabilité globale des stocks est un complément. Pour rendre ses fonctionnalités disponibles, vous devez l’installer à partir de Microsoft Dynamics Lifecycle Services (LCS). Vous pouvez choisir de l’évaluer dans un environnement de test avant de l’activer pour les environnements de production.

La comptabilité globale des stocks ne prend actuellement pas en charge toutes les fonctionnalités de gestion des coûts intégrées à Supply Chain Management. Par conséquent, il est important d’évaluer si l’ensemble de fonctionnalités actuellement disponible répondra à vos attentes.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>Comment obtenir la version préliminaire de la comptabilité globale des stocks

> [!IMPORTANT]
> Pour utiliser la comptabilité globale des stocks, vous devez disposer d’un environnement à haute disponibilité compatible LCS (et non d’un environnement OneBox). De plus, vous devez exécuter Supply Chain Management version 10.0.19 ou ultérieure.

Pour vous inscrire à la version préliminaire publique de la comptabilité globale des stocks, envoyez votre ID d’environnement LCS par e-mail à l’[Équipe Comptabilité globale des stocks](mailto:GlobalInventoryAccounting@service.microsoft.com). Une fois que vous avez été approuvé pour le programme, l’équipe vous enverra un e-mail de suivi contenant une clé bêta de Comptabilité globale des stocks et vos points de terminaison de service. Après avoir reçu la clé bêta, vous pourrez [installer le complément](#install).

## <a name="licensing"></a>Gestionnaire de licences

Le complément Comptabilité globale des stocks est concédé sous licence avec les fonctionnalités standard de la comptabilité des stocks disponibles pour Supply Chain Management. Vous n’avez pas besoin d’acheter une licence supplémentaire pour utiliser la comptabilité globale des stocks.

## <a name="prerequisites"></a>Conditions préalables

### <a name="set-up-microsoft-power-platform-integration"></a>Paramétrer l’intégration à Microsoft Power Platform

Avant de pouvoir activer la fonctionnalité de complément, vous devez l’intégrer à Microsoft Power Platform en suivant les étapes ci-après.

1. Ouvrez l’environnement LCS dans lequel vous souhaitez ajouter le service.
1. Accédez à **Détails complets**.
1. Dans la section **Intégration Power Platform**, sélectionnez **Configurer**.
1. Dans la boîte de dialogue **Configuration de l’environnement Power Platform**, cochez la case, puis sélectionnez **Installer**. En règle générale, la configuration prend entre 60 et 90 minutes.
1. Une fois la configuration de l’environnement Microsoft Power Platform terminée, la page affiche le nom de votre environnement. De plus, la section **Intégration de Power Platform** affiche la déclaration suivante : « La configuration de l’environnement Power Platform est terminée. » La comptabilité globale des stocks ne nécessite pas d’application à double écriture.

Pour plus d’informations, voir [Configurer après le déploiement de l’environnement](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).

### <a name="set-up-dataverse"></a>Configuration de Dataverse

Avant de configurer Dataverse, ajoutez les principaux de service Comptabilité globale des stocks à votre locataire en suivant les étapes ci-après.

1. Installez le module Azure AD pour Windows PowerShell v2 comme décrit dans [Installer Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).
1. Exécutez la commande suivante PowerShell.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

Ensuite, créez des utilisateurs d’application pour la comptabilité globale des stocks dans Dataverse en suivant les étapes ci-après.

1. Ouvrez l’URL de votre environnement Dataverse.
1. Aller à **Paramètre avancé \> Système \> Sécurité \> Utilisateurs** et créez un utilisateur d’application. Utilisez le champ **Vue** pour changer la vue de page en *Utilisateurs de l’application*.
1. Sélectionnez **Nouveau**.
1. Définissez le champ **ID application** sur *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. Sélectionner **Attribuer un rôle**, puis *Administrateur système*. S’il y a un rôle nommé *Utilisateur Common Data Service*, sélectionnez-le aussi.
1. Répétez les étapes précédentes, mais définissez le champ **ID d’application** sur *5f58fc56-0202-49a8-ac9e-0946b049718b*.

Pour plus d’informations, voir [Créer un utilisateur d’application](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

Si la langue par défaut de votre installation Dataverse n’est pas l’anglais, suivez les étapes ci-après.

1. Accédez à **Paramètres avancés \> Administration \> Langues**.
1. Sélectionnez *Anglais* (*LanguageCode=1033*), puis sélectionnez **Appliquer**.

## <a name="install-the-add-in"></a><a name="install"></a>Installer le complément

Suivez ces étapes pour installer le complément afin de pouvoir utiliser la comptabilité globale des stocks.

1. [S’inscrire](#sign-up) pour la version préliminaire de Comptabilité globale des stocks.
1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index).
1. Accédez à **Gestion des fonctionnalités d’aperçu**.
1. Sélectionnez le signe plus (**+**).
1. Dans le champ **Code**, entrez votre clé bêta du complément Comptabilité globale des stocks. (Vous devriez avoir reçu votre clé bêta par e-mail lors de votre inscription.)
1. Sélectionnez **Débloquer**.
1. Ouvrez l’environnement LCS dans lequel vous souhaitez ajouter le service.
1. Accédez à **Détails complets**.
1. Accédez à **Intégration Power Platform** et sélectionnez **Installer**.
1. Dans la boîte de dialogue **Configuration de l’environnement Power Platform**, cochez la case, puis sélectionnez **Installer**. En règle générale, la configuration prend entre 60 et 90 minutes.
1. Une fois la configuration de l’environnement Microsoft Power Platform terminée, dans le raccourci **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
1. Sélectionnez **Comptabilité globale des stocks**.
1. Suivez le guide d’installation, et acceptez les conditions générales du contrat.
1. Sélectionnez **Installer**.
1. Dans le raccourci **Compléments d’environnement**, vous devriez voir que le complément Comptabilité globale des stocks est en cours d’installation. Après quelques minutes, le statut devrait passer de *Installation* à *Installé*. (Vous devrez peut-être actualiser la page pour voir cette modification.) À ce stade, le complément Comptabilité globale des stocks est prêt à être utilisé.

## <a name="set-up-the-integration"></a>Paramétrage de l’intégration

Suivez les étapes ci-après pour configurer l’intégration entre Comptabilité globale des stocks et Supply Chain Management.

1. Connectez-vous à Supply Chain Management.
1. Accédez à **Administration système \> Gestion des fonctionnalités**.
1. Sélectionnez **Rechercher des mises à jour**.
1. Sur l’onglet **Tout**, recherchez l’entité nommée *Comptabilité globale des stocks*.
1. Sélectionnez **Activer maintenant**.
1. Accédez à **Comptabilité globale des stocks \> Installer \> Paramètres de la comptabilité globale des stocks \> Paramètres d’intégration**.
1. Dans les champs **Point de terminaison du service de données** et **Point de terminaison de Comptabilité globale des stocks**, saisissez les URL de l’e-mail que l’équipe Comptabilité globale des stocks vous a envoyé lorsque vous vous êtes inscrit à la version préliminaire.

Comptabilité globale des stocks est maintenant prêt à être utilisé.
