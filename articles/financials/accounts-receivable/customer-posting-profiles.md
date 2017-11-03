---
title: Profils de validation client
description: "Les profils de validation client contrôlent la validation des transactions client dans la comptabilité."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: da750645612c2a0a7650edfd933d707618d9f9ce
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="customer-posting-profiles"></a>Profils de validation client

[!include[banner](../includes/banner.md)]


Les profils de validation client contrôlent la validation des transactions client dans la comptabilité.

<a name="customer-posting-profiles"></a>Profils de validation client
-------------------------

Les profils de validation client permettent d'affecter des comptes généraux et des paramètres de document à tous les clients, à un groupe de clients ou à un client unique. Ces paramètres sont utilisés lorsque vous créez des commandes client, des factures financières, des paiements en espèces, des lettres de relance et des notes d'intérêt. Pour certaines transactions, vous pouvez sélectionner un profil de validation différent qui prime sur les profils de validation paramétrés pour les transactions dans cette page. 

Le profil de validation par défaut est défini dans l'organisateur Comptabilité et taxe sur la page de paramètres de la Comptabilité fournisseur. Le profil de validation par défaut est alors automatiquement inclus dans l'en-tête des nouveaux documents dans lesquels vous pouvez le modifier en un profil de validation différent, si nécessaire.

Vous pouvez également associer des définitions de validation aux types de validation de transaction sur la page Définitions de validation de transaction. Les définitions de validation contrôlent la validation des transactions client dans la comptabilité à la place des profils de validation.

## <a name="creating-a-posting-profile"></a>Création d'un profil de validation
Permet de spécifier les comptes généraux utilisés dans la validation des transactions dont le profil de validation est sélectionné. Permet de sélectionner un code compte et, si possible, un numéro de compte ou de groupe pour le profil de validation sélectionné. Lors de la validation, le profil de validation qui convient le mieux à chaque transaction est localisé en recherchant la combinaison code compte, numéro de compte ou groupe et numéro la plus spécifique selon la priorité suivante :

| Valeur du champ **Code de compte** | Valeur du champ **Numéro de compte/groupe**            | Priorité de recherche |
|------------------------------|-------------------------------------------------|-----------------|
| **Enregistrement**                    | Compte client spécifique                       | 1               |
| **Groupe**                    | Groupe de clients affecté au client | 2               |
| **Tout**                      | Blanc                                           | 3               |

Si vous souhaitez que toutes les transactions client aient le même profil de validation, paramétrez un seul profil de validation à l'aide de la valeur Tous du champ Code de compte. Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Profil de validation</strong></td>
<td>Permet d'entrer un code pour le profil de validation. Par exemple, vous pouvez créer deux profils de validation afin d'obtenir un compte pour les soldes client dans la devise nationale et un autre dans une devise étrangère. Vous pouvez appeler un compte National et l'autre Étranger.</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Permet d'entrer la description du profil de validation. Cela est uniquement utilisé pour mieux identifier le profil de validation lorsque vous l'affichez sur cette page.</td>
</tr>
<tr class="odd">
<td><strong>Code de compte</strong></td>
<td>Permet de spécifier si le profil de validation s'applique à un seul client, à un groupe de clients ou à tous les clients :
<ul>
<li><strong>Table</strong> – Le profil de validation s'applique à un seul client. Sélectionnez le compte client dans le champ Numéro de compte/groupe.</li>
<li><strong>Group</strong> – Le profil de validation s'applique à un groupe de clients. Sélectionnez le groupe de clients dans le champ Numéro de compte/groupe.</li>
<li><strong>Tous</strong> – Le profil de validation s'applique à tous les clients. Laissez vide le champ Numéro de compte/groupe.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Numéro de compte/groupe</strong></td>
<td>Si l'option Table est sélectionnée dans le champ Code de compte, sélectionnez le numéro de compte du client associé au profil de validation. Si l'option Groupe est sélectionnée, sélectionnez le groupe de clients. Si l'option Tous est sélectionnée, laissez ce champ vide.</td>
</tr>
<tr class="odd">
<td><strong>Compte collectif</strong></td>
<td>Permet de sélectionner le compte général qui sera utilisé comme compte collectif client pour les clients associés au profil de validation.</td>
</tr>
<tr class="even">
<td><strong>Compte de règlement</strong></td>
<td>Permet de sélectionner le compte général de liquidités utilisé pour les prévisions de flux de trésorerie. Ce champ s'affiche uniquement si les prévisions de flux de trésorerie sont activées.</td>
</tr>
<tr class="odd">
<td><strong>Acomptes de taxe</strong></td>
<td>Permet de sélectionner le compte pour les paiements en avance des taxes.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Remarque" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Remarque</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>La page Paramètres de la comptabilité client permet de spécifier le profil de validation à utiliser lorsqu'un paiement est marqué comme acompte.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Passif du compte de remise</strong></td>
<td>Permet de sélectionner le compte général des engagements de remise.</td>
</tr>
<tr class="odd">
<td><strong>Série de lettres de relance</strong></td>
<td>Permet de sélectionner l'identificateur de la série de lettres de relance à utiliser pour les clients auxquels le profil de validation est affecté.</td>
</tr>
<tr class="even">
<td><strong>Code intérêt</strong></td>
<td>Permet de sélectionner le code intérêt à utiliser pour le calcul des intérêts des clients auxquels le profil de validation est affecté.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Restrictions de table**

Pour les transactions dont le profil de validation est sélectionné, spécifiez si les transactions seront réglées automatiquement, si des intérêts seront calculés et si des lettres de relance seront émises. Vous pouvez également sélectionner le compte utilisé lorsque des transactions dont le profil de validation est sélectionné sont clôturées.

Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :

| Champ                 | Description                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Règlement**        | Sélectionnez cette bascule pour activer le règlement automatique des transactions dotées de ce profil de validation. Si cette bascule est désactivée, vous devez régler manuellement les transactions par l'intermédiaire de la page Régler les transactions en cours ou de la page Entrer les paiements client. |
| **Intérêts**          | Sélectionnez cette bascule si des intérêts doivent être calculés sur les soldes restants pour les comptes client qui utilisent ce profil. Si elle est désactivée, les intérêts ne seront pas calculés pour ces clients.                                           |
| **Lettre de relance** | Sélectionnez cette bascule si des lettres de relance doivent être générées pour les comptes client qui utilisent ce profil. Si elle est désactivée, les lettres de relance ne seront pas générées pour ces clients.                                                 |
| **Clôture**             | Permet de sélectionner un autre profil de validation à utiliser lors de la clôture des transactions présentant ce profil de validation. Une transaction est considérée comme clôturée si elle a été totalement réglée.                                                                           |



Pour plus d'informations, voir [Vue d'ensemble des paiements client](../cash-bank-management/tasks/customer-payment-overview.md).


