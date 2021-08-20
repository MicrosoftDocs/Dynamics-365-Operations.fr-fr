---
title: Créer une cellule de travail sous-traitée de lean manufacturing
description: Pour modéliser le travail sous-traité pour lean manufacturing, vous devez créer une cellule de travail associée au fournisseur qui fournit le travail.
author: cvocph
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acb0adf3e53830f951ae6d1faefd3f30aa3a445e28dc1a08b76a408bdf9af810
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744676"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Créer une cellule de travail sous-traitée de lean manufacturing

[!include [banner](../../includes/banner.md)]

Pour modéliser le travail sous-traité pour lean manufacturing, vous devez créer une cellule de travail associée au fournisseur qui fournit le travail. Une cellule de travail sous-traitée est liée au fournisseur via l’association d’une ressource du type Fournisseur. Si vous lisez cet enregistrement dans la société fictive USMF, vous pouvez sélectionner l’ID compte fournisseur 1002 et le site 1.


## <a name="create-a-vendor-resource"></a>Créer un groupe de ressources
1. Allez dans Ressources.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Ressource.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Type, sélectionnez « Fournisseur ».
6. Dans le champ Fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.

## <a name="create-the-resource-group"></a>Créer le groupe de ressources
1. Allez dans Groupes de ressources.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Groupe de ressources.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez le site auquel la cellule de travail doit être affectée. En théorie, un site peut représenter un site unique exploité par un fournisseur. Toutefois, dans la plupart des cas, les ressources sous-traitées sont simplement affectées au site qui commande le travail sous-traité. Notez que les entrepôts d’entrée et de sortie des cellules de travail sous-traitées doivent être sur le même site.  
6. Tapez une valeur dans le champ Site.
7. @SysTaskRecorder:_RequestClose
8. Activez ou désactivez la case à cocher Cellule de travail.
9. Dans le champ Entrepôt d’entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez l’entrepôt et l’emplacement utilisés pour stocker les matières pour la cellule de travail gérée par le fournisseur. Dans de nombreux cas, l’entrepôt et l’emplacement sont modélisés en utilisant un entrepôt distinct par fournisseur et un emplacement par cellule de travail.  
10. Dans le champ Emplacement de l’entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans le champ Entrepôt de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Définissez l’entrepôt et l’emplacement où les matières sont validées lorsque les activités sous-traitées de la cellule de travail sont validées. L’entrepôt et l’emplacement peuvent être sur le site du fournisseur si le fournisseur déclare les tâches de kanban. Sinon, l’entrepôt et l’emplacement peuvent être l’emplacement de réception associé à l’étape suivante du flux de production.  
12. Dans le champ Emplacement de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Développez ou réduisez la section Calendriers.
14. Cliquez sur Ajouter.
15. Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Associez le calendrier du temps de travail de la cellule de travail au groupe de ressources. Pour les ressources critiques, il est recommandé de définir des calendriers spécifiques qui représentent les temps de travail exacts et les capacités associées de la cellule de travail ou du site du fournisseur.  
16. Développez ou réduisez la section Ressources.
17. Cliquez sur Ajouter.
    * Un groupe de ressources sous-traitées doit avoir une ressource associée du type Fournisseur qui lie le groupe de ressources au compte fournisseur.  
18. Dans le champ Ressources, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez ou entrez la ressource fournisseur que vous avez créée dans la sous-tâche précédente.  
19. Développez ou réduisez la section Capacité de cellule de travail.
20. Cliquez sur Ajouter.
    * Une cellule de travail doit avoir une capacité définie. Dans cet exemple, nous créons une capacité de production de 100 pièces par jour de travail standard.  
21. Dans le champ Modèle de flux de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
22. Dans le champ Période de capacité, sélectionnez une option.
23. Dans le champ Quantité moyenne de débit, entrez un nombre.
24. Dans le champ Unité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
25. Résolvez les modifications de l’unité.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]