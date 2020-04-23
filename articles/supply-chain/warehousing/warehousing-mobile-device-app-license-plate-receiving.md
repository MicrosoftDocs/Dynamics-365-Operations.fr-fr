---
title: Réception du contenant via l'application mobile Entrepôt
description: Cette rubrique explique comment configurer l'application mobile Entrepôt pour prendre en charge l'utilisation d'un processus de réception de contenant pour recevoir le stock physique.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 98cd608edea1d5365d0d3532244f1fcdb6293d3c
ms.sourcegitcommit: 3a823444005d316bd95fc663e2dbc8252ac7d93a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261330"
---
# <a name="license-plate-receiving-via-the-warehousing-mobile-app"></a>Réception du contenant via l'application mobile Entrepôt

Cette rubrique explique comment configurer l'application mobile Entrepôt pour prendre en charge l'utilisation d'un processus de réception de contenant pour recevoir le stock physique.

Vous pouvez utiliser cette fonctionnalité pour enregistrer rapidement la réception du stock entrant lié à un avis préalable d'expédition (APE). Le système crée automatiquement un APE lorsque des processus de gestion d'entrepôt sont utilisés pour expédier un ordre de transfert. Pour le processus de commande fournisseur, un APE peut être enregistré manuellement ou il peut être automatiquement importé à l'aide d'un processus d'entité de données APE entrant.

Les données de l'APE sont liées aux chargements et expéditions via les *structures d'emballage*, où les palettes (contenants parent) peuvent contenir des caisses (contenants imbriqués).

> [!NOTE]
> Pour réduire le nombre de transactions de stock lorsque des structures d'emballage qui ont des contenants imbriqués sont utilisées, le système enregistre l'inventaire physique disponible sur le contenant parent. Pour déclencher le mouvement de l'inventaire physique en stock du contenant parent vers les contenants imbriqués, en fonction des données de structure d'emballage, l'appareil mobile doit fournir un élément de menu basé sur le processus de création de travaux *Conditionner dans des contenants imbriqués*.

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a>Afficher ou ignorer la page récapitulative de réception

Vous pouvez utiliser la fonctionnalité *Contrôler s'il faut afficher une page récapitulative de réception sur les appareils mobiles* pour bénéficier d'un flux d'application Entrepôt détaillé supplémentaire dans le cadre du processus de réception des contenants.

Avant de pouvoir utiliser cette fonctionnalité, vous devez l'activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Contrôler s'il faut afficher une page récapitulative de réception sur les appareils mobiles*

Lorsque cette fonction est activée, les options de menu d'appareil mobile pour la réception des contenants ou la réception et le rangement des contenants fourniront un paramètre **Afficher la page récapitulative de réception**. Ce paramètre a les options suivantes :

- **Afficher un résumé détaillé** - Pendant la réception des contenants, les collaborateurs verront une page supplémentaire qui affiche les informations complètes de l'APE.
- **Ignorer le récapitulatif** - Les collaborateurs ne verront pas les informations complètes de l'APE. Les collaborateurs de l'entrepôt ne sont également pas en mesure de définir un code de disposition ou d'ajouter des exceptions pendant le processus de réception.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Empêcher les contenants expédiés par ordre de transfert d'être utilisés dans des entrepôts autres que l'entrepôt de destination

Un processus de réception des contenants ne peut pas être utilisé si un APE contient un ID de contenant qui existe déjà et possède des données physiques à portée de main à un emplacement d'entrepôt autre que l'emplacement de l'entrepôt où l'enregistrement de contenant a lieu.

Pour les scénarios d'ordre de transfert dans lesquels l'entrepôt de transit ne suit pas les contenants (et ne suit donc pas non plus l'inventaire physique en stock par contenant), vous pouvez utiliser la fonctionnalité *Empêcher l'utilisation des contenants expédiés par ordre de transfert dans d'autres entrepôts que l'entrepôt de destination* pour empêcher les mises à jour physiques des contenants en transit.

Avant de pouvoir utiliser cette fonctionnalité, vous devez l'activer sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l'activer si nécessaire. Dans l'espace de travail **Gestion des fonctionnalités**, cette fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des entrepôts*
- **Nom de la fonctionnalité :** *Empêcher l'utilisation des contenants expédiés par ordre de transfert dans d'autres entrepôts que l'entrepôt de destination*

Pour gérer la fonctionnalité lorsque cette fonctionnalité est disponible, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Sur l'onglet **Général**, sur le raccourci **Contenants**, définissez le champ **Stratégie de contenant de l'entrepôt de transit** sur l'une des valeurs suivantes :

    - **Autoriser la réutilisation de contenant non suivi** - Le système fonctionne de la même manière qu'il fonctionne lorsque la fonctionnalité *Empêcher l'utilisation des contenants expédiés par ordre de transfert dans d'autres entrepôts que l'entrepôt de destination* n'est pas disponible. Cette valeur est le paramètre par défaut lors de la première activation de la fonction.
    - **Empêcher la réutilisation du contenant non suivi** - Seules les mises à jour en rapport avec un contenant expédié seront autorisées dans l'entrepôt de destination jusqu'à réception de l'ordre de transfert.

## <a name="more-information"></a>Informations supplémentaires

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

Pour plus d'informations sur les éléments de menu des appareils mobiles, voir [Configurer des appareils mobiles pour le travail en entrepôt](configure-mobile-devices-warehouse.md).
