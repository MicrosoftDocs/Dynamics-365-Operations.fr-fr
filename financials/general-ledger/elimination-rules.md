---
title: "Règles d'élimination"
description: "Cette rubrique fournit des informations sur les règles d'élimination et les différentes options permettant de générer un état sur les éliminations."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 76af350f37109260a757ccc0b93908637d0579dc
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="elimination-rules"></a>Règles d'élimination

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur les règles d'élimination et les différentes options permettant de générer un état sur les éliminations.

Les transactions d'élimination sont nécessaires lorsqu'une entité juridique parente fait des affaires avec une ou plusieurs entités juridiques filiales et utilise la génération d'états financiers consolidés. Les tableaux d'analyse consolidés doivent inclure uniquement les transactions qui surviennent entre l'organisation consolidée et tout autre entité extérieure. Par conséquent, les transactions entre les entités juridiques faisant partie d'une même organisation doivent être supprimées ou éliminées de la comptabilité, afin qu'elles ne figurent pas dans les états financiers. Il existe plusieurs manières de générer un état sur les éliminations :

-   Une règle d'élimination peut être créée et traitée dans une société de consolidation ou d'élimination.
-   La génération d'états financiers peut être utilisée pour afficher les comptes et les dimensions d'élimination sur une ligne ou une colonne spécifique.
-   Une entité juridique distincte peut être utilisée pour valider les entrées de transaction manuelles pour suivre les éliminations.

Cette rubrique est consacrée aux règles d'élimination traitées dans une société de consolidation ou d'élimination. Vous pouvez paramétrer des règles d'élimination pour créer des transactions d'élimination au sein d'une entité juridique spécifiée comme entité juridique cible des éliminations. Cette entité juridique de destination est appelée entité juridique d'élimination. Les journaux d'élimination peuvent être générés au cours du processus de consolidation ou à l'aide d'une proposition de journal d'élimination. Avant de paramétrer des règles d'élimination, vous devez vous familiariser avec les termes suivants :

-   **Entité juridique source** – Entité juridique dans laquelle les montants qui sont éliminés ont été validés.
-   **Entité juridique cible** – Entité juridique au sein de laquelle les règles d'élimination sont validées.
-   **Entité juridique d'élimination** – Entité juridique spécifiée comme entité juridique cible pour les éliminations.
-   **Entité juridique consolidée** – Entité juridique créée pour faire état des résultats financiers pour un groupe d'entités juridiques. Les données financières venant des entités juridiques sont consolidées au sein de cette entité juridique, puis des états financiers sont créés à l'aide des données combinées.

Le tableau suivant indique les types de transactions qui peuvent être éliminées.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de transaction</th>
<th>Exemple :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Entrée et facturation de commandes client (traitement centralisé)</td>
<td>Vous vendez un produit à un client au nom d'une autre entité juridique de votre organisation.</td>
</tr>
<tr class="even">
<td>Entrée de commandes client (intersociétés/intrasociété) et facturation</td>
<td>Vous vendez des produits entre les entités juridiques de votre organisation.</td>
</tr>
<tr class="odd">
<td>Commandes fournisseur (traitement centralisé)</td>
<td>Vous achetez du stock, des fournitures, des services, des immobilisations et d'autres produits auprès d'un fournisseur au nom d'une autre entité juridique de votre organisation.</td>
</tr>
<tr class="even">
<td>Gestion des stocks (intersociétés/intrasociété)</td>
<td><ul>
<li>Vous transférez le stock d'une entité juridique vers les immobilisations d'une autre entité juridique de votre organisation.</li>
<li>Vous transférez le stock d'une entité juridique vers le stock d'une autre entité juridique de votre organisation.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Suivi du stock en transit</td>
<td>Vous transférez des articles entre les entrepôts de la même entité juridique, mais entre différents sites géographiques.</td>
</tr>
<tr class="even">
<td>Traitement centralisé des factures des achats</td>
<td>Vous enregistrez une facture au nom d'une autre entité juridique de votre organisation.</td>
</tr>
<tr class="odd">
<td>Traitement centralisé des paiements des achats</td>
<td>Vous payez une facture au nom d'une autre entité juridique de votre organisation.</td>
</tr>
<tr class="even">
<td>Gestion des disponibilités et trésorerie (traitement centralisé)</td>
<td><ul>
<li>Vous traitez des paiements de taxes, des remboursements de taxes, des intérêts, des prêts, des avances, des dividendes payés et des royalties ou commissions prépayées.</li>
<li>Vous réglez des frais au nom d'une autre entité juridique de votre organisation. La facture est entrée dans les registres de l'entité juridique cible, et vous devez effectuer un règlement croisé entre les entités juridiques. Par exemple, une entité juridique paie l'état de dépenses d'un employé dans une autre entité juridique. Dans ce cas, l'état de dépenses de l'employé a des dépenses liées à une autre entité juridique.</li>
<li>Vous transférez les disponibilités d'une entité juridique à un autre entité juridique de votre organisation.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ventes (traitement centralisé)</td>
<td>Vous recevez des disponibilités de la facture client d'une autre entité juridique et déposez le chèque sur le compte bancaire de cette entité juridique.</td>
</tr>
<tr class="even">
<td>Salaires (traitement centralisé, intersociétés/intrasociété)</td>
<td><ul>
<li>Vous payez la paie d'une autre entité juridique. Par exemple, une entité juridique paie sa propre paie pour ses employés, mais facture les frais engagés par un employé d'une autre entité juridique lors de ce processus de paie. Ou, un employé a travaillé à temps partiel pour l'entité juridique A et à temps partiel pour l'entité juridique B, et les avantages sont répartis sur le salaire total. Dans ces cas, le salaire de l'employé inclut le salaire des deux entités juridiques. Non seulement les salaires sont validés, mais les taxes, les avantages, les déductions et les régularisations pour les salaires sont également validés.</li>
<li>Vous transférez de la main-d'œuvre d'un département ou d'une division à l'autre.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Immobilisations (intersociétés/intrasociété)</td>
<td>Vous transférez les immobilisations vers les immobilisations ou le stock d'une autre entité juridique.</td>
</tr>
<tr class="even">
<td>Répartitions (intersociétés/intrasociété)</td>
<td>Vous traitez les répartitions d'entreprise. Les répartitions sont des activités vers les comptes répartis, quel que soit le module d'origine.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Exemple :
Votre entité juridique (entité juridique A) vend des widgets à une autre entité juridique de votre organisation (entité juridique B). L'exemple suivant montre de quelle manière éliminer les transactions qui surviennent entre les deux entités juridiques :

-   L'entité juridique A vend un widget d'une valeur de 10,00 à l'entité juridique B pour 10,00.
-   L'entité juridique A vend un widget d'une valeur de 10,00 à l'entité juridique B pour 10,00, plus 2,00 pour les coûts d'expédition réels.
-   L'entité juridique A vend un widget d'une valeur de 10,00 à l'entité juridique B pour 15,00 et reconnaît une marge pour la vente.
-   L'entité juridique A vend un widget d'une valeur de 10,00 à l'entité juridique B pour 15,00 et reconnaît la moitié de la marge pour la vente. L'entité juridique B identifie l'autre moitié de la marge sur la vente. Par conséquent, le produit est fractionné. Le produit fractionné encourage la commande auprès d'une autre entité juridique de l'organisation, plutôt qu'auprès d'une organisation externe.

Toutes ces transactions créent des transactions intersociétés validées sur des comptes vostro et nostro. De plus, ces transactions peuvent inclure des montants majorés et minorés lorsque le montant de la vente intersociétés est différent du coût des marchandises vendues.

## <a name="set-up-elimination-rules"></a>Configurer les règles d'élimination
Lors du paramétrage des règles d'élimination dans Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, il est recommandé de créer une dimension financière spécialement à des fins d'élimination. La plupart des clients la nomment « Partenaire commercial » ou un nom similaire. Si vous décidez de ne pas utiliser une dimension financière, assurez-vous d'avoir des comptes principaux qui sont spécifiques aux transactions intersociétés uniquement. 

Le paramétrage des éliminations est effectué dans la zone Paramétrage du module Consolidations. Après avoir entré une description pour la règle, vous devez sélectionner la société dans laquelle le journal d'élimination sera validé. Il doit s'agir d'une société pour laquelle l'option **Utiliser pour le processus d'élimination financière** est sélectionnée dans le paramétrage de l'entité juridique. 

Vous pouvez définir la date d'effet et d'expiration de la règle d'élimination, si nécessaire. Vous devez définir **Actif** sur **Oui** si vous souhaitez qu'elle soit disponible dans le processus de proposition d'élimination. Sélectionnez un nom de journal dont le type est **Élimination**.

Après avoir défini les paramètres de base, vous pouvez définir les règles de traitement réelles en cliquant sur **Lignes**. Il existe deux options pour les éliminations : l'élimination du montant de modification net ou la définition d'un montant fixe. 

Sélectionnez votre compte source. Vous pouvez utiliser un astérisque (\*) comme caractère générique. Par exemple, 1\* sélectionne tous les comptes qui commencent par 1 comme source de données pour la répartition. 

Après avoir sélectionné les comptes source, l'option **Spécification de compte** détermine le compte de la société de destination qui est utilisé. Sélectionnez **Source** si vous souhaitez utiliser le même compte principal défini dans le compte **Source**. Si vous sélectionnez **Défini par l'utilisateur**, vous devez spécifier un compte de destination. 

La spécification de dimension fonctionne de la même manière. Si vous sélectionnez **Source**, les mêmes dimensions de la société de destination sont utilisées pour la société source. Si vous sélectionnez **Défini par l'utilisateur**, vous devrez spécifier les dimensions de la société de destination en cliquant sur l'option de menu **Dimensions de destination**. 

Sélectionnez les dimensions source et les dimensions financières et valeurs utilisées comme source de l'élimination.

## <a name="process-elimination-transactions"></a>Traiter les transactions d'élimination
Il existe deux manières de traiter les transactions d'élimination : pendant le processus de consolidation en ligne ou en créant un journal d'élimination et en exécutant le processus de proposition d'élimination. Cette section porte sur la création du journal et l'exécution du processus d'élimination. 

Dans une société définie comme société d'élimination, sélectionnez **Journal d'élimination** dans le module Consolidations. Après avoir sélectionné le nom du journal, cliquez sur **Lignes**. Vous pouvez exécuter la proposition en sélectionnant le menu **Propositions**, puis **Proposition d'élimination**.

Sélectionnez la société qui est la source des données consolidées, puis choisissez la règle que vous souhaitez traiter. Entrez une date de début pour démarrer la recherche des montants d'élimination, et une date de fin pour terminer la recherche. Le champ **Date de validation dans la Comptabilité** est la date utilisée pour valider le journal dans la comptabilité. Après avoir cliqué sur **OK**, vous pouvez examiner les montants et valider le journal.




