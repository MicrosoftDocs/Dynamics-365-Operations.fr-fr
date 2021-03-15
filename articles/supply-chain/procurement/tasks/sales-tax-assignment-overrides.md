---
title: Affectation et remplacement des taxes
description: Cette procédure explique comment affecter des groupes de taxes aux canaux de commerce.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c6e1de5046a3ce5d896ba3686a28d6d474d4268
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020726"
---
# <a name="sales-tax-assignment-and-overrides"></a>Affectation et remplacement des taxes

[!include [banner](../../includes/banner.md)]

Cette procédure explique comment affecter des groupes de taxes aux canaux de commerce. Elle décrit également le processus de création d'un nouveau remplacement de taxe et son affectation à un groupe de remplacement de taxe existant. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Retail et Commerce > Canaux > Magasins > Tous les magasins.
2. Dans la liste, cliquez sur le lien ID canal pour « Houston ».
3. Cliquez sur Modifier.
    * Le champ « Groupe de taxe » contient la liste des groupes de taxe pour la société actuelle. Le groupe actuellement affecté est un groupe générique de taxe « Texas ». Il y a également des groupes de taxes pour « Washington » et « Washington, comté de King » Les groupes de taxes peuvent inclure des taxes applicables pour les différentes municipalités.  
    * Le champ « Remplacement de taxe » est le champ où les groupes de remplacement de taxe peuvent être mis en correspondance avec le canal. Les groupes de remplacement de taxe peuvent être employés pour regrouper les remplacements de taxe qui travaillent pour plusieurs magasins. Plutôt que d'affecter manuellement des remplacements de taxe un par un, le groupe peut être créé et affecté directement aux canaux pour gagner du temps.  
4. Cliquez sur Enregistrer.
5. Fermez la page.
6. Accédez à Retail et Commerce > Paramétrage du canal > Taxes > Remplacements de taxe.
7. Cliquez sur Nouveau.
8. Dans le champ Remplacement de taxe, fournissez un nom pour votre nouveau dépassement.
9. Dans le champ Description, entrez la description du remplacement.
10. Définissez le statut sur « Activer ».
11. Développez ou réduisez la section Remplacer.
12. Sélectionnez une option dans le champ Type.
    * Les groupes de taxe d'article peuvent être employés pour remplacer des impôts pour des articles spécifiques qui appartiennent au groupe. Par exemple, des produits alimentaires sont généralement imposés différemment des biens d'équipement, et auraient certainement leur propre groupe de taxe. Les groupes de taxe sont des groupes qui s'appliquent à un canal particulier. Par exemple, si un canal fait de la vente au détail et d'entreprise à entreprise, différents groupes de taxe de vente d'articles peuvent être employés. Toutes les taxes applicables seraient mises en correspondance avec le groupe de taxe.  
    * Maintenant vous pouvez choisir entre les taxes « De départ » et « D'arrivée » ou « Groupe de taxe de départ » et « Groupe de taxe d'arrivée » pour créer votre remplacement de taxe. Le champ « De départ » indique l'impôt ou le groupe d'impôts à remplacer. Le remplacement par le groupe de taxe d'article fournit des options différentes du remplacement par le groupe de taxe. Remplacements de taxe peut être défini pour remplacer des taxes sur des transactions entières ou sur des lignes particulières de la transaction.  
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Accédez à Retail et Commerce > Paramétrage du canal > Taxes > Groupes de remplacements de taxe.
    * Dans cette étape, vous allez affecter le remplacement de taxe précédemment créé au groupe de remplacement de taxe affecté au canal « Houston ».  
16. Cliquez sur Modifier.
17. Développez ou réduisez la section Paramétrage.
18. Cliquez sur Ajouter.
19. Dans le champ Groupes de remplacement de taxe, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
20. Choisissez le remplacement de taxe précédemment créé à partir de la liste.
21. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
22. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]