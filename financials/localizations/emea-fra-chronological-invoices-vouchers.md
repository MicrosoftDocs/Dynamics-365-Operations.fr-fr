---
title: "Numéros de facture et de document chronologiques pour la France"
description: "Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client pour les entités juridiques en France."
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

# <a name="chronological-invoice-and-voucher-numbers-for-france"></a>Numéros de facture et de document chronologiques pour la France

[!include[banner](../includes/banner.md)]


Cette rubrique explique comment paramétrer et utiliser des numéros chronologiques pour les factures et les documents dans la comptabilité client pour les entités juridiques en France.  

En France, il est obligatoire que toutes les factures et les documents associés émis soient numérotés dans l'ordre chronologique. La chronologie doit être prise en charge par les périodes fiscales. Tous les numéros qui appartiennent à des périodes antérieures doivent être inférieurs aux numéros qui appartiennent aux périodes ultérieures. Dans une période fiscale, l'ordre chronologique n'est pas obligatoire, mais il ne doit y avoir aucun écart dans la numérotation. Pour répondre à cette exigence, la numérotation chronologique dans le module Comptabilité client affecte les documents suivants :

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
<li>Dans la page <strong>Paramètres de la comptabilité client</strong>, sous l'onglet <strong>Mises à jour</strong>, définissez l'option <strong>Numérotation chronologique</strong> sur <strong>Oui</strong>.</li>
<li>Dans la page <strong>Souches de numéros</strong>, définissez autant de souches de numéros qu'il est nécessaire pour couvrir les périodes fiscales affectées. Vous devez spécifier une société pour chaque souche de numéros. Les segments des souches de numéros doivent être définis de manière à fournir l'ordre chronologique des périodes. Par exemple, les noms de segment peuvent contenir un préfixe spécial qui identifie une période spécifique.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="set-up-chronological-numbering"></a>Paramétrer la numérotation chronologique
### <a name="accounts-receivable-parameters"></a>Paramètres de la comptabilité client

Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, par exemple **Facture financière**. Cliquez ensuite sur le bouton **Paramétrage de la numérotation chronologique** qui sera disponible pour les références prises en charge. Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.

### <a name="number-sequence-groups"></a>Groupes de souches de numéros

Si différents clients utilisent différents modèles de numérotation, vous devez paramétrer la numérotation chronologique au niveau du groupe de souches de numéros. Dans la page **Paramètres de la comptabilité client**, sous l'onglet **Souches de numéros**, sélectionnez l'une des références prises en charge, puis cliquez sur **Groupe**. Dans la page **Groupe de souches de numéros**, sélectionnez un groupe existant ou créez-en un. Dans la section **Référence**, sélectionnez l'une des références prises en charge, puis cliquez sur **Paramétrage de la numérotation chronologique**. Dans la page **Paramétrage de la numérotation chronologique**, définissez les souches de numéros ayant des périodes valides.

## <a name="invoice-posting"></a>Validation de facture
Lorsque vous validez une facture ou un avoir, la souche de numéros appropriée est utilisée pour générer un numéro. Cette souche de numéros est sélectionnée selon la période valide contenant la date de la facture. La numérotation chronologique spécifique au client a une priorité plus élevée que la numérotation chronologique.




