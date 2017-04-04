---
title: "Gérer le cycle de vie de la configuration des états électroniques"
description: "Cette rubrique décrit la procédure de gestion du cycle de vie des configurations de déclarations électroniques de (ER) pour Microsoft Dynamics 365 pour la solution d&quot;opérations."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: f4d8994f6548119789715a4879b6bc02d25598e9
ms.lasthandoff: 03/31/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Gérer le cycle de vie de la configuration des états électroniques

Cette rubrique décrit la procédure de gestion du cycle de vie des configurations de déclarations électroniques de (ER) pour Microsoft Dynamics 365 pour la solution d'opérations.

<a name="overview"></a>Vue d'ensemble
--------

La génération d'états électronique (ER) est un moteur qui prend en charge les documents électroniques exigés par les règlements et spécifiques aux pays dans Microsoft Dynamics 365 for Operations. En général, l'ER suppose une capacité à effectuer les tâches suivantes pour un document électronique unique. Pour plus de détails, voir [vue d'ensemble électronique de génération d'états] (general-electronic-reporting.md).

-   Créez un modèle pour un document électronique :
    -   Identifiez les sources de données exigées qui peuvent être présentées dans le document :
        -   Dynamics sous-jacentes 365 pour les données d'opérations, telles que les tables de données, les entités de données, et des classes.
        -   propriétés Processus-spécifiques, telles que la date d'exécution et l'heure, et fuseau horaire.
        -   L'utilisateur entre des paramètres, spécifiés par l'utilisateur au moment de l'exécution.
    -   Définissez les éléments du document nécessaires ainsi que leur topologie afin de spécifier un format de document final.
    -   Configurez le flux de données souhaité à partir des sources de données sélectionnées vers les éléments du document définis (via les liaisons de sources de données aux composants de format du document) et spécifiez la logique de contrôle du processus.
-   Mettez un modèle à disposition afin qu'il puisse être utilisé dans d'autres instances de Dynamics 365 for Operations :
    -   Transformez un modèle de document créé dans Dynamics 365 for Operations dans une configuration ER, et exportez la configuration de l'instance actuelle de Dynamics 365 for Operations en tant que package XML pouvant être enregistré localement ou dans LCS.
    -   Transformez une configuration ER en modèle de document Dynamics 365 for Operations.
    -   Importez un package XML qui est enregistré localement ou dans LCS dans l'instance actuelle de Dynamics 365 for Operations.
-   Personnalisez le modèle d'un document électronique :
    -   Importez un modèle issu de LCS dans l'instance actuelle de Dynamics 365 for Operations en tant que configuration ER.
    -   Créez une version personnalisée d'une configuration ER et conservez une référence à la version de base.
-   Intégrez un modèle à un processus entreprise particulier, afin qu'il soit disponible dans Dynamics 365 for Operations :
    -   Configurez des paramètres afin que Dynamics 365 for Operations commence à utiliser une configuration ER, en se rapportant à cette configuration dans un paramètre associé au processus. Par exemple, reportez-vous à la configuration d'ER dans un mode de paiement spécifique Achats pour générer un message de paiement électronique pour le traitement des factures.
-   Utilisez un modèle dans un processus d'entreprise spécifique :
    -   Exécutez une configuration d'ER dans un processus entreprise spécifique. Par exemple, pour générer un message de paiement électronique pour traiter facture lorsqu'un mode de paiement qui référence de la configuration d'ER est sélectionné.

## <a name="concepts"></a>Concepts
Les rôles et les activités associées sont associés au cycle de vie de configuration d'ER.

| Rôle                                       | Activités                                                      | description ;                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consultant fonctionnel de gestion des états électroniques | Créez et gérez des composants ER (modèles et formats).           | Personne entreprise qui conçoit les modèles de données domaine- spécifiques d'ER, conçoit les modèles requis pour les documents électroniques, et les liens en conséquence.                                                                           |
| Développeur de gestion des états électroniques             | Créez et gérez les mises en correspondance de modèle de données.                          | Dynamics 365 pour le spécialiste des opérations qui sélectionne Dynamics requis 365 pour les sources de données d'opérations et les liens aux modèles de données domaine- spécifiques d'ER.                                                                 |
| Chef comptable                      | Configurez les paramètres liés au processus qui référencent des artefacts ER. | Par exemple, ** superviseur de comptabilité ** un rôle qui autorise les paramètres d'une configuration d'ER à utiliser dans un mode de paiement particulier Achats pour générer un message de paiement électronique pour traiter facture. |
| Commis au paiement de la comptabilité fournisseur            | Utilisez des artefacts ER dans un processus d'entreprise spécifique.                | Par exemple, ** les paiements des achats travaillent comme employé ** un rôle permettant aux messages de paiement électronique à générer pour le traitement des factures, selon le format d'ER qui est configuré pour un mode de paiement spécifique.           |

## <a name="er-configuration-development-lifecycle"></a>Cycle de vie de développement de la configuration ER
Pour les raisons suivantes associées à ER, nous recommandons que vous conceviez des configurations ER dans l'environnement de développement en tant qu'instance distincte de Dynamics 365 for Operations :

-   Les utilisateurs, qu'ils soient dans des rôles de **Développeur d'états électroniques** ou de **Consultant fonctionnel des états électroniques**, peuvent modifier des configurations et les exécuter à des fins de test. Ce scénario peut provoquer des appels de méthodes de classes et de tables qui sont potentiellement néfastes pour les données commerciales et les performances de l'instance Dynamics 365 for Operations.
-   Les appels de méthodes de classes et de tables en tant que sources de données ER des configurations ER ne sont pas limités par les points d'entrée de Dynamics 365 for Operations, ni par le contenu d'entreprise consigné. Par conséquent, les utilisateurs dans les rôles de **Développeur d'états électroniques** ou de **Consultant fonctionnel des états électroniques** peuvent accéder aux données commerciales importantes.

Les configurations d'ER qui sont conçues dans l'environnement de développement peuvent être téléchargées à l'environnement de test pour l'évaluation de configuration (intégration appropriée de processus, exactitude des résultats, puis performances) et la assurance qualité, telles que l'exactitude des droits d'accès et de répartition des tâches motivés par le rôle. Les fonctions qui activent l'échange de configuration d'ER peuvent être utilisées à cet effet. Enfin, les configurations prouvées d'ER peut s'agir de l'un ou l'autre téléchargés au lettres de crédit, où elles peuvent être partagées avec les abonnés de service, ou à l'environnement de production pour un usage interne, comme décrit dans l'illustration suivante. ![Cycle de vie de configuration d'ER](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)


