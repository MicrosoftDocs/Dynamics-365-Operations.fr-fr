---
title: "Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d&quot;approbation de facture"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4691ac4456b08084bcd93f7a8447719a15299c93
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a>Comptes de contrepartie par défaut pour les journaux de facture fournisseur et les journaux d'approbation de facture

[!include[banner](../includes/banner.md)]




Les comptes de contrepartie par défaut sont utilisés dans les pages suivantes de journal des factures fournisseur :

-   Journal des factures
-   Journal des approbations de facture

Utilisez le tableau suivant pour vous aider à décider où affecter les comptes par défaut pour les journaux des factures.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramétrez des comptes par défaut ici...</th>
<th>... pour fournir les comptes par défaut ici</th>
<th>Comment cette option affecte le traitement</th>
<th>Quand utiliser cette option</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Groupe de fournisseurs</strong> – Paramétrez des comptes de contrepartie par défaut pour des groupes de fournisseurs sur la page <strong>Paramétrage du compte par défaut</strong>, que vous pouvez ouvrir depuis la page <strong>Groupes de fournisseurs</strong>.</td>
<td><ul>
<li>Compte fournisseur</li>
<li>Entrées de journal pour les comptes fournisseur dans le groupe de fournisseurs, si des comptes par défaut ne sont pas spécifiés pour les comptes fournisseur</li>
</ul></td>
<td>Les comptes de contrepartie par défaut pour les groupes de fournisseurs sont affichés comme des comptes de contrepartie par défaut pour les fournisseurs sur la page <strong>Paramétrage du compte par défaut</strong>. Vous pouvez ouvrir cette page depuis la page de la liste <strong>Tous les fournisseurs</strong>.</td>
<td>Utilisez cette option si vous payez généralement le même type de choses auprès des mêmes groupes de fournisseurs.</td>
</tr>
<tr class="even">
<td><strong>Compte fournisseur</strong> – Paramétrez les comptes par défaut pour les comptes fournisseur sur la page <strong>Paramétrage du compte par défaut</strong>, que vous pouvez ouvrir depuis la page <strong>Fournisseurs</strong>.</td>
<td>Entrées de journal pour le compte fournisseur</td>
<td>Les comptes de contrepartie par défaut pour les comptes fournisseur sont affichés comme des comptes de contrepartie par défaut pour les entrées de journal du compte fournisseur.</td>
<td>Utilisez cette option si vous payez généralement le même type de choses auprès des mêmes fournisseurs.</td>
</tr>
<tr class="odd">
<td><strong>Noms de journal</strong> – Paramétrez des comptes de contrepartie par défaut pour les journaux sur la page <strong>Noms de journal</strong>. Sélectionnez l'option <strong>Compte de contrepartie fixe</strong>. Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut dans les noms de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</td>
<td><ul>
<li>En-tête de journal utilisant le nom de journal</li>
<li>Entrées de journal dans les journaux qui utilisent le nom de journal</li>
</ul></td>
<td>Si l'option <strong>Compte de contrepartie fixe</strong> de la page <strong>Noms de journal</strong> est sélectionnée, le compte de contrepartie pour le nom de journal remplace le compte de contrepartie par défaut pour le fournisseur ou le groupe de fournisseurs.</td>
<td>Utilisez cette option pour paramétrer des journaux pour les coûts spécifiques et les dépenses facturées sur des comptes spécifiques, indépendamment du fournisseur ou du groupe de fournisseurs dont le fournisseur fait partie.</td>
</tr>
<tr class="even">
<td><strong>Noms de journal</strong> – Paramétrez des comptes de contrepartie par défaut pour les journaux sur la page <strong>Noms de journal</strong>. Désactivez l'option <strong>Compte de contrepartie fixe</strong>. Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut dans les noms de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</td>
<td><ul>
<li>En-tête de journal</li>
<li>Entrées de journal dans les journaux qui utilisent le nom de journal</li>
</ul></td>
<td>Ces entrées par défaut sont utilisées dans des écrans d'en-tête de journal, et le compte de contrepartie dans l'écran d'en-tête de journal est utilisé comme entrée par défaut sur la pages de N° document de journal. Les comptes par défaut de la page <strong>Noms de journal </strong>sont utilisés uniquement si les comptes par défaut ne sont pas paramétrés pour le compte fournisseur.</td>
<td>Utilisez cette option pour paramétrer des comptes par défaut à utiliser lorsqu'un compte de contrepartie par défaut du fournisseur n'est pas affecté.</td>
</tr>
<tr class="odd">
<td><strong>En-tête de journal</strong> – Paramétrez un compte de contrepartie par défaut pour un journal à utiliser comme entrée par défaut dans les pages de N° document de journal. Notez que vous ne pouvez pas spécifier de comptes de contrepartie par défaut sur l'en-tête de journal si le type de journal des noms de journal est <strong>Registre des factures</strong> ou <strong>Approbation</strong>.</td>
<td>Entrées de journal dans le journal</td>
<td>Le compte de contrepartie par défaut pour un journal est utilisé comme entrée par défaut sur les pages de N° document de journal.</td>
<td>Utilisez cette option pour accélérer la saisie des données si la plupart des entrées d'un journal ont le même compte de contrepartie.</td>
</tr>
</tbody>
</table>






