---
title: Enregistrer les configurations pour les relevés de vente au détail
description: Cette procédure détaille les configurations du magasin qui affectent la création et la validation des relevés de commerce.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e255c58997ed1c0ad5614b15867f14714a8bcfc8
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2020
ms.locfileid: "4412421"
---
# <a name="store-configurations-for-retail-statements"></a> Enregistrer les configurations pour les relevés de vente au détail

[!include [banner](../includes/banner.md)]

Cette procédure détaille les configurations du magasin qui affectent la création et la validation des relevés de commerce. Les dimensions financières pour les magasins sont traitées dans une autre procédure. La société fictive USRT sert d'exemple dans cette procédure.

1. Dans le **Volet de navigation**, accédez à **Modules > Commerce et vente au détail > Canaux > Magasins > Tous les magasins**.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur **Modifier**.
5. Les paramètres du FastTab **Relevé/clôture** affectent la création, le contrôle et la validation de relevés pour le magasin. Développez le FastTab **Relevé/clôture**.  
6. Dans le champ **Méthode de relevé**, sélectionnez la méthode à utiliser pour regrouper les lignes de relevé.  
7. Sélectionnez « Oui » dans **Un relevé par jour** si un seul relevé doit être créé par jour lors de la création de relevés à partir du traitement par lots de la création de relevés.  
8. Le champ **Calcul de comptage de caisse** définit si les comptages de caisse doivent être ajoutés ensemble ou si c'est le dernier qui doit être utilisé.  
9. Dans le champ **Arrondi**, sélectionnez le compte général dans lequel valider les différences d'arrondi.  
10. Dans le champ **Différence d'arrondi maximale**, spécifiez la différence d'arrondi maximale autorisée.
11. Dans le champ **Validation**, vous pouvez spécifier la différence de validation totale maximale autorisée pour un relevé.
12. Dans le champ **Équipe**, vous pouvez spécifier la différence totale maximale au sein d'une équipe dans un relevé.  
13. Dans le champ **Transaction**, vous pouvez spécifier la différence totale maximale dans une ligne de relevé.  
14. Dans le champ **Méthode de clôture**, définissez si les transactions à inclure dans un relevé doivent faire partie d'une équipe de travail clôturée ou s'il peut s'agir de toute transaction comprise dans la période définie.  
15. Dans le champ **Fin du jour ouvrable**, spécifiez une heure si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.  
16. Sélectionnez « Oui » dans **Valider comme jour ouvrable** si les transactions qui surviennent après minuit doivent être validées dans le cadre du jour précédent.  
17. Sélectionnez « Oui » dans **Fractionner par mode de relevé** pour que des relevés soient créés pour chaque méthode de relevé définie. Cette action peut s'avérer utile si les performances de la validation doit être améliorée pour les magasins affichant des volumes élevé de transactions, car cela créera de nombreux relevés plus petits qui peuvent être traités en parallèle.  
18. Dans le FastTab **Général**, dans le champ **Client par défaut**, vous pouvez sélectionner le compte client à utiliser pour les ventes aux clients qui se rendent dans le magasin.  

