---
title: Correction de l’erreur du moteur de planification « Capacité suffisante introuvable » et de la capacité finie
description: Cette rubrique fournit des informations sur les raisons de l’impossibilité de programmer l’ordre de fabrication %1 et sur les moyens de résolution du problème. Capacité suffisante introuvable ».
author: ChristianRytt
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: becd537d37a8ba8931f2598dccbae8554a4d168e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985028"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Correction de l’erreur du moteur de planification « Capacité suffisante introuvable »

[!include [banner](../includes/banner.md)]

Lorsque vous exécutez la planification, vous pouvez recevoir le message d’erreur suivant :

> Impossible de planifier l’ordre de fabrication %1. Capacité suffisante introuvable.

Il existe plusieurs raisons pour lesquelles le moteur de planification peut échouer et émettre ce message d’erreur. Cette rubrique fournit des instructions qui vous aideront à trouver la cause première de l’erreur, puis à l’atténuer.

## <a name="review-the-applicable-resources"></a>Passer en revue les ressources concernées

L’erreur peut se produire si aucune ressource applicable ne satisfait aux besoins de l’opération sur le site de l’ordre de fabrication.

Pour passer en revue les ressources concernées, procédez comme suit.

1. Accédez à **Contrôle de production \> Ordres de fabrication \> Tous les ordres de fabrication**, et ouvrez ou sélectionnez l’ordre de fabrication qui ne peut pas être planifié.
1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Détails de la production**, sélectionnez **Gamme**.
1. Sur la page **Gamme de production**, sélectionnez l’opération puis, dans le volet Actions, sélectionnez **Ressources applicables**.
1. Dans la boîte de dialogue **Ressources applicables**, définissez le champ **Utiliser les besoins pour** sur *Ordonnancement* ou *Planification de tâche*, selon le type de planification que vous utilisez.
1. Assurez-vous qu’il existe des ressources applicables sur le site de l’ordre de fabrication.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Passer en revue les calendriers associés aux ressources

L’erreur peut se produire si aucun calendrier n’est associé à la ressource ou au groupe de ressources, ou si le calendrier associé n’est pas correctement configuré (par exemple, il ne comporte pas d’heures de travail ou son efficacité en pourcentage est de 0 \[zéro\]).

Pour vérifier qu’un calendrier est associé à la ressource ou au groupe de ressources, procédez comme suit.

1. Accédez à **Contrôle de production \> Ordres de fabrication \> Tous les ordres de fabrication**, et ouvrez ou sélectionnez l’ordre de fabrication qui ne peut pas être planifié.
1. Dans le volet Actions, sous l’onglet **Ordre de fabrication**, dans le groupe **Détails de la production**, sélectionnez **Gamme**.
1. Sur la page **Gamme de production**, sélectionnez l’opération puis, dans le volet Actions, sélectionnez **Ressources applicables**.
1. Dans la boîte de dialogue **Ressources applicables**, sélectionnez la ressource, puis sélectionnez **Afficher la ressource**. Sinon, sélectionnez et maintenez sélectionné (ou cliquez avec le bouton droit) dans le champ **Groupe de ressources**, puis sélectionnez **Afficher les détails**.
1. Sur la page **Ressources** ou la page **Groupes de ressources**, dans le raccourci **Calendriers**, assurez-vous qu’un calendrier est associé à la ressource ou au groupe de ressources.

> [!NOTE]
> Si l’erreur se produit lors de l’ordonnancement, vous devez vous assurer qu’un calendrier est associé à tous les groupes de ressources applicables.

Pour examiner la configuration du calendrier, procédez comme suit.

1. Accédez à **Administration d’organisation \> Paramétrage \> Calendriers \> Calendriers**, puis sélectionnez le calendrier associé à la ressource ou au groupe de ressources.
1. Dans le volet Actions, sélectionnez **Heures de travail**.
1. Sur la page **Heures de travail**, assurez-vous que la page n’est pas vierge. De plus, pour les jours qui vous intéressent, assurez-vous que le champ **Contrôle** n’est pas défini sur *Fermé*, que les heures de travail existent, et que le champ **Efficacité en pourcentage** n’est pas défini sur *0* (zéro).

Si le calendrier est associé au calendrier de base, vous devez également revoir la configuration du calendrier de base.

> [!NOTE]
> Dans l’ordonnancement, le calendrier du groupe de ressources est utilisé pour déterminer les heures et dates de début et de fin de chaque opération. Il limite également la durée pendant laquelle le système peut planifier une opération spécifique pour un jour spécifique dans un groupe de ressources spécifique. Par exemple, si les heures de travail d’un groupe de ressources d’un jour spécifique sont comprises entre 8 h 00 et 16 h 00, la charge qu’une opération exerce sur le groupe de ressources ne peut pas dépasser la charge qui peut tenir dans huit heures, quelle que soit la capacité disponible du groupe de ressources ce jour-là. Toutefois, la capacité disponible peut limiter davantage la charge.

## <a name="review-the-scheduling-parameters"></a>Passer en revue les paramètres de planification

Pour garantir de bonnes performances, le moteur de planification recherchera une ressource uniquement pendant une durée spécifique et un nombre spécifique de conflits de planification.

Pour examiner les paramètres de planification, procédez comme suit.

1. Accédez à **Administration d’organisation \> Paramétrage \> Paramètres de planification**.
1. Utilisez l’une des procédures suivantes :

    - Si l’option **Délai de planification activé** est définie sur *Non*, passez à l’étape 3.
    - Si l’option **Délai de planification activé** est définie sur *Oui*, augmentez la valeur du champ **Temps de planification maximum par séquence** de manière à accorder plus de temps à la réalisation du traitement.

1. Utilisez l’une des procédures suivantes :

    - Si l’option **Délai d’optimisation de la planification activé** est définie sur *Non*, passez à l’étape 4.
    - Si l’option **Délai d’optimisation de la planification activé** est définie sur *Oui*, augmentez la valeur du champ **Délai des tentatives d’optimisation** de manière à accorder plus de temps à la réalisation du traitement.

1. Si vous avez modifié l’un des paramètres de la page, reprogrammez la commande pour réessayer.

## <a name="review-capacity"></a>Examiner la capacité

L’erreur peut se produire lorsque vous effectuez une planification finie, mais qu’il n’y a pas de capacité libre.

Pour effectuer une planification de capacité infinie, procédez comme suit.

1. Accédez à **Contrôle de production \> Ordres de fabrication \> Tous les ordres de fabrication**, et ouvrez ou sélectionnez l’ordre de fabrication qui ne peut pas être planifié.
1. Dans le volet Actions, dans l’onglet **Programme**, dans le groupe **Ordre de fabrication**, sélectionnez **Planifier les opérations** ou **Planifier les tâches**.
1. Dans la boîte de dialogue **Ordonnancement** ou **Planification de tâche**, définissez l’option **Capacité finie** sur *Non*.
1. Sélectionnez **OK** pour planifier la commande.

Pour examiner la capacité disponible sur la ressource, procédez comme suit.

1. Accédez à **Administration d’organisation \> Ressources \> Ressources**, puis sélectionnez une ressource applicable à la commande qui ne peut pas être planifiée.
1. Dans le volet Actions, dans l’onglet **Ressource**, dans le groupe **Vue**, sélectionnez **Capacité maximale** ou **Charge maximale, graphique**, et assurez-vous qu’il y a de la capacité disponible.

Pour examiner la capacité disponible sur le groupe de ressources, procédez comme suit.

1. Accédez à **Administration d’organisation \> Ressources \> Groupe de ressources**, puis sélectionnez un groupe de ressources applicable à la commande qui ne peut pas être planifiée.
1. Dans le volet Actions, dans l’onglet **Groupe de ressources**, dans le groupe **Vue**, sélectionnez **Capacité maximale** ou **Charge maximale, graphique**, et assurez-vous qu’il y a de la capacité disponible.

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>La planification générale réserve une ressource lorsque le calendrier des ressources est fermé

Lors de l’utilisation de la planification des opérations, la planification générale planifiera la capacité en fonction du calendrier du groupe de ressources principal. Elle réserve l’opération secondaire en même temps que l’opération primaire et ne tient pas compte des calendriers ou de la capacité de l’opération secondaire. Cela peut entraîner la planification de l’ordre de fabrication sur un calendrier fermé ou à un moment où l’opération secondaire n’est pas disponible (calendrier fermé, pas de capacité).

Lors de l’utilisation de la planification des tâches, la planification principale prendra en compte la capacité et le calendrier de l’opération principale et secondaire lors de la planification de l’ordre. Pour que l’ordre soit planifié, les calendriers des ressources des deux opérations doivent être ouverts et avoir une capacité disponible.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
