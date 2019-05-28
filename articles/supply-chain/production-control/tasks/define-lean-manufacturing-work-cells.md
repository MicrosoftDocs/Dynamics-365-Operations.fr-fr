---
title: Définir les cellules de travail pour la lean manufacturing
description: Une cellule de travail est une forme spécifique des groupes de ressources qui peuvent être utilisés dans les activités de processus Lean Manufacturing.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, InventLocationIdLookup, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f31fbd2ed8e20b92527af88fc3c955d3c66a364
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566535"
---
# <a name="define-lean-manufacturing-work-cells"></a>Définir les cellules de travail pour la lean manufacturing

[!include [task guide banner](../../includes/task-guide-banner.md)]

Une cellule de travail est une forme spécifique des groupes de ressources qui peuvent être utilisés dans les activités de processus Lean Manufacturing. Les cellules de travail ont des emplacements d'entrée et de sortie et une définition de capacité basée sur un modèle de flux de production. Pour plus d'informations sur les concepts de base des cellules de travail Lean Manufacturing et les calculs de capacité, consultez les livres blancs sur le concept de Lean Manufacturing. La société fictive de démonstration utilisée pour créer cette procédure est USMF


## <a name="create-a-work-cell"></a>Créez une cellule de travail. 
1. Accédez à Administration d'organisation > Ressources > Groupes de ressources.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Groupe de ressources.
    * L'ID de cellule de travail est généralement un code systématique et doit être unique pour l'entité juridique.  
4. Dans le champ Description, entrez une valeur.
    * La description contient le nom ou le titre de la cellule de travail.  
5. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Une cellule de travail est située sur un site spécifique. L'entrepôt et l'emplacement d'entrée et de sortie doivent être situés sur ce site.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Dans le champ Unité de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Sélectionnez une unité de production à laquelle cette cellule de travail appartient.  
9. Cochez la case Cellule de travail.
    * Pour utiliser un groupe de ressources comme cellule de travail au plus juste, vous devez cocher la case Cellule de travail.  Notez que cette propriété ne peut pas être modifiée une fois le groupe de ressources créé.  
10. Dans le champ Entrepôt d'entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
11. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Pour la comptabilité et le contrôle matières, les matières à l'état intermédiaires dans l'atelier sont généralement affectées à un entrepôt virtuel spécifique. Toutefois, si vous souhaitez réapprovisionner des emplacements par l'intermédiaire du travail d'entrepôt, ils doivent faire partie de l'entrepôt destinataire de matières premières.  
12. Dans le champ Emplacement de l'entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
13. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Notez que pour une activité de processus, l'emplacement d'entrée peut être remplacé en général ou pour un produit ou une variante de produit spécifiques en définissant des activités de prélèvement qui concourent à l'activité de processus. Les emplacements d'entrée d'une cellule de travail ne peuvent pas faire l'objet d'un contrôle de contenant.  
14. Dans le champ Entrepôt de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Dans les flux de production ou les lignes de production à plusieurs activités, il s'agit souvent de l'entrepôt d'entrée de la cellule de travail suivante ou de l'entrepôt de vente ou de transit vers lequel un produit est généralement transféré après le processus de production. Lorsque vous modélisez les processus Lean Manufacturing, n'oubliez pas que le transport est généralement considéré comme rebut, ainsi que l'état de transport.  
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Dans le champ Emplacement de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Dans un flux de production contenant plusieurs activités de processus, il s'agit souvent de l'emplacement d'entrée de la cellule de travail suivante.  
18. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
19. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
20. Développez ou réduisez la section Opération.
    * Une catégorie de temps d'exécution doit être fournie pour activer le calcul du coût et le traitement des tâches de kanban au plus juste.  
21. Dans le champ Catégorie de temps d'exécution, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
22. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * La catégorie de coûts d'exécution est utilisée dans le calcul du coût standard et dans la comptabilité à rebours.  
23. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
24. Développez ou réduisez la section Calendriers.
25. Cliquez sur Ajouter.
26. Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
27. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Généralement, les cellules de travail d'un site donné utilisent le même calendrier de temps de travail. Si les cellules de travail peuvent avoir des temps de travail différents, vous devrez peut-être créer un calendrier de temps de travail spécifique pour la cellule de travail concernée. Notez que le calendrier doit avoir un temps de travail standard défini lorsqu'il est utilisé pour une cellule de travail au plus juste, car la définition de capacité est généralement associée au temps de travail standard d'un jour de travail.  
28. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
29. Développez ou réduisez la section Capacité de cellule de travail.
30. Cliquez sur Ajouter.
31. Dans le champ Modèle de flux de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
32. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Ces procédures exigent le type de modèle de flux de production Débit, afin d'indiquer la définition de la capacité de débit.  
33. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
34. Dans le champ Période de capacité, sélectionnez une option.
    * Les options sont les suivantes : Jour de travail standard - la capacité est exprimée par la durée du jour de travail standard du calendrier de temps de travail pour la cellule de travail. Pour chaque jour, le temps de travail réel est déterminé à partir du calendrier et la capacité efficace disponible effet est calculée en conséquence.   Semaine - autorise une capacité hebdomadaire. Aucun ajustement n'est effectué par rapport au temps de travail réel.   Mois - autorise une capacité mensuelle. Aucun ajustement n'est effectué par rapport à la capacité réelle.   Généralement, le jour de travail standard est utilisé pour les périodes quotidiennes et la capacité hebdomadaire est utilisée pour les périodes de capacité hebdomadaires.  
35. Dans le champ Quantité moyenne de débit, entrez un nombre.
    * Notez qu'une opération au plus juste n'est jamais configurée pour la capacité maximale possible dans un environnement idéal. Au contraire, la capacité doit toujours être définie pour les opérations exécutées dans des circonstances habituelles.  
36. Dans le champ Unité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
37. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
38. Résolvez les modifications de l'unité.

## <a name="add-a-financial-dimension"></a>Ajouter une dimension financière
1. Développez ou réduisez la section Dimensions financières.
    * Notez que les dimensions financières définies sur le flux de production remplacent la dimension financière d'une cellule de travail donnée.    Les dimensions financières qui peuvent être sélectionnées dépendent de la configuration des dimensions financières de votre système. Les étapes suivantes correspondent au jeu de données de démonstration de la société fictive USMF. Lorsque vous utilisez des données différentes, les étapes ne sont pas forcément applicables.  
2. Dans le champ Centre de coût, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Les dimensions qui doivent être sélectionnées pour les cellules de travail au plus juste dépendent de la mise en œuvre des dimensions financières dans le modèle de comptabilité pour une entité juridique spécifique.  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ Groupe d'articles, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="save"></a>Enregistrer
1. Cliquez sur Enregistrer.

