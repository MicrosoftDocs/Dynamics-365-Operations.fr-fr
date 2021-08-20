---
title: Configurer le bon de travail pour les périphériques
description: Cette rubrique décrit les différentes options de configuration du périphérique de bon de travail.
author: johanhoffmann
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch, JmgRegistrationTouchUserConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 9da14c22b0ab62a8384fbe76918cc19da0205cdbbf2f4fd2ef8e7aec57b264ee
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781012"
---
# <a name="configure-job-card-for-devices"></a>Configurer le bon de travail pour les périphériques

[!include [banner](../includes/banner.md)]

Le périphérique de bon de travail est utilisé par les collaborateurs de l’atelier pour enregistrer leur travail quotidien : heure de début des tâches, commentaires sur les tâches, enregistrement d’activités indirectes et signalement des absences. Ces enregistrements servent de base pour suivre l’avancement et le coût des ordres de fabrication et pour calculer la base de la rémunération des collaborateurs. Cette rubrique décrit les différentes options de configuration des périphériques de bon de travail.

## <a name="enable-new-features-in-feature-management"></a>Activer les nouvelles fonctionnalités dans la gestion des fonctionnalités

Quelques-uns des paramètres décrits dans cette rubrique doivent être activés dans votre système avant d’être disponibles. Utilisez la page [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer une ou toutes les fonctionnalités suivantes, si nécessaire.

### <a name="generate-license-plate"></a>Générer un contenant

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre) :

1. Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail
1. Activer la génération automatique du numéro de contenant lors de la déclaration de fin dans le périphérique de bon de travail

### <a name="print-label"></a>Imprimer l’étiquette

Pour rendre cette fonctionnalité disponible, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre) :

1. Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail
1. Imprimer une étiquette à partir d’un périphérique de bons de travail

### <a name="allow-locking-of-touch-screen"></a>Autoriser le verrouillage de l’écran tactile

Pour rendre cette fonctionnalité disponible, activez la fonctionnalité suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- Fonctionnalité de verrouillage des périphériques des bons de travail et des terminaux des bons de travail afin de procéder à leur désinfection

## <a name="manage-your-device-configurations"></a>Gérer la configuration des périphériques

Pour paramétrer les configurations de périphériques, accédez à **Contrôle de la production > Paramétrage > Contrôle et suivi de la production > Configurer le bon de travail pour les périphériques**. La page **Configurer le bon de travail pour les périphériques** s’ouvre et affiche une liste des configurations existantes. De là, vous pouvez effectuer les opérations suivantes : 

- Sélectionner n’importe quelle configuration de périphérique répertoriée dans la colonne de gauche pour la visualiser et la modifier.
- Sélectionner **Nouveau** dans le volet Actions pour ajouter une nouvelle configuration de périphérique à la liste. Entrez alors un nom dans le champ **Configuration** pour identifier la nouvelle configuration. La valeur que vous entrez ici doit être unique parmi toutes les configurations de périphérique et vous ne pourrez pas la modifier ultérieurement.

Reportez-vous aux sections suivantes pour plus de détails sur chacun des paramètres de configuration des périphériques de bon de travail.

## <a name="general-settings"></a>Paramètres généraux

Le raccourci **Général** vous permet de configurer chacune des différentes options disponibles pour la configuration de périphérique sélectionnée. Les paramètres disponibles sont les suivants :

- **Déclarer la quantité à la sortie** - Définissez cette option sur **Oui** pour inviter les collaborateurs à faire part de leurs commentaires sur les travaux en cours à leur départ. Lorsqu’elle est définie sur **Non**, les employeurs ne reçoivent pas d’invite.
- **Verrouiller le collaborateur** - Lorsque cette option est définie sur **Non**, chaque employé sera déconnecté immédiatement après avoir effectué un enregistrement (comme une nouvelle tâche), puis le périphérique reviendra à la page de connexion. Lorsque cette option est définie sur **Oui**, chaque collaborateur restera connecté au périphérique de bon de travail. Cependant, le collaborateur pourra toujours se déconnecter manuellement pour permettre à un autre collaborateur de se connecter pendant que le périphérique de bon de travail continue de fonctionner sous le même compte d’utilisateur système. Pour plus d’informations sur ces types de compte, voir [Utilisateurs affectés](#assigned-users).
- **Scanner de codes-barres** - Définissez cette option sur **Oui** pour fournir une option sur le périphérique de bon de travail permettant aux collaborateurs d’enregistrer le début d’une nouvelle tâche en scannant un code-barres.
- **Utiliser l’heure réelle d’enregistrement** - Définissez cette option sur **Oui** pour que l’heure de chaque nouvel enregistrement soit égale à l’heure exacte à laquelle l’enregistrement a été soumis par un collaborateur. Définissez-la sur **Non** pour utiliser l’heure de connexion à la place. Vous souhaiterez généralement définir cette option sur **Oui** si vous avez activé les options **Verrouiller le collaborateur** et/ou **Collaborateur unique**, où les collaborateurs restent souvent connectés pendant de longues périodes.
- **Collaborateur unique** - Définissez cette option sur **Oui** si un seul collaborateur utilise chaque périphérique de bon de travail où cette configuration est active. Lorsque cette option est sélectionnée, l’option **Verrouiller le collaborateur** est automatiquement définie sur **Oui**. De plus, cette option supprime le besoin (et la capacité) pour le collaborateur de se connecter à l’aide d’un ID badge (ou ID similaire). Au lieu de cela, le collaborateur se connecte à Supply Chain Management à l’aide d’un compte utilisateur système lié à un *collaborateur à temps enregistré* (issu de la table *collaborateurs*) et se connecte au périphérique de bon de travail en tant que ce collaborateur à la même heure.  Pour plus d’informations sur ces types de compte, voir [Utilisateurs affectés](#assigned-users).
- **Autoriser les collaborateurs à définir des filtres personnels** - Définissez cette option sur **Oui** pour permettre aux collaborateurs de filtrer les tâches qui leur sont présentées sur le périphérique. Le collaborateur peut modifier les valeurs de l’un des trois critères de filtrage : **Unité de production**, **Groupe de ressources** et **Ressource**. Seules les tâches programmées sur des ressources correspondant aux critères de filtre sélectionnés seront affichées sur le périphérique. Vous pouvez également attribuer des valeurs par défaut à tout ou partie de ces critères, et ceux-ci s’appliqueront même si cette option n’est pas sélectionnée.
- **Autoriser le verrouillage de l’écran tactile** - Définissez cette option sur **Oui** pour permettre aux collaborateurs de verrouiller l’écran tactile du périphérique de bon de travail afin de pouvoir le désinfecter. Lorsqu’elle est activée, un bouton **Verrouiller l’écran pour la désinfection** est ajouté à la page de connexion du périphérique. Lorsqu’un collaborateur sélectionne ce bouton, l’écran tactile se verrouille temporairement pour empêcher toute entrée involontaire et un compte à rebours s’affiche. Le collaborateur peut maintenant nettoyer en toute sécurité l’appareil et l’écran. Une fois le compte à rebours terminé, l’écran tactile se déverrouille automatiquement.
- **Durée de verrouillage de l’écran** - Quand l’option **Autoriser le verrouillage de l’écran tactile** est activée, utilisez cette option pour spécifier le nombre de secondes pendant lesquelles l’écran tactile doit être verrouillé pour la désinfection. La durée doit être un nombre compris entre 5 et 120 secondes.
- **Unité de production** - Sélectionnez une unité de production à appliquer comme critère de filtrage par défaut pour la liste des tâches affichées à chaque collaborateur. Seules les tâches programmées sur des ressources regroupées sous l’unité de production sélectionnée seront initialement affichées par le périphérique. Si l’option **Autoriser les collaborateurs à définir des filtres personnels** est activée, les utilisateurs pourront modifier cette valeur, sinon ce filtre s’appliquera toujours lorsque cette configuration de périphérique sera active.
- **Groupe de ressources** - Sélectionnez un groupe de ressources à appliquer comme critère de filtrage par défaut pour la liste des tâches affichées à chaque collaborateur. Seules les tâches programmées sur des ressources regroupées sous le groupe de ressources sélectionné seront initialement affichées par le périphérique. Si l’option **Autoriser les collaborateurs à définir des filtres personnels** est activée, les utilisateurs pourront modifier cette valeur, sinon ce filtre s’appliquera toujours lorsque cette configuration de périphérique sera active.
- **Ressource** - Sélectionnez une ressource à appliquer comme critère de filtrage par défaut pour la liste des tâches affichées à chaque collaborateur. Seules les tâches programmées sur la ressource sélectionnée seront initialement affichées par le périphérique. Si l’option **Autoriser les collaborateurs à définir des filtres personnels** est activée, les utilisateurs pourront modifier cette valeur, sinon ce filtre s’appliquera toujours lorsque cette configuration de périphérique sera active.
- **Générer un contenant** - Définissez cette option sur **Oui** pour générer un nouveau contenant chaque fois qu’un collaborateur utilise le périphérique de bon de travail pour effectuer une déclaration de fin. Le numéro du contenant est généré à partir d’une séquence de numéros configurée sur la page **Paramètres de gestion de l’entrepôt**. Quand cette option est définie sur **Non**, les collaborateurs doivent spécifier un contenant existant lorsqu’ils font une déclaration de fin.
- **Imprimer l’étiquette** - Définissez cette option sur **Oui** pour imprimer une étiquette de contenant quand un collaborateur utilise le périphérique de bon de travail pour effectuer une déclaration de fin. La configuration de l’étiquette est définie dans l’acheminement des documents, comme décrit dans [Mise en page d’acheminement de document pour les étiquettes de contenant](../warehousing/document-routing-layout-for-license-plates.md).

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Utilisateurs affectés

Utilisez le raccourci **Utilisateurs affectés** pour associer un ou plusieurs utilisateurs du système à la configuration actuelle du périphérique. Chaque utilisateur système ne peut se voir attribuer qu’une seule configuration de périphérique de bon de travail.

Lors de la configuration d’un périphérique, un collaborateur du service IT se connecte généralement à Supply Chain Management à l’aide d’un compte utilisateur système. Par la suite, la configuration du périphérique de bon de travail associée à cet utilisateur système s’applique tant que cet utilisateur système reste connecté. Ces comptes d’utilisateurs système sont généralement restreints pour autoriser uniquement l’accès à la page du périphérique de bon de travail et à aucune autre partie de Supply Chain Management.

Une fois que l’utilisateur système s’est connecté et que la configuration du périphérique de bon travail est chargée, les collaborateurs peuvent alors se connecter au périphérique de bon de travail à l’aide de leur compte *collaborateur à temps enregistré* (par exemple, en scannant un code-barres sur leur badge) afin de pouvoir commencer de nouvelles tâches et effectuer d’autres types d’enregistrements. Différents collaborateurs peuvent se connecter et se déconnecter pendant la journée, tandis que la même configuration de périphérique reste en vigueur sur cette machine car l’utilisateur système reste connecté à Supply Chain Management pour toute la journée.

Cependant, comme mentionné précédemment, lorsque vous utilisez une configuration de périphérique avec l’option **Collaborateur unique**, les collaborateurs eux-mêmes se connectent généralement à Supply Chain Management en utilisant un utilisateur système lié à leur compte *Collaborateur à temps enregistré*, de sorte qu’ils chargent la configuration du périphérique et se connectent en tant que collaborateur sur le périphérique de bon de travail en même temps.

## <a name="additional-resources"></a>Ressources supplémentaires

[Déclarer comme terminé à partir du périphérique de bon de travail](report-finished-job-device.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]