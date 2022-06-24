---
title: Profils de validation client
description: Cet article décrit les profils de validation client qui contrôlent la validation des transactions client dans la comptabilité.
author: JodiChristiansen
ms.date: 12/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0563040590eefab57706b183281c47a82e46076
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891693"
---
# <a name="customer-posting-profiles"></a>Profils de validation client

[!include [banner](../includes/banner.md)]

Cet article décrit les profils de validation client qui contrôlent la validation des transactions client dans la comptabilité.

## <a name="customer-posting-profiles"></a>Profils de validation client

Les profils de validation client vous permettent d’affecter des comptes généraux et des paramètres de document à tous les clients, à un groupe de clients ou à un client unique. Ces paramètres sont utilisés lorsque vous créez des factures des commandes client, des factures financières, des factures de projet, des feuilles paiement, des paiements en espèces, des lettres de relance et des notes d’intérêt. 

Le profil de validation par défaut est défini dans l’onglet **Comptabilité et taxe** sur la page de **paramètres de la Comptabilité fournisseur**. Il est alors automatiquement inclus dans l’en-tête des nouveaux documents. Vous pouvez le modifier ici si un profil de validation différent est requis. 

Les organisations qui acceptent les acomptes des clients configurent souvent un deuxième profil de validation pour les acomptes et le lient dans les paramètres en tant que profil de validation par défaut pour les acomptes. Pour plus d’informations, voir [Acomptes client](customer-prepayments.md).

Vous pouvez également associer des définitions de validation aux types de validation de transaction sur la page **Définitions de validation de transaction**. Les définitions de validation sont utilisées à la place des profils de validation pour contrôler la validation des transactions client dans la comptabilité. Pour plus d’informations, voir [Définitions de validation](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Création d’un profil de validation
Permet de spécifier les comptes généraux utilisés dans la validation des transactions dont le profil de validation est sélectionné. Permet de sélectionner un code compte et, si possible, un numéro de compte ou de groupe pour le profil de validation sélectionné. Lors de la validation, le profil de validation qui convient le mieux à chaque transaction est localisé en recherchant la combinaison code compte, numéro de compte ou groupe et numéro la plus spécifique selon la priorité suivante :

| Valeur du champ Code de compte | Valeur du champ Numéro de compte/groupe                | Priorité de recherche |
|--------------------------|-------------------------------------------------|-----------------|
| Table                    | Compte client spécifique                       | 1               |
| Groupe                    | Groupe de clients affecté au client | 2               |
| Tout                      | Blanc                                           | 3               |

Si vous souhaitez que toutes les transactions client aient le même profil de validation, paramétrez un seul profil de validation, où **Tous** est saisi dans le champ **Code de compte**. Spécifiez les valeurs suivantes pour paramétrer votre profil de validation.

<table>
<thead>
<tr>
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Profil de validation</td>
<td>Permet d’entrer un code pour le profil de validation. Par exemple, vous pouvez créer deux profils de validation afin d’obtenir un compte pour les soldes client dans la devise nationale et un autre dans une devise étrangère. Vous pouvez appeler un compte National et l’autre Étranger.</td>
</tr>
<tr>
<td>Description</td>
<td>Permet d’entrer la description du profil de validation. Cela est uniquement utilisé pour mieux identifier le profil de validation lorsque vous l’affichez sur cette page.</td>
</tr>
<tr>
<td>Code de compte</td>
<td>Permet de spécifier si le profil de validation s’applique à un seul client, à un groupe de clients ou à tous les clients :
<ul>
<li><b>Table</b> – Le profil de validation s’applique à un seul client. Sélectionnez le compte client dans le champ <b>Numéro de compte/groupe</b>.</li>
<li><b>Group</b> – Le profil de validation s’applique à un groupe de clients. Sélectionnez le groupe de clients dans le champ <b>Numéro de compte/groupe</b>.</li>
<li><b>Tous</b> – Le profil de validation s’applique à tous les clients. Laissez vide le champ <b>Numéro de compte/groupe</b>.</li>
</ul>
</td>
</tr>
<tr>
<td>Numéro de compte/groupe</td>
<td>Si l’option <b>Table</b> est sélectionnée dans le champ <b>Code de compte</b>, sélectionnez le numéro de compte du client associé au profil de validation. Si l’option <b>Groupe</b> est sélectionnée, sélectionnez le groupe de clients. Si l’option <b>Tous</b> est sélectionnée, laissez ce champ vide.</td>
</tr>
<tr>
<td>Compte collectif</td>
<td>Permet de sélectionner le compte principal qui sera utilisé comme compte de transactions Comptabilité client pour les clients associés au profil de validation. Ce compte est le compte du type de validation <b>Solde client</b>.</td>
</tr>
<tr>
<td>Compte de liquidités pour les paiements</td>
<td>Permet de sélectionner le compte général de liquidités utilisé pour les prévisions de flux de trésorerie. Ce champ s’affiche uniquement si les prévisions de flux de trésorerie sont activées.</td>
</tr>
<tr>
<td>Acomptes de taxe</td>
<td><p>Permet de sélectionner le compte pour les paiements en avance des taxes.</p>
<p><strong>Remarque :</strong> Utilisez la page <b>Paramètres de la comptabilité client</b> permet de spécifier le profil de validation utilisé lorsqu’un paiement est marqué comme acompte.</p>
</td>
</tr>
<tr>
<td>Compte d’engagements de remise</td>
<td>Permet de sélectionner le compte général des engagements de remise.</td>
</tr>
<tr>
<td>Série de lettres de relance</td>
<td>Permet de sélectionner l’identificateur de la série de lettres de relance à utiliser pour les clients auxquels le profil de validation est affecté.</td>
</tr>
<tr>
<td>Code intérêt</td>
<td>Permet de sélectionner le code intérêt à utiliser pour le calcul des intérêts des clients auxquels le profil de validation est affecté.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>Exemples de validation

Le tableau suivant montre des exemples de types de comptabilisation par défaut avec des exemples de comptes principaux et des descriptions. La colonne **Débit/Crédit** indique si la transaction est généralement débitée ou créditée ou, dans certains cas, peut être enregistrée. La colonne **Compte de compensation** indique que le type de comptabilisation est un compte de compensation. Cela signifie que le montant enregistré sur ce compte est automatiquement annulé lorsqu’une transaction ultérieure est enregistrée. 

| Type de validation | Exemple de compte principal | Exemple de nom de compte principal | Type de compte | Débit/crédit | Compte de compensation | Description |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Client – Solde | 130100 | Transaction de Comptabilité client | Actif | Les deux | N° | Spécifiez le compte dans le champ **Compte collectif**.|
| Aucune | 110110 | Compte bancaire | Actif | Les deux | N° | Spécifiez le compte principal dans le champ **Compte de liquidité pour les paiements**. Ce compte n’est pas utilisé pour la validation. Il est utilisé uniquement pour la prévision des flux de trésorerie. |
| Acomptes de taxe | 202900 | Compensation de taxe | Passif | Les deux | Oui | Permet de sélectionner le compte pour les paiements en avance des taxes. |
| Compte d’engagements de remise | 250600 | Revenus différés et remises | Passif | Les deux | Oui | Permet de sélectionner le compte général des engagements de remises.|     

### <a name="table-restrictions"></a>Restrictions de table

Pour les transactions dont le profil de validation est sélectionné, spécifiez si les transactions seront réglées automatiquement, si des intérêts seront calculés et si des lettres de relance seront émises. Vous pouvez également sélectionner le compte utilisé lorsque des transactions dont le profil de validation est sélectionné sont clôturées.

Spécifiez les valeurs suivantes pour paramétrer votre profil de validation :

| Champ                 | Description                                           |
|-----------------------|-------------------------------------------------------|
| Lettrage        | Sélectionnez cette bascule pour activer le règlement automatique des transactions dotées de ce profil de validation. Si cette bascule est désactivée, vous devez régler manuellement les transactions par l’intermédiaire de la page **Régler les transactions en cours** ou de la page **Entrer les paiements client**. |
| Intérêts          | Sélectionnez cette bascule si des intérêts doivent être calculés sur les soldes restants pour les comptes client qui utilisent ce profil. Si elle est désactivée, les intérêts ne seront pas calculés pour ces clients.                                           |
| Lettre de relance | Sélectionnez cette bascule si des lettres de relance doivent être générées pour les comptes client qui utilisent ce profil. Si elle est désactivée, les lettres de relance ne seront pas générées pour ces clients.                                                 |
| Fermer             | Permet de sélectionner un autre profil de validation à utiliser lors de la clôture des transactions présentant ce profil de validation. Une transaction est considérée comme clôturée si elle a été totalement réglée.             |



Pour plus d’informations, voir [Vue d’ensemble des paiements client](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
