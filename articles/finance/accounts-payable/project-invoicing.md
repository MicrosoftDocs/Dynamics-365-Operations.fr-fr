---
title: Facturation de projet
description: Cette rubrique fournit une vue d’ensemble des projets en régie et des projets à prix fixe. Il inclut des informations sur les propositions de facture (factures préliminaires), le contrôle de facture, la facturation en compte, la facturation fournisseur, et les avoirs.
author: TaylorVH
manager: AnnBe
ms.date: 07/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2020-07-06
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: eab7523296996709dfe7407c582e61e28b7d4f23
ms.sourcegitcommit: 27233e0fda61dac541c5210ca8d94ab4ba74966f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2020
ms.locfileid: "3651590"
---
# <a name="project-invoicing"></a>Facturation de projet

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d’ensemble des projets en régie et des projets à prix fixe. Il inclut des informations sur les propositions de facture (factures préliminaires), le contrôle de facture, la facturation en compte, la facturation fournisseur, et les avoirs.

Le type de projet détermine la procédure de facturation applicable. Seuls les deux types de projet externes (en régie et à prix fixe), sont facturables. Les projets en régie et les projets à prix fixe sont toujours liés à un contrat de projet.

-   **Projets à prix fixe** – Le montant de la facture client est basé sur des programmes de facturation. La facturation est effectuée via un paramétrage en compte, également appelé programme de facturation. Les projets à prix fixe peuvent être facturés par projet ou par contrat de projet.
-   **Projets en régie** – Le montant de la facture client est basé sur des lignes de transactions entrées pour des projets. Les transactions peuvent être facturées par projet ou par contrat de projet.

Les projets en régie et les projets à prix fixe peuvent être liés aux projets de facture de trois façons différentes :

-   **Facturation en compte** – Les projets à prix fixe et les projets en régie peuvent être facturés en compte. Deux types de paramétrages en compte sont requis, un pour chaque type de projet.
-   **Facturation dans la section périodique** – Grâce aux fonctions périodiques, des transactions peuvent être facturées sur plusieurs projets. Les fonctions périodiques offrent une vue d’ensemble des transactions à facturer.
-   **Utilisation d’avoirs dans la facturation** – Vous pouvez créer un avoir pour les projets en régie et les projets à prix fixe.

## <a name="invoice-proposals"></a>Propositions de facture
Avant de créer une facture client pour un projet, vous pouvez créer une facture préliminaire, ou proposition de facture. Dans une proposition de facture, vous pouvez sélectionner des transactions de projet à inclure dans une facture de projet. Vous pouvez ensuite réviser les détails de la facture avant de valider la facture de projet et l’envoyer au client ou à une autre source de financement.

### <a name="creating-invoice-proposals"></a>Création de propositions de facture

Vous pouvez créer des propositions de facture en les sélectionnant manuellement une transactions dans une liste de transactions disponibles pour un projet spécifié. Vous pouvez également paramétrer des règles de facturation qui spécifient quand créer automatiquement une proposition de facture. Par exemple, vous pouvez créer une règle de facturation pour créer une proposition de facture lorsque le travail d’un projet est terminé à 25 %, 50 %, 75 % et 100 %. 

Vous pouvez créer des propositions de facture pour les transactions suivantes :

-   heures, dépenses et autres transactions de projet ;
-   Les montants qui sont retenus par les clients sur les factures de projet précédentes
-   Avoirs
-   Les montants qui vous ont été payés par un client avant le démarrage du projet

> [!NOTE]
> La fonctionnalité **Activer le tri par ressource lors de la création de proposition de facture de projet** permet au comptable du projet de trier les transactions du projet disponibles pour la facturation par ressource lors de la création d’une proposition de facture de projet. La grille affichant les transactions de projet disponibles aura des champs séparés pour **ID de la ressource** et **Ressource**. Ces champs vous permettent de filtrer et de trier le nom de la ressource. Par défaut, cette fonctionnalité est désactivée. Elle peut être activée à l’aide de la page **Gestion des fonctionnalités** (**Espaces de travail > Gestion des fonctionnalités**). Contactez votre administrateur système pour obtenir de l’assistance pour activer cette fonctionnalité.

Vous pouvez créer des transactions de frais dans une proposition de facture. Vous pouvez également modifier le prix de vente sur les transactions horaires, de dépense, d’article, et de frais. Lorsque vous validez une proposition de facture, les prix et les transactions mis à jour sont ajoutés aux états de projet et à l’historique des transactions. 

Pour créer plusieurs factures client pour un projet, vous devez créer une proposition de facture pour chaque facture. Par exemple, vous pouvez créer des factures en fonction du type de transaction. Pour spécifier des heures sur une facture client et des articles sur une autre facture, vous devez créer des propositions de facture distinctes pour les transactions horaires et pour les transactions de frais. 

Si un projet a plusieurs sources de financement, vous pouvez créer une proposition de facture distincte pour chaque source de financement. Sur la page **Répartitions des règles de financement**, vous pouvez définir le pourcentage du montant de la transaction à attribuer à chaque source de financement, et la source permettant de valider les différences d’arrondi.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Création de factures client à partir des propositions de facture

Une fois une proposition de facture créée et validée, une facture client est créée automatiquement pour les transactions incluses dans la proposition de facture. 

Avant de valider une proposition de facture, vous pouvez lui ajouter ou en supprimer des transactions. Par exemple, vous pouvez supprimer les transactions de dépense validées dans un projet mais qui ne sont pas facturables au client. 

Si votre organisation exige que les propositions de facture soient révisées avant leur validation, vous pouvez devoir l’approuver par l’intermédiaire du workflow « Examiner les propositions de facture du projet » avant de la valider.

### <a name="view-grant-information-on-project-invoice-list-pages"></a>Afficher les informations de subvention sur les pages de liste de factures de projet

Les utilisateurs du secteur public peuvent ajouter **ID de subvention** et **Nom de la subvention** à aux pages de liste **Propositions de facture de projet** et **Factures de projet**. Ces colonnes sont activées à l’aide de la fonctionnalité **Ajouter des informations de subvention aux pages de liste de factures de projet**. Cette fonctionnalité est désactivée par défaut et peut être activée dans **Espaces de travail > Gestion des fonctionnalités**. Contactez votre administrateur système pour obtenir de l’assistance pour activer cette fonctionnalité.

## <a name="on-account-invoicing"></a>Facturation en compte
Le montant entré pour un projet dans une facture en compte est basé sur l’échéance, le pourcentage d’achèvement, et sur d’autres conditions de facturation spécifiées dans le contrat de projet associé. Le montant n’est pas calculé en fonction des heures, des articles, des dépenses ou des frais validés dans le projet. 

Vous devez créer une transaction en compte pour un projet en régie ou un projet à prix fixe avant de pouvoir ajouter cette transaction en compte à une facture de projet. Dans la transaction en compte, entrez le montant à facturer à un client. Pour créer une facture de projet pour le montant, créez une facture préliminaire (proposition de facture). Dans la proposition de facture, sélectionnez la transaction en compte. Vous pouvez réviser les informations en compte dans la proposition de facture avant de créer une facture de projet pour celle-ci. 

### <a name="fixed-price-projects"></a>Projets à prix fixe
Pour les projets à prix fixe, les transactions en compte sont basées sur un jalon convenu, l’unité de livraison, ou l’accord de facturation par tranche spécifié dans un contrat de projet. Une ligne est créée pour chaque paiement qui doit être reçu du client du projet. Aucune déduction n’est nécessaire.

### <a name="time-and-material-projects"></a>Projets en régie

Pour les projets en régie, vous pouvez facturer un client ou une autre source de financement pour un montant d’acompte à l’aide d’une proposition de facture en compte. Entrez les transactions en compte sur une seule ligne. Vous pouvez; si vous le souhaitez, entrer des lignes supplémentaires comme déductions pour compenser les acomptes déjà versés par le client. Pour créer des lignes de déduction, saisissez un signe moins devant le montant.

## <a name="invoice-control"></a>Contrôle de facture
Vous pouvez utiliser le contrôle de facture pour effectuer le suivi des transactions facturées et non facturées, ainsi que pour analyser ces transactions par rapport aux devis pour un affichage de vos projets de bout en bout, du stade de devis à la fin. Vous pouvez voir quelles transactions ont été facturées pour un projet spécifique et quelles lignes ont été facturées. Vous pouvez également consulter des transactions individuelles, afin de pour pouvoir les ajuster après leur validation.

## <a name="invoicing-fixed-price-projects"></a>Facturation des projets à prix fixe
Pour facturer un projet à prix fixe, vous devez définir un programme de facturation et de exécuter la procédure de facturation.

### <a name="billing-schedule"></a>Programme de facturation

Vous pouvez facturer des projets à prix fixe selon un programme de facturation. Le programme de facturation est défini à l’aide d’un ou plusieurs jalons pour le projet. Pour chaque jalon, vous pouvez définir une date, une devise de vente, un prix de vente, et une activité spécifiques. 

Par exemple, vous pouvez paramétrer le programme de facturation suivant :

-   20 % à la signature du contrat de projet
-   30 % à la première livraison
-   15 % à la deuxième livraison
-   35 % à la livraison finale

### <a name="invoicing-procedure"></a>Procédure de facturation

Lorsque les paiements échelonnés sont prêts à être facturés, vous utilisez la procédure de facturation des montants en compte.

## <a name="vendor-invoicing"></a>Facturation fournisseur
Lorsque vous commandez un article auprès d’un fournisseur et affectez l’article à un projet, la propriété de ligne que vous sélectionnez pour la ligne de commande fournisseur de cet article détermine si l’article acheté est facturé à un client ou non. Si vous paramétrez des propriétés de ligne par défaut, elles sont affichées pour l’article sur la ligne de commande fournisseur (**Détails de ligne > Projet > Propriété de ligne**). Il existe deux manières de modifier la propriété de ligne :

-   Facturez le client du projet pour l’article. Pour cela, définissez la propriété de ligne pour l’article sur une valeur facturable sur la commande fournisseur, puis facturez le client par l’intermédiaire de la méthode de facturation du projet correcte.
-   Ne facturez pas le client du projet pour l’article. Pour cela, ne sélectionnez pas la propriété de ligne **Payant** sur la ligne de commande d’achat de l’article. Vous pouvez alors facturer la commande fournisseur et aucune action supplémentaire n’est requise.

> [!NOTE] 
> Les lignes de rétention des versions ne sont pas facturables par défaut. Cela signifie que la possibilité de créer une proposition de facture pour la rétention validée n’est pas activée.

## <a name="credit-notes"></a>Avoirs
Lorsque le montant d’une facture client est négatif, celle-ci est classée comme avoir Lorsque le document est imprimé, il est doté du titre « Avoir ». 

Lorsque vous créez un avoir pour créditer un montant précédemment facturé, vous devez commencer par sélectionner le montant facturé pour l’établissement du crédit. Créez ensuite un avoir en suivant la procédure de création de facture client ordinaire. Sélectionnez les transactions précédemment validées dans une facture client, puis créez et validez une proposition d’avoir. 

Le même document peut inclure des transactions sélectionnées pour l’établissement de crédit, des transactions créditrices et des transactions qui ont été validées. Le document est classé en tant que facture ou avoir, selon que le montant total soit positif ou négatif. 

Pour créditer un montant facturé, vous commencez par sélectionner le montant facturé à créditer, puis vous créez un avoir. Vous créez un avoir en suivant la même procédure de création que vous utiliseriez pour générer une facture client. 

Vous pouvez créer une facture dont le montant est négatif ; cette facture est alors classée comme un avoir. Pour créer et imprimer un avoir, vous devez sélectionner les transactions précédemment validées pour une facture client, puis les modifier. À moins que l’adresse principale de l’entité juridique soit située en Allemagne, le titre de la facture est « Facture corrective ».



