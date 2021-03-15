---
title: Intégration de la gestion des actifs avec des immobilisations
description: Cette rubrique explique comment intégrer les modules Gestion d'actifs et Immobilisations, afin de pouvoir lier des immobilisations à des actifs de maintenance.
author: kamaybac
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 879950b9aeb345fcd59dfe73d3963a44607c7ac2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994227"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>Intégration de la gestion des actifs avec des immobilisations

[!include [banner](../../includes/banner.md)]

En intégrant les modules **Gestion d'actifs** et **Immobilisations**, afin de pouvoir lier des immobilisations à des actifs de maintenance. Les utilisateurs d'immobilisations peuvent ensuite créer un actif de maintenance à partir d'un actif fixe, nouveau ou existant, et les utilisateurs de la gestion d'actifs peuvent associer un actif de maintenance à un actif fixe existant. Cette fonctionnalité permet également aux utilisateurs des immobilisations de visualiser facilement les coûts qui ont été enregistrés à partir des ordres de travail pour les actifs de maintenance associés.

> [!NOTE]
> Dans cette rubrique, *actifs de maintenance* se réfère aux actifs du module **Gestion d'actifs**, et *Immobilisations* se réfère aux actifs du module **Immobilisations**.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>Définir un emplacement par défaut pour les nouveaux actifs de maintenance créés à partir d'immobilisations (facultatif)

Cette configuration facultative vous permet de définir un poste technique par défaut pour les nouveaux actifs de maintenance créés à partir d'immobilisations. Vous terminez généralement cette configuration une seule fois, si vous la terminez.

Procédez comme suit pour effectuer cette configuration :

1. Accédez à **Gestion d'actifs \> Configuration \> Paramètres de gestion des actifs**.
1. Sous l'onglet **Immobilisations**, dans le champ **Poste technique**, sélectionnez l'emplacement par défaut.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>Utiliser des actifs de maintenance et des immobilisations intégrés

Cette section fournit un ensemble de procédures qui montrent différentes manières d'utiliser les fonctionnalités intégrées de gestion des actifs et des immobilisations.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>Associer un actif de maintenance existant à une immobilisation

Pour associer un actif de maintenance existant à une immobilisation, procédez comme suit.

1. Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs** (ou **Actifs actifs**).
1. Sélectionnez un actif.
1. Sur l'organisateur **Immobilisation**, dans le champ **Numéro d'immobilisation**, sélectionnez une immobilisation existante.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>Afficher l'immobilisation associée à un actif de maintenance sélectionné

Pour afficher l'immobilisation associée à un actif de maintenance sélectionné, procédez comme suit.

1. Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs** (ou **Actifs actifs**).
1. Sélectionnez un actif.
1. Sur l'organisateur **Immobilisation**, dans le champ **Numéro d'immobilisation**, sélectionnez le lien.

    La page **Immobilisations** de l'actif sélectionné s'ouvre. (En règle générale, cette page se trouve à l'adresse **Immobilisations \> Immobilisations \> Immobilisations**.)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>Afficher la ressource en cours de maintenance associée à une immobilisation sélectionné

Pour afficher la ressource en cours de maintenance associée à une immobilisation sélectionné, procédez comme suit.

1. Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.
1. Sélectionnez un actif.
1. Dans le volet Actions, sous l'onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Ressource en cours de maintenance**.

    La page **Ressource en cours de maintenance** de l'actif associé à l'immobilisation sélectionnée est ouverte. (En règle générale, cette page se trouve à l'adresse **Gestion d'actifs \> Actifs \> Tous les actifs**.)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>Afficher les coûts de maintenance associés à une immobilisation

Les ordres de travail de gestion des actifs peuvent être enregistrés pour les ressources en cours de maintenance, et chacun de ces ordres de travail a généralement un coût. Lorsqu'une immobilisation est associée à une ressource en cours de maintenance, vous pouvez aller directement de l'immobilisation pour afficher les coûts associés.

Pour afficher les coûts de maintenance associés à une immobilisation, procédez comme suit.

1. Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.
1. Sélectionnez un actif.
1. Dans le volet Actions, sous l'onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Coût de maintenance**.

    La page **Coût de maintenance** est ouverte et affiche les coûts associés.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>Créer une ressource en cours de maintenance pour une immobilisation existante

Pour créer une ressource en cours de maintenance pour une immobilisation associée, procédez comme suit.

1. Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.
1. Sélectionnez un actif.
1. Dans le volet Actions, sous l'onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Créer une ressource en cours de maintenance**. (Si cette option n'est pas disponible, une ressource en cours de maintenance peut déjà être associée à l'immobilisation sélectionnée.)
1. Terminez la création de l'actif comme décrit dans [Créer un actif](../objects/create-an-object.md).

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>Créer une immobilisation et ajoutez-lui une nouvelle ressource en cours de maintenance

Pour créer une immobilisation et lui ajouter une nouvelle ressource en cours de maintenance, procédez comme suit.

1. Allez dans **Immobilisations \> Immobilisations \> Immobilisations**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Terminez la création de l'immobilisation comme décrit dans [Créer une immobilisation](../../../finance/fixed-assets/tasks/create-fixed-asset.md).
1. Dans le volet Actions, sous l'onglet **Gestion des actifs**, dans le groupe **Nouveau**, sélectionnez **Créer une ressource en cours de maintenance**.
1. Terminez la création de l'actif comme décrit dans [Créer un actif](../objects/create-an-object.md).

### <a name="remove-the-association-between-two-assets"></a>Supprimer l'association entre deux actifs

Dans certains cas, vous devrez peut-être dissocier une ressource en cours de maintenance de son immobilisation. Par exemple, si vous souhaitez [créer une ressource en cours de maintenance](#new-maintenance-from-fixed) à partir d'une immobilisation, vous devez d'abord supprimer toute association existante.

Pour supprimer une association existante entre une ressource en cours de maintenance et une immobilisation, procédez comme suit.

1. Accédez à **Gestion des actifs \> Actifs \> Tous les Actifs** (ou **Actifs actifs**).
1. Recherchez et ouvrez l'immobilisation.
1. Sur l'organisateur **Immobilisation**, effacez la valeur du champ **Poste technique**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]