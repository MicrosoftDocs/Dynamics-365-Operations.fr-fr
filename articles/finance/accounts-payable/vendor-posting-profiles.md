---
title: Profils de validation fournisseur
description: Les profils de validation fournisseur contrôlent la validation des transactions fournisseur pour la comptabilité.
author: abruer
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022e7d979ca7572bb824bc5248fec8c0b3c283d0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248157"
---
# <a name="vendor-posting-profiles"></a>Profils de validation fournisseur

[!include [banner](../includes/banner.md)]

Les profils de validation fournisseur contrôlent la validation des transactions fournisseur pour la comptabilité.

<a name="vendor-posting-profiles"></a>Profils de validation fournisseur
-----------------------

Les profils de validation fournisseur permettent d’affecter des comptes généraux et des paramètres de document à tous les fournisseurs, à un groupe de fournisseurs ou à un fournisseur unique. Ces paramètres sont utilisés lorsque vous créez des commandes fournisseur, des factures fournisseur et des paiements en espèces. Pour certaines transactions, vous pouvez sélectionner un profil de validation différent qui prime sur les profils de validation paramétrés pour les transactions dans cette page. Le profil de validation par défaut est défini dans l’organisateur **Comptabilité et Taxe** dans la page des **Paramètres de la Comptabilité fournisseur**. Le profil de validation par défaut est alors automatiquement inclus dans l’en-tête des nouveaux documents dans lesquels vous pouvez le modifier en un profil de validation différent, si nécessaire.

Vous pouvez également associer des définitions de validation aux types de validation de transaction sur la page **Définitions de validation de transaction**. Les définitions de validation contrôlent la validation des transactions fournisseur dans la comptabilité à la place des profils de validation.

## <a name="creating-a-posting-profile"></a>Création d’un profil de validation
### <a name="setup"></a>**Paramétrage**

Permet de spécifier les comptes généraux utilisés dans la validation des transactions dont le profil de validation est sélectionné. Permet de sélectionner un code compte et, si possible, un numéro de compte ou de groupe pour le profil de validation sélectionné. Lors de la validation, le profil de validation qui convient le mieux à chaque transaction est localisé en recherchant la combinaison code compte, numéro de compte ou groupe et numéro la plus spécifique selon la priorité suivante.

| Valeur du champ **Code de compte** | Valeur du champ **Numéro de compte/groupe**        | Priorité de recherche |
|------------------------------|---------------------------------------------|-----------------|
| **Enregistrement**                    | Compte fournisseur spécifique                     | 1               |
| **Regrouper**                    | Groupe de fournisseurs assigné au fournisseur | 2               |
| **Tous**                      | Blanc                                       | 3               |

Si vous souhaitez que toutes les transactions fournisseur aient le même profil de validation, paramétrez un seul profil de validation à l’aide de la valeur **Tous** du champ **Code de compte**. Spécifiez les valeurs suivantes pour paramétrer votre profil de validation.

<table>
<thead>
<tr class="header">
<th>Champ</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Profil de validation</strong></td>
<td>Permet d’entrer un code pour le profil de validation. Par exemple, vous pouvez créer deux profils de validation afin d’obtenir un compte pour les soldes fournisseur dans la devise nationale et un autre dans une devise étrangère. Vous pouvez appeler un compte National et l’autre Étranger.</td>
</tr>
<tr class="even">
<td><strong>Description</strong></td>
<td>Permet d’entrer la description du profil de validation.</td>
</tr>
<tr class="odd">
<td><strong>Code de compte</strong></td>
<td>Permet de spécifier si le profil de validation s’applique à un fournisseur spécifique, à un groupe de fournisseurs ou à tous les fournisseurs :
<ul>
<li><strong>Table</strong> – Le profil de validation s’applique à un seul fournisseur. Sélectionnez le compte fournisseur dans le champ <strong>Numéro de compte/groupe</strong>.</li>
<li><strong>Groupe</strong> – Le profil de validation s’applique à un groupe de fournisseurs. Sélectionnez le groupe de fournisseurs dans le champ <strong>Numéro de compte/groupe</strong>.</li>
<li><strong>Tous</strong> – Le profil de validation s’applique à tous les fournisseurs. Laissez vide le champ <strong>Numéro de compte/groupe</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Numéro de compte/groupe</strong></td>
<td>Si <strong>Table</strong> est sélectionné dans le champ <strong>Code de compte</strong>, sélectionnez le numéro de compte du fournisseur associé au profil de validation. Si <strong>Groupe</strong> est sélectionné, sélectionnez un groupe de fournisseurs. Si l’option <strong>Tous</strong> est sélectionnée, laissez ce champ vide.</td>
</tr>
<tr class="odd">
<td><strong>Compte collectif</strong></td>
<td>Permet de sélectionner le compte général qui sera utilisé comme compte collectif pour les fournisseurs auxquels se rapporte le profil de validation. Le paramètre <strong>Ne pas autoriser la saisie manuelle</strong> pour ce compte principal est marqué. Si vous supprimez ensuite ce compte du profil de validation, validez le paramètre <strong>Ne pas autoriser la saisie manuelle</strong> sur la page <strong>Comptes principaux</strong>. 
<p><strong>Remarque :</strong> Si l’option <strong>Utiliser les définitions de validation</strong> est activée dans la page <strong>Paramètres de comptabilité</strong>, la définition de validation de transaction pour les factures fournisseur est utilisée à la place du compte collectif.</p>
</td>
</tr>
<tr class="even">
<td><strong>Compte de règlement</strong></td>
<td>Permet de sélectionner le compte général de liquidités utilisé pour les prévisions de flux de trésorerie. Ce champ n’est disponible que lorsque la prévision du flux de trésorerie est activée.</td>
</tr>
<tr class="odd">
<td><strong>Acomptes de taxe</strong></td>
<td>Permet de sélectionner le compte pour les paiements de taxe reçus en avance.
<p><strong>Remarque :</strong> Le profil de validation utilisé lorsque le paiement est marqué comme acompte est sélectionné dans le champ <strong>Profil de validation</strong> avec le champ <strong>N° document du journal des acomptes</strong> dans la zone <strong>Comptabilité et Taxe</strong> de la page <strong>Paramètres de la comptabilité fournisseur</strong>.</p>
</td>
</tr>
<tr class="even">
<td><strong>Arrivée</strong></td>
<td>Permet de sélectionner le compte général sur lequel les informations relatives aux factures fournisseur non approuvées sont validées. Les informations sont entrées dans le journal du registre des factures. Par exemple, un utilisateur entre des informations très élémentaires sur des factures fournisseur lors de leur réception dans le registre des factures. Lors de la validation du registre des factures, les transactions sont validées sur le compte entré ici et dans le champ <strong>Compte de contrepartie</strong>. Lors de l’approbation des factures, la dette est transférée du compte Arrivée vers le compte collectif fournisseur.</td>
</tr>
<tr class="odd">
<td><strong>Compte de contrepartie</strong></td>
<td>Permet de sélectionner le compte général utilisé pour compenser les factures fournisseur non approuvées qui sont mises à jour à l’aide du registre des factures. Le compte de contrepartie agit comme le compte de contrepartie pour les transactions qui sont validées sur les comptes d’arrivée. Par conséquent, le compte contient les achats fournisseur qui n’ont pas encore été approuvés.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Restrictions de table**

Pour les transactions dont le profil de validation est sélectionné, spécifiez si les transactions seront réglées automatiquement, si des intérêts seront calculés et si des lettres de relance seront émises. Vous pouvez également sélectionner le compte utilisé lorsque des transactions dont le profil de validation est sélectionné sont clôturées.

Spécifier les valeurs suivantes pour paramétrer votre profil de validation

| Champ          | Description                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Lettrage** | Sélectionnez cette option pour activer le règlement automatique des transactions bénéficiant de ce profil de validation. Si cette option est désactivée, vous devez régler manuellement les transactions à l’aide de la page **Régler les transactions en cours**. |
| **Annuler**     | Sélectionnez cette option pour pouvoir annuler les transactions associées à ce profil de validation.                                                                                                               |
| **Clôture**      | Permet de sélectionner un autre profil de validation à utiliser lors de la clôture des transactions présentant ce profil de validation. Une transaction est considérée comme clôturée si elle a été totalement réglée.                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]