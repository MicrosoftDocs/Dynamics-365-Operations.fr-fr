---
title: Paramètres de l’entrepôt pour le traitement des vagues
description: Cet article décrit comment définir les paramètres d’entrepôt pour le traitement des vagues. Vous pouvez utiliser le traitement de vagues pour regrouper les travaux de prélèvement pour plusieurs ordres d’exécution dans une vague unique.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2a64cba837faf84f3e8470a9831d1641213a5cc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909610"
---
# <a name="warehouse-parameters-for-wave-processing"></a>Paramètres de l’entrepôt pour le traitement des vagues

[!include [banner](../includes/banner.md)]

Cet article décrit comment définir les paramètres d’entrepôt pour le traitement des vagues. Vous pouvez utiliser le traitement de vagues pour regrouper les travaux de prélèvement pour plusieurs ordres d’exécution dans une vague unique.

Pour utiliser le traitement des vagues, spécifiez les éléments suivants sur la page **Paramètres de gestion de l’entrepôt** :

- Si vous pouvez traiter les vagues à l’aide d’un traitement par lots.
- Si vous collectez des informations dans un fichier journal lors du traitement des vagues.

## <a name="set-up-warehouse-management-parameters-for-wave-processing"></a>Définir les paramètres de gestion d’entrepôt pour le traitement des vagues

Pour définir les paramètres d’entrepôt pour le traitement des vagues, procédez comme suit :

1. Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Paramètres de gestion des entrepôts**.

1. Sur le raccourci **Traitement des vagues**, définissez les paramètres suivants :

    - **Groupe de traitements par lots pour le traitement de la vague** : sélectionnez le groupe de traitements par lots à utiliser lorsque vous traitez les vagues à l’aide de traitements par lots. Le groupe de traitements par lots spécifie le serveur sur lequel les traitements par lots seront exécutés.
    - **Traiter les vagues dans des traitements par lots** : choisissez d’activer ou non le traitement automatique des vagues en traitements par lots. Vous devez définir cette option sur *Oui* pour utiliser le traitement en parallèle. Vous pouvez paramétrer le traitement par lots sur la page **Traiter les vagues**. (Voir également la note à la fin de cette liste.)
    - **Créer un journal de progression de la vague** : choisissez si le système doit générer un enregistrement de journal à chaque début et fin de l’allocation d’un article et de ses dimensions. Vous ne devez activer ce journal que lorsque vous en avez besoin, par exemple, lors des tests initiaux ou pour la résolution des problèmes. Pour plus d’informations, voir [Répartition des vagues](wave-allocation-method.md).
    - **Créer un journal d’historique de traitement des vagues** : choisissez d’enregistrer automatiquement les informations sur une vague dans un fichier journal après le traitement de la vague, y compris pendant le traitement parallèle des allocations en attente. En règle générale, vous ne devez activer cette option que lors du dépannage, car cela ajoute une surcharge supplémentaire. Pour afficher le journal, accédez à **Gestion d’entrepôt \> Vagues sortantes \> Journal d’historique de traitement des vagues**. Pour plus d’informations, voir [Création et traitement des vagues](wave-processing.md).
    - **Créer un journal d’historique de mise en conteneur** : choisissez d’enregistrer automatiquement les informations sur la mise en conteneur d’une vague dans un fichier journal après le traitement de la vague. Pour afficher le journal, accédez à **Gestion d’entrepôt \> Emballage et mise en conteneur \> Historique de la mise en conteneur**.
    - **Attendre le verrouillage (ms)**  : permet d’entrer le temps, exprimé en millisecondes, pendant lequel une étape de répartition attendra une ressource système qui est verrouillée par une autre étape de répartition. Lorsque ce temps est dépassé, la vague n’est pas traitée et un message d’erreur s’affiche.

1. Sur le raccourci **Libération dans l’entrepôt**, définissez le paramètre suivant :

    - **Erreur en cas d’échec du lot** : choisissez de générer ou non une erreur en cas d’échec d’un traitement par lots de libération dans l’entrepôt. Si cette option est activée, les travaux ayant échoué se termineront avec un statut *Erreur*. Si elle est désactivée, les travaux ayant échoué se termineront avec un statut *Terminé*.

> [!NOTE]
> Dans le modèle de vague utilisé pour traiter la vague, vous pouvez spécifier les paramètres pour l’automatisation du traitement de la vague. Si vous paramétrez un programme pour le traitement par lots, vous devez coordonner le temps avec les paramètres d’automatisation dans le modèle de vague. Pour plus d’informations, voir [Création d ’un modèle de vague](wave-templates.md).
>
> Si vous utilisez la *Gestion du transport* et la *Gestion avancée des entrepôts*, vous pouvez spécifier si les charges sont consolidées lorsque vous traitez une vague. Par exemple, cela est utile lorsque plusieurs petites charges peuvent être expédiées simultanément. Pour consolider les charges lorsque vous traitez une vague, sur l’onglet **Charges**, cochez la case **Consolider les charges pendant le traitement des vagues**.</P>

## <a name="set-up-full-or-partial-reservation-for-production-waves"></a>Paramétrer une réservation complète ou partielle pour les vagues de production

Pour les commandes client et des commandes kanban, le stock doit être réservé avant que la commande ne soit libérée dans l’entrepôt. Sinon, les articles ou les lignes de répartition ne pourront pas être traités dans une vague. Toutefois, les ordres de fabrication sont légèrement plus flexibles. Pour les ordres de fabrication, vous pouvez spécifier ce qui suit :

- Autoriser la libération des ordres de fabrication dans l’entrepôt même si toutes les matières premières ne peuvent être réservées. Si vous sélectionnez cette option, vous devez répéter manuellement le processus de libération dans l’entrepôt lorsque des matières premières supplémentaires deviennent disponibles. Par exemple, cela peut s’avérer utile si vous disposez des matières premières nécessaires pour démarrer une production, et si pouvez attendre jusqu’à ce que les matières premières supplémentaires deviennent disponibles.
- Exiger que toutes les matières premières soient réservées avant qu’une commande puisse être libérée dans l’entrepôt.

Pour exiger la réservation complète ou autoriser la réservation partielle, procédez comme suit :

1. Accédez à **Contrôle de la production** \> **Paramétrage** \> **Paramètres de contrôle de la production**.
1. Sur l’onglet **Général**, dans le champ **Libération dans l’entrepôt**, sélectionnez le paramètre par défaut.
