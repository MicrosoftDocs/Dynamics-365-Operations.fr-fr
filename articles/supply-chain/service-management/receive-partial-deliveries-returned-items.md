---
title: Recevoir des livraisons partielles d’articles retournés
description: Des livraisons partielles sont définies en termes de lignes d’ordre de retour, pas d’expéditions de retour.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51213f8f46638b0cce10251e761d7f276c39d924
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836132"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>Recevoir des livraisons partielles d’articles retournés    

[!include [banner](../includes/banner.md)]


Des livraisons partielles sont définies en termes de lignes d’ordre de retour, pas d’expéditions de retour.

Cela signifie que, si vous recevez la quantité complète indiquée sur une ligne d’ordre de retour, mais rien en rapport avec les autres lignes, la livraison n’est pas partielle. En revanche, si une ligne d’ordre de retour indique que dix unités d’un article doivent être retournées et que vous n’en recevez que quatre, la livraison est partielle.

Si une expédition de retour contient une quantité inférieure à celle indiquée sur une ligne d’ordre de retour, vous pouvez soit mettre l’expédition de côté en attendant de recevoir le reste de la quantité retournée, soit enregistrer et valider la quantité partielle.

## <a name="register-and-post-a-partial-quantity"></a>Enregistrement et validation d’une quantité partielle

1.  Après avoir sélectionné un ordre de retour pour arrivée dans l’écran **Vue d’ensemble des arrivées - Entrepôt : %1, Quai : %2, Nom du journal : %3**, cliquez sur **Commencer une arrivée** pour créer le journal des arrivées, puis sur **Journaux** \> **Afficher les arrivées à partir des réceptions** pour ouvrir l’écran **Journaux des emplacements**.

2.  Sélectionnez la ligne du journal sur laquelle vous voulez travailler, puis cliquez sur **Lignes** pour ouvrir l’écran **Lignes de journal, emplacements**.

3.  Sélectionnez la ligne du numéro d’article pour laquelle seule une quantité partielle est arrivée, puis cliquez sur **Fonctions** \> **Fractionner** pour ouvrir l’écran **Fractionner**.

4.  Dans le champ **Quantité fractionnée**, entrez la quantité correspondant au nombre total d’articles reçus, puis cliquez sur **OK**.

5.  Dans l’écran **Lignes de journal, emplacements**, sélectionnez la ligne indiquant la quantité d’articles arrivés, puis cliquez sur **Valider**. Vous pouvez valider la ligne pour la quantité supplémentaire une fois les articles arrivés.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]