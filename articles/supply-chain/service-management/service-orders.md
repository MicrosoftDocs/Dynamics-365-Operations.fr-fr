---
title: Commandes de service
description: "Une commande de service représente la visite d'un site client par un technicien de service à une date spécifique."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
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
ms.openlocfilehash: 647bbe9cca0167d33048ad07e092708f90b41fc3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="service-orders"></a>Commandes de service   

[!include [banner](../includes/banner.md)]


Une commande de service représente la visite d'un site client par un technicien de service à une date spécifique. Chaque commande de service comporte une ou plusieurs ligne de commande de service. Les lignes de commande de service représentent les heures de travail que doit exécuter le technicien chargé du service, ainsi que les articles liés, les dépenses et les frais.

Vous pouvez associer des tâches et des objets à une ligne de commande de service. Vous pouvez ensuite regrouper les lignes de commande de service par tâche ou par objet. Vous pouvez également associer les articles répertoriés dans le stock aux lignes de la commande de service.

## <a name="create-service-orders"></a>Créer des commandes de service

Vous pouvez créer des commandes de service sur la base d'un accord de service et des lignes de cet accord. Toutefois, vous pouvez créer des commandes de service associées à un accord de service uniquement pendant la période indiquée dans l'accord. Par exemple, si un accord de service est valide pour l'année civile 2011, vous pouvez créer des commandes de service pour l'accord entre le 1er janvier 2011 et le 31 décembre 2011.

Vous pouvez également créer des commandes de service de façon individuelle, sans les associer à un accord. Ces commandes de service permettent de gérer les visites non planifiées ou occasionnelles. Par exemple, au mois de mars, votre client décide de faire exécuter un service sur deux machines supplémentaires à celles spécifiées dans l'accord de service. Pour cette tâche, vous devez créer des commandes de service sans les associer à un accord.


> [!NOTE]
> <P>Pour créer des commandes de service sans les associer à un accord de service, vous devez activer la case à cocher <STRONG>Autoriser sans accord de service</STRONG> dans l'écran <STRONG>Paramètres de gestion des services</STRONG>.</P>

**Scénario**

Le scénario suivant décrit une autre situation dans laquelle il est utile de créer une commande de service qui n'est pas associée à un accord de service.

Le répartiteur de la société reçoit un appel concernant une demande de service d'urgence sur un ascenseur. Il n'y a plus le temps de paramétrer un accord de service et un projet pour le service. Par conséquent, le répartiteur crée une commande de service directement dans l'écran **Commandes de service**, associe la commande de service à un projet existant, puis crée les lignes de commande de service. Il crée également une relation de tâche ou d'objet pour une commande de service existante afin d'enregistrer des tâches qui ne sont pas associées à l'accord de service. Pour plus d'informations, voir [Création manuelle de commandes de service](create-service-orders-manually.md) et [Création de relations de tâches de service](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>Surveiller la progression des commandes de service

Pour surveiller la progression d'une commande de service via différentes équipes et divers processus de travail, vous pouvez définir un système d'étapes et des codes motif pour les commandes de service. Vous pouvez spécifier les actions autorisées pour chaque étape. Pour plus d'informations, voir [Créer des codes motifs](create-reason-codes.md).

**Exemple**

Une commande de service est approuvée par le répartiteur. Le répartiteur met à jour l'étape de la commande de service et spécifie un code motif qui indique que la commande de service a été lancée au technicien de service. Le technicien se rend sur le site du client et exécute le service.

## <a name="specify-item-requirements-for-service-orders"></a>Spécifier des demandes d'articles pour des commandes de service

Vous pouvez spécifier les articles en stock requis pour les commandes de service. Toutefois, la commande de service doit être associée à un projet. Les demandes d'articles pour les commandes de service sont traitées au travers d'un projet. 

**Exemple**

Les commandes de service créées à partir de l'accord de service sont ensuite traitées par le répartiteur. Pour la première commande de service, le répartiteur réalise que le technicien de service a besoin d'une pièce de rechange importante non disponible en stock. Il crée donc une demande d'article (pièce détachée) à partir de la commande de service.

## <a name="move-and-post-lines"></a>Déplacement et validation des lignes

Un technicien de service revient d'une visite de service et modifie et met à jour les lignes de la commande de service. Au cours de sa visite de service, il a exécuté une tâche de service qui devait être réalisée au cours de la visite suivante. Il déplace donc les lignes de la prochaine visite de service à la visite de service en cours. Le technicien valide ensuite la commande de service. Pour plus d'informations, voir [Déplacer des lignes de commande de service](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Annuler des commandes de service

L'une des autres commandes de service générée pour le mois de janvier est devenue obsolète en raison de l'annulation de la tâche. Le répartiteur de service annule donc la commande de service. Pour plus d'informations, voir [Annuler des commandes de service](cancel-service-orders.md).

## <a name="post-from-projects"></a>Validation à partir de projets

À la fin de chaque semaine, le répartiteur souhaite valider toutes les commandes de service associées à un projet spécifique. Par conséquent, il identifie le projet approprié dans l'écran **Projets** et valide les commandes de service terminées. Pour plus d'informations, voir [Valider des commandes de service (écran Classe)](https://technet.microsoft.com/en-us/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Supprimer des commandes de service

Au cours du second semestre, le client décide que les visites de service sont trop irrégulières. Vous devez créer une série de visites de service plus régulières pour la période restante de l'accord de service. Vous devez donc supprimer les commandes de service existantes, puis créer des commandes de service. Pour plus d'informations, voir [Supprimer des commandes de service](delete-service-orders.md).

## <a name="see-also"></a>Voir également :

[Commandes de service (écran)](https://technet.microsoft.com/en-us/library/aa554361\(v=ax.60\))

  



