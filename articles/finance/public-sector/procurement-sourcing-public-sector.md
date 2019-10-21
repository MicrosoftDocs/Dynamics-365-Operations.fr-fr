---
title: Approvisionnements dans le secteur public
description: Cette vue d'ensemble présente la fonctionnalité d'approvisionnements disponible pour le secteur public. Cela inclut les codes de commande fournisseur, les types de certification des fournisseurs, la fonctionnalité de classification de contrat d'achat, et les montants de ligne de commande fournisseur.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AgreementClassification, BudgetParameters, ProcCategoryHierarchyManagement, PurchTableListPage, smmActivities, VendCertificationType, VendTableListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 19681
ms.assetid: c99b2aeb-4ac2-4abe-b8b9-786b664c103d
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9b6c619174be34d5bd4448542e33206a9f3f864
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174624"
---
# <a name="procurement-and-sourcing-in-the-public-sector"></a>Approvisionnements dans le secteur public

[!include [banner](../includes/banner.md)]

Cette vue d'ensemble présente la fonctionnalité d'approvisionnements disponible pour le secteur public. Cela inclut les codes de commande fournisseur, les types de certification des fournisseurs, la fonctionnalité de classification de contrat d'achat, et les montants de ligne de commande fournisseur.

Cet article décrit la fonctionnalité d'approvisionnements disponible pour le secteur public. 

## <a name="what-are-the-prerequisites-for-setting-up-procurement-and-sourcing-in-the-public-sector"></a>Quelles sont les conditions préalables au paramétrage des approvisionnements dans le secteur public ?
Avant de commencer à ajuster les paramètres et à entrer vos données, vous devez effectuer les opérations suivantes :

-   Paramétrage des fournisseurs
-   Paramétrer le système de numérotation pour les fournisseurs, les commandes fournisseur, etc.
-   Spécifier les types de certification des fournisseurs

Vous devez peut-être paramétrer les fonctionnalités d'approvisionnement suivantes pour les organisations du secteur public :

-    [Codes de commandes fournisseur du secteur public](purchase-order-codes-public-sector.md) Créez des codes et des messages spéciaux pour la confirmation des commandes fournisseur. Une commande fournisseur de confirmation permet de contourner le processus d'achat habituel.

> [!NOTE]
> Cela s'applique également à la comptabilité fournisseur.

-   [Comptabilité du secteur public en France](../localizations/emea-fra-public-sector-accounting.md) 

Pour les organisations françaises, des étapes supplémentaires peuvent être nécessaires pour le secteur public.

Les sections suivantes décrivent les fonctionnalités d'approvisionnements disponible pour le secteur public.

## <a name="what-are-vendor-certification-types"></a>Que sont les types de certification des fournisseurs ?
Vous pouvez créer et affecter aux organisations de fournisseurs n'importe quels types de certification que les fournisseurs détiennent. Il s'agit non seulement d'informations d'identification professionnelles, comme la licence d'un ingénieur professionnel ou la certification Microsoft SQL Server, mais aussi de l'assurance du passif, du statut minoritaire ou de la conformité avec diverses normes de sécurité relatives à l'environnement ou au consommateur. 

La page **Type de certification** de la comptabilité fournisseur vous permet de spécifier le type et la description de la certification.

## <a name="what-do-i-need-to-know-about-purchase-or-sales-agreement-classifications"></a>Que dois-je savoir sur les classifications de contrat d'achat ou de vente ?
Lorsque les utilisateurs créent un contrat d'achat ou de vente, ils doivent toujours sélectionner son type. Les contrôles supplémentaires du secteur public sont disponibles sur les pages **Classifications de contrat**. 

Pour créer et spécifier des classifications de contrat, utilisez la page **Classification de contrat d'achat** dans le module Approvisionnements ou la page **Classification de contrat de vente** dans le module Ventes et marketing. 

Prenez en compte les informations suivantes lorsque vous spécifiez les détails des classifications de contrat d'achat ou de vente.

### <a name="how-do-i-enter-information-about-subcontractors-on-purchase-agreements"></a>Comment saisir les informations sur les sous-traitants dans les contrats d'achat ?

Sélectionnez l'option **Sous-traitants**.

### <a name="how-do-i-enter-information-about-insurance-policies-and-bonds-on-purchase-agreements"></a>Comment spécifier les informations sur les polices d'assurance et les obligations dans les contrats d'achat ?

Sélectionnez l'option **Certifications**. Les informations peuvent servir à générer un état qui vous permet de contrôler la conformité des fournisseurs avec les conditions de certification. (Pour générer l'état, accéder accédez à la page **Conformité de la certification des contrats d'achat**.)

### <a name="how-do-i-enter-information-about-milestones-and-tasks-on-purchase-agreements"></a>Comment saisir les informations sur les jalons et les tâches dans les contrats d'achat ?

Sélectionnez l'option **Activités**.

### <a name="how-do-i-require-direct-invoicing-and-prevent-the-use-of-release-orders-with-purchase-agreements"></a>Comment imposer une facturation directe et empêcher l'utilisation d'ordres de lancement pour les contrats d'achat ?

Sélectionnez l'option **Exiger une facturation directe**. 

## <a name="can-i-view-purchase-order-line-amounts"></a>Puis-je afficher les montants de la ligne de commande fournisseur ?
Oui. Vous pouvez afficher les montants de ligne d'une commande fournisseur (notamment le montant commandé actuel, les montants reçus ou facturés). Vous pouvez également afficher les montants restant à facturer ou ceux des factures en attente.

### <a name="tip"></a>Conseil

Supposons que vous affichiez une ligne de commande fournisseur contenant des achats validés dans deux comptes généraux. Le premier inclut le mobilier de bureau commandé auprès d'un fournisseur. Le second inclut les fournitures de bureau. Le montant commandé est égal à la somme des montants facturés, des montants des factures en attente, et des montants restants à facturer. Le montant reçu correspond à la partie du montant commandé reçu du fournisseur.

<table style="width:100%;">

<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />

<tbody>
<tr class="odd">
<td><strong>Compte général</strong></td>
<td><strong>Commandé</strong></td>
<td><strong>Reçu</strong></td>
<td><strong>Facturé</strong></td>
<td><strong>Facture en attente</strong></td>
<td><strong>Reste de la facture</strong></td>
</tr>
<tr class="even">
<td>60010 (mobilier de bureau)</td>
<td><p>1 200,00</p></td>
<td>250,00</td>
<td>350,00</td>
<td>200,00</td>
<td><p>650,00</p></td>
</tr>
<tr class="odd">
<td>60020 (fournitures de bureau)</td>
<td><p>750,00</p></td>
<td>150,00</td>
<td>400,00</td>
<td></td>
<td><p>350,00</p></td>
</tr>
<tr class="even">
<td>Totaux</td>
<td><p>1 950,00</p></td>
<td>400,00</td>
<td>750,00</td>
<td>200,00</td>
<td><p>1 000,00</p></td>
</tr>
</tbody>
</table>



Pour plus d'informations, voir [Approvisionnements](../../supply-chain/procurement/procurement-sourcing-overview.md) et [Comptabilité fournisseur dans le secteur public](accounts-payable-public-sector.md).



