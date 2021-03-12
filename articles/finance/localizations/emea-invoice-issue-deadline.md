---
title: Délai d’émission de facture
description: Cet article explique comment définir les paramètres pour calculer les dates d’échéance d’émission des factures client et des factures fournisseur dans l’Union européenne (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, LedgerInvoiceIssueDueDateSetup_W
audience: Application User
ms.reviewer: kfend
ms.custom: 10923
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Iceland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 261b831806a7912b270fd3ae098e1b758ef4f521
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962689"
---
# <a name="invoice-issue-deadline"></a>Délai d’émission de facture

[!include [banner](../includes/banner.md)]

Cet article explique comment définir les paramètres pour calculer les dates d’échéance d’émission des factures client et des factures fournisseur dans l’Union européenne (UE).

La directive 45/2010 de l’Union européenne (EU) et d’autres directives demandent que les expéditions au sein de l’UE (expéditions intra-UE) doivent être facturées avant le quinzième jour du mois après que la livraison soit effectuée. En même temps, chaque pays européen peut avoir différentes limites de facturation pour les livraisons intérieures. La fonctionnalité de date d’échéance d’émission de facture permet d’aligner l’intervalle de dates au type de pays/région. Ensuite, pour toutes les expéditions vers et depuis un pays/une région d’un type particulier, la date d’échéance d’émission de la facture est calculée à l’aide des règles définies dans l’intervalle de dates spécifié. En outre, vous pouvez obtenir tous les bons de livraison portant une date d’échéance d’émission de facture spécifique, filtrer par date d’échéance d’émission de facture au cours de la facturation des ventes périodiques, et contrôler la date d’émission des factures client lors de la validation des factures. Vous pouvez paramétrer un code intervalle de dates, puis une règle de calcul pour la date d’émission des factures en affectant un code intervalle de dates à un type de pays/région. La règle de calcul est utilisée pour calculer la date d’échéance d’émission des factures pour les transactions suivantes :

-   Expéditions intra-UE
-   Expéditions locales au sein d’un état membre de l’UE

Vous pouvez également paramétrer des contrôles de date pour garantir que les factures client et les avoirs pour les transactions client sont générés dans la période spécifiée, une fois la livraison effectuée.

## <a name="prerequisites"></a>Logiciels requis
Le tableau suivant indique les paramétrages qui doivent être en place avant d’utiliser la fonctionnalité de date d’échéance d’émission de facture.

| Catégorie            | Logiciel requis                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pays/Région      | L’adresse principale de l’entité juridique doit être dans un pays membre de l’UE.                                                                                                                                                                                                                                                                                                                    |
| Tâches associées de paramétrage | Dans la page **Intervalles de dates**, paramétrez un intervalle de dates utilisé pour calculer la date d’échéance d’émission de facture. (Cliquez sur **Comptabilité** &gt; **Paramétrage de la comptabilité** &gt; **Intervalles de dates**.) Dans la page **Paramètres du commerce extérieur**, paramétrez les propriétés du commerce extérieur pour différents pays/régions. (Cliquez sur **Taxe** &gt; **Paramétrage** &gt; **Commerce extérieur** &gt; **Paramètres du commerce extérieur**.) |

## <a name="invoice-issue-due-date-calculation-rule"></a>Règle de calcul de la date d’échéance d’émission des factures
Utilisez la page **Paramétrer le calcul pour la date d’échéance d’émission des factures** pour définir une règle de calcul pour la date d’émission des factures en affectant un code intervalle de dates à un type de pays/région.

## <a name="date-control-parameters-for-customer-invoices-and-credit-notes"></a>Paramètres de contrôle de date pour les factures client et les avoirs
Vous pouvez également définir des paramètres de contrôle de date pour garantir que les factures client et les avoirs pour les transactions client sont générés dans la période spécifiée, une fois la livraison effectuée. Vous pouvez trouver ces paramètres dans la zone **Contrôle des dates de facture** de la page **Paramètres des ventes**.

## <a name="example"></a>Exemple
Pour calculer les dates d’échéance d’émission des factures pour les expéditions intra-européennes au 15ème jour du mois suivant une fois la livraison effectuée, créez un code intervalle de dates et une règle de calcul avec les paramètres suivants :

### <a name="date-interval-code"></a>Code intervalle de dates

| Champ                                                           | Valeur                           |
|-----------------------------------------------------------------|---------------------------------|
| Code intervalle de dates                                              | 15-NM                           |
| Description                                                     | Quinzième jour du mois suivant |
| Avant (Dans le groupe de champs **Date de fin**)                         | Mois                           |
| Début/fin (Dans le groupe de champs **Date de fin**)                      | Fin                             |
| +/- (Dans le groupe de champs **Date de fin**)                            | 15                              |
| Jours, mois, années ou périodes (Dans le groupe de champs **Date de fin**) | Jours                            |

### <a name="invoice-issue-due-date-calculation-rule"></a>Règle de calcul de la date d’échéance d’émission des factures

| Champ               | Valeur                                                     |
|---------------------|-----------------------------------------------------------|
| Type de pays/région | **UE**                                                    |
| Date de début          | Entrez la date à laquelle la ligne actuelle de paramétrage devient valide. |
| Code intervalle de dates  | **15-NM**                                                 |

## <a name="next-steps"></a>Étapes suivantes
Après avoir terminé de définir les paramètres pour calculer les dates d’échéance d’émission des factures, vous pouvez créer et valider les transactions suivantes pour calculer et mettre à jour automatiquement les dates d’échéance d’émission des factures :

-   **Commandes client** – Lorsque vous créez une commande client et validez un bon de livraison, la date d’échéance d’émission des factures est calculée et mise à jour sur le bon de livraison. La date d’échéance est calculée en fonction de l’intervalle de dates associé au pays ou à la région spécifié dans l’adresse de livraison de la commande client. Après avoir validé le bon de livraison, vous pouvez vérifier la date d’échéance d’émission de facture dans le champ **Date d’échéance d’émission des factures** de la page **Journal des bons de livraison**. (Cliquez sur **Ventes et marketing** &gt; **Commande client** &gt; **Expédition de commande** &gt; **Bon de livraison**.) Vous pouvez afficher tous les bons de livraison qui ne sont pas facturés, et leur date d’échéance d’émission de facture dans la page **Bons de livraison non facturés**. (Cliquez sur **Ventes et marketing** &gt; **Commande client** &gt; **Expédition de commande** &gt; **Bons de livraison non facturés**.)
-   **Commandes client** – Lorsque vous créez une commande client et validez un accusé de réception de marchandises, la date d’échéance d’émission des factures est calculée et mise à jour sur l’accusé de réception de marchandises. La date d’échéance est calculée en fonction de l’intervalle de dates associé au pays/région spécifié dans l’adresse de livraison principale du fournisseur. Après avoir validé l’accusé de réception de marchandises, vous pouvez vérifier la date d’échéance d’émission de facture dans le champ **Date d’échéance d’émission des factures** de la page **Journal d’accusé de réception de marchandises**. (Cliquez sur **Approvisionnements** &gt; **Commandes fournisseur** &gt; **Réception des produits** &gt; **Accusé de réception de marchandises**.) Vous pouvez afficher tous les accusés de réception de marchandises qui ne sont pas facturés et leur date d’échéance d’émission de facture dans la page **Accusés de réception de marchandises non facturés**. (Cliquez sur **Approvisionnements** &gt; **Commandes fournisseur** &gt; **Réception des produits** &gt; **Accusés de réception de marchandises non facturés**).

## <a name="technical-information-for-system-administrators"></a>Informations destinées aux administrateurs système
Si vous n’avez pas accès aux pages qui vous permettent d’effectuer les tâches mentionnées dans cet article, contactez votre administrateur système et fournissez les informations répertoriées dans le tableau suivant.

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
<td>Clés de configuration</td>
<td>Cliquez sur <strong>Administration du système</strong> &gt; <strong>Paramétrage</strong> &gt; <strong>Gestionnaire de licences</strong> &gt; <strong>Configuration des licences</strong>. Cliquez sur la clé de configuration <strong>Comptabilité</strong>.</td>
</tr>
<tr class="even">
<td>Rôles de sécurité et droits</td>
<td>Pour effectuer cette tâche, vous devez être membre d’un rôle de sécurité comprenant les responsabilités suivantes :
<ul>
<li><strong>CustInvoiceInvoiceAndCashProcessEnable</strong> (Activer le processus de facturation et de disponibilités)</li>
<li><strong>VendInvoiceInvoicePaymentProcessEnable</strong> (Activer le processus de facturation et de paiement)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Rôles de sécurité et privilèges</td>
<td>Pour effectuer cette tâche, vous devez être membre d’un rôle de sécurité comprenant les privilèges suivants :
<ul>
<li><strong>CustPackingSlipJournalView</strong> (Afficher les bons de livraisons liés aux ventes)</li>
<li><strong>VendPackingSlipJournalView</strong> (Afficher le journal des accusés de réception de marchandises de la commande fournisseur)</li>
<li><strong>LedgerInvoiceIssueDueDateSetupMaintain_W</strong> (Calculer les dates d’échéance d’émission des factures)</li>
</ul></td>
</tr>
</tbody>
</table>





