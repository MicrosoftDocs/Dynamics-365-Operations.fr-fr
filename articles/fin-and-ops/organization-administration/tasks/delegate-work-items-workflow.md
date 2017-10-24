--- 
title: "Délégation d'éléments de travail dans un workflow"
description: "Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4765fec0cdce0e2f8859c979ff97d20aa6b20bfa
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="delegate-work-items-in-a-workflow"></a>Délégation d'éléments de travail dans un workflow

[!include[task guide banner](../../includes/task-guide-banner.md)]

Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs. Cette procédure vous permet de configurer le système pour déléguer automatiquement vos éléments de travail à un autre utilisateur.



Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="set-up-automatic-delegation"></a>Paramétrage de la délégation automatique
1. Accédez à Commun > Paramétrage > Options utilisateur.
2. Cliquez sur l'onglet Workflow.
    * Assurez-vous que la section Délégation est développée.    Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d'autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d'éléments de travail sont délégués. Pour créer une règle de délégation, procédez comme suit :  
3. Cliquez sur Ajouter.
4. Dans le champ Portée, sélectionnez une option.
    * Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.    Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow. Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ Nom.    Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné. Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ Nom.  
5. Dans le champ Déléguer, sélectionnez l'utilisateur auquel déléguer les éléments de travail.
    * Les champs Date/heure de début et Date/heure de fin permettent de spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.  
6. Dans le champ Date/heure de début, entrez une date et une heure.
7. Dans le champ Date/heure de fin, entrez une date et une heure.
8. Activez la case à cocher Activé pour activer la règle de délégation.
    * Si vous avez sélectionné Module comme Portée, vous devez alors sélectionner le module dans le champ Nom.    Si vous avez sélectionné Workflow comme Portée, vous devez alors sélectionner le workflow spécifique à déléguer dans le champ Nom.  
9. Dans le champ Commentaire, entrez un commentaire expliquant le motif de la délégation des éléments de travail.


