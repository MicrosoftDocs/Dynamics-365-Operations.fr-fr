---
title: Rendre les produits finis physiquement disponibles avant la validation dans les journaux
description: Lorsqu’un article manufacturé est signalé comme terminé, il est enregistré comme disponible pour un traitement physique ultérieur et un ou plusieurs journaux sont validés. Cet article décrit comment différer les validations de journal en leur permettant d’être traitées par un traitement par lots dans une file d’attente de messages.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ee767a5d7c3dca2681861802ae42d7a07217c54d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689338"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Rendre les produits finis physiquement disponibles avant la validation dans les journaux

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Lorsqu’un collaborateur signale un article manufacturé comme terminé, le système l’enregistre comme disponible pour un traitement physique ultérieur (tel qu’une expédition ou un rangement). Au cours de ce processus, un ou plusieurs journaux sont également publiés (tels que le rapport en tant que journal terminé, le journal des prélèvements et le journal des cartes de tournée). Si vous souhaitez rendre vos articles physiquement disponibles avant que toutes les validations aient été traitées, vous pouvez configurer le système pour différer les validations du journal. Les validations différées sont alors gérées par un traitement par lots qui traitera les validations selon les ressources du système.

L’illustration suivante montre comment les processus de validation des journaux sont appelés avec et sans validation différée.

![Le processus de rapport terminé avec et sans validation du journal différée.](media/deferred-posting-flowchart.png "Le processus de rapport terminé avec et sans validation du journal différée")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Activer la validation différée du journal pour votre système

Avant de pouvoir utiliser la validation différée du journal, vous devez l’activer sur votre système. Les administrateurs peuvent utiliser l’espace de travail [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Contrôle de la production*
- **Nom de la fonctionnalité :** *(Version préliminaire) Rendre les produits finis physiquement disponibles avant la validation dans les journaux*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Configurer les options de validation de journal pour la déclaration de fin

Les collaborateurs peuvent signaler que des éléments sont terminés à l’aide de l’un des clients suivants :

- Client Web
- Application mobile Warehouse Management
- Interface d’exécution de l’atelier de production

Le client Web utilise la même configuration de méthode de validation que l’application mobile Warehouse Management. Cependant, la méthode de validation utilisée par l’interface d’exécution de l’atelier de production doit être configurée séparément.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Définir les options de validation du journal pour le client Web et l’application mobile Warehouse Management

Dans l’application mobile, les collaborateurs signalent les éléments comme étant terminés en ouvrant un élément de menu de l’appareil mobile où la valeur **Processus de création de travail** est définie sur *Signaler comme terminé* ou *Signaler comme terminé et rangé*. Dans le client Web, les collaborateurs signalent les éléments comme terminés à partir de la page répertoriant **Tous les ordres de production** ou la page **Ordre de fabrication (détails)**. Vous pouvez configurer une méthode par défaut à l’échelle de l’entreprise et également configurer des remplacements spécifiques à l’entrepôt selon vos besoins.

Utilisez la procédure suivante pour configurer la méthode de validation par défaut à l’échelle de l’entreprise pour signaler les articles comme terminés à partir du client Web ou de l’application mobile Warehouse Management.

1. Accédez à **Contrôle de la production \>Paramétrage\> Paramètres de contrôle de la production**.
1. Dans l’onglet **Journaux**, dans la section **Journal de déclaration de fin**, définissez le champ **Méthode de validation** sur l’une des valeurs suivantes :

    - *Immédiat* – Lorsqu’un article est signalé comme terminé, le système traite entièrement toutes les validations de journal associées avant de marquer l’article fini comme physiquement disponible.
    - *Différé* – Lorsqu’un article est signalé comme terminé, le système marque l’article fini comme physiquement disponible et ajoute les validations de journal à la file d’attente des messages. Le système n’attend pas que les validations soient entièrement traitées pour marquer l’article fini comme physiquement disponible.

Utilisez la procédure suivante pour configurer des remplacements spécifiques à l’entrepôt pour la méthode de validation par défaut qui est configurée sur la page **Paramètres de contrôle de production**.

1. Accédez à **Gestion des entrepôts \> Paramétrage \> Décomposition de l’inventaire \> Entrepôts**.
1. Sélectionnez l’entrepôt à configurer.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Dans le raccourci **Entrepôt**, dans la section **Ordres de production**, définissez le champ **Méthode de validation** sur l’une des valeurs suivantes :

    - *Hériter* – L’entrepôt sélectionné hérite du paramètre défini sur la page **Paramètres de contrôle de production**.
    - *Immédiat* – Lorsqu’un article est signalé comme terminé, le système traite entièrement toutes les validations de journal associées avant de marquer l’article fini comme physiquement disponible.
    - *Différé* – Lorsqu’un article est signalé comme terminé, le système marque l’article fini comme physiquement disponible et ajoute les validations de journal à la file d’attente des messages. Le système n’attend pas que les validations soient entièrement traitées pour marquer l’article fini comme physiquement disponible.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Définir les options de validation de journal pour l’interface d’exécution de l’atelier de production

Utilisez la procédure suivante pour configurer la méthode de validation utilisée lorsque les articles sont signalés comme terminés à partir de l’interface d’exécution de l’atelier de production.

1. Accédez à **Contrôle de la production\> Paramétrage \> Contrôle et suivi de la production \> Valeurs par défaut de l’ordre de fabrication**.
1. Dans l’onglet **Signaler comme terminé**, dans la section **Journal de déclaration de fin**, définissez le champ **Méthode de validation** sur l’une des valeurs suivantes :

    - *Immédiat* – Lorsqu’un article est signalé comme terminé, le système traite entièrement toutes les validations de journal associées avant de marquer l’article fini comme physiquement disponible.
    - *Différé* – Lorsqu’un article est signalé comme terminé, le système marque l’article fini comme physiquement disponible et ajoute les validations de journal à la file d’attente des messages. Le système n’attend pas que les validations soient entièrement traitées pour marquer l’article fini comme physiquement disponible.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Planifier le travail par lots du processeur de messages pour traiter les validations différées

Le traitement par lots du processeur de messages est responsable du traitement des validations de journal une fois qu’elles ont été placées en file d’attente. Pour vous assurer que vos validations de journal sont traitées, vous devez configurer ce travail pour qu’il s’exécute à intervalle régulier. Suivez la procédure suivante pour configurer les tâches par lot requises.

1. Accédez à **Administration du système \> Processeur de messages \> Processeur de messages**.
1. Sur le raccourci **Paramètres**, définissez le champ **File d’attente de messages** sur *Production*.
1. Dans le raccourci **Exécuter en arrière-plan**, définissez l’option **Traitement par lots** sur *Oui*. Configurez ensuite un programme récurrent et configurez d’autres paramètres si nécessaire. Les paramètres fonctionnent comme pour d’autres types de [tâches en arrière-plan](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>Suivez l’avancement de vos validations différées

Les validations de journal différées sont placées en file d’attente en tant que *messages du processeur de messages* qui attendent d’être traités par le *processeur de messages*. Le processeur de messages doit être configuré pour s’exécuter en tant que travail par lots planifié. Pour afficher les messages de validation différée qui ont été ou seront traités par le processeur de messages, accédez à **Contrôle de production \> Ordres de production \> Validation d’ordre de production différée**.

### <a name="message-grid-columns-and-filters"></a>Colonnes et filtres de la grille de messages

Vous pouvez utiliser les champs en haut de la page **Validation d’ordre de production différée** pour trouver les messages que vous recherchez.

Les filtres disponibles sont les suivants :

- **Type de message** – Spécifiez le type de messages affichés dans la grille.
- **État du message** – Spécifiez l’état des messages affichés dans la grille. Les états suivants existent :

    - *En file d’attente* – Le message est prêt à être traité par le processeur de messages.
    - *Traité* – Le message a été traité par le processeur de messages.
    - *Annulé* – Le message n’a pas pu être traité lors de la dernière tentative et a ensuite été annulé par l’utilisateur.
    - *Échec* – Le message n’a pas pu être traité lors de la dernière tentative. Le système réessayera trois fois de traiter les messages en échec. Il abandonnera après ces trois tentatives et définira l’état *Échec*. Notez que vous ne pouvez pas annuler ou modifier manuellement un message avant la fin de la dernière de ces trois tentatives.

- **Contenu du message** – Ce filtre lance une recherche en texte intégral du contenu du message. (Le contenu du message n’est pas affiché dans la grille.) Le filtre traite la plupart des symboles spéciaux (tels que « - ») comme des espaces et traite tous les caractères d’espacement comme des opérateurs booléens OR. Par exemple, si vous recherchez une valeur `journalid` spécifique équivalente à *USMF-123456*, le système recherchera tous les messages contenant soit « USMF », soit « 123456 ». Dans ce cas, la liste des résultats risque d’être longue. Par conséquent, il est préférable de saisir uniquement *123456*, car cela renverra des résultats plus spécifiques.

Vous pouvez également trier et filtrer la liste en sélectionnant l’un des en-têtes de colonne et en entrant des critères dans la boîte de dialogue déroulante.

### <a name="view-the-message-log-message-content-and-details"></a>Afficher le journal des messages, le contenu des messages et les détails

Vous trouverez des informations détaillées sur un message en le sélectionnant dans la grille, puis en sélectionnant les onglets **Journal** ou **Contenu brut** sous la grille de messages, où chaque événement de traitement est affiché.

La barre d’outils sur l’onglet **Journal** comprend les boutons suivants :

- **Journal** – Sélectionnez ce bouton pour afficher les résultats du traitement. Ce bouton est particulièrement utile lorsque les messages indiquent une valeur **Résultat du traitement** définie sur *Échec*, et que vous souhaitez connaître les raisons de l’échec du traitement.
- **Groupe** – Plusieurs opérations de traitement de messages peuvent s’exécuter dans le cadre du même traitement par lots. Sélectionnez ce bouton pour afficher ces données détaillées. Par exemple, vous pouvez voir s’il existe des dépendances qui obligent un ordre de traitement spécifique pour certains messages.

### <a name="manually-process-or-cancel-a-message"></a>Traiter ou annuler manuellement un message

Vous pouvez traiter ou annuler manuellement un message si nécessaire, en fonction de son état actuel. Sélectionnez le message dans la grille, puis sélectionnez **Traiter** ou alors **Annuler** sur le volet Actions.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Configurer des événements commerciaux pour envoyer des alertes en cas d’échec du traitement des résultats

Vous pouvez configurer des [événements commerciaux](../../fin-ops-core/dev-itpro/business-events/home-page.md) qui vous préviennent en cas d’échec de traitement. Accédez à **Administration système \> Configuration \> Événements commerciaux \> Catalogue des événements commerciaux**, et activez l’événement commercial intitulé *Messages du processeur de messages traités*.

Dans le cadre du processus d’activation, vous êtes invité à spécifier si l’événement est spécifique à une entité juridique ou s’il s’applique à toutes les entités juridiques. Vous êtes également invité à fournir une valeur **Nom du point de terminaison**. Cette valeur doit être définie en premier.

> [!NOTE]
> Si le champ **Quand un événement commercial se produit** est défini sur *Microsoft Power Automate* (plutôt que *HTTPS*, par exemple), la valeur **Nom de point de terminaison** sera automatiquement créé dans la gestion Supply Chain Management en fonction de la configuration *Microsoft Power Automate*.
