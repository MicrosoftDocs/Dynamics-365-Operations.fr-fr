---
title: Afficher les notifications dans le point de vente (PDV)
description: Cette rubrique décrit la procédure d'activation des notifications de commande dans le point de vente et l'infrastructure de notifications.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: c3b8e2774a189f2afefa757e7c4f3885b674918c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976786"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Afficher les notifications dans le point de vente (PDV)

[!include [banner](includes/banner.md)]

Dans l'environnement de vente au détail moderne, diverses tâches sont affectées aux associés du magasin, par exemple aider les clients, saisir des transactions, effectuer des inventaires et réceptionner les commandes en magasin. Le client du point de vente (PDV) fournit une application unique aux associés leur permettant d'effectuer toutes ces tâches et bien plus. Du fait que plusieurs tâches doivent être effectuées dans une journée, les associés peuvent devoir être informés lorsqu'un événement nécessite leur attention. L'infrastructure de notification dans le PDV permet aux détaillants de configurer des notifications basées sur les rôles. À compter de Dynamics 365 for Retail avec la mise à jour 5 de l'application, ces notifications peuvent être configurées uniquement pour les opérations de PDV.


Actuellement, le système peut afficher des notifications uniquement pour les opérations d'exécution de commande. Toutefois, comme l'infrastructure est conçue pour être extensible, les développeurs peuvent, le cas échéant, écrire un gestionnaire de notification pour toutes les opérations, et afficher les notifications pour cette opération dans le PDV.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Activer les notifications pour les opérations d'exécution des commandes

Pour activer les notifications pour les opérations d'exécution des commandes, effectuez les étapes suivantes.

1. Accédez à **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **PDV** &gt; **Opérations**.
2. Recherchez l'opération **Exécution de l'ordre**, puis activez la case à cocher **Activer les notifications** pour qu'elle indique que l'infrastructure de notification doit écouter le gestionnaire pour cette opération. Si le gestionnaire est implémenté, les notifications de cette opération seront ensuite affichées dans le PDV.
3. Accédez à **Retail et Commerce** &gt; **Employés** &gt; **Collaborateurs** &gt;, sous l'onglet Commerce, ouvrez les autorisations du PDV associées au collaborateur. Développez l'organisateur **Notifications**, ajoutez l'opération **Exécution de l'ordre**, puis définissez le champ **Ordre d'affichage** sur **1**. Si plusieurs notifications sont configurées, ce champ est utilisé pour réorganiser les notifications. Les notifications ayant une valeur d'**Ordre d'affichage** inférieure s'affichent avant les notifications ayant une valeur supérieure. Les notifications ayant une valeur d'**Ordre d'affichage** de **1** se situent en premier.

    Les notifications sont affichées uniquement pour les opérations ajoutées dans l'organisateur **Notifications**, et vous pouvez ajouter des opérations uniquement si la case à cocher **Activer les notifications** est sélectionnée pour ces opérations sur la page **Opérations du PDV**. En outre, les notifications d'une opération sont affichées pour les travailleurs uniquement si l'opération est ajoutée aux autorisations du PDV pour ceux-ci.

    > [!NOTE]
    > Les notifications peuvent être remplacées au niveau de l'utilisateur. Ouvrez l'enregistrement du travailleur, sélectionnez **Autorisations PDV**, puis modifiez l'abonnement à la notification de l'utilisateur.

4. Accédez à **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Profils POS** &gt; **Profils de fonctionnalité**. Dans le champ **Intervalle de notification**, spécifiez la fréquence à laquelle les notifications doivent être extraites. Pour certaines notifications, le PDV doit effectuer des appels en temps réel à l'application administrative. Ces appels consomment de la capacité de calcul de votre application administrative. Par conséquent, lorsque vous définissez l'intervalle de notification, vous devez prendre en compte à la fois vos exigences métier et l'impact des appels en temps réel à l'application administrative. Une valeur de **0** (zéro) désactive les notifications.
5. Accédez à **Retail et Commerce** &gt; **Informatique Retail et Commerce** &gt; **Programme de distribution**. Sélectionnez le programme **1060** (**Personnel**) pour synchroniser les paramètres d'abonnement aux notifications, puis sélectionnez **Exécuter maintenant**. Ensuite, sélectionnez le programme **1070** (**Configuration des canaux**) pour synchroniser l'intervalle d'autorisation et sélectionnez **Exécuter maintenant**.

## <a name="view-notifications-in-the-pos"></a>Afficher les notifications dans le PDV

Après avoir terminé les étapes précédentes, les travailleurs peuvent afficher les notifications dans le PDV. Pour afficher les notifications, appuyez sur l'icône de notification dans le coin supérieur droit du PDV. Un centre de notification s'affiche avec les notifications pour l'opération d'exécution des commandes. Le centre de notification doit afficher les groupes suivants dans l'opération d'exécution des commandes :

- **Prélèvement en magasin** : ce groupe affiche le nombre de commandes dont le mode de livraison est **Prélèvement** et le prélèvement est prévu à partir du magasin actuel. Vous pouvez appuyer sur le numéro du groupe pour ouvrir la page **Exécution de l'ordre**. Dans ce cas, la page est filtrée pour afficher uniquement les ordres actives paramétrées pour le prélèvement à partir du magasin actuel.
- **Expédier à partir du magasin** : ce groupe affiche le nombre de commandes dont le mode de livraison est **Expédition** et l'expédition est prévue à partir du magasin actuel. Vous pouvez appuyer sur le numéro du groupe pour ouvrir la page **Exécution de l'ordre**. Dans ce cas, la page est filtrée pour afficher uniquement les ordres actives paramétrées pour l'expédition à partir du magasin actuel.

Si de nouvelles commandes sont affectées au magasin pour exécution, l'icône de notification change pour indiquer les nouvelles notifications et le nombre des groupes correspondants est mis à jour. Bien que les groupes soient actualisés à intervalles réguliers, les utilisateurs du PDV peuvent actualiser manuellement les groupes à tout moment en sélectionnant le bouton **Actualiser** en regard du groupe. Enfin, si un groupe dispose d'un nouvel article et que le travailleur actuel ne l'a pas vu, le groupe affiche un symbole de rafale pour indiquer le nouveau contenu.

## <a name="enable-live-content-on-pos-buttons"></a>Activer le contenu en direct sur les boutons du PDV

Les boutons du PDV peuvent désormais afficher un nombre permettant aux travailleurs de déterminer facilement les tâches nécessitant leur attention immédiate. Pour afficher ce nombre sur un bouton du PDV, vous devez exécuter le paramétrage des notifications décrit plus haut dans cette rubrique (autrement dit, vous devez activer les notifications pour une opération, paramétrer un intervalle de notification, puis mettre le groupe d'autorisations du PDV à jour pour le travailleur). En outre, vous devez ouvrir le concepteur de grille de boutons, afficher les propriétés du bouton, puis activer la case à cocher **Activer le contenu en direct**. Dans le champ **Alignement de contenu**, vous pouvez choisir si le nombre doit s'afficher dans le coin supérieur droit du bouton (**Haut-Droite**) ou au centre (**Centré**).

> [!NOTE]
> Le contenu en direct peut être activé pour les opérations uniquement si la case à cocher **Activer les notifications** a été activée pour elles sur la page **Opérations du PDV**, comme décrit précédemment dans cette rubrique.

L'illustration suivante présente les paramètres de contenu en direct dans le concepteur de grille de boutons.

![Paramètres de contenu en direct dans le concepteur de grille de boutons](./media/ButtonGridDesigner.png "Paramètres de contenu en direct dans le concepteur de grille de boutons")

Pour afficher le nombre de notifications sur un bouton, vous devez vous assurer que la mise en page de l'écran appropriée est mise à jour. Pour déterminer la mise en page de l'écran utilisée par le PDV, sélectionnez l'icône **Paramètres** dans l'angle supérieur droit et notez l'**ID mise en page de l'écran** et **Résolution de mise en page**. Maintenant, à l'aide du navigateur Edge, cliquez sur la page **Mise en page de l'écran**, recherchez l'**ID mise en page de l'écran** et **Résolution de mise en page** identifiés ci-dessus et activez la case à cocher **Activer le contenu en direct**. Accédez à **Retail et Commerce \> Informatique Retail et Commerce \> Programme de distribution** et exécutez les 1 090 tâches (registres) pour synchroniser les modifications de la mise en page.


![Trouver la mise en page de l'écran utilisée par le PDV](./media/Choose_screen_layout.png "Trouver la mise en page de l'écran")

L'illustration suivante présente les effets de la sélection de **Haut-Droite** par rapport à **Centré** dans le champ **Alignement de contenu** pour les boutons de différentes tailles.

![Contenu en direct sur les boutons du PDV](./media/ButtonsWithLiveContent.png "Contenu en direct sur les boutons du PDV")
