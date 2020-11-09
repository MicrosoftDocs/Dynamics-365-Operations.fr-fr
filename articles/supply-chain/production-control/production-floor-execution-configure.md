---
title: Configurer l'interface d'exécution de l'atelier de production
description: Cette rubrique décrit comment créer une ou plusieurs configurations pour l'interface d'exécution de l'atelier de production. Lorsque vous ouvrez l'interface d'exécution de l'atelier de production, elle charge automatiquement une configuration sélectionnée et un filtre de tâches spécifiques au navigateur et à l'appareil. Dans la configuration, vous définissez les stratégies qui doivent être applicables pour une utilisation spécifique.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cf58a7d851577854d08bad70cff69794c3841a2d
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012474"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurer l'interface d'exécution de l'atelier de production

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Les collaborateurs de l'atelier utilisent l'interface d'exécution de l'atelier de production pour enregistrer leur travail quotidien : heure de début d'une tâche, générer des commentaires sur les tâches, enregistrer des activités indirectes et signaler des absences. Ces enregistrements servent de base pour suivre l'avancement et le coût des ordres de fabrication et pour calculer la base de la rémunération des collaborateurs.

Lorsque vous ouvrez l'interface d'exécution de l'atelier de production, elle charge automatiquement une configuration sélectionnée et un filtre de tâches spécifiques au navigateur et à l'appareil. Dans la configuration, vous définissez les stratégies qui doivent être applicables pour une utilisation spécifique. Voici quelques exemples d'utilisation :

- Sur un appareil situé dans le hall de l'entreprise, les employés pointent lorsqu'ils entrent dans le bureau et lorsqu'ils partent pour la journée.
- Sur un appareil de l'atelier, les opérateurs de machines enregistrent lorsqu'ils démarrent et terminent des tâches. Ils enregistrent également les pauses et les activités indirectes.

Cette rubrique décrit les différentes options de configuration des périphériques de bon de travail.

## <a name="turn-on-new-features-in-feature-management"></a>Activer de nouvelles fonctionnalités dans la gestion des fonctionnalités

Quelques-uns des paramètres décrits dans cette rubrique doivent être activés dans votre système avant d'être disponibles. Utilisez la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer une ou toutes les fonctionnalités suivantes, si nécessaire.

### <a name="generate-license-plate"></a>Générer un contenant

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre suivant) :

1. Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail
1. Activer la génération automatique du numéro de contenant lors de la déclaration de fin dans le périphérique de bon de travail

### <a name="print-label"></a>Imprimer l'étiquette

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre suivant) :

1. Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail
1. Imprimer une étiquette à partir d'un périphérique de bons de travail

### <a name="allow-locking-the-touch-screen"></a>Autoriser le verrouillage de l'écran tactile

Pour rendre cette fonctionnalité disponible, activez la fonctionnalité suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- (Version préliminaire) Fonctionnalité de verrouillage des périphériques des bons de travail et des terminaux des bons de travail afin de procéder à leur désinfection

## <a name="work-with-production-floor-execution-configurations"></a>Utiliser les configurations de l'exécution de l'atelier de production

Pour créer et gérer des configurations de périphérique, accédez à **Contrôle de la production \> Configuration \> Contrôle et suivi de la production \> Configurer l'exécution de l'atelier de production**. La page **Configurer l'exécution de l'atelier de production** affiche une liste des configurations existantes. Sur cette page, vous pouvez effectuer l'une des actions suivantes :

- Sélectionner n'importe quelle configuration d'atelier de production répertoriée dans la colonne de gauche pour la visualiser et la modifier.
- Sélectionner **Nouveau** dans le volet Actions pour ajouter une nouvelle configuration de périphérique à la liste. Ensuite, dans le champ **Configuration** , entrez alors un nom pour identifier la nouvelle configuration. Le nom que vous entrez ici doit être unique parmi toutes les configurations de périphérique et vous ne pourrez pas le modifier ultérieurement.

Ensuite, configurez les différents paramètres pour la configuration de périphérique sélectionnée. Les champs disponibles sont les suivants :

- **Déclarer la quantité à la sortie** - Définissez cette option sur *Oui* pour inviter les collaborateurs à faire part de leurs commentaires sur les travaux en cours lorsqu'ils pointent à la sortie. Lorsque cette option est définie sur *Non* , les collaborateurs ne reçoivent pas d'invite.
- **Verrouiller l'employé** - Lorsque cette option est définie sur *Non* , les travailleurs seront déconnectés immédiatement après avoir effectué un enregistrement (comme un nouveau travail). L'appareil retournera ensuite à la page de connexion. Lorsque cette option est définie sur *Oui* , les collaborateurs resteront connectés au périphérique pour le bon de travail. Cependant, un collaborateur peut se déconnecter manuellement afin qu'un autre collaborateur puisse se connecter pendant que le périphérique pour le bon de travail continue de s'exécuter sous le même compte d'utilisateur système. Pour plus d'informations sur ces types de compte, voir [Utilisateurs affectés](config-job-card-device.md#assigned-users).
- **Utiliser l'heure réelle d'enregistrement** - Définissez cette option sur *Oui* pour définir l'heure de chaque nouvel enregistrement sur l'heure exacte à laquelle le collaborateur a soumis l'enregistrement. Lorsque cette option est définie sur *Non* , l'heure de connexion est utilisée à la place. Vous souhaiterez généralement définir cette option sur *Oui* si vous avez défini les options **Verrouiller le collaborateur** et/ou **Collaborateur unique** sur *Oui* dans les cas où les collaborateurs restent souvent connectés pendant de longues périodes.
- **Collaborateur unique** - Définissez cette option sur *Oui* si un seul collaborateur utilise chaque périphérique de bon de travail sur lequel cette configuration est active. Lorsque cette option est définie sur *Oui* , l'option **Verrouiller le collaborateur** est automatiquement définie sur *Oui*. De plus, ce paramètre supprime le besoin (et la capacité) pour le collaborateur de se connecter à l'aide d'un ID badge (ou autre ID similaire). Au lieu de cela, le collaborateur se connecte à Microsoft Dynamics 365 Supply Chain Management à l'aide d'un compte utilisateur système lié à un collaborateur *à temps enregistré* (issu de la table *collaborateurs* ) et se connecte au périphérique pour le bon de travail en tant que ce collaborateur en même temps.
- **Autoriser le verrouillage de l'écran tactile** - Définissez cette option sur *Oui* pour permettre aux collaborateurs de verrouiller l'écran tactile du périphérique pour le bon de travail afin de pouvoir le désinfecter. Lorsque cette option est définie sur *Oui* , un bouton **Verrouiller l'écran pour la désinfection** est ajouté à la page de connexion de l'appareil. Lorsqu'un collaborateur sélectionne ce bouton, l'écran tactile est verrouillé temporairement pour empêcher toute entrée involontaire. Un compte à rebours est également affiché. Le collaborateur peut ensuite nettoyer en toute sécurité l'appareil et l'écran. Une fois le compte à rebours terminé, l'écran tactile est déverrouillé automatiquement.
- **Durée de verrouillage de l'écran** - Quand l'option **Autoriser le verrouillage de l'écran tactile** est définie sur *Oui* , utilisez cette option pour spécifier le nombre de secondes pendant lesquelles l'écran tactile doit être verrouillé pour la désinfection. La durée doit être un nombre compris entre 5 et 120 secondes.
- **Générer un contenant** - Définissez cette option sur *Oui* pour générer un nouveau contenant chaque fois qu'un collaborateur utilise le périphérique pour le bon de travail pour effectuer une déclaration de fin. Le numéro du contenant est généré à partir d'une séquence de numéros configurée sur la page **Paramètres de gestion de l'entrepôt**. Quand cette option est définie sur *Non* , les collaborateurs doivent spécifier un contenant existant lorsqu'ils font une déclaration de fin.
- **Imprimer l'étiquette** - Définissez cette option sur *Oui* pour imprimer une étiquette de contenant quand un collaborateur utilise le périphérique pour le bon de travail pour effectuer une déclaration de fin. La configuration de l'étiquette est définie dans l'acheminement des documents, comme décrit dans [Mise en page d'acheminement de document pour les étiquettes de contenant](../warehousing/document-routing-layout-for-license-plates.md).

## <a name="clean-up-job-configurations"></a>Nettoyage des configurations de tâches

Lorsque le superviseur d'atelier configure l'interface d'exécution de l'atelier de production, il sélectionne une configuration et un filtre de tâche. Ces sélections sont stockées dans une table de référence dans Supply Chain Management et le navigateur utilise un ID qui est stocké dans un cookie local pour trouver la ligne correcte dans cette table. La table enregistre également la date et l'heure de la dernière connexion d'un travailleur sur chaque appareil.

Un traitement par lots nettoie périodiquement les entrées de la table des références pour les appareils qui n'ont enregistré aucune activité au cours des 60 derniers jours. Vous pouvez également nettoyer manuellement les entrées à tout moment en suivant ces étapes.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer l'exécution de l'atelier de production**.
1. Dans le volet Actions, sélectionnez **Nettoyer les configurations du client**.
1. Dans la boîte de dialogue **Nettoyer la configuration du client** , définissez le champ **Nombre de jours** sur le nombre de jours d'inactivité (avant aujourd'hui) à prendre en compte. Vous supprimerez toutes les configurations et les enregistrements de connexion pour les appareils qui n'ont pas été actifs pendant cette période.
1. Sélectionnez **OK** pour nettoyer les configurations pertinentes, en fonction du paramètre **Nombre de jours**.
