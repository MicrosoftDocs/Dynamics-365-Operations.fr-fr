---
title: "Intégration des immobilisations"
description: "Le module Immobilisations peut être intégré avec les modules Comptabilité, Gestion des stocks, Ventes et Achats. Vous pouvez également paramétrer le module Immobilisations en vue de son intégration avec les commandes fournisseur."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 305010c41aa87222c652f98e6aa2b097606052e8
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-assets-integration"></a>Intégration des immobilisations

[!include[banner](../includes/banner.md)]


Le module Immobilisations peut être intégré avec les modules Comptabilité, Gestion des stocks, Ventes et Achats. Vous pouvez également paramétrer le module Immobilisations en vue de son intégration avec les commandes fournisseur.

<a name="general-ledger"></a>Comptabilité
--------------

Dans le module Comptabilité, la valeur de toutes les immobilisations est généralement récapitulée dans plusieurs comptes généraux nécessaires pour la génération d'états financiers. Toutefois, sur la page **Immobilisations**, vous pouvez créer de nombreux enregistrements d'immobilisation. Ces enregistrements peuvent inclure des informations telles que le prix d'acquisition, l'amortissement et l'évaluation. Chaque fois que vous validez une transaction relative à une immobilisation, les comptes principaux appropriés sont mis à jour. Les comptes principaux pour les immobilisations affichent toujours la valeur mise à jour des immobilisations.

Sur la page **Profils de validation des immobilisations**, vous définissez les comptes principaux dans lesquels les transactions de registre d'immobilisation sont validées. Vous spécifiez également les types de transactions d'immobilisation validées dans chaque compte principal. Vous pouvez créer diverses combinaisons de comptes principaux d'immobilisations, en fonction du niveau de détail que vous souhaitez pour les immobilisations dans la comptabilité. Les comptes principaux peuvent être basés sur des types de transactions, des registres et des comptes principaux.

## <a name="inventory-management"></a>Gestion des stocks
Dans le journal de stock pour des immobilisations, vous pouvez entrer l'acquisition d'immobilisations que l'entité juridique a produites ou construites pour elle-même. Vous pouvez ensuite transférer des articles en stock vers les immobilisations comme acquisition ou dans le cadre d'une acquisition. 

Vous pouvez également acquérir des immobilisations à l'aide de commandes fournisseur. Lorsque des commandes fournisseur contiennent des articles de stock désignés comme immobilisations, le paramétrage de l'option **Autoriser l'acquisition d'actifs à partir d'Achats** de la page **Paramètre des immobilisations** détermine si une acquisition est validée pour l'immobilisation lors de la validation de la facture. L'effet de l'acquisition d'immobilisations sur le stock dépend du paramétrage de l'entité juridique. 

Quand un article en stock devient une acquisition d'immobilisation, par l'intermédiaire du journal de stock, d'une commande fournisseur ou d'une proposition d'acquisition, une transaction de registre d'immobilisation est créée. Si une acquisition de registre inclut un registre des amortissements dérivé, une transaction d'acquisition du registre dérivé est également créée. 

Les règles de validation paramétrées sur la page **Validation** de la Gestion des stocks contrôle la baisse du stock qui survient lors de la validation d'une acquisition. Toutefois, la validation de factures liées à des immobilisations ne s'accompagne pas toujours d'une baisse du stock. Dans certains cas, les immobilisations peuvent être achetées pour un usage interne. Par exemple, un ordinateur portable acheté pour le département Ventes. Lors du traitement de commandes fournisseur, vous pouvez gérer des articles paramétrés pour la revente ou l'utilisation interne. 

Si vous utilisez des comptes de réception et de sortie spécifiques pour des immobilisations de groupes d'articles, le même article de stock peut servir pour les achats internes et pour le stock en vue de sa revente. 

Les immobilisations qui sont destinées à un usage interne sont définies avec un compte de type de **réception des immobilisations**. Ce type de compte est utilisé pour suivre la réception de l'immobilisation. Lorsque vous validez une facture fournisseur, utilisez le compte de réception d'immobilisation si l'une des conditions suivantes est vraie :

-   La ligne de facture contient une immobilisation existante à des fins internes.
-   La case à cocher **Nouvelle immobilisation ?** est activée pour la ligne d'accusé de réception de marchandises qui est validée.
-   La case à cocher **Créer une nouvelle immobilisation** est sélectionnée pour la ligne de facture fournisseur.

En général, ce compte est un compte de dépenses. Vous pouvez paramétrer le compte de type **réception des immobilisations** pour un groupe d'articles ou pour un article en particulier à l'aide de l'onglet **Commande fournisseur** sur les pages **Groupe d'articles** ou **Validation**.

De même, les immobilisations destinées à un usage interne peuvent être paramétrées avec un tpe de compte **Sortie d'immobilisations**. Ce type de compte est utilisé pour suivre l'émission de l'immobilisation vers le destinataire. Lorsqu'une immobilisation est acquises à l'aide d'une commande fournisseur, le compte de sortie de l'immobilisation sert de contrepartie au compte à débiter associé à l'immobilisation. La validation de l'acquisition d'immobilisation peut avoir lieu en même temps que la validation d'une commande fournisseur ou dans le journal Immobilisations, en utilisant, le cas échéant, une proposition d'acquisition. Vous pouvez paramétrer le compte de type **Sortie d'immobilisations** pour un groupe d'articles ou pour un article en particulier à l'aide de l'onglet **Stock** sur les pages **Groupe d'articles** ou **Validation**. 

Enfin, les comptes principaux utilisés pour la validation sont déterminés par les options de l'intégration comptable spécifiées pour le groupe de modèles d'article. En outre, les comptes principaux utilisés varient selon qu'une immobilisation soit affectée ou non à la ligne de commande fournisseur. Les comptes sont dérivés du profil de validation pour chaque groupe d'articles. 
**Remarque :** Si une réservation de stock est détectée lors de la validation des accusés de réception de marchandises, il ne vous est pas possible d'affecter une immobilisation ou de créer une immobilisation à partir de la ligne. 

Les comptes dans lesquels les transactions d'immobilisation sont validées varient selon deux facteurs : si les immobilisations sont achetées ou construites par l'entité juridique, et selon le type de transaction sur laquelle porte l'immobilisation. 

Le type de transaction relie le mouvement de stock au profil de validation dans Immobilisations. Comme le profil de validation dans Immobilisations définit les comptes qui seront mis à jour, la sélection d'un type de transaction d'immobilisation est indirectement aussi une sélection des comptes principaux dans lesquels la transaction est validée. Pour les immobilisations construites et achetées, le type de transaction est généralement **Acquisition** ou **Ajustement d'acquisition**.

## <a name="accounts-receivable"></a>Module Comptabilité client
L'intégration des modules Immobilisations et Ventes utilise les profils de validation paramétrés dans Immobilisations. Ces profils de validation sont activés lorsqu'une immobilisation, un registre et un type de transaction d'immobilisation sont sélectionnés pour une facture client avant que la facture client ne soit validée. Comme les immobilisations ne font pas partie de Gestion des stocks, vous devez utiliser la page **Facture financière** lorsque vous vendez une immobilisation. 

Si le registre inclut un registre des amortissements dérivés, une transaction de registre dérivé est créée lors de la validation de la facture client.

## <a name="accounts-payable"></a>Module Comptabilité fournisseur
En général, les immobilisations sont acquises auprès de fournisseurs externes. La page **Paramètres des immobilisations** permet d'indiquer si les acquisitions d'immobilisations sont toujours validées en même temps que les factures fournisseurs ou uniquement à partir d'Immobilisations. Si vous autorisez la validation des acquisitions d'immobilisations à partir d'Achats, les comptes d'immobilisations sont mis à jour lors de la validation d'une facture fournisseur pour une acquisition d'immobilisation. 

Si le système est paramétré de manière à valider une acquisition d'immobilisation lorsqu'une facture est validée, la transaction est validée en fonction des profils de validation paramétrés définis dans Immobilisations pour les divers types de transactions d'immobilisations. La validation est contrôlée par l'immobilisation, le registre et le type de transaction d'immobilisation sélectionnés sur la page **Commande fournisseur** avant la validation de la facture fournisseur. 

Si le registre inclut un registre des amortissements dérivés, une transaction de registre dérivé est créée lors de la validation de la facture fournisseur.

L'intégration de chaque ligne de commande est activée sous l'onglet **Immobilisations** de l'organisateur **Détails de ligne** sur la page **Commande fournisseur**. Vous pouvez envoyer une commande fournisseur pour une immobilisation au fournisseur. Toutefois, les immobilisations et comptes principaux sont mis à jour uniquement lorsque vous validez la facture fournisseur après la réception de l'immobilisation. Comme les commandes fournisseur ne peuvent contenir que des articles en stock, l'impact de l'acquisition d'immobilisations sur le stock dépend du paramétrage de l'entité juridique.

## <a name="project-management-and-accounting"></a>Gestion de projets et comptabilité ;
Vous pouvez associer un projet comportant une immobilisation concernée par le projet. Vous pouvez également associer chaque phase, tâche ou sous-projet à une immobilisation différente. Une immobilisation peut être associé à chaque enregistrement de projet. Vous créez l'association lors de la saisie d'un numéro d'immobilisation dans le champ **Numéro d'immobilisation** de la page **Projets**. Le projet doit être de type **Interne** ou **Projet de coût**. 

La page **Projets** permet également d'afficher des informations détaillées sur des immobilisations associées à des projets. Pour afficher l'enregistrement de l'immobilisation, cliquez sur le lien d'immobilisation dans l'organisateur **Paramétrage** pour ouvrir la page **Immobilisations**. Puis cliquez sur **Projets** &gt; **Tous les projets** pour consulter les projets associés à l'immobilisation. 

En général, vous associez les immobilisations à des projets lorsque les projets sont liés à des tâches de gestion, de maintenance ou d'amélioration de l'immobilisation. À l'issue du projet, Axapta n'effectue aucun ajustement de revalorisation pour l'immobilisation. Par conséquent, si une augmentation est obligatoire, vous devez créer l'augmentation manuellement. 

Pour supprimer l'association entre un projet et une immobilisation, désactivez le champ **Numéro d'immobilisation** sur la page **Projets**. 

Vous pouvez également identifier une immobilisation que vous créez ou fabriquez comme partie intégrante d'un projet d'estimation. À la fin d'un tel projet, vous avez la possibilité de valider automatiquement une transaction d'acquisition d'immobilisation.

Pour plus d'informations, voir [Acquérir les actifs via l'approvisionnement](acquire-assets-procurement.md)




