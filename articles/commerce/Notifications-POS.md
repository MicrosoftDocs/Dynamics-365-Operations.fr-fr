---
title: Afficher les notifications dans le point de vente (PDV)
description: Cet article décrit la procédure d’activation des notifications de commande dans le point de vente et l’infrastructure de notifications.
author: ShalabhjainMSFT
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: a9e646d6bf48461e78dc75c8a154f2fbf1443393
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853978"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Afficher les notifications dans le point de vente (PDV)

[!include [banner](includes/banner.md)]

Les collaborateurs du magasin peuvent se voir attribuer diverses tâches dans leur magasin, telles que l’exécution des commandes ou l’exécution de la réception des stocks ou les inventaires. Le client du point de vente (PDV) fournit une application unique aux collaborateurs, qui leur permet d’être informé de ces tâches. L’infrastructure de notification dans le PDV permet aux détaillants de configurer des notifications basées sur les rôles. À partir de Dynamics 365 Retail avec la mise à jour d’application 5, ces notifications peuvent être configurées pour les opérations de PDV.

Le système peut afficher des notifications pour l’*exécution des commandes* et à partir de la version 10.0.18 de Commerce, les notifications peuvent également être affichées pour le *rappel de commande*. Toutefois, comme l’infrastructure est conçue pour être extensible, les développeurs peuvent [écrire un gestionnaire de notification](dev-itpro/extend-pos-notification.md) pour toutes les opérations, et afficher les notifications pour cette opération dans le PDV.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>Activer les notifications pour les opérations d’exécution des commandes et de rappel de commande

Pour activer les notifications pour les opérations d’exécution des commandes ou de rappel de commande, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Opérations**.
1. Recherchez l’opération **Exécution des commandes** ou **Rappel de commande**, puis sélectionnez **Activer les notifications** pour l’opération afin d’indiquer que l’infrastructure de notification doit écouter le gestionnaire pour cette opération. Si le gestionnaire est implémenté, les notifications de cette opération seront ensuite affichées dans le PDV.
1. Accédez à **Retail et Commerce \> Employés \> Collaborateurs**.
1. Sélectionnez l’onglet **Commerce**, sélectionnez la ligne d’un collaborateur, puis sélectionnez **Autorisations PDV**. Sélectionnez le raccourci **Notifications** pour le développer, puis ajoutez les opérations pour lesquelles vous avez activé les notifications. Si vous configurez une notification unique pour un collaborateur, assurez-vous que la valeur **Ordre d’affichage** est définie sur **1**. Si vous configurez plusieurs opérations, définissez les valeurs **Ordre d’affichage** pour indiquer l’ordre dans lequel les notifications doivent être affichées. 

      Les notifications ne sont affichées que pour les opérations ajoutées sur le raccourci **Notifications**. Vous ne pouvez y ajouter des opérations que si les cases **Activer les notifications** ont été cochées pour ces opérations sur la page **Opérations PDV**. En outre, les notifications d’une opération sont uniquement affichées pour les collaborateurs si l’opération est ajoutée aux autorisations du PDV pour ceux-ci.

    > [!NOTE]
    > Les notifications peuvent être remplacées au niveau de l’utilisateur. Pour cela, ouvrez l’enregistrement du collaborateur, sélectionnez **Autorisations PDV**, puis modifiez l’abonnement à la notification de l’utilisateur.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. Dans le champ **Intervalle de notification**, spécifiez la fréquence à laquelle les notifications doivent être extraites. Pour certaines notifications, le PDV doit effectuer des appels en temps réel à l’application administrative. Ces appels consomment de la capacité de calcul de votre application administrative. Par conséquent, lorsque vous définissez l’intervalle de notification, vous devez prendre en compte à la fois vos exigences métier et l’impact des appels en temps réel à l’application administrative. Une valeur de **0** (zéro) désactive les notifications.
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**. Sélectionnez le programme **1060** (**Personnel**) pour synchroniser les paramètres d’abonnement aux notifications, puis sélectionnez **Exécuter maintenant**. Ensuite, sélectionnez le programme **1070** (**Configuration des canaux**) pour synchroniser l’intervalle d’autorisation et sélectionnez **Exécuter maintenant**.

## <a name="view-notifications-in-the-pos"></a>Afficher les notifications dans le PDV

Après avoir terminé les étapes précédentes, les travailleurs peuvent afficher les notifications dans le PDV. Pour afficher les notifications, sélectionnez l’icône de notification dans le coin supérieur droit du PDV. Un volet de notification apparaît et affiche des notifications pour les opérations configurées pour le collaborateur. 

Pour l’opération d’**exécution des commandes**, le volet de notifications affichera les groupes suivants :

- **Prélèvement en magasin** – Ce groupe affiche le nombre de lignes de commande différentes dont le prélèvement est prévu à partir du magasin actuel. Vous pouvez sélectionner le nombre de commandes dans le groupe pour ouvrir l’opération **Exécution des commandes** avec un filtre de sorte que seules s’affichent les lignes de commande actives qui sont configurées pour être prélevées dans le magasin actuel.
- **Expédier à partir du magasin** – Ce groupe affiche le nombre de lignes de commande individuelles qui ont été configurées pour être expédiées à partir du magasin actuel de l’utilisateur. Vous pouvez sélectionner le nombre de commandes dans le groupe pour ouvrir l’opération **Exécution des commandes** avec une vue filtrée de sorte que seules s’affichent les lignes de commande actives qui sont configurées pour être prélevées dans le magasin actuel.

Pour l’opération de **rappel de commande**, le volet de notifications affichera les groupes suivants :

- **Commandes à traiter** – Ce groupe affiche le nombre de commandes configurées pour être prélevées ou expédiées pour le magasin actuel de l’utilisateur. Vous pouvez sélectionner le nombre de commandes dans le groupe pour ouvrir l’opération **Rappel de commande** avec une vue filtrée qui affiche uniquement les commandes en cours qui doivent être exécutées par le magasin actuel de l’utilisateur pour les scénarios de retrait en magasin ou d’expédition à partir du magasin.
- **Commandes à prélever** – Ce groupe affiche le nombre de commandes dont le prélèvement est prévu à partir du magasin actuel. Vous pouvez sélectionner le nombre de commandes dans le groupe pour ouvrir l’opération **Rappel de commande** avec une vue filtrée qui affiche uniquement les commandes en cours qui doivent être traitées pour retrait par le client dans le magasin actuel de l’utilisateur.
- **Commandes à expédier** – Ce groupe affiche le nombre de commandes à expédier à partir du magasin actuel de l’utilisateur. Vous pouvez sélectionner le nombre de commandes dans le groupe pour ouvrir l’opération **Rappel de commande** avec une vue filtrée qui affiche uniquement les commandes en cours qui doivent être traitées pour être expédiées à partir du magasin actuel de l’utilisateur.

Pour les notifications d’exécution des commandes et de rappel de commande, lorsque de nouvelles commandes sont prélevées par le processus, l’icône de notification change pour indiquer les nouvelles notifications et le nombre des groupes correspondants est mis à jour. Bien que les groupes soient actualisés à intervalles réguliers, les utilisateurs du PDV peuvent actualiser manuellement les groupes à tout moment en sélectionnant **Actualiser** en regard du groupe. Enfin, si un groupe dispose d’un nouvel article et que le collaborateur actuel ne l’a pas vu, le groupe affiche un symbole de rafale pour indiquer le nouveau contenu.

## <a name="enable-live-content-on-pos-buttons"></a>Activer le contenu en direct sur les boutons du PDV

Les boutons du PDV peuvent désormais afficher un nombre permettant aux travailleurs de déterminer facilement les tâches nécessitant leur attention immédiate. Pour afficher ce nombre sur un bouton du PDV, vous devez exécuter le paramétrage des notifications décrit plus haut dans cet article (autrement dit, vous devez activer les notifications pour une opération, paramétrer un intervalle de notification, puis mettre le groupe d’autorisations du PDV à jour pour le travailleur). En outre, vous devez ouvrir le concepteur de grille de boutons, afficher les propriétés du bouton, puis activer la case à cocher **Activer le contenu en direct**. Dans le champ **Alignement de contenu**, vous pouvez choisir si le nombre doit s’afficher dans le coin supérieur droit du bouton (**Haut-Droite**) ou au centre (**Centré**).

> [!NOTE]
> Le contenu en direct peut être activé pour les opérations uniquement si la case à cocher **Activer les notifications** a été activée pour elles sur la page **Opérations du PDV**, comme décrit précédemment dans cet article.

L’illustration suivante présente les paramètres de contenu en direct dans le concepteur de grille de boutons.

![Paramètres de contenu en direct dans le concepteur de grille de boutons.](./media/ButtonGridDesigner.png "Paramètres de contenu en direct dans le concepteur de grille de boutons")

Pour afficher le nombre de notifications sur un bouton, vous devez vous assurer que la mise en page de l’écran appropriée est mise à jour. Pour déterminer la mise en page de l’écran utilisée par le PDV, sélectionnez l’icône **Paramètres** dans l’angle supérieur droit et notez l’**ID mise en page de l’écran** et **Résolution de mise en page**. Maintenant, à l’aide du navigateur Edge, cliquez sur la page **Mise en page de l’écran**, recherchez l’**ID mise en page de l’écran** et **Résolution de mise en page** identifiés ci-dessus et activez la case à cocher **Activer le contenu en direct**. Accédez à **Retail et Commerce \> Informatique Retail et Commerce \> Programme de distribution** et exécutez les 1 090 tâches (registres) pour synchroniser les modifications de la mise en page.

![Trouver la mise en page de l’écran utilisée par le PDV.](./media/Choose_screen_layout.png "Trouver la mise en page de l’écran")

L’illustration suivante présente les effets de la sélection de **Haut-Droite** par rapport à **Centré** dans le champ **Alignement de contenu** pour les boutons de différentes tailles.

![Contenu en direct sur les boutons du PDV.](./media/ButtonsWithLiveContent.png "Contenu en direct sur les boutons du PDV")

[!INCLUDE[footer-include](../includes/footer-banner.md)]
