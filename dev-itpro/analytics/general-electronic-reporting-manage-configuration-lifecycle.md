---
title: "Gérer le cycle de vie de la configuration des états électroniques"
description: "Cette rubrique décrit comment gérer le cycle de vie des configurations d'états électroniques (ER) pour la solution Microsoft Dynamics 365 for Finance and Operations."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: b1f5da07ffff5e34d8c73012a1e3c85fe1546fda
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017


---

# <a name="manage-the-electronic-reporting-configuration-lifecycle"></a>Gérer le cycle de vie de la configuration des états électroniques

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment gérer le cycle de vie des configurations d'états électroniques (ER) pour la solution Microsoft Dynamics 365 for Finance and Operations.

<a name="overview"></a>Vue d'ensemble
--------

La génération d'états électronique (ER) est un moteur qui prend en charge les documents électroniques exigés par les règlements et spécifiques aux pays dans Microsoft Dynamics 365 for Finance and Operations. En général, l'ER suppose une capacité à effectuer les tâches suivantes pour un document électronique unique. Pour plus de détails, voir [Vue d'ensemble des États électroniques](general-electronic-reporting.md).

-   Créez un modèle pour un document électronique :
    -   Identifiez les sources de données exigées qui peuvent être présentées dans le document :
        -   Données Finance and Operations sous-jacentes, telles que les tables de données, entités de données et classes.
        -   Propriétés spécifiques aux processus, tels que les date et heure d'exécution et fuseau horaire.
        -   Paramètres d'entrée utilisateur, spécifiés par l'utilisateur final au moment de l'exécution.
    -   Définissez les éléments du document nécessaires ainsi que leur topologie afin de spécifier un format de document final.
    -   Configurez le flux de données souhaité à partir des sources de données sélectionnées vers les éléments du document définis (via les liaisons de sources de données aux composants de format du document) et spécifiez la logique de contrôle du processus.
-   Mettez un modèle à disposition afin qu'il puisse être utilisé dans d'autres instances de Finance and Operations :
    -   Transformez un modèle de document créé dans Finance and Operations dans une configuration ER, et exportez la configuration de l'instance actuelle de Finance and Operations en tant que package XML pouvant être enregistré localement ou dans LCS.
    -   Transformez une configuration ER en modèle de document Finance and Operations.
    -   Importez un package XML qui est enregistré localement ou dans LCS dans l'instance actuelle de Finance and Operations.
-   Personnalisez le modèle d'un document électronique :
    -   Importez un modèle issu de LCS dans l'instance actuelle de Finance and Operations en tant que configuration ER.
    -   Créez une version personnalisée d'une configuration ER et conservez une référence à la version de base.
-   Intégrez un modèle à un processus entreprise particulier, afin qu'il soit disponible dans Finance and Operations :
    -   Configurez des paramètres afin que Finance and Operations commence à utiliser une configuration ER, en se rapportant à cette configuration dans un paramètre associé au processus. Par exemple, consultez la configuration ER dans un mode de paiement Achats spécifique pour générer un message de paiement électronique pour traiter les factures.
-   Utilisez un modèle dans un processus d'entreprise spécifique :
    -   Exécutez une configuration ER dans un processus d'entreprise spécifique. Par exemple, pour générer un message de paiement électronique pour le traitement des factures lorsqu'un mode de paiement qui référence la configuration ER est sélectionné.

## <a name="concepts"></a>Concepts
Les rôles suivants et les activités liées sont associés au cycle de vie de la configuration ER.

| Rôle                                       | Activités                                                      | description ;                                                                                                                                                                                                                  |
|--------------------------------------------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Consultant fonctionnel de gestion des états électroniques | Créez et gérez des composants ER (modèles et formats).           | Un commercial qui conçoit des modèles de données spécifique au domaine ER, conçoit les modèles requis pour des documents électroniques et les lie en conséquence.                                                                           |
| Développeur de gestion des états électroniques             | Créez et gérez les mises en correspondance de modèle de données.                          | Un spécialiste de Finance and Operations qui sélectionne les sources de données requises de Finance and Operations et les lie aux modèles de données spécifiques au domaine ER.                                                                 |
| Chef comptable                      | Configurez les paramètres liés au processus qui référencent des artefacts ER. | Par exemple, un rôle de **Chef comptable** qui autorise les paramètres d'une configuration ER à être utilisés dans un mode de paiement Achats particulier pour générer un message de paiement électronique pour traiter les factures. |
| Commis au paiement de la comptabilité fournisseur            | Utilisez des artefacts ER dans un processus d'entreprise spécifique.                | Par exemple, un rôle de **Commis au paiement de la comptabilité fournisseur** qui autorise des messages de paiement électronique à générer pour le traitement des factures, selon le format ER configuré pour un mode de paiement spécifique.           |

## <a name="er-configuration-development-lifecycle"></a>Cycle de vie de développement de la configuration ER
Pour les raisons suivantes associées à ER, nous recommandons que vous conceviez des configurations ER dans l'environnement de développement en tant qu'instance distincte de Finance and Operations :

-   Les utilisateurs, qu'ils soient dans des rôles de **Développeur d'états électroniques** ou de **Consultant fonctionnel des états électroniques**, peuvent modifier des configurations et les exécuter à des fins de test. Ce scénario peut provoquer des appels de méthodes de classes et de tables qui sont potentiellement néfastes pour les données commerciales et les performances de l'instance Finance and Operations.
-   Les appels de méthodes de classes et de tables en tant que sources de données ER des configurations ER ne sont pas limités par les points d'entrée de Finance and Operations, ni par le contenu d'entreprise consigné. Par conséquent, les utilisateurs dans les rôles de **Développeur d'états électroniques** ou de **Consultant fonctionnel des états électroniques** peuvent accéder aux données commerciales importantes.

Les configurations ER conçues dans l'environnement de développement peuvent être téléchargées dans l'environnement de test pour l'évaluation de la configuration (intégration correcte au processus, exactitude des résultats et des performances) et l'assurance qualité, comme l'exactitude des droits d'accès motivés par le rôle et la répartition des tâches. Les fonctions qui activent l'échange de configuration ER peuvent être utilisées à cet effet. Enfin, les configurations ER éprouvées peuvent être téléchargées soit dans LCS où elles peuvent être partagées avec des abonnés au service, ou dans l'environnement de production pour une utilisation interne, comme indiqué dans l'illustration suivante. ![Cycle de vie de la configuration ER](./media/ger-configuration-lifecycle.png)

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des États électroniques](general-electronic-reporting.md)




