---
title: Validation du journal des arrivées pour les produits retournés
description: Validation du journal des arrivées pour les produits retournés.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff41db85e57313429a6c723672ffd6a3181ecb1f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676717"
---
# <a name="post-arrival-journal-for-returned-products"></a>Validation du journal des arrivées pour les produits retournés 

[!include [banner](../includes/banner.md)]


Pour traiter un retour, commencez par valider la quantité retournée et mettre à jour le champ de quantité dans le journal des arrivées d’articles. Puis sélectionnez un code disposition ou indiquez que les articles retournés doivent être inspectés. Une fois ces opérations accomplies, vous pouvez valider le journal des arrivées d’articles pour l’ordre de retour.

1.  Cliquez sur **Gestion des stocks** \> **Périodique** \> **Vue d’ensemble des arrivées**.

2.  Dans le filtre **Nom du paramétrage**, sélectionnez **Ordre de retour**.

3.  Si la liste des réceptions est longue, utilisez les champs de la zone **Plage** pour la raccourcir.

4.  Repérez la ligne de l’ordre de retour à valider, activez la case **Sélectionner pour l’arrivée** associée, puis cliquez sur **Commencer une arrivée**.

5.  Cliquez sur **Journaux** \> **Afficher les arrivées à partir des réceptions** pour ouvrir l’écran **Journal des emplacements**.
    

    > [!TIP]
    > <P>Pour afficher des informations détaillées, sélectionnez un journal, puis cliquez sur <STRONG>Lignes</STRONG>.</P>


6.  Apportez les mises à jour nécessaires, puis cliquez sur **Valider**.

Une fois le journal validé, les articles retournés sont enregistrés en stock et l’écran **Ordres de retour** indique qu’ils sont arrivés à l’entrepôt.

## <a name="see-also"></a>Voir également :

[Journal des emplacements (écran)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]