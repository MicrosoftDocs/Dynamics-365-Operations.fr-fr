---
title: Gérer le cycle de vie de la configuration des états électroniques (ER)
description: Cette rubrique décrit comment gérer le cycle de vie des configurations d'états électroniques (ER) pour la solution Microsoft Dynamics 365 Finance.
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ecaeb80f3cda2ee24533ed263df63cc10c5ffc65
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771094"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Gérer le cycle de vie de la configuration des états électroniques (ER)

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment gérer le cycle de vie des configurations d'états électroniques (ER) pour Microsoft Dynamics 365 Finance.

## <a name="overview"></a>Présentation

La génération d'états électronique (ER) est un moteur qui prend en charge les documents électroniques exigés par les règlements et spécifiques aux pays. En général, l'ER suppose une capacité à effectuer les tâches suivantes pour un document électronique unique. Pour plus de détails, voir [Vue d'ensemble des États électroniques](general-electronic-reporting.md).

- Créez un modèle pour un document électronique :

    - Identifiez les sources de données exigées qui peuvent être présentées dans le document :

        - Données sous-jacentes, telles que les tables de données, entités de données et classes.
        - Propriétés spécifiques aux processus, tels que les date et heure d'exécution et fuseau horaire.
        - Paramètres d'entrée utilisateur, spécifiés par l'utilisateur final au moment de l'exécution.

    - Définissez les éléments du document nécessaires ainsi que leur topologie afin de spécifier un format de document final.
    - Configurez le flux de données souhaité à partir des sources de données sélectionnées vers les éléments du document définis (via les liaisons de sources de données aux composants de format du document) et spécifiez la logique de contrôle du processus.

- Mettez un modèle à disposition afin qu'il puisse être utilisé dans d'autres instances :

    - Transformez un modèle de document créé dans une configuration ER, et exportez la configuration de l'instance actuelle de l'application en tant que package XML pouvant être enregistré localement ou dans LCS.
    - Transformez une configuration ER en modèle de document d'application.
    - Importez un package XML qui est enregistré localement ou dans LCS dans l'instance actuelle.

- Personnalisez le modèle d'un document électronique :

    - Importez un modèle issu de LCS dans l'instance actuelle en tant que configuration ER.
    - Créez une version personnalisée d'une configuration ER et conservez une référence à la version de base.

- Intégrez un modèle à un processus entreprise particulier, afin qu'il soit disponible dans l'application :

    - Configurez des paramètres afin que l'application commence à utiliser une configuration ER, en se rapportant à cette configuration dans un paramètre associé au processus. Par exemple, consultez la configuration ER dans un mode de paiement Achats spécifique pour générer un message de paiement électronique pour traiter les factures.

- Utilisez un modèle dans un processus d'entreprise spécifique :

    - Exécutez une configuration ER dans un processus d'entreprise spécifique. Par exemple, pour générer un message de paiement électronique pour le traitement des factures lorsqu'un mode de paiement qui référence la configuration ER est sélectionné.

## <a name="concepts"></a>Concepts
Les rôles suivants et les activités liées sont associés au cycle de vie de la configuration ER.

| Rôle                                       | Activités                                                      | description ; |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Consultant fonctionnel de gestion des états électroniques | Créez et gérez des composants ER (modèles et formats).           | Un commercial qui conçoit des modèles de données spécifique au domaine ER, conçoit les modèles requis pour des documents électroniques et les lie en conséquence. |
| Développeur d'états électroniques             | Créez et gérez les mises en correspondance de modèle de données.                          | Un spécialiste qui sélectionne les sources de données requises de Finance et les lie aux modèles de données spécifiques au domaine ER. |
| Chef comptable                      | Configurez les paramètres liés au processus qui référencent des artefacts ER. | Par exemple, un rôle de **Chef comptable** qui autorise les paramètres d'une configuration ER à être utilisés dans un mode de paiement Achats particulier pour générer un message de paiement électronique pour traiter les factures. |
| Commis au paiement de la comptabilité fournisseur            | Utilisez des artefacts ER dans un processus d'entreprise spécifique.                | Par exemple, un rôle de **Commis au paiement de la comptabilité fournisseur** qui autorise des messages de paiement électronique à générer pour le traitement des factures, selon le format ER configuré pour un mode de paiement spécifique. |

## <a name="er-configuration-development-lifecycle"></a>Cycle de vie de développement de la configuration ER
Pour les raisons suivantes associées à ER, nous recommandons que vous conceviez des configurations ER dans l'environnement de développement en tant qu'instance distincte de Finance and Operations :

- Les utilisateurs, qu'ils soient dans des rôles de **Développeur d'états électroniques** ou de **Consultant fonctionnel des états électroniques**, peuvent modifier des configurations et les exécuter à des fins de test. Ce scénario peut provoquer des appels de méthodes de classes et de tables qui sont potentiellement néfastes pour les données commerciales et les performances de l'instance.
- Les appels de méthodes de classes et de tables en tant que sources de données ER des configurations ER ne sont pas limités par les points d'entrée, ni par le contenu d'entreprise consigné. Par conséquent, les utilisateurs dans les rôles de **Développeur d'états électroniques** ou de **Consultant fonctionnel des états électroniques** peuvent accéder aux données commerciales importantes.

Les configurations ER conçues dans l'environnement de développement peuvent être téléchargées dans l'environnement de test pour l'évaluation de la configuration (intégration correcte au processus, exactitude des résultats et des performances) et l'assurance qualité, comme l'exactitude des droits d'accès motivés par le rôle et la répartition des tâches. Les fonctions qui activent l'échange de configuration ER peuvent être utilisées à cet effet. Enfin, les configurations ER éprouvées peuvent être téléchargées soit dans LCS où elles peuvent être partagées avec des abonnés au service, ou dans l'environnement de production pour une utilisation interne, comme indiqué dans l'illustration suivante.

![Cycle de vie de la configuration ER](./media/ger-configuration-lifecycle.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des états électroniques (ER)](general-electronic-reporting.md)
