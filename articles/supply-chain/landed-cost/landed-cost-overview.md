---
title: Module de coût au débarquement
description: Le module de coût au débarquement aide les entreprises à rationaliser les opérations d’expédition entrantes en offrant aux utilisateurs un contrôle financier et logistique complet sur le fret importé, du fabricant à l’entrepôt.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ccc6f0100582b9703b9755b50b7e8504aa153d15
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022130"
---
# <a name="landed-cost-module"></a>Module de coût au débarquement

[!include [banner](../../includes/banner.md)]

Le module de **coût au débarquement** aide les entreprises à rationaliser les opérations d’expédition entrantes en offrant aux utilisateurs un contrôle financier et logistique complet sur le fret importé, du fabricant à l’entrepôt. Pour les marchandises importées, les coûts au débarquement peuvent représenter 40 pour cent ou plus du coût total de chaque article importé. Par conséquent, le défi consiste à fournir des estimations précises des coûts au débarquement.

Les entreprises peuvent utiliser le coût fixe pour effectuer les tâches suivantes :

- Estimer les coûts au débarquement au moment de la création du voyage.
- La répartition des frais de débarquement sur plusieurs articles et bons de commande ou sur les ordres de transfert en un seul voyage.
- Soutenir le transfert des marchandises entre les emplacements physiques en reconnaissant les coûts au débarquement.
- Reconnaître les charges à payer pour les marchandises en transit.

Le coût au débarquement fournit des estimations de coûts précises et opportunes pour les frais généraux au débarquement. En même temps, il offre une visibilité financière et logistique accrue sur la chaîne d’approvisionnement étendue. Cela permet également de réduire l’administration des erreurs de coût et de calcul.

## <a name="highlights"></a>Points forts

### <a name="voyages"></a>Voyages

Dans Coût au débarquement, un voyage est un mouvement distinct d’un emplacement de départ, via un ensemble spécifique de destinations sur une période spécifiée, à un emplacement d’entrepôt d’arrivée spécifié. Les commandes fournisseur et les lignes de commande peuvent être ajoutés à un seul conteneur ou à plusieurs conteneurs pour un voyage, et les coûts seront correctement réattribués à la ligne d’article. Les commandes et les lignes de commande peuvent également être ajoutées entre les entités juridiques pour un seul voyage.

### <a name="item-ownership"></a>Propriété de l’article

Dans Microsoft Dynamics 365 Supply Chain Management, les marchandises sont généralement reçues à la destination de l’entrepôt puis facturées. Cependant, dans la plupart des accords commerciaux internationaux, une entreprise prend possession des marchandises à partir du moment où elles quittent le port d’origine, avant qu’elles n’aient été physiquement reçues. Le coût au débarquement permet aux entreprises de facturer les marchandises avant qu’elles n’aient été physiquement reçues. Ce concept est connu sous le nom d’ordre de transit. Il crée un type de commande pour gérer la réception des marchandises après la facturation de la commande d’achat d’origine.

### <a name="costs"></a>Coûts

Lorsque vous créez un voyage dans Coût au débarquement, des coûts peuvent y être automatiquement ajoutés. Ces coûts sont définis dans le coût au débarquement, et diverses options de coûts et bases de coûts sont disponibles pour eux. Chaque coût peut être configuré pour différents niveaux d’un voyage et réparti au niveau de l’article via des règles de répartition qui prennent en charge la quantité, le volume, le poids, le montant et les diviseurs volumétriques définis. Ces coûts estimés fournissent une estimation précise de tous les coûts d’un voyage.

Le coût au débarquement exécute ensuite une comptabilisation / une accumulation préliminaire des coûts estimés au débarquement pour garantir qu’un calcul précis des coûts estimés est fourni au moment de la création du voyage. Au fur et à mesure que ces coûts automatiques sont facturés, les coûts estimés sont contrepassés et remplacés par les coûts réels, sur la base des factures de coûts.

Les coûts réels sont des coûts estimés contrepassés qui sont validés au moment de la facturation des coûts en utilisant des comptes de compensation configurés pour chaque type de coût (par exemple, droits de douane, fret et assurance). Ces écritures suivent le comportement de publication associé à l’élément spécifique. Ils mettent automatiquement à jour la comptabilisation de l’inventaire, que le type de comptabilisation soit premier entré, premier sorti (FIFO), dernier entré, premier sorti (LIFO), moyenne pondérée mobile ou moyenne mobile. Tous les types de publication de groupe de modèles d’inventaire sont pris en charge. Pour la moyenne mobile et la comptabilisation des coûts standard, des comptes d’écart de prix d’achat sont disponibles pour enregistrer les différences entre les coûts estimés et les coûts réels.

### <a name="item-and-order-tracking"></a>Suivi des articles et des commandes

Lorsqu’un voyage passe du lieu de départ d’origine à l’entrepôt de destination finale, les utilisateurs peuvent mettre à jour chaque *étape*, de son voyage selon les besoins. Pour chaque étape, un délai de livraison et un statut d’expédition sont identifiés. Les dates de livraison confirmées pour le passage à l’étape suivante du voyage sont également identifiées. Ensemble, ces dates de livraison fournissent une date de livraison estimée des marchandises à l’entrepôt d’arrivée. Les utilisateurs peuvent modifier ces dates de livraison. Dans ce cas, la date de livraison estimée de la marchandise est alors automatiquement mise à jour, en fonction des délais et des étapes du voyage. La visibilité des marchandises en transit par voyage et par bateau est disponible par conteneur avant la réception des marchandises. Étant donné que les dates sont mises à jour sur chaque ligne de commande, les entreprises ont plus de contrôle sur la logistique et la planification des entrepôts.

## <a name="landed-cost-concepts"></a>Concepts de coût au débarquement

Le tableau suivant résume certains concepts de base du coût au débarquement.

| Concept | Description |
|---|---|
| Voyage | En règle générale, un voyage est un navire. Cependant, selon vos pratiques et procédures, il peut s’agir d’un fournisseur ou d’une commande fournisseur. Il n’y a pas de limites à l’utilisation de ce concept. |
| Folio | Un folio est souvent déterminé par la réglementation douanière. Un folio se compose de marchandises d’un fournisseur pour une entité/entreprise par expédition. Les marchandises d’un folio peuvent se trouver dans un seul conteneur ou réparties sur plusieurs conteneurs. |
| Conteneur d’expédition | Les conteneurs d’expédition stockent les lignes de commande fournisseur. Ils se situent à un niveau inférieur au niveau d’expédition. Ils sont généralement utilisés si les coûts sont répartis pour les marchandises par conteneur, ou si la réception se fait par conteneur. |
| Type de conteneur d’expédition | Les types de conteneurs d’expédition peuvent déterminer le prix d’un type de coût (par exemple, fret). Ils fournissent également des informations d’expédition utiles. |
| Type de coût | Les types de coûts identifient les coûts associés aux importations, tels que les droits de douane, le fret et l’assurance. |
| Coût automatique | Les coûts automobiles fonctionnent comme des accords commerciaux. Un coût auto est lié à un niveau de voyage. |
| Port | Les ports sont des zones de réception et de transfert des marchandises. |
| Bateau | Un navire est le support utilisé pour transporter des marchandises, comme un navire ou un avion. |
| Marchandises en transit | Selon les paramètres, les marchandises sont placées dans un entrepôt en transit après la mise à jour d’une facture. |
| Activité | Les activités peuvent être utilisées pour stocker chaque étape significative du voyage entre deux ports. Ils peuvent être utilisés pour mettre à jour les dates. |
| Modèle de parcours | Les modèles de voyage sont des itinéraires empruntés par les marchandises entre deux ports. |

Pour une comparaison de la terminologie et des caractéristiques des modules **Prix au débarquement** et **Gestion des transports** (TMS), voir [Coût au débarquement vs gestion du transport](landed-cost-vs-tms.md).
