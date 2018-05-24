---
title: "Enregistrement de la réception d'articles retournés"
description: "Vous pouvez enregistrer la réception des articles retournés à l'aide de l'écran Vue d'ensemble des arrivées ou de l'écran Enregistrement."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 550b59a64fb0e81a56d6fea921e1b1df20c5f6e6
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---


# <a name="register-the-receipt-of-returned-items"></a>Enregistrement de la réception d'articles retournés 

[!include [banner](../includes/banner.md)]


Il existe deux méthodes d'enregistrement de la réception des articles retournés. La première méthode est un processus de réception dans l'entrepôt qui utilise l'écran **Vue d'ensemble des arrivées**. La deuxième méthode utilise l'écran **Enregistrement**.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>Enregistrement de la réception des articles retournés à l'aide de l'écran Vue d'ensemble des arrivées

L'écran **Vue d'ensemble des arrivées** permet d'identifier une expédition de retour par son numéro de retour marchandises. Si un nom de journal est défini sous l'onglet **Paramétrage** et que les lignes de journal correspondant aux lignes sélectionnées dans l'écran **Vue d'ensemble des arrivées** existent, un en-tête de journal est créé lorsque vous cliquez sur **Commencer une arrivée**.

1.  Cliquez sur **Gestion des stocks** \> **Périodique** \> **Vue d'ensemble des arrivées**.

2.  Dans le champ **Nom du paramétrage**, sélectionnez **Ordre de retour**, puis cliquez sur **Mettre à jour**.
    

    > [!TIP]
    > <P>Les champs <STRONG>Plage</STRONG> permettent d'affiner les résultats de la recherche. Vous pouvez taper ou sélectionner le numéro de retour marchandises dans le champ <STRONG>Numéro de retour marchandises</STRONG> pour obtenir un résultat exact. Pour définir et enregistrer un ensemble de filtres qui limiteront les arrivées entrantes affichées, cliquez sur l'onglet <STRONG>Paramétrage</STRONG>. Les filtres disponibles sont des types, des entrepôts et des quais.</P>

    

    > [!WARNING]
    > <P>Les ordres de retour ne peuvent pas être mélangés à d'autres types d'arrivées dans l'écran <STRONG>Vue d'ensemble des arrivées</STRONG>. Par conséquent, la référence est toujours la commande client, mais aucun ID de commande client n'est spécifié dans l'en-tête de journal.</P>



3.  Dans la grille **Réceptions**, localisez la ligne correspondant à l'article retourné, puis activez la case à cocher dans la colonne **Sélectionner pour l'arrivée**.

4.  Pour exclure certaines lignes de la réception de retour, telles que les articles de la commande d'origine non inclus dans l'expédition de retour, désactivez les cases à cocher **Sélectionner pour l'arrivée** associées dans le tableau **Lignes** dans la partie inférieure de l'écran.

5.  Cliquez sur le bouton **Commencer une arrivée** pour créer un journal des arrivées.
    

    > [!NOTE]
    > <P>Vous pouvez sélectionner plusieurs ordres de retour et les inclure dans un processus d'arrivée unique. Chaque ligne d'ordre de retour est copiée dans une ligne correspondante du journal des arrivées d'articles.</P>

    

    > [!NOTE]
    > <P>Vous pouvez également créer manuellement un journal des arrivées à l'aide de l'écran <STRONG>Arrivée d'articles</STRONG>. 



6.  Cliquez sur **Gestion des stocks** \> **Journaux** \> **Arrivée d'articles** \> **Arrivée d'articles**.

7.  Sélectionnez le journal des arrivées que vous venez de créer, puis cliquez sur **Lignes** pour ouvrir l'écran **Lignes de journal, emplacements**.

8.  Sous l'onglet **Général**, ajustez le numéro dans le champ **Quantité**, si nécessaire, puis affectez un code disposition dans le champ **Code disposition**.
    
    Sinon, vous pouvez activer la case à cocher **Gestion des contrôles** pour que les articles retournés soient envoyés via un processus d'inspection dans le contexte d'un ordre de contrôle.
    

    > [!NOTE]
    > <P>Si vous envoyez les articles retournés via contrôle, vous ne pouvez pas spécifier de code disposition.</P>



9.  Cliquez sur le bouton **Contrôler**.

10. S'il n'y a aucune erreur dans le processus de contrôle, cliquez sur **Valider**.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>Enregistrement de la réception des articles retournés à l'aide de l'écran Enregistrement

Au lieu d'utiliser l'écran **Vue d'ensemble des arrivées**, vous pouvez utiliser l'écran **Enregistrement** pour enregistrer l'arrivée des articles retournés.

1.  Cliquez sur **Ventes et marketing** \> **Commun** \> **Ordres de retour** \> **Tous les ordres de retour**. Créez un ordre de retour ou ouvrez un ordre de retour dans la liste. Dans l'organisateur **Lignes**, sélectionnez la ligne d'ordre de retour. Cliquez sur **Mettre à jour la ligne**, puis sur **Enregistrement**.

2.  Affectez un code disposition dans le champ **Code disposition**, puis cliquez sur **OK**.
    

    > [!NOTE]
    > <P>Il est impossible d'envoyer l'article pour inspection comme ordre de contrôle à l'aide de l'écran <STRONG>Enregistrement</STRONG>.</P>



3.  Dans la grille **Transactions**, sélectionnez la transaction à enregistrer.

4.  Dans la grille **Enregistrer maintenant**, cliquez sur **Ajouter**. Répétez les deux étapes précédentes jusqu'à ce que tous les articles retournés soient affichés dans la grille **Enregistrer maintenant**.

5.  Cliquez sur **Valider tout**.

## <a name="see-also"></a>Voir également :

[Vue d'ensemble des arrivées (écran)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))

  



