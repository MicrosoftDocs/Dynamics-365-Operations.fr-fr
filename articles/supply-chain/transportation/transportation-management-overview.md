---
title: Vue d’ensemble de la gestion du transport
description: Cet article fournit une vue d’ensemble de la fonctionnalité de gestion du transport dans Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "30251"
- intro-internal
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12f870c95f28e752c3c3b3dd4161d82815b9954a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897456"
---
# <a name="transportation-management-overview"></a>Vue d’ensemble de la gestion du transport

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de la fonctionnalité de gestion du transport dans Supply Chain Management.

La Gestion du transport vous permet d’utiliser les transports de votre société et d’identifier les solutions utilisant des fournisseurs et des prestataires d’acheminement spécifiques pour les commandes entrantes et sortantes. Par exemple, vous pouvez identifier le parcours le plus rapide ou le moins cher pour une expédition. Le tableau suivant décrit les principaux scénarios utilisés pour la Gestion du transport.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario</th>
<th>Avantages de la Gestion du transport</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilisez des fournisseurs logistique externes pour les activités de transport.</td>
<td>Utilisez la Gestion du transport pour le transport entrant et/ou sortant.</td>
</tr>
<tr class="even">
<td>La propre flotte de la société est disponible pour la livraison/le chargement et les frais de livraison sont transférés aux clients.</td>
<td>Pour les processus sortants, vous pouvez utiliser la Gestion du transport pour déterminer les frais de transport et les transférer aux clients. Toutefois, le processus de rapprochement de la facture du transporteur n’est nécessaire.</td>
</tr>
<tr class="odd">
<td>La propre flotte de la société est disponible pour la livraison/le chargement, mais des frais de livraison ne sont pas transférés aux clients, car les prix des produits comprennent le transport.</td>
<td>Une grande partie de la fonctionnalité Gestion du transport n&#39;est pas nécessaire. Toutefois, vous pouvez utiliser la Gestion du transport pour déterminer les taux de transport et pour ajuster le prix de vente en conséquence.</td>
</tr>
<tr class="even">
<td>Le service logistique est fourni par une autre entité juridique dans la même société.</td>
<td><ul>
<li>Utilisez la Gestion du transport en traitant l’autre entité juridique comme n’importe quel transporteur. Vous ne pouvez pas automatiser les transactions économiques entre les entités juridiques. Par conséquent, vous devez gérer ces transactions manuellement (par exemple, en créant une commande fournisseur).</li>
<li>Dans l’entité juridique qui fournit les services logistiques, la Gestion du transport peut être utilisée pour déterminer les taux de transport.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a>Planification du transport dans Supply Chain Management
Dans Gestion du transport, la planification des transports peut être basée sur les commandes ou sur les expéditions créées selon ces commandes. Les expéditions existent toujours à un moment donné mais elles ne sont pas requises pour la planification des transports. Les ordres de transfert font partie du scénario sortant et peuvent être planifiés avec des commandes client. 

![Load drawing.](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Transport entrant
Lorsque vous commandez des articles à un fournisseur et que ces articles doivent être livrés à votre entrepôt, vous pouvez souhaiter organiser le transport des articles vous-même. Utilisez Supply Chain Management pour planifier le transport et la réception de la charge entrante. La figure suivante indique le flux du processus entreprise de planification du transport pour un chargement entrant. 

![Flux de processus entreprise pour le transport de chargement entrant.](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Transport sortant
Vous pouvez planifier et traiter une charge sortante pour expédier des articles spécifiques de l’entrepôt d’une société à un client. Utilisez Supply Chain Management pour planifier le transport et l’expédition de la charge sortante. La figure suivante indique le flux du processus entreprise de planification et le traitement des charges sortantes pour l’expédition. 

![Planification et traitement des charges sortantes.](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Création de chargement
Supply Chain Management fournit une stratégie de création de chargement qui est nommée Stratégie de création de chargement basée sur le volume. Cette stratégie vous permet d’utiliser les valeurs maximales spécifiées pour la hauteur et le poids dans le modèle de chargement, sinon vous pouvez remplacer les paramètres en entrant de nouvelles valeurs. Pour utiliser cette stratégie, sélectionnez-la dans le champ **Stratégie de création de chargement** dans l’organisateur **Paramétrage** sur la page **Atelier de création de chargement**. En outre, vous pouvez ajouter vos propres stratégies de création de chargement en créant une nouvelle classe dans l’arbre d’objets d’application (AOA).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]