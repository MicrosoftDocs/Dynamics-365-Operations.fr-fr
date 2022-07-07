---
title: Démarrage de la comptabilité globale des stocks
description: Cet article décrit comment démarrer avec la comptabilité globale des stocks.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cbe6bff6fab96900b8bd4e112a8858363fff86d1
ms.sourcegitcommit: 9870b773a2ea8f5675651199fdbc63ca7a1b4453
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013553"
---
# <a name="get-started-with-global-inventory-accounting"></a>Premiers pas avec la comptabilité globale des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

La comptabilité globale des stocks vous permet d’effectuer plusieurs comptabilités de stock dans les différents registres de comptabilité globale des stocks que vous avez configurés. Vous devez associer chaque registre de comptabilité globale des stocks à une *convention*. Une convention est un ensemble des types de stratégies comptables suivants :

- Objet de coût
- Base de la mesure en entrée
- Hypothèse de flux de coût
- Élément de coût

> [!NOTE]
> Même après avoir activé la comptabilité globale des stocks, vous pouvez toujours effectuer la comptabilité de stock dans Microsoft Dynamics 365 Supply Chain Management de la manière habituelle.

Le service de comptabilité globale des stocks est un complément. Pour rendre ses fonctionnalités disponibles, vous devez l’installer à partir de Microsoft Dynamics Lifecycle Services (LCS). Vous pouvez choisir de l’évaluer dans un environnement de test avant de l’activer pour les environnements de production.

La comptabilité globale des stocks ne prend actuellement pas en charge toutes les fonctionnalités de gestion des coûts intégrées à Supply Chain Management. Par conséquent, il est important d’évaluer si l’ensemble de fonctionnalités actuellement disponible répondra à vos attentes.

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a>Comment obtenir le complément Comptabilité globale des stocks

> [!IMPORTANT]
> Pour utiliser la comptabilité globale des stocks, vous devez disposer d’un environnement à haute disponibilité compatible LCS (et non d’un environnement OneBox). De plus, vous devez exécuter Supply Chain Management version 10.0.19 ou ultérieure.

### <a name="supply-chain-management-version-10019-to-10026"></a>Supply Chain Management version 10.0.19 à 10.0.26

Pour installer Comptabilité globale des stocks pour Supply Chain Management version 10.0.19 à 10.0.26, commencez par [installer le complément](#install). Envoyez ensuite votre ID d'environnement LCS et le nom de votre entreprise par e-mail à l'[Équipe Comptabilité globale des stocks](mailto:GlobalInvAccount@microsoft.com). L’équipe vous enverra un e-mail de suivi contenant vos points de terminaison de service Comptabilité globale des stocks.

### <a name="supply-chain-management-version-10027-and-later"></a>Supply Chain Management version 10.0.27 et versions ultérieures

Pour installer Comptabilité globale des stocks pour Supply Chain Management versions 10.0.27 et ultérieures, [installez simplement le complément](#install). Pour ces versions de Supply Chain Management, les points de terminaison du service Comptabilité globale des stocks seront configurés automatiquement, vous n'avez donc pas besoin de les rechercher manuellement. Si vous rencontrez des problèmes lors de la configuration du complément, veuillez contacter l'[Équipe Comptabilité globale des stocks](mailto:GlobalInvAccount@microsoft.com).

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

Pour plus d’informations, voir [Activer après le déploiement de l’environnement](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="install-the-add-in"></a><a name="install"></a>Installer le complément

Suivez ces étapes pour installer le complément afin de pouvoir utiliser la comptabilité globale des stocks.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index).
1. Ouvrez l’environnement LCS dans lequel vous souhaitez ajouter le service.
1. Accédez à **Détails complets**.
1. Accédez à **Intégration Power Platform** et sélectionnez **Installer**.
1. Dans la boîte de dialogue **Configuration de l’environnement Power Platform**, cochez la case, puis sélectionnez **Installer**. En règle générale, la configuration prend entre 60 et 90 minutes.
1. Après la configuration de l’environnement Microsoft Power Platform, connectez-vous au [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com), puis installez le complément Comptabilité globale des stocks en procédant comme suit :
   1. Sélectionnez l'environnement où vous souhaitez installer le complément.
   1. Sélectionnez **Applications Dynamics 365**.
   1. Sélectionnez **Installer l'application**.
   1. Sélectionnez **Comptabilité globale des stocks Dynamics 365**.
   1. Sélectionnez **Suivant** pour effectuer l’installation.
1. Revenez à l’environnement LCS. Dans le raccourci **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
1. Sélectionnez **Comptabilité globale des stocks**.
1. Suivez le guide d’installation, et acceptez les conditions générales du contrat.
1. Sélectionnez **Installer**.
1. Dans le raccourci **Compléments d’environnement**, vous devriez voir que le complément Comptabilité globale des stocks est en cours d’installation. Après quelques minutes, le statut devrait passer de *Installation* à *Installé*. (Vous devrez peut-être actualiser la page pour voir cette modification.) À ce stade, le complément Comptabilité globale des stocks est prêt à être utilisé.

Si la langue par défaut de votre installation Dataverse n’est pas l’anglais, suivez les étapes ci-après :
1. Accédez à **Paramètres avancés \> Administration \> Langues**.
1. Sélectionnez *Anglais* (*LanguageCode=1033*), puis sélectionnez **Appliquer**.

## <a name="set-up-the-integration"></a>Paramétrage de l’intégration

Suivez les étapes ci-après pour configurer l’intégration entre Comptabilité globale des stocks et Supply Chain Management.

1. Connectez-vous à Supply Chain Management.
1. Accédez à **Administration système \> Gestion des fonctionnalités**.
1. Sélectionnez **Rechercher des mises à jour**.
1. Sur l’onglet **Tout**, recherchez l’entité nommée *Comptabilité globale des stocks (Version préliminaire)*.
1. Sélectionnez **Activer maintenant**.
1. Accédez à **Comptabilité globale des stocks \> Installer \> Paramètres de la comptabilité globale des stocks \> Paramètres d’intégration**.
1. Selon le type d’environnement de Supply Chain Management sur lequel vous travaillez, effectuez l’une des étapes suivantes :
    - **Supply Chain Management version 10.0.19 à 10.0.26** : Dans les champs **Point de terminaison du service de données** et **Point de terminaison de comptabilité d'inventaire global**, entrez les URL qui vous ont été envoyées par e-mail par l'équipe Comptabilité globale des stocks (voir aussi [Comment obtenir le complément Comptabilité globale des stocks](#sign-up)).
    - **Supply Chain Management version 10.0.27 et plus récente** : vous n'avez pas besoin d'entrer les points de terminaison, vous pouvez donc ignorer cette étape.

Comptabilité globale des stocks est maintenant prêt à être utilisé.
