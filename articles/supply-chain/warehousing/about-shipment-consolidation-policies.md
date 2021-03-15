---
title: Stratégies de consolidation de l'expédition
description: Cette rubrique fournit une vue d'ensemble des fonctionnalités permettant une configuration flexible des stratégies de consolidation de l'expédition.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate, WHSShipConsolidationTemplateApply, WHSShipConsolidationTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 326e9a32cdab049d974b6d88742434fbc8d56817
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006439"
---
# <a name="shipment-consolidation-policies"></a>Stratégies de consolidation de l'expédition

Le processus de consolidation de l'expédition qui utilise des stratégies de consolidation permet une consolidation automatisée des expéditions lors du lancement automatique et manuel dans l'entrepôt. La consolidation automatisée qui était disponible avant l'introduction de cette fonctionnalité comportait des champs codés en dur et était basée sur le champ **Consolider l'expédition au lancement dans l'entrepôt** qui a été défini pour un entrepôt.

Les stratégies de consolidation de l'expédition sont utilisées pour les fonctionnalités suivantes :

- Le traitement par lots automatisé de lancement dans l'entrepôt
- La commande **Lancement dans l'entrepôt** dans une commande client ou un ordre de transfert
- La page **Lancement dans l'entrepôt** dédiée
- La commande **Lancement dans l'entrepôt** de la page **Atelier de planification des chargements**
- La consolidation manuelle des expéditions sur les pages **Consolider les expéditions** et **Atelier de consolidation des expéditions**

Avant l'introduction des stratégies de consolidation d'expédition, la fonction de consolidation existait en tant que paramètre au niveau de l'entrepôt. Toutes les commandes de tous les clients d'un même entrepôt ont été traitées comme si elles avaient les mêmes exigences de consolidation. Les stratégies de consolidation de l'expédition prennent en charge les scénarios dans lesquels différentes organisations ont des exigences différentes pour la consolidation de l'expédition.

Les requêtes sont utilisées pour identifier la stratégie de consolidation d'expédition qui s'applique, puis un ensemble modifiable de champs détermine la façon dont les lignes de chargement sont regroupées au niveau de l'expédition. (Ce modèle ressemble au modèle suivi par les modèles de la vague.) De plus, une option **Consolider avec les expéditions existantes** a été ajoutée à chaque stratégie. Lorsque cette option est activée, la procédure *Lancement dans l'entrepôt* recherche les expéditions à consolider en recherchant parmi les envois existants qui ont été créés sur la base de la même stratégie de consolidation. Dans ce cas, le système sélectionnera une expédition ou un chargement existant au lieu d'en créer un nouveau. Cependant, le système ne sera consolidé qu'avec les expéditions existantes qui ont le statut *Ouvert* ; les expéditions qui appartiennent à un lancement dont le statut est *Lancé* ou autre ne seront pas considérées comme des objectifs de consolidation.

Lorsque les stratégies de consolidation de l'expédition sont mises à disposition, le paramètre **Consolider l'expédition au lancement dans l'entrepôt** qui était auparavant disponible sur la page de configuration **Entrepôts** est masqué. Pour vous aider à passer à la nouvelle fonctionnalité de consolidation des expéditions, une fonction de la page **Stratégies de consolidation de l'expédition** crée une stratégie par défaut qui inclut automatiquement l'ancien paramètre pour les entrepôts existants. Une fois cette stratégie par défaut créée, le paramètre **Consolider l'expédition au lancement dans l'entrepôt** de la page de configuration **Entrepôts** ne sera plus pris en compte.

Vous pouvez utiliser la page **Lancement dans l'entrepôt** pour remplacer manuellement la stratégie de consolidation applicable de la même manière que vous pouvez remplacer les stratégies d'exécution.

Vous pouvez utiliser la commande **Lancer \> Lancement dans l'entrepôt** de la page **Atelier de planification des chargements** pour créer des chargements sortants basés sur la commande client et les lignes d'ordre de transfert avant de lancer la validation dans l'entrepôt. Ces chargements utilisent la même logique de consolidation que celle introduite avec la consolidation des stratégies d'expédition.

Vous pouvez utiliser la page **Atelier de consolidation des expéditions** pour consolider les expéditions existantes qui n'ont pas encore été confirmées mais qui ont déjà été validées dans l'entrepôt. Cette fonctionnalité prend en charge les scénarios dans lesquels le processus de validation automatisé, qui possède sa propre consolidation d'expédition, est exécuté plusieurs fois par jour, mais des consolidations supplémentaires potentielles sont identifiées manuellement avant la fin de l'expédition aux transporteurs pendant le processus de confirmation. Cette fonctionnalité vous permet de consolider les expéditions sortantes qui sont créées à partir des lignes de commande client ou d'ordre de transfert à tout moment après que les expéditions ont été validées dans l'entrepôt mais avant qu'elles ne soient confirmées.

La page **Atelier de consolidation des expéditions** fonctionne comme l'atelier de création de chargement, où vous pouvez évaluer plusieurs expéditions en même temps et affecter une commande non consolidée à une expédition spécifique. Vous pouvez appliquer des modèles de consolidation d'expédition pour évaluer plusieurs fois les consolidations proposées et les confirmer. Certaines règles sont mises en œuvre pour empêcher une consolidation non autorisée et pour vous avertir d'éventuelles erreurs.

## <a name="overview-of-new-functionality"></a>Aperçu des nouvelles fonctionnalités

Cette section décrit les pages, commandes et fonctionnalités qui sont modifiées ou ajoutées lorsque vous activez et utilisez la fonctionnalité *Stratégies de consolidation de l'expédition*.

### <a name="shipment-consolidation-policies-page"></a>Page Stratégies de consolidation de l'expédition

Les stratégies sont différenciées par type d'ordre de travail. Le type **Commandes client** représente _Commande client_ expéditions et le type **Ordre de transfert** représente _Problème de transfert_ expéditions.

Chaque stratégie de consolidation d'expédition a une requête qui définit quand elle est appliquée et un numéro de séquence qui détermine l'ordre d'exécution. La consolidation est appliquée pour chaque combinaison unique des champs sélectionnés. Un paramètre supplémentaire fourni est utilisé pour la consolidation avec les expéditions existantes (en cours). Les stratégies sont évaluées et appliquées chaque fois qu'une nouvelle expédition est créée (avant le traitement des vagues).

Si une stratégie ne contient aucun champ obligatoire ou si elle inclut des champs interdits, elle est marquée comme non valide dans la section **Sélectionné**. Les listes des champs obligatoires et interdits sont codées en dur et peuvent être étendues.

La liste suivante indique les champs obligatoires. Étant donné que les expéditions sont toujours fractionnées en fonction de ces champs, vous ne pouvez pas grouper plusieurs expéditions ayant des valeurs différentes pour ces champs.

- Pour les commandes client :

    - **Numéro de compte :** _WHSShipmentTable.AccountNum_
    - **Destinataire de la livraison :** _WHSShipmentTable.DeliveryName_
    - **Adresse postale (RecId) :** _WHSShipmentTable.DeliveryPostalAddress_
    - **Entrepôt :** _WHSShipmentTable.InventLocationId_

- Pour les ordres de transfert :

    - **Entrepôt d'origine :** _InventTransferTable.InventLocationIdFrom_
    - **Entrepôt de destination :** _InventTransferTable.InventLocationIdTo_

Les champs suivants ne sont pas disponibles pour tous les types de documents. Ces champs ne sont pas visibles dans l'interface utilisateur (UI) et ne peuvent pas être utilisés pour la consolidation.

- **ID d'expédition :** _WHSShipmentTable.ShipmentId_
- **Statut :** _WHSShipmentTable.ShipmentStatus_
- **Stratégie de consolidation d'expédition :** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Type de transaction de travail :** _WHSShipmentTable.WorkTransType_
- **ID de vague :** _WHSShipmentTable.WaveId_
- **ID de chargement :** _WHSShipmentTable.LoadId_
- **ID d'expédition :** _WHSLoadLine.ShipmentId_
- **ID de chargement :** _WHSLoadLine.LoadId_

Par défaut, lorsque vous créez une stratégie, l'ensemble des champs obligatoires est utilisé comme champs de consolidation. Cependant, vous pouvez modifier la liste à l'aide des boutons flèche gauche et flèche droite. (Le processus ressemble au processus de sélection des méthodes dans les modèles de vagues.)

Les valeurs que les utilisateurs sélectionnent pour ces champs seront utilisées pour toutes les expéditions nouvellement créées, ou elles seront ajoutées aux expéditions existantes lors de leur consolidation. Lorsque deux expéditions ont la même valeur pour un champ qui est sélectionné pour la consolidation de ces expéditions, elles sont consolidées. Le même principe s'applique à tous les champs de consolidation suivants qui sont sélectionnés. Si les valeurs diffèrent, la deuxième expédition est rejetée et sera sélectionnée pour une nouvelle expédition. Le processus de consolidation automatisé consiste à créer toutes les combinaisons uniques de valeurs pour les champs de consolidation des expéditions, puis à affecter une expédition à la combinaison appropriée.

Les champs non sélectionnés sont ignorés lors du processus de consolidation. Si deux expéditions ont des valeurs différentes pour un champ non sélectionné, le champ est effacé (c'est-à-dire qu'il est défini sur vide). Si les deux expéditions ont la même valeur pour un champ non sélectionné, le champ est renseigné.

La liste des champs de consolidation (c'est-à-dire les champs qui seront effacés s'ils ont des valeurs différentes) est codée en dur. La liste contient tous les champs qui sont initialisés à partir d'une ligne de commande client ou d'un ordre de transfert lorsqu'un nouvel envoi est créé. En d'autres termes, si un champ n'est pas initialisé à partir d'une ligne de commande client ou d'un ordre de transfert, il est ignoré lorsque de nouvelles données sont ajoutées à une expédition existante.

### <a name="release-to-warehouse-page"></a>Page Lancement dans l'entrepôt

- Un nouveau champ dans la grille inférieure montre la stratégie de consolidation qui a été appliquée.
- Un nouveau bouton vous permet de sélectionner et/ou de remplacer manuellement la stratégie de consolidation.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>Commande Lancement dans l'entrepôt de la page Atelier de planification des chargements

- La logique a été ajustée afin d'utiliser des stratégies de consolidation appliquées.
- Les expéditions ne sont désormais regroupées qu'en un seul chargement.

### <a name="consolidate-shipments-page"></a>Page Consolider les expéditions

- La recherche d'expéditions similaires (c'est-à-dire les candidats à la consolidation) a été modifiée afin d'utiliser les champs sélectionnés dans la stratégie de consolidation des expéditions.
- Les champs qui ont des valeurs différentes dans différentes expéditions sont désormais définis sur vide. (Auparavant, les valeurs de l'expédition « de base » sélectionnée étaient utilisées.)

### <a name="shipment-consolidation-workbench-page"></a>Page Atelier de consolidation des expéditions

- La nouvelle fonctionnalité reproduit le processus de consolidation manuelle à plus grande échelle.
- Vous pouvez maintenant ouvrir cette page depuis le menu **Lancement dans l'entrepôt** du module **Gestion des entrepôts**.
- L'algorithme analyse les expéditions existantes qui n'ont pas encore été expédiés. Il propose ensuite la consolidation, en fonction des champs sélectionnés dans les stratégies de consolidation.

## <a name="comparison-of-functionality"></a>Comparaison des fonctionnalités

Le tableau suivant résume le fonctionnement de la consolidation de l'expédition lorsque vous n'utilisez pas de stratégies de consolidation et quand vous les utilisez.

| Sans stratégie de consolidation de l'expédition | Avec stratégie de consolidation de l'expédition |
|---|----|
| Non applicable | Les expéditions de vente ou de transfert sélectionnées pour la consolidation doivent avoir la même stratégie de consolidation que l'expédition en cours de création, ou elles doivent être affectées à une expédition en cours (lorsque l'option **Consolider avec les expéditions existantes** est activée). |
| La procédure *Lancement dans l'entrepôt* ne recherche pas parmi les expéditions existants pour trouver une expédition à consolider. Seules les expéditions créées par une instance actuelle de la procédure *Lancement dans l'entrepôt* sont utilisées pour rechercher une expédition à consolider. | Si l'option **Consolider avec les expéditions existantes** est activée pour une stratégie de consolidation actuellement utilisée, la procédure *Lancement dans l'entrepôt* recherche parmi les expéditions existantes qui ont été créées en fonction de la même stratégie de consolidation pour trouver une expédition à consolider. Par conséquent, si vous avez deux stratégies, une expédition en cours de création en fonction de la stratégie 2 ne sera jamais consolidée avec une expédition créée en fonction de la stratégie 1. |
| Non applicable | Si une liste de champs de stratégie de consolidation est vide ou si une stratégie est introuvable, une nouvelle expédition est créée pour chaque commande client ou ligne d'ordre de transfert. |
| Le champ de consolidation suivant définit la combinaison unique de valeurs utilisée pour consolider les expéditions pour une *ligne de transfert*. (Tous les autres champs sont ignorés).<ul><li>Numéro de commande (OrderNum)</li></ul> | Les champs de consolidation suivant définissent la combinaison unique de valeurs utilisée pour consolider les expéditions pour une *ligne de transfert*. (Tous les autres champs sont ignorés).<ul><li>Numéro de commande (OrderNum)</li><li>Destinataire de la livraison (DeliveryName)</li><li>Adresse postale (DeliveryPostalAddress)</li><li>Code ISO du pays (CountryRegionISOCode)</li><li>Adresse (Address)</li><li>Site (InventSiteId)</li><li>Entrepôt (InventLocationId)</li><li>Transporteur (CarrierCode)</li><li>Service de transporteur (CarrierServiceCode)</li><li>Mode de livraison (ModeCode)</li><li>Groupe de transporteurs (CarrierGroupCode)</li><li>Conditions de livraison (DlvTermId)</li></ul>Ces champs sont les seuls champs disponibles et initialisés lors de la création d'une nouvelle expédition. |
| Les champs de consolidation suivant définissent la combinaison unique de valeurs utilisée pour consolider les expéditions pour une *ligne de vente*. (Tous les autres champs sont ignorés).<ul><li>Numéro de commande (OrderNum)</li><li>Référence client (CustomerRef)</li><li>Demande client (CustomerReq)</li><li>Conditions de livraison (DlvTermId)</li></ul> | Les champs de consolidation suivant définissent la combinaison unique de valeurs utilisée pour consolider les expéditions pour une *ligne de vente*. (Tous les autres champs sont ignorés).<ul><li>Numéro de commande (OrderNum)</li><li>Numéro de compte (AccountNum)</li><li>Destinataire de la livraison (DeliveryName)</li><li>Adresse postale (DeliveryPostalAddress)</li><li>Code ISO du pays (CountryRegionISOCode)</li><li>Adresse (Address)</li><li>Site (InventSiteId)</li><li>Entrepôt (InventLocationId)</li><li>Transporteur (CarrierCode)</li><li>Service de transporteur (CarrierServiceCode)</li><li>Mode de livraison (ModeCode)</li><li>Groupe de transporteurs (CarrierGroupCode)</li><li>ID courtier (BrokerCode)</li><li>Direction (LoadDirection)</li><li>Conditions de livraison (DlvTermId)</li><li>Référence client (CustomerRef)</li><li>Demande client (CustomerReq)</li></ul>Ces champs sont les seuls champs disponibles et initialisés lors de la création d'une nouvelle expédition. |
| Non applicable | Les champs de consolidation suivants sont obligatoires pour une *ligne de vente* et ne peuvent pas être supprimés :<ul><li>Numéro de compte (AccountNum)</li><li>Destinataire de la livraison (DeliveryName)</li><li>Adresse postale (DeliveryPostalAddress)</li><li>Entrepôt (InventLocationId)</li></ul>Par défaut, ces champs seront attribués lors de la création d'une nouvelle stratégie. Ils ne peuvent pas être supprimés. |
| La procédure *Lancement des chargements dans l'entrepôt* de la page **Atelier de planification des chargements** utilise son propre code distinct pour créer des expéditions et des vagues. | Les stratégies de consolidation des expéditions sont appliquées pour déterminer quels champs doivent être évalués pour la consolidation. Les expéditions ne sont consolidées qu'en un seul chargement. |
| Vous devez sélectionner manuellement **Consolider les expéditions** sur la page **Toutes les expéditions**, puis sélectionner une expédition « de base » cible. Le filtre suggérera toutes les expéditions existantes qui ont des valeurs correspondantes pour plusieurs champs clés. | Vous devez sélectionner manuellement **Consolider les expéditions** sur la page **Toutes les expéditions**, puis sélectionner une expédition « de base » cible. Le système suggérera d'autres expéditions existantes en faisant correspondre les valeurs de plusieurs champs clés configurés pour les stratégies de consolidation des expéditions pertinentes. |
| Vous pouvez utiliser la commande **Consolider les expéditions** de la page **Toutes les expéditions** pour une seule expédition. | La page **Atelier de consolidation des expéditions** vous aide à trouver un ensemble d'expéditions qui n'ont pas encore été expédiées. Ces expéditions sont analysées en fonction de plusieurs champs clés configurés dans vos stratégies de consolidation de l'expédition. Toutes les expéditions dont les valeurs de ces champs correspondent sont suggérées pour la consolidation.<p>Vous pouvez gérer manuellement la consolidation en supprimant des expéditions des consolidations suggérées et/ou en leur ajoutant des expéditions. Plusieurs types d'erreurs peuvent se produire, mais vous pouvez ignorer certaines.</p> |
| **Note de conception :** La procédure *Lancement automatique des commandes client dans l'entrepôt* divise les lignes de vente en groupes. Chaque groupe a sa propre valeur **ReleaseToWarehouseId** et est traité séparément par la procédure *Lancement dans l'entrepôt*. Cette procédure crée un nouveau travail quelle que soit la répartition du travail. | **Note de conception :** La procédure *Lancement automatique des commandes client dans l'entrepôt* attribue la même valeur **ReleaseToWarehouseId** à toutes les lignes de vente en cours de traitement. Toutes les lignes de vente sont traitées par la procédure *Lancement dans l'entrepôt* en même temps. Pour garantir le comportement antérieur, vous devez configurer l'interruption de travail par ID d'expédition. |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Configurer les stratégies de consolidation de l'expédition](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]