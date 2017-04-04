---
title: "Facture et n° document chronologiques pour la France"
description: "Cette rubrique explique comment configurer et utiliser des nombres chronologiques pour les factures et documents dans Ventes pour les entités juridiques en France."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustParameters, NumberSequenceGroup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264514
ms.assetid: d1fce1dc-2186-443c-9b4d-b6f64236bc3a
ms.search.region: France
ms.author: ilyako
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 8596e7214b3209709b384f9903e41ad3014f708a
ms.lasthandoff: 03/31/2017


---

# <a name="chronological-invoice-and-voucher-numbers-for-france"></a>Facture et n° document chronologiques pour la France

Cette rubrique explique comment configurer et utiliser des nombres chronologiques pour les factures et documents dans Ventes pour les entités juridiques en France.  

En France, il existe une obligation légale que tous les factures et documents associés qui sont publiés soient compté dans l'ordre chronologique. La ligne temporelle doit être prise en charge par les périodes fiscales. Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieur aux numéros qui appartiennent aux périodes ultérieures. Dans le mois d'un exercice, l'ordre chronologique n'est pas obligatoire, mais il ne doit exister aucune manque dans la numérotation. Pour répondre à la demande, la numérotation chronologique dans Ventes affecte les documents suivants :

-   Facture financière
-   N° document de facture financière
-   Avoir financier
-   N° document d'avoir financier
-   Facture client
-   Document de facture client
-   Avoir sur vente
-   N° document d'avoir sur vente

## <a name="prerequisites"></a>Conditions préalables
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Logiciel requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pays/région</td>
<td>L'adresse principale de l'entité juridique doit être en France.</td>
</tr>
<tr class="even">
<td>Tâches associées de paramétrage</td>
<td><ul>
<li>Sur <strong>Paramètres des ventes</strong> la page, sous <strong>Mises à jour</strong> l'onglet, définissez <strong>Numérotation chronologique</strong> l'option pour.</li>
<li>Sur <strong>Souches de numéros</strong> la page, définissez autant de souches de numéros comme vous le souhaitez pour couvrir les périodes fiscales affectées. Vous devez spécifier une société pour chaque souche de numéros. Les segments des souches de numéros doivent être définis afin qu'ils constituent la commande chronologique pour les périodes. Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="set-up-chronological-numbering"></a>Numérotation chronologique de paramétrage
### <a name="accounts-receivable-parameters"></a>Paramètres de la comptabilité client

Sous ** des paramètres des ventes ** page, sous ** des souches de numéros ** l'onglet, sélectionnez l'une des références prises en charge, comme ** facture financière **. Cliquez ensuite sur ** numérotation chronologique paramétrée ** qui se bouton est disponible pour les références prises en charge. Sous ** numérotation chronologique paramétrée ** la page, définissez les souches de numéros dates d'effet qui ont des périodes valides.

### <a name="number-sequence-groups"></a>Groupes de souches de numéros

Si les différents clients utilisent différents modèles pour le comptage, vous devez paramétrer la numérotation chronologique au niveau de le groupe de souches de numéros. Sous ** des paramètres des ventes ** page, sous ** des souches de numéros ** l'onglet, sélectionnez l'une des références prises en charge, puis cliquez sur ** groupe **. Sous ** groupe de souches de numéros ** la page, sélectionnez un groupe existant, ou créer un nouveau groupe. Dans ** référence ** la section, sélectionnez l'une des références prises en charge, puis cliquez sur ** numérotation chronologique paramétrée **. Sous ** numérotation chronologique paramétrée ** la page, définissez les souches de numéros dates d'effet qui ont des périodes valides.

## <a name="invoice-posting"></a>Validation de facture
Lorsque vous validez une facture ou un avoir, la souche de numéros appropriée est utilisée pour générer un nombre. Cette souche de numéros est activée selon la période valide qui contient la date de facture. la numérotation chronologique Client- spécifique a la priorité élevée que la numérotation chronologique.


