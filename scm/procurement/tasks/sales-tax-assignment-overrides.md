--- 
title: Affectation et remplacement des taxes
description: "Cette procédure illustre comment affecter des groupes de taxe aux canaux de vente au détail."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 02ed6b5c7d83d9781a842c4b06a5907ad23d0969
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="sales-tax-assignment-and-overrides"></a>Affectation et remplacement des taxes

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure illustre comment affecter des groupes de taxe aux canaux de vente au détail. Elle décrit également le processus de création d'un nouveau remplacement de taxe et son affectation à un groupe de remplacement de taxe existant. Cette procédure

utilise la société USRT dans les données de démonstration.

1. Accédez à Commerce et vente au détail > Canaux > Magasins de vente au détail > Tous les magasins de vente au détail.
2. Dans la liste, cliquez sur le lien de l'ID canal de vente au détail pour « Houston. »
3. Cliquez sur Modifier.
    * Le champ « Groupe de taxe » contient la liste des groupes de taxe pour la société actuelle. Le groupe actuellement affecté est un groupe générique de taxe « Texas ». Il y a également des groupes de taxes pour « Washington » et « Washington, comté de King » Les groupes de taxes peuvent inclure des taxes applicables pour les différentes municipalités.  
    * Le champ « Remplacement de taxe » est le champ où les groupes de remplacement de taxe peuvent être mis en correspondance avec le canal. Les groupes de remplacement de taxe peuvent être employés pour regrouper les remplacements de taxe qui travaillent pour plusieurs magasins. Plutôt que d'affecter manuellement des remplacements de taxe un par un, le groupe peut être créé et affecté directement aux canaux pour gagner du temps.  
4. Cliquez sur Enregistrer.
5. Fermez la page.
6. Allez dans Commerce et vente au détail > Paramétrage du canal > Taxes > Remplacements de taxe.
7. Cliquez sur Nouveau.
8. Dans le champ Remplacement de taxe, fournissez un nom pour votre nouveau dépassement.
9. Dans le champ Description, entrez la description du remplacement.
10. Définissez le statut sur « Activer ».
11. Développez ou réduisez la section Remplacer.
12. Sélectionnez une option dans le champ Type.
    * Les groupes de taxe d'article peuvent être employés pour remplacer des impôts pour des articles spécifiques qui appartiennent au groupe. Par exemple, des produits alimentaires sont généralement imposés différemment des biens d'équipement, et auraient certainement leur propre groupe de taxe.     Les groupes de taxe sont des groupes qui s'appliquent à un canal particulier. Par exemple, si un canal fait de la vente au détail et d'entreprise à entreprise, différents groupes de taxe de vente d'articles peuvent être employés. Toutes les taxes applicables seraient mises en correspondance avec le groupe de taxe.  
    * Maintenant vous pouvez choisir entre les taxes « De départ » et « D'arrivée » ou « Groupe de taxe de départ » et « Groupe de taxe d'arrivée » pour créer votre remplacement de taxe.    Le champ « De départ » indique l'impôt ou le groupe d'impôts à remplacer. Le remplacement par le groupe de taxe d'article fournit des options différentes du remplacement par le groupe de taxe.    Remplacements de taxe peut être défini pour remplacer des taxes sur des transactions entières ou sur des lignes particulières de la transaction.  
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Allez dans Commerce et vente au détail > Paramétrage du canal > Taxes > Groupes de remplacement de taxe.
    * Dans cette étape, vous allez affecter le remplacement de taxe précédemment créé au groupe de remplacement de taxe affecté au canal « Houston ».  
16. Cliquez sur Modifier.
17. Développez ou réduisez la section Paramétrage.
18. Cliquez sur Ajouter.
19. Dans le champ Groupes de remplacement de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
20. Choisissez le remplacement de taxe précédemment créé à partir de la liste.
21. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
22. Cliquez sur Enregistrer.


