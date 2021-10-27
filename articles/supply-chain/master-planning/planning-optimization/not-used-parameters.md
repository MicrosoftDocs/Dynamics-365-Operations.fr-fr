---
title: Paramètres non utilisés par Planning Optimization
description: Cette rubrique répertorie les paramètres que Planning Optimization ne prend pas en compte actuellement lors de son fonctionnement.
author: ChristianRytt
ms.date: 09/02/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e1b4e6df2c514b55ec101c0edf22590041628
ms.sourcegitcommit: fcb1aa39e933216dea9e586b552bce6057f416a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645756"
---
# <a name="parameters-not-used-by-planning-optimization"></a>Paramètres non utilisés par Planning Optimization

[!include [banner](../../includes/banner.md)]

Cette rubrique répertorie les paramètres que Planning Optimization ne prend pas en compte actuellement lors de son fonctionnement. Le service de planification peut ignorer un paramètre car, par exemple, les fonctionnalités associées ne sont pas encore prises en charge. D’autre part, le paramètre peut être devenu obsolète en raison de changements fonctionnels.

Les sections suivantes répertorient les paramètres que Planning Optimization n’utilise pas sur des pages spécifiques. Elles expliquent également pourquoi chaque paramètre n’est pas utilisé.

## <a name="master-planning-parameters-page"></a>Page Paramètres de Planification générale

Planning Optimization n’utilise pas les paramètres ou options suivants sur la page **Paramètres de planification générale** :

- Onglet **Général** :

  - **Plan prévisionnel actuel** - Support *Prévision* en attente.
  - **Plan général statique actuel** – Support *Copier le plan statique vers le plan dynamique* en attente.
  - **Plan général dynamique actuel** – Support *Copier le plan statique vers le plan dynamique* en attente.
  - **Copier le plan général statique complet et mis à jour dans le plan général dynamique** – Support *Copier le plan statique vers le plan dynamique* en attente.
  - **Heure de début des retards calculés** – Support *Retards calculés* en attente.
  - **Utiliser les jours négatifs dynamiques** – Planning Optimization utilise toujours l’approche *Jours négatifs dynamiques*.
  - **Calendrier des dates du jour** – Support *Planification* en attente.
  - **Utilisation du cache** – La configuration de l’abonnement Microsoft Azure gère les points de performance.
  - **Nombre de tâches dans le groupe de tâches d’assistance** – La configuration de l’abonnement Azure gère les points de performance.
  - **Pré-traitement : filtrer automatiquement par articles avec une demande directe** – La configuration de l’abonnement Azure gère les points de performance.
  - **Post-traitement : filtrer automatiquement par articles avec une demande directe** – La configuration de l’abonnement Azure gère les points de performance.
  - **Nombre d’ordres dans le groupe de tâches d’assistance** – La configuration de l’abonnement Azure gère les points de performance.
  - **Nombre de threads** – La configuration de l’abonnement Azure gère les points de performance.
  - **Expiration du processus de planification en minutes** – La configuration de l’abonnement Azure gère les points de performance.
  - **Planification de l’heure de début** – Support *Planification* en attente.

- Onglet **Ordres prévisionnels** :

  - **Heure de réception** – Support *Planification* en attente.
  - **Production** – Support *Planification* en attente.
  - Champs dans la section **Projet** – Support *Planification* en attente.

## <a name="coverage-groups-page"></a>Page Groupes de couverture

Planning Optimization n’utilise pas les paramètres ou options suivants sur la page **Groupes de couverture** :

- Organisateur **Général** :

  - **Jours positifs** – Support *Jours positifs* en attente.
  - **Consommer le stock disponible** – Support *Consommation du stock disponible* en attente.
  - **Utiliser la nomenclature ou la version de formule spécifiée** – Support *Versions de formule avec co/sous-produit* en attente.
  - **Utiliser la version de routage spécifiée** – Support *Demande avec des exigences de nomenclature ou de routage spécifiques définies* en attente.

- Raccourci **Action** :

  - **Message d’action** – Support *Actions* en attente.
  - **Plage de gestion d’action** – Support *Actions* en attente.
  - **Reporter la marge** – Support *Actions* en attente.
  - **Avancer la marge** – Support *Actions* en attente.
  - **Date de base** – Support *Actions* en attente.
  - **Avancer** – Support *Actions* en attente.
  - **Reporter** – Support *Actions* en attente.
  - **Diminuer** – Support *Actions* en attente.
  - **Augmenter** – Support *Actions* en attente.
  - **Actions dérivées** – Support *Actions* en attente.

- Raccourci **Autre** :

  - **Geler la plage de gestion (jours)** – Le support *Geler la plage de gestion* n’est pas prévu dans Planning Optimization.
  - **Plage de gestion de l’explosion de nomenclature (jours)** – Support *Planification* en attente.
  - **Plage de gestion de la planification de capacité (jours)** – Support *Planification* en attente.
  - **Plage de gestion des demandes d’achat approuvées (jours)** – Support *Demande d’achat* en attente.
  - **Plage de gestion du plan prévisionnel** – Support *Prévision* en attente.

- Raccourci **Retards** :

  - **Retards calculés** – Support *Retards calculés* en attente.
  - **Calculer la plage de gestion des retards (jours)** – Support *Retards calculés* en attente.

## <a name="item-coverage-page"></a>Page Couverture de l’article

Planning Optimization n’utilise pas les paramètres ou options suivants sur la page **Couverture de l’article** :

- Onglet **Général** :

  - **Type d’ordre planifié** – Planning Optimization ne prend pas en charge l’option *Kanban*, support *Kanban* en attente.
  - **Geler la plage de gestion (jours)** – Le support *Geler la plage de gestion* n’est pas prévu dans Planning Optimization.
  - **Plage de gestion de l’explosion de nomenclature (jours)** – Support *Planification* en attente.
  - **Plage de gestion de la planification de capacité (jours)** – Support *Planification* en attente.
  - **Plage de gestion des demandes d’achat approuvées (jours)** – Support *Demande d’achat* en attente.
  - **Remplir le minimum** – Planning Optimization ne prend pas en charge les options *Date du jour*, *Première émission* et *Plage de gestion de la couverture*. Elle utilise toujours l’option *Date du jour + heure d’achat*.
  - **Périodes minimum** – Support *Niveau d’inventaire minimum* en attente.
  - **Formule de planification** – Support *Versions de formules avec co/sous-produits* en attente.
  - **Priorité par défaut** – Support *Versions de formules avec co/sous-produits* en attente.
  - **Priorité actuelle** – Support *Versions de formules avec co/sous-produits* en attente.
  - **Date de modification** – Support *Versions de formules avec co/sous-produits* en attente.
  - **Consommer le stock disponible** – Support *Consommation du stock disponible* en attente.

- Onglet **Délai** :

  - **Moment d'achat** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.
  - **Délai de production** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.
  - **Délai de transfert** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.
  - **Jours ouvrés** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.

## <a name="master-plans-page"></a>Page Plans généraux

Planning Optimization n’utilise pas les paramètres ou options suivants sur la page **Plans généraux** :

- Organisateur **Général** :

  - **Inclure le stock disponible** – Support *Consommation du stock disponible* en attente.
  - **Remplacer le stock disponible** – Support *Consommation du stock disponible* en attente.
  - **Consommer le stock disponible** – Support *Consommation du stock disponible* en attente.
  - **Inclure les transactions de stock** – Support *Consommation du stock disponible* en attente.
  - **Inclure les devis de vente** – Support *Devis de vente* en attente.
  - **Inclure la demande de devis** – Support *Demande de devis* en attente.
  - **Utiliser les dates de conservation** – Support *Durée de vie* en attente.
  - **Inclure le plan de continuité** – Support *Planification de la continuité* en attente.
  - **Méthode de planification** – Support *Planification* en attente.
  - **Propriété finie** – Support *Planification* en attente.
  - **Plage de gestion de capacité de retour en arrière dans la planification** – Support *Planification* en attente.
  - **Capacité finie** – Support *Planification* en attente.
  - **Plage de gestion de la capacité finie** – Support *Planification* en attente.
  - **Capacité finie pour les ressources de goulot d’étranglement** – Support *Planification* en attente.
  - **Plage de gestion de la capacité pour les ressources de goulot d’étranglement** – Support *Planification* en attente.
  - **Commandes planifiées** – Planning Optimization utilise des séquences de numéros fixes.
  - **Session** – Planning Optimization utilise des séquences de numéros fixes.
  - **Plan de continuité** – Planning Optimization utilise des séquences de numéros fixes.

- Raccourci **Plages de gestion en jours** :

  - **Geler** – Le support *Geler la plage de gestion* n’est pas planifié dans Planning Optimization.
  - **Explosion** – Support *Planification* en attente.
  - **Plan prévisionnel** – Support *Prévision* supplémentaire en attente.
  - **Capacité** – Support *Planification* en attente.
  - **Plan de continuité** – Support *Planification de la continuité* en attente.
  - **Message d’action** – Support *Actions* en attente.
  - **Retards calculés** – Support *Retards calculés* supplémentaire en attente.
  - **Classement** – Support *Production* en attente.

- Raccourci **Retards calculés** :

  - **Assurez-vous que les commandes planifiées ne sont pas créées avant la date d’exécution de la planification principale** – Support *Retards calculés* en attente.
  - **Ajouter le délai calculé à la date du besoin** (dans la section **Bons de commande planifiés**) – Support *Retards calculés* en attente.
  - **Ajouter le délai calculé à la date du besoin** (dans la section **Ordres de fabrication prévisionnels**) – Support *Retards calculés* en attente.
  - **Ajouter le délai calculé à la date du besoin** (dans la section **Transfert planifié**) – Support *Retards calculés* en attente.
  - **Ajouter le délai calculé à la date du besoin** (dans la section **Kanban planifié**) – Support *Retards calculés* en attente.

- Raccourci **Classement** :

  - **Classer les ordres planifiés après la planification générale** – Support *Classement* en attente.
  - **Type de compartiment** – Support *Classement* en attente.
  - **Type de période** – Support *Classement* en attente.
  - Support **Nombre de compartiments dans le cycle de campagne** - En attente *Séquençage*.

## <a name="released-product-details-page"></a>Page Détails des produits lancés

Planning Optimization n’utilise pas l’option de paramètre suivante sur la page **Détails des produits lancés** :

- Raccourci **Ingénieur** :

  - Support **Type de fabrication** – Planning Optimization ne prend pas en charge l’option *Élément de planification*, *Éléments de planification* en attente.

## <a name="default-order-settings-page"></a>Page Paramètres de commande par défaut

Planning Optimization n’utilise pas l’option de paramètre suivante sur la page **Paramètres de commande par défaut** :

- Onglet **Commande fournisseur** :

  - **Délai d’achat** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.
  - **Jours ouvrés** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.

- Raccourci **Stock** :

  - **Contrôle de la date de livraison** – Planning Optimization ne prend pas en charge l’option *CTP*, support *CTP* en attente.
  - **Délai de stock** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.
  - **Jours ouvrés** : dans les versions du service Optimisation de la planification antérieures à la version du 6 août 2021, l'Optimisation de la planification utilise ce paramètre pour calculer les dates de commande et de livraison correctes, mais il n'enregistre pas le délai calculé lui-même dans la commande planifiée. Dans les versions ultérieures, le service utilise également le délai calculé pour définir le champ **Délai** et l'option **Jours ouvrés** requis pour la commande planifiée concernée.

## <a name="working-time-calendars-page"></a>Page Calendriers de temps de travail

Planning Optimization n’utilise pas le paramètre suivant sur la page **Calendriers de temps de travail** :

- Support **Calendrier de base** – En attente *Calendriers de base*.

## <a name="batch-disposition-master-page"></a>Page Données principales de disposition de lot

Planning Optimization n’utilise pas le paramètre suivant sur la page **Données principales de disposition de lot** :

- Raccourci **Configurer** :

  - Support **Disponible à la vente** – En attente *Codes de disposition des lots*.
