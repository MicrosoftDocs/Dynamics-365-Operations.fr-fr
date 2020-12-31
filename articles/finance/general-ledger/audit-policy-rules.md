---
title: Règles de stratégie d’audit
description: Les stratégies d’audit permettent d’évaluer la conformité des états de dépenses, factures fournisseur et commandes fournisseur avec les règles de stratégie que vous créez. Toutes les règles associées à une stratégie d’audit sont exécutées en mode de traitement par lots selon le programme que vous spécifiez.  Chaque règle de stratégie est une instance d’un type de règle de stratégie. Pour chaque type de règle de stratégie, une seule règle de stratégie peut être active à la fois.
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de6406029aa88424863dd9a47505f5b3ad27f237
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443131"
---
# <a name="audit-policy-rules"></a>Règles de stratégie d’audit

[!include [banner](../includes/banner.md)]

Les stratégies d’audit permettent d’évaluer la conformité des états de dépenses, factures fournisseur et commandes fournisseur avec les règles de stratégie que vous créez. Toutes les règles associées à une stratégie d’audit sont exécutées en mode de traitement par lots selon le programme que vous spécifiez.  Chaque règle de stratégie est une instance d’un type de règle de stratégie. Pour chaque type de règle de stratégie, une seule règle de stratégie peut être active à la fois. 

<a name="queries-and-query-types"></a>Requêtes et types de requêtes
-----------------------

Lorsque vous créez une règle de stratégie d’audit, vous commencez par sélectionner un type de règle de stratégie. Celui-ci spécifie la requête AOA (arbre d’objets d’application) à utiliser comme point de départ pour créer la règle de stratégie. Il spécifie également le type de requête à utiliser pour la règle de stratégie. La requête détermine le document source évalué par la règle de stratégie. Elle spécifie également les champs dans le document source qui identifient l’entité juridique et la date à utiliser lors de la sélection de documents pour audit. Le type de requête contrôle les champs par défaut dans la page de requête et dans la page Règle de stratégie d’audit. Le tableau suivant indique les types de requêtes disponibles pour les règles de stratégie d’audit.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de requête</th>
<th>Objectif</th>
<th>Plus d’informations</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Conditionnelle</td>
<td>Permet d’évaluer les attributs de document source par rapport à des valeurs spécifiées.</td>
<td></td>
</tr>
<tr class="even">
<td>Regroupement</td>
<td>Permet d’évaluer plusieurs documents sources ou lignes de document source par rapport à une règle de stratégie via le regroupement de valeurs numériques.</td>
<td></td>
</tr>
<tr class="odd">
<td>Échantillonnage</td>
<td>Permet d’évaluer un pourcentage spécifié de documents sources sélectionnés au hasard en relation avec les violations de stratégie.</td>
<td>Lorsque vous sélectionnez cette option, utilisez la page Règle de stratégie d’audit pour spécifier le pourcentage de documents à sélectionner au hasard pour l’audit.</td>
</tr>
<tr class="even">
<td>Doublon</td>
<td>Permet d’évaluer des documents sources afin de déterminer s’ils contiennent des entrées en double dans des champs spécifiés.</td>
<td>Lorsque vous sélectionnez cette option, utilisez la page Règle de stratégie d’audit pour spécifier le nombre de jours que vous souhaitez ajouter au début de la plage de dates de sélection de documents dans le cadre de l’évaluation des documents en relation avec les entrées en double.</td>
</tr>
<tr class="odd">
<td>Recherche de liste</td>
<td>Permet d’évaluer les documents sources pour des entités spécifiques.</td>
<td>Le document racine de la requête définit le document en cours d’audit. La requête doit être une requête de liste qui inclut une référence à la table DirPartyTable. Cette option peut être utilisée uniquement avec les requêtes AOA suivantes :
<ul>
<li><span class="ui">AuditPolicyExpenseList</span> (États de dépenses au niveau des employés)</li>
<li><span class="ui">AuditPolicyPurchList</span> (Commandes fournisseur au niveau des fournisseurs)</li>
<li><span class="ui">AuditPolicyVendInvoiceList</span> (Facture fournisseur au niveau des fournisseurs)</li>
</ul>
Lorsque vous sélectionnez cette option, spécifiez les entités contrôlées dans la page Règle de stratégie d’audit.</td>
</tr>
<tr class="even">
<td>Recherche de mots-clés</td>
<td>Permet d’évaluer les documents sources pour déterminer s’ils contiennent certains mots.</td>
<td>Lorsque vous sélectionnez cette option, entrez les mots à rechercher dans la page Règle de stratégie d’audit. La page Règle de stratégie d’audit inclut des options qui vous permettent de spécifier les tables et champs à évaluer en relation avec les mots que vous avez entrés.</td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a>Paramètres courants
L’ensemble des règles de stratégie pour une stratégie d’audit spécifique partagent les mêmes paramètres de lot et la même plage de dates de sélection de documents. Ces paramètres sont spécifiés dans la page Options supplémentaires pour la stratégie.



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Violations et incidents de stratégie d’audit](audit-policy-violations-cases.md)
[Définir des stratégies d’audit pour les documents source](tasks/define-audit-policies-source-documents.md)


