---
title: Inspection des articles retournés
description: Inspection des articles retournés.
author: sorenva
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41214663ec48a8cbcd8bec7f6801adb4311b2373
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669934"
---
# <a name="take-returned-items-through-inspection"></a>Inspection des articles retournés 

[!include [banner](../includes/banner.md)]


1.  Cliquez sur **Gestion des stocks** \> **Périodique** \> **Gestion de la qualité** \> **Ordres de contrôle**.

2.  Accédez à la ligne de commande qui correspond à l’article retourné que vous inspectez.

    > [!NOTE]
    > <P>Un ordre de contrôle ne peut être associé qu’à un seul numéro d’article. Si 10 articles avec différents numéros d’article sont retournés en une seule fois et envoyés en contrôle, 10 ordres de contrôle individuels sont créés.</P>

3.  Après inspection de l’article, effectuez une sélection dans le champ **Code disposition** pour indiquer les actions à réaliser et le mode de traitement des transactions financières associées. Voici quelques exemples d’actions : renvoi de l’article en stock et remboursement du client, mise au rebut de l’article et envoi d’un article de remplacement au client ou renvoi de l’article au client sans crédit.
    
    > [!NOTE]
    > <P>S’il est impossible d’affecter le même code disposition à plusieurs articles retournés faisant partie d’un lot de numéros d’article, vous devez fractionner l’ordre de contrôle (<STRONG>Fonctions</STRONG> &gt; <STRONG>Fractionner</STRONG>) de manière à affecter un code disposition différent à chaque sous-lot.</P>


4.  Lorsque l’inspection est terminée, cliquez sur **Déclaration de fin** pour libérer les articles retournés, puis créez une entrée de journal des arrivées d’articles. La personne ou le service qui reçoit les articles traite ensuite le journal pour que les articles soient renvoyés en stock.
    
    - ou -
    
    Terminez l’ordre de contrôle, puis retournez les articles en stock à l’aide de l’une des fonctions **Stock**.

5.  Fermez l’écran pour enregistrer vos modifications.

## <a name="see-also"></a>Voir également :

[Spécification de la procédure de cession des articles retournés](specify-how-to-dispose-of-returned-items.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]