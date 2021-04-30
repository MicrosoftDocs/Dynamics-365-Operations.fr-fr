---
title: Provisionnement d’abonnements
description: Les services récurrents permettent de provisionner manuellement le produit dans les périodes suivant la date à laquelle vous avez facturé une transaction de frais.
author: ShylaThompson
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a2b581c8ae52f4c379e8e511dc898a8d106d149
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908058"
---
# <a name="accruing-subscriptions"></a>Provisionnement d’abonnements 

[!include [banner](../includes/banner.md)]


Les services récurrents permettent de provisionner manuellement le produit dans les périodes suivant la date à laquelle vous avez facturé une transaction de frais.

Des périodes de régularisation sont créées pour la période de facturation paramétrée pour les frais d’abonnement. Elles sont basées sur le code période de l’abonnement.

Vous pouvez provisionner et contrepasser le produit à recevoir.

## <a name="reverse-accruals-of-credit-amounts"></a>Contrepassation des régularisations des montants créditeurs

Si vous créditez des montants d’abonnement facturés, vous pouvez utiliser deux méthodes pour contrepasser les montants de régularisation :

  - Vous pouvez contrepasser chaque transaction de produit à recevoir individuellement avant de créer la proposition d’avoir pour la transaction. Il s’agit de la méthode manuelle. (manuel)

  - Vous pouvez contrepasser automatiquement les montants de régularisation à la date de validation de l’avoir ou à la date de validation d’origine de la régularisation.

Pour plus d’informations, voir [Paramètres d’abonnement (écran)](/dynamicsax-2012//subscription-parameters-form).

## <a name="setup-requirements"></a>Paramétrer des besoins

Pour provisionner le produit, vérifiez que les conditions suivantes relatives aux données sont remplies :

## <a name="account-setup"></a>Paramétrage des comptes

Les comptes **Travaux en cours - abonnement** et **Produit à recevoir - abonnement** doivent être paramétrés dans le module **Projet**.

Lorsque vous validez des produits à recevoir, le compte **Travaux en cours - abonnement** est débité du montant de régularisation et le compte **Produit à recevoir - abonnement** est crédité du montant de régularisation.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Paramétrage de comptes pour la régularisation de produits d’abonnement

1.  Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Validation** \> **Paramétrage de la validation dans la comptabilité**.

2.  Cliquez sur l’onglet **Comptes de produit** et sélectionnez **Travaux en cours - abonnement** ou **Produit à recevoir - abonnement** pour paramétrer les comptes.

## <a name="subscription-group-setup"></a>Paramétrage de groupes d’abonnements

La case à cocher **Provisionner le produit** doit être activée pour provisionner le produit pour les abonnements. Cette case est située dans l’écran **Groupes d’abonnements** pour le groupe associé à cet abonnement. Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d’abonnements**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Activation du provisionnement du produit dans un groupe d’abonnements

1.  Cliquez sur **Gestion des services** \> **Paramétrage** \> **Services récurrents** \> **Groupes d’abonnements**.

## <a name="periods"></a>Périodes

Vous devez paramétrer un code période de facturation. Vous devez également paramétrer une période de régularisation, sauf si vous souhaitez provisionner le produit dans les intervalles de temps utilisés dans le cadre de la facturation.

Le tableau suivant offre un aperçu des types de périodes de régularisation que vous pouvez paramétrer pour chaque période de facturation :

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Période de facturation</p></th>
<th><p>Période de régularisation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Années</strong></p></td>
<td><ul>
<li><p><strong>Années</strong></p></li>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mois</strong></p></li>
<li><p><strong>Jour</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Trimestre</strong></p></td>
<td><ul>
<li><p><strong>Trimestre</strong></p></li>
<li><p><strong>Mois</strong></p></li>
<li><p><strong>Jour</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Mois</strong></p></td>
<td><ul>
<li><p><strong>Mois</strong></p></li>
<li><p><strong>Jour</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Semaine</strong></p></td>
<td><ul>
<li><p><strong>Jour</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Jour</strong></p></td>
<td><ul>
<li><p><strong>Jour</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

Le paramétrage de la période de facturation est obligatoire dans le cadre du paramétrage global du groupe d’abonnements. Vous pouvez également décider de paramétrer une période de régularisation pour le groupe d’abonnements. Si vous paramétrez une période de régularisation pour le groupe d’abonnements, cette période est suggérée dans le champ **Code période**. Ce champ est disponible dans l’écran **Provisionner le produit d’abonnement**, lorsque vous provisionnez le produit d’abonnement. Cependant, la période de régularisation est une information facultative pour le groupe d’abonnements.


> [!NOTE]
> <P>Utilisez le chemin suivant pour ouvrir l’écran <STRONG>Provisionner le produit d’abonnement</STRONG>. Cliquez sur <STRONG>Gestion des services</STRONG> &gt; <STRONG>Périodique</STRONG> &gt; <STRONG>Services récurrents</STRONG> &gt; <STRONG>Provisionner le produit d’abonnement</STRONG>.</P>


## <a name="transactions"></a>Transactions

Vous pouvez contrôler le nombre d’écritures comptables créées lorsque vous validez le produit à recevoir. Dans le cadre des abonnements, définissez si les écritures comptables doivent être créées en tant que total ou par ligne.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>Spécifiez le niveau de détail de la validation à afficher pour les transactions à recevoir.

1.  Cliquez sur **Gestion et comptabilité des projets** \> **Paramétrage** \> **Paramètres de gestion et comptabilité des projets**.

2.  Sous l’onglet **Financier**, dans le champ **Facture**, sélectionnez **Total** ou **Ligne**.


## <a name="see-also"></a>Voir également :

[Provisionner l’abonnement](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]