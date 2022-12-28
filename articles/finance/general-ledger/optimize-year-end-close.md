---
title: Optimiser la clôture de fin d’exercice
description: Cet article décrit le complément de service Optimiser la clôture de fin d’exercice qui est disponible pour le processus de clôture de fin d’exercice comptable.
author: moaamer
ms.date: 12/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: bc6ab7e36f37707442f8d5d5b6e0d5f5d42e2171
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831527"
---
# <a name="optimize-year-end-close"></a>Optimiser la clôture de fin d’exercice 

Le complément de service Optimiser la clôture de fin d’exercice pour Microsoft Dynamics 365 Finance permet au processus de clôture de fin d’exercice de s’exécuter en dehors de l’instance Serveur d’objets d’application (AOS) pour les ressources de Dynamics 365 Finance. Il utilise la technologie des microservices. Les avantages associés à la fonctionnalité Optimiser la clôture de fin d’exercice comprennent des performances améliorées et un impact réduit sur la base de données SQL pendant le processus de clôture de fin d’exercice.

>[!NOTE]
> La clôture d’exercice optimisée est disponible sur Microsoft Dynamics 365 Finance version 10.0.31. Cette fonctionnalité a été rajoutée aux versions 10.0.30 et 10.0.29 de Dynamics Finance et vous devrez prendre la dernière mise à jour de qualité.   

Pour utiliser la fonctionnalité Optimiser la clôture de fin d’exercice, vous devez effectuer les tâches suivantes :

1. Installer le complément de service Optimiser la clôture de fin d’exercice à partir de votre projet dans Microsoft Dynamics Lifecycle Services.
2. Activer la fonctionnalité **Optimiser la clôture de fin d’exercice** dans Gestion des fonctionnalités.

> [!NOTE]
> Vous pouvez toujours utiliser la fonctionnalité de clôture de fin d’exercice actuelle pour Finance en désactivant la fonctionnalité **Optimiser la clôture de fin d’exercice** dans Gestion des fonctionnalités.

## <a name="improved-performance"></a>Performances améliorées

La fonctionnalité **Optimiser la clôture de fin d’exercice** est conçue pour accélérer le processus de clôture de fin d’exercice, en particulier pour les clients qui ont de gros volumes de données. Lorsque la clôture de fin d’exercice s’exécute sur un service, le traitement lourd est déchargé des ressources de Finance pour aider à réduire le temps de traitement et libérer les ressources susceptibles d’affecter les opérations quotidiennes des autres utilisateurs.

La fonctionnalité **Optimiser la clôture de fin d’exercice** peut vous aider à atteindre les objectifs suivants :

- Améliorer les performances de la clôture de fin d’exercice en réduisant le temps d’exécution.
- Réduire l’impact sur d’autres processus pendant l’exécution de la clôture de fin d’exercice.
- Améliorer les rapports et les ajustements pour les résultats de fin d’exercice, car l’exécution de la clôture de fin d’exercice prend moins de temps.

## <a name="new-options-and-visibility"></a>Nouvelles options et visibilité

Lorsque la fonctionnalité **Optimiser la clôture de fin d’exercice** est activée, deux nouvelles colonnes, **Résultats** et **Statut**, sont ajoutées aux emplacements suivants :

- Sur la page **Clôture de fin d’exercice**
- Dans la boîte de dialogue **Résultats de la clôture de fin d’exercice**
- Dans les options **Transfert des dimensions financières du bilan** de la page **Modèle de clôture de fin d’exercice**

L’illustration suivante montre un exemple des colonnes **Résultats** et **Statut** sur la page **Clôture de fin d’exercice**. Vous pouvez sélectionner le lien **Afficher les résultats** dans la colonne **Résultats** pour ouvrir les résultats de la clôture de fin d’exercice. La colonne **Statut** indique l’état actuel du processus de clôture de fin d’exercice. Par conséquent, les nouvelles colonnes offrent une visibilité sur la progression du processus de clôture de fin d’exercice.

[![Colonnes Résultats et Statut sur la page Clôture de fin d’exercice.](./media/Optimize-year-end-close-Image3.png)](./media/Optimize-year-end-close-Image3.png)

En outre, lorsque la fonctionnalité **Optimiser la clôture de fin d’exercice** est activée, un raccourci **Dimensions financières du bilan** devient disponible sur la page **Modèle de clôture de fin d’exercice**. Vous pouvez utiliser ce raccourci pour spécifier en détail les dimensions financières du bilan lorsque vous clôturez un exercice. Cette capacité est parallèle à la capacité déjà disponible pour les comptes de résultats.

[![Raccourci Dimensions financières du bilan](./media/Optimize-year-end-close-Image4.png)](./media/Optimize-year-end-close-Image4.png)

## <a name="architecture-and-data-flow"></a>Architecture et flux de données

Pour utiliser la fonctionnalité **Optimiser la clôture de fin d’exercice** et exécuter la clôture de fin d’exercice sur un microservice, vous devez installer le **complément de service Optimiser la clôture de fin d’exercice** à partir de Lifecycle Services, puis activer la fonctionnalité **Optimiser la clôture de fin d’exercice** dans Gestion des fonctionnalités.

Comme le montre l’illustration suivante, le processus de clôture de fin d’exercice vérifie que le complément est installé et que la fonctionnalité est activée. Si les deux conditions préalables sont remplies, la clôture de fin d’exercice s’exécute sur le microservice.

[![Diagramme de flux de données.](./media/Optimize-year-end-close-Image5.png)](./media/Optimize-year-end-close-Image5.png)

## <a name="high-level-flow-for-year-end-close-processing"></a>Flux de haut niveau pour le processus de clôture de fin d’exercice

1. Le processus de clôture de fin d’exercice commence dans Finance, accédez à **Comptabilité \> Clôture de période \> Clôture de fin d’exercice**. Le processus crée des traitements par lots et des tâches de clôture pour les entités juridiques en cours de clôture.
2. La clôture de fin d’exercice détermine si la clôture de fin d’exercice doit être exécutée sur le microservice ou sur la logique de clôture actuelle.

    - Si le complément de service **Optimiser la clôture de fin d’exercice** est installé dans Lifecycle Services et la fonctionnalité **Optimiser la clôture de fin d’exercice** est activée dans Gestion des fonctionnalités, la clôture de fin d’exercice s’exécutera sur le microservice.

        1. La fonctionnalité Optimiser la clôture de fin d’exercice crée une tâche de service de clôture de fin d’exercice pour chaque entité juridique en cours de clôture, puis exécute la logique de clôture de fin d’exercice. Le microservice effectue la clôture de fin d’exercice.
        2. Finance écoute la clôture de fin d’exercice sur le microservice pour déterminer quand le microservice a terminé. Les résultats de la clôture d’exercice sont ensuite mis à jour sur la page **Clôture de fin d’exercice** dans Finance.

    - Sinon, la clôture de fin d’exercice s’exécutera selon la logique de clôture actuelle.
