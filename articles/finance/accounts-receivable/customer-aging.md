---
title: Balance âgée des clients
description: L'état Balance âgée des clients affiche les soldes dus par les clients, triés par intervalle de dates ou plage âgée.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 062e8972c879d770cc4106c2811cd4c16fff0446
ms.sourcegitcommit: 25909c6ad3616e4f75a2fe006057dda18d7cc856
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2020
ms.locfileid: "3974859"
---
# <a name="customer-aging-report"></a>Balance âgée des clients 

L'état **Balance âgée des clients** affiche les soldes dus par les clients, triés par intervalle de dates ou plage âgée.

Lorsque vous générez cet état, les paramètres par défaut suivants sont affichés. Ces paramètres permettent de filtrer les données qui seront affichées dans l'état. Pour plus d’informations, voir [Paramétrer des recouvrements](set-up-collections.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Champ</p></th>
<th><p>Description </p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classification de facturation</strong></p></td>
<td><p>Sélectionnez une ou plusieurs classifications de facturation à inclure dans l'état.</p>
<div class="alert">

**Remarque :** ce contrôle n'est disponible que si la clé de configuration <STRONG>Secteur public</STRONG> est sélectionnée.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Ajouter des transactions sans classification de facturation</strong></p></td>
<td><p>Lorsque cette case à cocher est activée, les transactions sans classification de facturation affectée sont affichées dans l'état.</p>
<div class="alert">

**Remarque :** ce contrôle n'est disponible que si la clé de configuration <STRONG>Secteur public</STRONG> est sélectionnée.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Agé tel que</strong></p></td>
<td><p>Entrez la date utilisée sur la plage âgée actuelle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Solde en date du</strong></p></td>
<td><p>Entrez la date pour laquelle afficher les soldes du client. Elle est également appelée date limite pour les transactions.</p></td>
</tr>
<tr class="even">
<td><p><strong>Date de début</strong></p></td>
<td><p>Entrez une date comprise dans le premier intervalle de périodes ou dans la plage âgée à inclure dans l'état.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Critères</strong></p></td>
<td><p>Sélectionnez le type de date sur lequel baser l'état.</p>
<ul>
<li><p><strong>Date de transaction</strong> – Date de validation des transactions. Par exemple, il peut s'agir d'une date de facture qui sert de base au calcul de date d'échéance.</p></li>
<li><p><strong>Date d'échéance</strong> – Date d'échéance des transactions, basée sur les conditions de paiement.</p></li>
<li><p><strong>Date de document</strong> – Date de document définie par l'utilisateur, qui sert de base de calcul de la date d'échéance.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Définition de la période de balance âgée</strong></p></td>
<td><p>Sélectionnez une définition de période de balance âgée. Le champ <strong>Intervalle</strong> n'est pas utilisé si vous sélectionnez une définition de plage âgée.</p>
<p>Les définitions de plage âgée comprenant plus de six plages âgées ne peuvent pas être utilisées dans l'état imprimé.</p>
<div class="alert">

**Remarque :** vous pouvez configurer des plages âgées sur la page <STRONG>Définitions des plages âgées</STRONG>.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Imprimer la description de la période de balance âgée</strong></p></td>
<td><p>Sélectionnez <strong>Oui</strong> pour inclure des descriptions de plage âgée en haut de chaque colonne de plage âgée de l'état. Sélectionnez <strong>Non</strong> pour imprimer l'état sans les en-têtes de colonnes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intervalle</strong></p></td>
<td><p>Permet de définir la période à utiliser en entrant le nombre d'unités de jours ou de mois dans chaque période. Par exemple, pour afficher des informations de balance âgée par semaine, entrez 7 dans ce champ, puis sélectionnez <strong>Jour</strong> dans le champ <strong>Jour/mois</strong>.</p>
<div class="alert">

**Remarque :** les informations entrées dans ce champ ne sont utilisées que si vous n'avez pas sélectionné de définition de plage âgée. Sinon, le sens d'impression est défini sur la définition de la plage âgée.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Jour/mois</strong></p></td>
<td><p>Permet de sélectionner l'unité, soit <strong>Jour</strong> soit <strong>Mois</strong>, utilisée pour définir la période dans le champ <strong>Intervalle</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sens d'impression</strong></p></td>
<td><p>Sélectionnez si les soldes doivent être calculés et si l'état de plage âgée doit être imprimée pour des périodes passées et futures. Les dates sont évaluées par rapport à la date sélectionnée dans le champ <strong>Solde à la date</strong>. Sélectionnez <strong>En arrière</strong> pour afficher les informations pour les périodes passées. Sélectionnez <strong>En avant</strong> pour afficher les informations pour les périodes futures.</p>

**Remarque :** les informations entrées dans ce champ ne sont utilisées que si vous n'avez pas sélectionné de définition de plage âgée.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Détails</strong></p></td>
<td><p>Sélectionnez cette option pour répertorier les transactions comprises dans les soldes affichés dans l'état.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inclure les montants en devise de transaction</strong></p></td>
<td><p>Sélectionnez cette option pour inclure les montants dans la devise de transaction, en plus des montants dans la devise comptable. Si cette case à cocher n'est pas activée, les montants de l'état ne sont affichés que dans la devise comptable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Solde négatif</strong></p></td>
<td><p>Sélectionnez pour inclure les comptes client qui ont des soldes négatifs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Exclure les comptes à solde nul</strong></p></td>
<td><p>Sélectionnez pour exclure les comptes client qui ont un solde nul.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Positionnement des paiements</strong></p></td>
<td><p>Sélectionnez pour afficher les paiements non réglés. Ceux-ci sont affichés dans la première colonne de l'état.</p></td>
</tr>
</tbody>
</table>

