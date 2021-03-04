---
title: Réception du contenant via l’application d’entrepôt
description: Cette rubrique explique comment configurer l’application d’entrepôt pour prendre en charge l’utilisation d’un processus de réception de contenant pour recevoir le stock physique.
author: perlynne
manager: tfehr
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 0d6894c0adb5671818e976dbb5116ecb947025d2
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428271"
---
# <a name="license-plate-receiving-via-the-warehouse-app"></a>Réception du contenant via l’application d’entrepôt

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment configurer l’application d’entrepôt pour prendre en charge l’utilisation d’un processus de réception de contenant pour recevoir le stock physique.

Vous pouvez utiliser cette fonctionnalité pour enregistrer rapidement la réception du stock entrant lié à un avis préalable d’expédition (APE). Le système crée automatiquement un APE lorsque des processus de gestion d’entrepôt sont utilisés pour expédier un ordre de transfert. Pour le processus de commande fournisseur, un APE peut être enregistré manuellement ou il peut être automatiquement importé à l’aide d’un processus d’entité de données APE entrant.

Les données de l’APE sont liées aux chargements et expéditions via les *structures d’emballage*, où les palettes (contenants parent) peuvent contenir des caisses (contenants imbriqués).

> [!NOTE]
> Pour réduire le nombre de transactions de stock lorsque des structures d’emballage qui ont des contenants imbriqués sont utilisées, le système enregistre l’inventaire physique disponible sur le contenant parent. Pour déclencher le mouvement de l’inventaire physique en stock du contenant parent vers les contenants imbriqués, en fonction des données de structure d’emballage, l’appareil mobile doit fournir un élément de menu basé sur le processus de création de travaux *Conditionner dans des contenants imbriqués*.

## <a name="warehousing-mobile-device-app-processing"></a>Traitement de l’application Entrepôt sur les appareils mobiles

Lorsqu’un travailleur scanne un ID de contenant entrant, le système initialise un processus de réception de contenant. Sur la base de ces informations, le contenu du contenant (les données provenant de l’APE) sont physiquement enregistrées à l’emplacement de quai de l’entrée. Les flux qui s’ensuivent dépendront des besoins de votre processus métier.

## <a name="work-policies"></a>Stratégies de travail

À l’instar du processus de l’option de menu *Déclarer comme terminé* sur appareil mobile (par exemple), le processus de réception de contenant prend en charge plusieurs flux de travail basés sur la configuration définie.

### <a name="work-policies-with-work-creation"></a>Stratégies de travail avec création de travail

Lorsque vous enregistrez des éléments entrants à l’aide d’une stratégie de travail qui crée du travail, le système génère et enregistre des enregistrements de travail de rangement pour chaque enregistrement. Si vous utilisez le processus de travail *Réception et rangement de contenant*, alors l’enregistrement et le rangement sont traités comme une seule opération à l’aide d’une seule option de menu sur l’appareil mobile. Si vous utilisez le processus *Réception de contenant*, alors les processus de réception et de rangement sont traités comme deux opérations d’entrepôt différentes, chacune avec sa propre option de menu sur l’appareil mobile.

### <a name="work-policies-without-work-creation"></a>Stratégies de travail sans création de travail

Vous pouvez utiliser le processus de réception de contenant sans créer de travail. Si vous définissez des stratégies de travail dont le type d’ordre de travail est *Réception du transfert* et/ou *Commandes fournisseur*, et que vous utilisez le processus *Réception (et rangement) de contenant*, aucun des deux processus de l’application mobile Entrepôt suivants ne créera de travail. Au lieu de cela, ils enregistreront simplement le stock physique entrant dans le contenant sur le quai de réception.

- *Réception de contenant*
- *Réception et rangement de contenant*

> [!NOTE]
> - Vous devez définir au moins un emplacement pour une stratégie de travail dans la section **Emplacements de stock**. Vous ne pouvez pas spécifier le même emplacement pour plusieurs stratégies de travail.
> - L’option **Imprimer l’étiquette** pour les options de menu des appareils mobiles Entrepôt n’imprimera pas d’étiquette de contenant sans création de travail.

Pour rendre cette fonctionnalité disponible sur votre système, vous devez activer la fonctionnalité *Améliorations de la réception de contenant* dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Recevoir du stock dans un emplacement qui ne suit pas les contenants

Il est possible d’utiliser un emplacement d’entrepôt affecté à un profil d’emplacement même lorsque l’option **Utiliser le suivi des contenants** n’est pas activée. Par conséquent, lorsque vous recevez du stock, vous pouvez directement enregistrer le stock disponible dans un emplacement sans création de travail.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Ajouter des options de menu d’appareil mobile pour chaque emplacement de réception dans un entrepôt

La fonctionnalité *Améliorations de la réception de contenant* vous permet de recevoir à n’importe quel emplacement d’un entrepôt en ajoutant des options de menu de réception (et de rangement) de contenant spécifiques à chaque emplacement dans l’application mobile Entrepôt. Auparavant, le système prenait en charge la réception uniquement à l’emplacement par défaut défini pour chaque entrepôt. Cependant, lorsque cette fonction est activée, les options de menu des appareils mobiles pour la réception (et le rangement) de contenant fournissent désormais une option **Utiliser les données par défaut**, qui vous permet de sélectionner un emplacement « vers » personnalisé pour chaque option de menu. (Cette option était déjà disponible pour certains autres types d’options de menu.)

Pour rendre cette fonctionnalité disponible sur votre système, vous devez activer la fonctionnalité *Améliorations de la réception de contenant* dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>Afficher ou ignorer la page récapitulative de réception

Vous pouvez utiliser la fonctionnalité *Contrôler s’il faut afficher une page récapitulative de réception sur les appareils mobiles* pour bénéficier d’un flux d’application Entrepôt détaillé supplémentaire dans le cadre du processus de réception des contenants.

Lorsque cette fonction est activée, les options de menu d’appareil mobile pour la réception des contenants ou la réception et le rangement des contenants fourniront un paramètre **Afficher la page récapitulative de réception**. Ce paramètre a les options suivantes :

- **Afficher un résumé détaillé** - Pendant la réception des contenants, les collaborateurs verront une page supplémentaire qui affiche les informations complètes de l’APE.
- **Ignorer le récapitulatif** - Les collaborateurs ne verront pas les informations complètes de l’APE. Les collaborateurs de l’entrepôt ne sont également pas en mesure de définir un code de disposition ou d’ajouter des exceptions pendant le processus de réception.

Pour rendre cette fonctionnalité disponible sur votre système, vous devez activer la fonctionnalité *Contrôler s’il faut afficher une page récapitulative de réception sur les appareils mobiles* dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Empêcher les contenants expédiés par ordre de transfert d’être utilisés dans des entrepôts autres que l’entrepôt de destination

Un processus de réception des contenant ne peut pas être utilisé si un APE contient un ID de contenant qui existe déjà et possède des données de disponibilité physique à un emplacement d’entrepôt autre que l’emplacement de l’entrepôt où l’enregistrement de contenant a lieu.

Pour les scénarios d’ordre de transfert dans lesquels l’entrepôt de transit ne suit pas les contenants (et ne suit donc pas non plus l’inventaire physique en stock par contenant), vous pouvez utiliser la fonctionnalité *Empêcher l’utilisation des contenants expédiés par ordre de transfert dans d’autres entrepôts que l’entrepôt de destination* pour empêcher les mises à jour physiques des contenants en transit.

Pour rendre cette fonctionnalité disponible sur votre système, vous devez activer la fonctionnalité *Empêcher l’utilisation des contenants expédiés par ordre de transfert dans d’autres entrepôts que l’entrepôt de destination* dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Pour gérer la fonctionnalité lorsque cette fonctionnalité est disponible, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
1. Sur l’onglet **Général**, sur le raccourci **Contenants**, définissez le champ **Stratégie de contenant de l’entrepôt de transit** sur l’une des valeurs suivantes :

    - **Autoriser la réutilisation de contenant non suivi** - Le système fonctionne de la même manière qu’il fonctionne lorsque la fonctionnalité *Empêcher l’utilisation des contenants expédiés par ordre de transfert dans d’autres entrepôts que l’entrepôt de destination* n’est pas disponible. Cette valeur est le paramètre par défaut lors de la première activation de la fonction.
    - **Empêcher la réutilisation du contenant non suivi** - Seules les mises à jour en rapport avec un contenant expédié seront autorisées dans l’entrepôt de destination jusqu’à réception de l’ordre de transfert.

## <a name="more-information"></a>Informations supplémentaires

Pour plus d’informations sur les éléments de menu des appareils mobiles, voir [Configurer des appareils mobiles pour le travail en entrepôt](configure-mobile-devices-warehouse.md).

Pour plus d’informations sur le scénario de production *Déclarer comme terminé*, voir la [Vue d’ensemble des stratégies de travail d’entrepôt](warehouse-work-policies.md).

Pour plus d’informations sur la gestion des chargements entrants, voir [Gestion en entrepôt des chargements entrants pour les commandes fournisseur](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]