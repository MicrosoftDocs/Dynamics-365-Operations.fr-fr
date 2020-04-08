---
title: Délégation d'éléments de travail dans un workflow
description: Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aceafbe8dfcdac2ac7b97a4f77a9a30599c60c51
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140580"
---
# <a name="delegate-work-items-in-a-workflow"></a>Délégation d'éléments de travail dans un workflow

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>Délégation manuelle d'un élément de travail

Pour déléguer un élément de travail individuel, sélectionnez l'option **Déléguer** dans le menu **Workflow** puis entrez l'utilisateur à qui déléguer l'élément de travail en y ajoutant un commentaire. Cela réaffectera l'élément de travail à cet utilisateur afin qu'il puisse l'exécuter.

## <a name="automatically-delegate-work-items"></a>Déléguer automatiquement des éléments de travail

Si vous prévoyez de vous absenter du bureau ou être indisponible d'une manière quelconque pour agir sur des éléments de travail pendant une période donnée, vous pouvez automatiquement déléguer de nouveaux éléments de travail à d'autres utilisateurs à l'aide de la page **Options utilisateur**.

### <a name="set-up-automatic-delegation"></a>Paramétrage de la délégation automatique
1. Accédez à **Commun > Paramétrage > Options utilisateur**.
2. Cliquez sur **Workflow** et vérifiez que la section Délégation est développée. Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d'autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d'éléments de travail sont délégués. Pour créer une règle de délégation, procédez comme suit :  
3. Cliquez sur **Ajouter**.
4. Sélectionnez une option dans le champ **Portée**.
    - Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.
    - Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow. Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ Nom.
    - Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné. Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ Nom.  
5. Dans le champ **Déléguer**, sélectionnez l'utilisateur auquel déléguer les éléments de travail. Les champs Date/heure de début et Date/heure de fin permettent de spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.  
6. Dans le champ **Date/heure de début**, entrez une date et une heure.
7. Dans le champ **Date/heure de fin**, entrez une date et une heure.
8. Activez la case à cocher **Activé** pour activer la règle de délégation. Si vous avez sélectionné **Module** comme Portée, vous devez alors sélectionner le module dans le champ Nom. Si vous avez sélectionné **Workflow** comme Portée, vous devez alors sélectionner le workflow spécifique à déléguer dans le champ Nom.  
9. Dans le champ **Commentaire**, entrez un commentaire expliquant le motif de la délégation des éléments de travail.

