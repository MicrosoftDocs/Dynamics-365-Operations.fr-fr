---
title: Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques
description: Cette rubrique explique comment approuver des fournisseurs pour des catégories d'approvisionnement spécifiques dans Dynamics 365 Supply Chain Management.
author: RichardLuan
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 159d918a4dd3b6502bc8ab411d0353545eb4fcba
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016347"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment approuver des fournisseurs pour des catégories d'approvisionnement spécifiques dans Dynamics 365 Supply Chain Management. Quand une demande d'achat est créée, il peut y avoir une condition pour choisir un fournisseur agréé ou préféré, selon la façon dont les politiques d'achat sont définies. Cette procédure vous montre comment spécifier qu'un vendeur est agréé ou préféré pour une catégorie spécifique d'approvisionnement. Cette tâche est généralement effectuée par un professionnel de l'approvisionnement. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.

1. Dans le volet de navigation, accédez à **Modules > Approvisionnements > Fournisseurs > Tous les fournisseurs**.
2. Choisissez le fournisseur que vous voulez définir en tant que fournisseur agréé ou préféré pour une catégorie.
3. Dans le volet Actions, sélectionnez **Général**.
4. Sélectionnez **Catégories**.
5. Sélectionnez **Ajouter une catégorie**.
6. Dans le champ **Catégorie**, sélectionnez **BUREAU ET ACCESSOIRES DE BUREAU (BUREAU ET ACCESSOIRES DE BUREAU)**.
7. Dans le champ **Statut de catégorie de fournisseur**, sélectionnez **Préféré**. Il est possible de spécifier plus d'un fournisseur préféré pour une catégorie.  
8. Sélectionnez **Enregistrer**.
9. Dans le volet de navigation, accédez à **Modules > Approvisionnements > Catégories d'approvisionnement**.
10. Dans l'arborescence, sélectionnez **CATÉGORIES D'APPROVISIONNEMENT DE L'ENTREPRISE\BUREAU ET ACCESSOIRES DE BUREAU**.
11. Développez la section **Fournisseurs**. Vérifiez si le fournisseur que vous avez choisi apparaît en tant que fournisseur préféré pour la catégorie d'accessoires de bureau et de bureau. Si vous exécutez cette procédure en tant que guide de tâche, vous devrez peut-être cliquer sur le bouton **Déverrouiller** pour pouvoir faire descendre l'écran jusqu'à la liste de fournisseurs.  Il est également possible d'ajouter les fournisseurs préférés et agréés à cette page.  
12. Dans l'arborescence, développez **BUREAU ET ACCESSOIRES DE BUREAU** et sélectionnez **Ciseaux**.
13. Choisissez **Non** dans le champ **Hériter des fournisseurs de la catégorie parente :**.
14. Choisissez **Oui** dans le champ **Hériter des fournisseurs de la catégorie parente :**.

