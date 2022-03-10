---
title: Configurer un appareil pour exécuter l’interface d’exécution de l’atelier de production
description: L’interface d’exécution de l’atelier de production est configurée pour chaque appareil de l’atelier de production. Les entreprises configurent généralement chaque appareil différemment, en fonction de l’objectif visé par l’appareil. Par exemple, une entreprise peut avoir un appareil dans la zone de réception, où les travailleurs pointent à l’entrée et à la sortie, et un autre dans l’atelier, où les travailleurs gèrent leur travail.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f0be79b54a279893f93d41981342e42c8880f059
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752830"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Configurer un appareil pour exécuter l’interface d’exécution de l’atelier de production

[!include [banner](../includes/banner.md)]

L’interface d’exécution de l’atelier de production est configurée pour chaque appareil de l’atelier de production. Les entreprises configurent généralement chaque appareil différemment, en fonction de l’objectif visé par l’appareil. Par exemple, une entreprise peut avoir un appareil dans la zone de réception, où les travailleurs pointent à l’entrée et à la sortie, et un autre dans l’atelier, où les travailleurs gèrent leur travail.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Définir la configuration et les filtres pour un appareil spécifique

Pour définir la configuration et les filtres de tâches d’un périphérique, connectez-vous à la page **Exécution de l’atelier de production** en utilisant un compte qui a un rôle de sécurité qui inclut le droit *Supervision de mise à jour du temps*. (Parmi les rôles de sécurité prêts à l’emploi, seuls *Superviseur de l’atelier* a ce droit.) Suivez ensuite ces étapes.

1. Accédez à l’appareil que vous souhaitez configurer et connectez-vous à Microsoft Dynamics 365 Supply Chain Management en tant que superviseur d’atelier. (Utilisez un compte qui inclut le droit *Supervision de mise à jour du temps*.)
1. Assurez-vous qu’une configuration est disponible pour l’appareil que vous configurez. Si aucune configuration n’existe déjà, une configuration par défaut est fournie. Pour plus d’informations sur le paramétrage d’une configuration, consultez [Configurer l’interface d’exécution de l’atelier de production](production-floor-execution-configure.md).
1. Accédez à **Contrôle de la production \> Contrôle et suivi de la production \> Exécution de l’atelier de production**.

    Si l’interface d’exécution de l’atelier de production a déjà été configurée au moins une fois sur l’appareil actuel, une page de connexion apparaît. Sinon, une page d’accueil apparaît.

1. Sur la page de connexion ou sur la page d’accueil, sélectionnez **Configurer**.
1. Sélectionnez une configuration dans la liste.
1. Sélectionnez **Suivant**.
1. Sélectionnez un ou plusieurs filtres à appliquer à l’appareil actuel. Ces filtres permettront de garantir que seules les tâches pertinentes sont affichées sur l’appareil. Pour définir un filtre, sélectionnez le type de filtre pour ouvrir une liste de valeurs, puis sélectionnez la valeur sur laquelle filtrer. Les filtres disponibles sont les suivants :

    - **Unité de production** - Ce filtre est le filtre de plus haut niveau. Il fait généralement référence à une vaste zone de travail contenant plusieurs groupes de ressources et des ressources individuelles.
    - **Groupe de ressources** - Ce filtre est un filtre de niveau intermédiaire. Il fait généralement référence à un ensemble de ressources associées dans une zone limitée de l’espace de travail. Si vous sélectionnez un filtre **Unité de production** en premier, la liste des groupes de ressources n’affiche que les groupes de cette unité. Sinon, il affiche tous les groupes de ressources disponibles.
    - **Ressource** - Ce filtre est le filtre le plus spécifique. Il fait généralement référence à une machine spécifique ou à une autre ressource unique. Si vous sélectionnez un filtre **Groupe de ressources** et/ou **Unité de production** en premier, la liste des ressources n’affiche que les ressources de ce groupe et/ou cette unité. Sinon, il affiche toutes les ressources disponibles.

1. Cliquez sur **OK**.
1. La page de connexion s’affiche et votre appareil est prêt à être utilisé.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Autoriser un collaborateur à remplacer les filtres par défaut

Vous pouvez autoriser des travailleurs spécifiques à modifier les paramètres de filtre sur tout appareil qu’ils utilisent. Pour les travailleurs qui ont cette autorisation, l’interface d’exécution de l’atelier de production fournit un bouton **Filtre** sur les pages **Toutes les tâches** et **Tâche active**.

> [!NOTE]
> Si un collaborateur modifie un filtre, le nouveau filtre s’applique à partir de ce moment-là, pour tous les utilisateurs qui se connectent à l’appareil.

Pour permettre à un collaborateur de remplacer les filtres de travail par défaut qui ont été configurés pour un appareil, procédez comme suit.

1. Accédez à **Pointage \> Paramétrage \> Enregistrement du temps des collaborateurs**.
1. Sélectionnez un travailleur dans la liste pour ouvrir la page **Enregistrement du temps des collaborateurs** de ce travailleur.
1. Sur l’onglet **Enregistrement du temps**, définissez l’option **Définir des filtres** sur *Oui*.

## <a name="run-the-interface-in-full-screen-mode"></a>Exécuter l’interface en mode plein écran

Souvent, vous exécuterez l’interface d’exécution de l’atelier de production sur un appareil utilisé exclusivement à cette fin. Par conséquent, il peut être judicieux d’exécuter l’interface en mode plein écran, sans afficher la navigation et / ou le navigateur Chrome.

- Pour masquer le volet de navigation affiché dans Supply Chain Management, ajoutez le texte suivant à la fin de l’URL dans la barre d’adresse du navigateur : `\&limitednav=true`.
- Pour masquer également la barre d’adresse du navigateur, utilisez le mode plein écran natif du navigateur. (Pour obtenir des instructions, consultez la documentation de votre navigateur.)

La partie supérieure de l’illustration suivante montre à quoi ressemble l’interface par défaut. La partie inférieure montre à quoi il ressemble en mode plein écran lorsque le volet de navigation est masqué.

![Interface standard ou plein écran.](media/pfei-full-screen.png "Interface standard ou plein écran")

## <a name="extend-the-session-past-12-hours"></a>Prolonger la session au-delà de 12 heures

Par défaut, l’interface d’exécution de l’atelier de production se déconnecte automatiquement si personne ne l’utilise pendant 12 heures. Un utilisateur de Supply Chain Management doit ensuite se reconnecter. Cependant, vous pouvez prolonger le délai d’expiration jusqu’à 90 jours.

Pour prolonger le délai d’expiration, connectez-vous à Supply Chain Management et accédez à **Administration système \> Utilisateurs \> Extensions de session**. Spécifiez le compte d’utilisateur de Supply Chain Management utilisé pour se connecter à l’appareil et le nombre d’heures pendant lesquelles la session doit rester active.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
