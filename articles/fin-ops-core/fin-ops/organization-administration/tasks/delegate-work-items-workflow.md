---
title: Délégation d’éléments de travail dans un workflow
description: Si vous pensez vous absenter du bureau ou être dans l’incapacité d’agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d’autres utilisateurs.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b4b9abff57386fda61e3a83b0b8f18e533c8758c
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694639"
---
# <a name="delegate-work-items-in-a-workflow"></a>Délégation d’éléments de travail dans un workflow

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>Délégation manuelle d’un élément de travail

Pour déléguer un élément de travail individuel, sélectionnez l’option **Déléguer** dans le menu **Workflow** puis entrez l’utilisateur à qui déléguer l’élément de travail en y ajoutant un commentaire. Cela réaffectera l’élément de travail à cet utilisateur afin qu’il puisse l’exécuter.

## <a name="manually-delegate-multiple-work-items"></a>Délégation manuelle de plusieurs éléments de travail

Plusieurs éléments de travail peuvent être délégués ensemble à partir de la page **Éléments de travail qui me sont affectés**. Les types de workflow suivants sont éligibles pour la délégation en masse : workflow d’approbation des contrats d’achat, workflow de commande fournisseur, révision de la demande d’achat et workflow de facture fournisseur. La fonctionnalité **Déléguer plusieurs éléments de travail** est désactivée par défaut et peut être activée dans **Espaces de travail > Gestion des fonctionnalités**. Contactez votre administrateur système pour obtenir de l’aide pour activer cette fonctionnalité.
1.  Allez dans **Commun > Commun > Éléments de travail > Éléments de travail qui me sont affectés**.
2.  Sélectionnez les éléments de travail qui seront délégués.
3.  Cliquez sur le menu **Déléguer des éléments de travail**.
4.  Dans le champ **Utilisateur**, sélectionnez l’utilisateur auquel déléguer les éléments de travail.
5.  Dans le champ **Commentaire**, entrez un commentaire expliquant le motif de la délégation des éléments de travail.
6.  Cliquez le bouton **Déléguer des éléments de travail** pour terminer la délégation des éléments de travail.

## <a name="automatically-delegate-work-items"></a>Déléguer automatiquement des éléments de travail

Si vous prévoyez de vous absenter du bureau ou être indisponible d’une manière quelconque pour agir sur des éléments de travail pendant une période donnée, vous pouvez automatiquement déléguer de nouveaux éléments de travail à d’autres utilisateurs à l’aide de la page **Options utilisateur**.

### <a name="set-up-automatic-delegation"></a>Paramétrage de la délégation automatique
1. Accédez à **Commun > Paramétrage > Options utilisateur**.
2. Cliquez sur **Workflow** et vérifiez que la section Délégation est développée. Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d’autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d’éléments de travail sont délégués. Pour créer une règle de délégation, procédez comme suit :  
3. Cliquez sur **Ajouter**.
4. Sélectionnez une option dans le champ **Étendue**.
    - Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.
    - Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow. Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ **Nom**.
    - Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné. Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ **Nom**.  
5. Dans le champ **Nom** :
    - Pour l’étendue **Module**, sélectionnez le module cible.
    - Pour l’étendue **Workflow**, sélectionnez le workflow cible.
6. Dans le champ **Déléguer**, sélectionnez l’utilisateur auquel déléguer les éléments de travail. Utilisez les champs **Date/heure de début** et **Date/heure de fin** pour spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.  
7. Dans le champ **Date/heure de début**, entrez une date et une heure.
8. Dans le champ **Date/heure de fin**, entrez une date et une heure.
9. Activez la case à cocher **Activé** pour activer la règle de délégation. 
10. Dans le champ **Commentaire**, entrez un commentaire expliquant le motif de la délégation des éléments de travail.
