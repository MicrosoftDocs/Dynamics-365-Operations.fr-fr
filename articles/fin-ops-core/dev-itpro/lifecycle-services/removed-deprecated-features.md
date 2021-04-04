---
title: Fonctionnalités supprimées ou obsolètes dans Lifecycle Services (LCS)
description: Cette rubrique décrit les fonctions qui ont été supprimées, ou qu’il est prévu de supprimer de Microsoft Dynamics Lifecycle Services (LCS).
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6b49a6f26b4c2fa895fe0e49f716ce423c3c0057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559083"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>Fonctionnalités supprimées ou obsolètes dans Lifecycle Services (LCS)

[!include[banner](../includes/banner.md)]

Cette rubrique décrit les fonctions qui ont été supprimées, ou qui sont devenues obsolètes pour Microsoft Dynamics Lifecycle Services (LCS).

- Une fonction *supprimée* n’est plus disponible dans le service.
- Une fonction *déconseillée* n’est pas en développement actif et peut être supprimée dans une prochaine mise à jour.

Cette liste est fournie pour vous aider à prendre en compte ces suppressions et abandons à mesure que vous avancez dans votre propre planification.

## <a name="october-2019-announcements"></a>Annonces d’octobre 2019

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Organigrammes du concepteur de processus d’entreprise

<table>
<tbody>
<tr>
<td><strong>Motif de l’abandon/de la suppression</strong></td>
<td>Nous déconseillons le composant d’organigrammes dans le Concepteur de processus d’entreprise (BPM), car la conception héritée a entraîné une faible utilisation.</td>
</tr>
<tr>
<td><strong>Remplacé par une autre fonctionnalité ?</strong></td>
<td>Non</td>
</tr>
<tr>
<td><strong>Domaines affectés</strong></td>
<td>Concepteur de processus d’entreprise</td>
</tr>
<tr>
<td><strong>Statut</strong></td>
<td>Obsolète : le composant d’organigrammes dans BPM devrait être supprimé en 2020. La fonctionnalité suivante ne sera pas disponible :
<ul>
<li>Tous les organigrammes seront en lecture seule et ne pourront pas être modifiés. Les propriétés de forme associées aux activités de l’organigramme ne seront pas non plus disponibles. Ces organigrammes comprennent à la fois des organigrammes par défaut générés automatiquement et des organigrammes personnalisés qui sont modifiés en fonction de ces organigrammes par défaut.</li>
<li>Les étapes de processus seront en lecture seule et ne pourront pas être modifiées.</li>     
<li>La fonctionnalité d’analyse d’adéquation/des écarts héritée ne sera pas disponible. Par conséquent, aucune liste des écarts ne sera automatiquement créée ou disponible pour l’exportation.
<p><strong>Remarque :</strong> Cette fonctionnalité était auparavant obsolète et remplacée par les intégrations Microsoft Azure DevOps.</p>
</li>
<li>L’historique des versions de l’organigramme ne sera pas disponible.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]