---
title: Rapprochement financier dans les magasins de détail
description: Cet article décrit le rapprochement financier dans les magasins de vente au détail du PDV pour Microsoft Dynamics 365 Commerce.
author: anpurush
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 19c0f6edd7756a611a234a162418ef5826bd5cc2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860242"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Rapprochement financier dans les magasins de détail

[!include [banner](includes/banner.md)]

Dans Microsoft Dynamics 365 Commerce version 10.0.10 et les versions antérieures, la fonctionnalité que le client de point de vente (PDV) fournit pour les processus de clôture de caisse dans les magasins de vente au détail permet aux commis de magasin et aux directeurs de magasin d’effectuer les opérations de clôture de caisse. Par exemple, ils peuvent procéder aux comptages de caisse, clôturer des équipes de travail en aveugle, rapprocher les transactions des équipes de travail et clôturer des équipes de travail. Cependant, il n’existe aucune fonctionnalité dans le PDV permettant de finaliser les informations financières des équipes de travail, afin qu’elles puissent être utilisées pour valider les états financiers dans Commerce Headquarters. Généralement, les directeurs de magasin sont chargés d’exécuter cette tâche. Avant qu’ils puissent valider une équipe de travail, ils doivent vérifier les informations, apporter les corrections nécessaires et finaliser les totaux pour cette équipe de travail. Les totaux finalisés doivent ensuite être validés dans les modules financiers de Commerce Headquarters.

En outre, dans Commerce version 10.0.10 et les versions antérieures, les directeurs de magasin peuvent réviser les lignes de relevé et apporter les ajustements nécessaires dans Commerce Headquarters. Cependant, la fonctionnalité est limitée et les directeurs de magasin ont rarement accès au client Commerce Headquarters. En outre, la révision et l’ajustement des tableaux d’analyse de la vente au détail ne peuvent être effectués que lorsque les relevés sont créés dans Commerce Headquarters. Cependant, ce processus est généralement un processus nocturne. Par conséquent, les directeurs de magasin doivent attendre la validation des équipes de travail lorsque les tableaux d’analyse de la vente de détail sont créés dans Commerce Headquarters.

Dans Commerce version 10.0.11 et les versions ultérieures, les directeurs de magasin peuvent réviser, ajuster et finaliser leurs équipes de travail dans le client PDV proprement dit. Ces données sont ensuite utilisées pour créer et valider les tableaux d’analyse de la vente au détail dans Commerce Headquarters.

> [!NOTE]
> La fonctionnalité associée au rapprochement financier dans les magasins de vente au détail ne fonctionne que si la création de commandes basée sur un flux en continu est activée. Pour plus d’informations, voir [Création de commandes basée sur un flux en continu pour les transactions du magasin de vente au détail](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Configurer le rapprochement financier

Suivez les étapes ci-après pour utiliser la fonctionnalité de rapprochement financier.

1. Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Relevés de vente au détail - Flux en continu**.
1. Dans le profil de la fonctionnalité PDV pour le magasin approprié, définissez l’option **Activer le rapprochement financier dans le magasin** sur **Oui**.

## <a name="more-information-about-financial-reconciliation"></a>Informations supplémentaires sur le rapprochement financier

Lorsque la fonctionnalité de rapprochement financier est activée, certains des paramètres définis dans l’organisateur **Relevé/clôture** de la page **Magasins de vente au détail** de Commerce Headquarters sont synchronisés avec la base de données du canal. Le même ensemble de critères de calcul et de seuils de montant utilisé pour les relevés de vente au détail est appliqué.

Lorsque l’opération **Clôturer l’équipe de travail** est appelée, le système valide que les montants calculés par le système et les montants déclarés correspondent. S’ils diffèrent et que la différence dépasse les seuils définis, l’utilisateur est invité à effectuer les ajustements nécessaires.

Les ajustements peuvent être effectués pour chaque offre. Lorsqu’une offre est sélectionnée, l’utilisateur peut afficher les totaux de différents types de transaction et modifier les totaux d’un type de transaction spécifique. Lors de la modification, le système affiche le montant calculé d’origine et le montant remplacé pour ce type de transaction. L’utilisateur peut également capturer des notes dans le cadre du processus de modification. Les notes peuvent être utilisées à des fins d’audit.

Les utilisateurs peuvent ignorer les invites et les messages de validation et procéder à la clôture de l’équipe de travail. Cependant, si un utilisateur ignore les invites de validation, les mêmes problèmes se poseront et devront être résolus lorsque l’équipe de travail validera les tableaux d’analyse dans Commerce Headquarters.

L’opération **Clôturer l’équipe de travail** du PDV valide également que toutes les transactions de la base de données hors connexion sont synchronisées avec la base de données du canal. Si des transactions ne sont pas synchronisées, l’utilisateur reçoit un message d’avertissement, car cette situation peut entraîner un calcul incorrect des montants système. Dans ce cas, l’utilisateur peut mettre fin à l’opération **Clôturer l’équipe de travail** et essayer de synchroniser les transactions hors connexion avec la base de données du canal. L’utilisateur peut également ajuster manuellement les montants calculés par le système pour tenir compte des transactions qui ne sont pas synchronisées, afin que l’ensemble correct de tableaux d’analyse soit finalisé et validé. 

Lorsque la validation des relevés en flux continu est utilisée pour que la validation des transactions soit séparée de la validation des relevés financiers, vous pouvez choisir d’ajuster les montants calculés par le système pour les transactions hors connexion manquantes. De cette façon, vous vous assurez que les états financiers sont toujours comptabilisés et validés correctement, indépendamment des transactions manquantes. Les transactions hors connexion peuvent être synchronisées avec la base de données du canal et Commerce Headquarters et validées ultérieurement, séparément des validations financières.

Les détails du rapprochement financier pour une équipe de travail sont synchronisés avec Commerce headquarters à l’aide du travail P.

Les tableaux d’analyse de la vente au détail dans Commece Headquarters ne calculent pas les totaux pour afficher les détails sur les lignes de relevé. À la place, les montants finalisés dans le client PDV sont utilisés pour créer et valider les tableaux d’analyse de la vente au détail.


[!INCLUDE[footer-include](../includes/footer-banner.md)]