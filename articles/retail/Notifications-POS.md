---
title: Afficher les notifications de commande dans POS
description: "Cette rubrique décrit la procédure d'activation des notifications de commande dans POS et l'infrastructure de notifications, qui peut être étendue à d'autres opérations."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ec6cb212766dd90fa9db7719a2119419ecb935c7
ms.openlocfilehash: aea36591a81f727059e37a958efa62a9ebde9d9d
ms.contentlocale: fr-fr
ms.lasthandoff: 12/20/2017

---

# <a name="display-notifications-in-point-of-sale"></a>Afficher les notifications dans POS

Dans l'environnement de vente au détail moderne actuel, diverses tâches sont affectées aux associés du magasin, par exemple aider les clients, saisir des transactions, effectuer des inventaires et réceptionner les commandes en magasin. Le client POS permet aux associés d'effectuer ces tâches et bien plus, dans une même application. Avec plusieurs tâches à effectuer dans une journée, les associés doivent être informés lorsqu'un événement nécessite leur attention. L'infrastructure de notification dans POS résout ce problème en autorisant les détaillants à configurer des notifications basées sur les rôles. Avec Dynamics 365 for Retail avec mise à jour 5 de l'application, ces notifications ne peuvent être configurées que pour les opérations POS.

Actuellement, le système permet d'afficher les notifications pour l'opération d'exécution des commandes. Cependant, l'infrastructure est conçue pour être extensible afin que, dans l'avenir, les développeurs puissent rechercher une opération dans le gestionnaire de notification et afficher les notifications dans POS.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Activer les notifications pour les opérations d'exécution des commandes

Pour activer les notifications pour les opérations d'exécution des commandes, consultez les étapes suivantes :

 - Accédez à la page **Opérations** (**Vente au détail** > **Paramétrage du canal** > **Paramétrage POS** > **POS** > **Opérations**).
 - Recherchez l'opération Exécution des commandes et activez la case à cocher **Activer les notifications** pour cette opération. L'infrastructure de notification doit rechercher l'opération d'exécution des commandes dans le gestionnaire. Si le gestionnaire est implémenté, les notifications s'affichent dans POS. Sinon, elles ne s'affichent pas pour cette opération.
- Accédez aux autorisations POS associées aux collaborateurs et sous l'organisateur **Notifications**, ajoutez l'opération Exécution des commandes avec 1 comme « ordre d'affichage ». Lorsque plusieurs notifications sont configurées, l'ordre d'affichage permet de réorganiser les notifications de haut en bas, 1 étant en haut. Seules les opérations pour lesquelles la case à cocher **Activer les notifications** a été activée peuvent être ajoutées. En outre, les notifications s'affichent uniquement pour les opérations qui ont été ajoutées ici et uniquement aux collaborateurs pour lesquels les opérations ont été ajoutées aux autorisations POS correspondantes. 

> [!NOTE]
> Les notifications peuvent être remplacées au niveau de l'utilisateur en accédant à l'enregistrement du collaborateur, en sélectionnant **Autorisations POS** et en modifiant l'abonnement aux notifications de cet utilisateur.

 - Accédez à la page **Profil de la fonctionnalité** (**Vente au détail** > **Paramétrage du canal** > **Paramétrage POS** > **Profils POS** > **Profils de fonctionnalité**). Mettez à jour la propriété **Intervalle de notification** pour définir l'intervalle d'affichage des notifications, en minutes. Il est recommandé de définir cette valeur sur 10 minutes pour éviter toute communication inutile avec le siège social. La définition de l'intervalle de notification sur « 0 » entraîne la désactivation des notifications.  

 - Accédez à **Vente au détail** > **Informatique au détail** > **Programme de distribution**. Sélectionnez le programme « 1060-Personnel » pour synchroniser les paramètres d'abonnement aux notifications, puis cliquez sur **Exécuter maintenant**. Ensuite, synchronisez l'intervalle d'autorisation en sélectionnant « 1070-Configuration des canaux » et en cliquant sur **Exécuter maintenant**. 

## <a name="view-notifications-in-pos"></a>Afficher les notifications dans POS

Une fois les étapes ci-dessus terminées, les collaborateurs pour lesquels les notifications sont paramétrées peuvent visualiser les notifications dans POS. Pour afficher les notifications, cliquez sur l'icône de notification dans la barre de titre du POS. Un centre de notification s'affiche avec les notifications pour l'opération d'exécution des commandes. Le centre de notification doit afficher les groupes suivants dans l'opération d'exécution des commandes : 

- **Commandes en attente** - Ce groupe affiche le nombre de commandes en attente, par exemple les commandes qui doivent être acceptées par un collaborateur POS disposant des autorisations requises pour l'exécution en magasin. Lorsque vous cliquez sur le nombre de commandes dans le groupe, la page **Exécution des commandes** s'ouvre. Elle est filtrée pour afficher uniquement les commandes en attente affectées au magasin pour exécution. Si les commandes sont automatiquement acceptées pour le magasin, le nombre de commandes pour ce groupe est égal à zéro.

- **Prélèvement en magasin** - Ce groupe affiche le nombre de commandes dont le mode de livraison est **Prélèvement** et le prélèvement est prévu à partir du magasin actuel. Lorsque vous cliquez sur le nombre de commandes dans le groupe, la page **Exécution des commandes** s'ouvre. Elle est filtrée pour afficher les commandes actives qui sont paramétrées pour être prélevées à partir du magasin actuel.

- **Expédier à partir du magasin** - Ce groupe affiche le nombre de commandes dont le mode de livraison est **Expédition** et l'expédition est prévue à partir du magasin actuel. Lorsque vous cliquez sur le nombre de commandes dans le groupe, la page **Exécution des commandes** s'ouvre. Elle est filtrée pour afficher les commandes actives qui sont paramétrées pour être expédiées à partir du magasin actuel.

Si de nouvelles commandes sont affectées au magasin pour exécution, l'icône de notification change pour indiquer les nouvelles notifications et le nombre des groupes correspondants est mis à jour. L'utilisateur peut également cliquer sur l'icône d'actualisation, en regard du nom de l'opération, pour mettre à jour immédiatement le nombre de commandes des groupes. Le nombre est également mis à jour à l'intervalle prédéfini. Tout groupe contenant un nouvel article, qui n'est pas visible par le collaborateur actuel, affiche une icône de rafale pour indiquer que ce groupe contient un nouvel article. Lorsque vous cliquez sur les vignettes des notifications, l'opération spécifique pour laquelle la notification est configurée s'ouvre. Dans les scénarios ci-dessus, lorsque vous cliquez sur les notifications, la page **Exécution des commandes** s'ouvre et affiche les paramètres appropriés : Commandes en attente, Prélèvement en magasin, Expédier à partir du magasin. 

> [!NOTE]
> Les notifications de commandes en attente seront activées dans une mise à jour à venir pour Dynamics 365 for Retail. 


