---
title: Prise en main du service de contrôle de gestion (version préliminaire privée)
description: Cette rubrique fournit des détails sur les licences et des instructions d'installation pour le service de contrôle de gestion.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: a82af9e8ec1806f470103897389d0316d33a4a06
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427789"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a>Prise en main du service de contrôle de gestion (version préliminaire privée)

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> La fonctionnalité décrite dans cette rubrique est accessible dans le cadre d'une préversion privée. Le contenu de cette rubrique et les fonctionnalités qu'elle décrit sont susceptibles d'être modifiés. Pour plus d'informations sur les préversions, voir [FAQ sur les mises à jour de service à une version](../../fin-ops-core/fin-ops/get-started/one-version.md).

Le service de contrôle de gestion vous permet d'effectuer la comptabilité de plusieurs stocks dans les comptabilités de contrôle de gestion que vous avez configurés. Vous associez chaque comptabilité de contrôle de gestion à une *convention*. Une convention est un ensemble des types de stratégies comptables suivants :

- Objet de coût
- Base de la mesure en entrée
- Hypothèse de flux de coût
- Élément de coût

> [!NOTE]
> Même après avoir activé le service de contrôle de gestion, vous pouvez toujours effectuer la comptabilité de stock dans Microsoft Dynamics 365 Supply Chain Management, comme d'habitude.

Le service de contrôle de gestion est un complément. Pour rendre ses fonctionnalités disponibles, vous devez l'installer à partir de Microsoft Dynamics Lifecycle Services (LCS). Par conséquent, vous pouvez choisir de l'évaluer dans un environnement de test avant de l'activer pour les environnements de production.

Le service de contrôle de gestion ne prend actuellement pas en charge toutes les fonctionnalités de gestion des coûts intégrées Dynamics 365 Supply Chain Management. Par conséquent, il est important d'évaluer si l'ensemble de fonctionnalités actuellement disponible répondra à vos attentes.

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a>Obtenir le service de contrôle de gestion (version préliminaire privée)

> [!IMPORTANT]
> Pour utiliser le service de contrôle de gestion, vous devez disposer d'un environnement à haute disponibilité compatible LCS (et non d'un environnement OneBox), et vous devez exécuter Dynamics 365 Supply Chain Management version 10.0.11 ou ultérieure.

Pour vous inscrire à la version préliminaire privée du service de contrôle de gestion, veuillez envoyer votre identifiant d'environnement LCS par e-mail au [Service de contrôle de gestion (version préliminaire privée)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29). Une fois que nous vous avons approuvé pour le programme, nous vous enverrons un e-mail de suivi contenant une clé bêta pour le service de contrôle de gestion. Après la réception de la clé bêta, vous pouvez [installer le complément](#install).

## <a name="licensing"></a>Gestionnaire de licences

Le service de contrôle de gestion est concédé sous licence avec les fonctionnalités standard de la comptabilité des stocks disponibles pour Supply Chain Management. Vous n'avez pas besoin d'acheter une licence supplémentaire pour utiliser le service de contrôle de gestion.

## <a name="install-the-add-in"></a><a name="install"></a>Installer le complément

Pour utiliser le service de contrôle de gestion, installez le complément de service de contrôle de gestion pour Supply Chain Management comme décrit dans la procédure suivante.

1. [Inscrivez-vous](#sign-up) au service de contrôle de gestion (version préliminaire privée).

1. Connectez-vous à LCS.

1. Accédez à **Gestion des fonctionnalités d'aperçu**.

1. Sélectionnez le signe plus (**+**).

1. Dans le **Code**, entrez votre clé bêta de complément pour le service de contrôle de gestion. (Vous devriez avoir reçu votre clé par e-mail.)

1. Sélectionnez **Débloquer**.

1. Ouvrez l'environnement LCS dans lequel vous souhaitez ajouter le service.

1. Accédez à **Détails complets**.

1. Faites défiler jusqu'à l'organisateur **Compléments d'environnement**.

1. Sélectionnez **Installer un nouveau complément**.

1. Sélectionnez **Service de contrôle de gestion**.

1. Suivez le guide d'installation, et acceptez les conditions générales du contrat.

1. Sélectionnez **Installer**.

1. Sur l'organisateur **Compléments d'environnement**, vous devriez voir que le service de contrôle de gestion est en cours d'installation. Après quelques minutes, le statut devrait passer de **Installation** à **Installé**. (Vous devrez peut-être actualiser la page pour voir cette modification.) À ce stade, le service de contrôle de gestion est prêt à être utilisé.

## <a name="set-up-the-integration"></a>Paramétrage de l'intégration

Mettre en place l'intégration entre le service de contrôle de gestion et Dynamics 365 Supply Chain Management :

1. Accédez à **Administration système > Gestion des fonctionnalités**.

1. Sélectionnez **Rechercher des mises à jour**.

1. Ouvrez l'onglet **Tous** et recherchez la fonctionnalité nommée *Service de contrôle de gestion*.

1. Sélectionnez **Activer maintenant**.

1. Aller à **Gestion des coûts > Service de contrôle de gestion > Configuration > Paramètres du service de contrôle de gestion > Paramètres d'intégration**.

1. Dans le champ **ID application**, entrez le code suivant :<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. Dans le champ **Point de terminaison du service de données**, entrez l'URL suivante :<br>https://operationsdataservice.operations365.dynamics.com/

1. Dans le champ **Point de terminaison du service de contrôle de gestion**, entrez l'URL suivante :<br>https://costaccountingservice.operations365.dynamics.com/

1. Le service de contrôle de gestion est maintenant prêt à l'emploi.

## <a name="related-resources"></a>Ressources associées

[Page d'accueil du service Contrôle de gestion](cost-accounting-service-home.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]