---
title: Utilisation de l’interface d’exécution de l’atelier de production par les collaborateurs
description: Cette rubrique décrit comment utiliser l’interface d’exécution de l’atelier de production du point de vue d’un travailleur.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e84df8aa4f3e4079cf97d35b0d67a75d68dbb4b2
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860531"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Utilisation de l’interface d’exécution de l’atelier de production par les collaborateurs

[!include [banner](../includes/banner.md)]

L’interface d’exécution de l’atelier de production est optimisée pour l’interaction tactile. Sa conception offre un contraste visuel qui répond aux exigences d’accessibilité pour les environnements d’atelier. Elle offre toutes les mêmes capacités fonctionnelles que le périphérique de bon de travail. Cependant, elle permet également de démarrer plusieurs tâches en parallèle à partir d’une liste de tâches. (Cette capacité est également connue sous le nom de *regroupement des tâches*.) De plus, à partir d’une liste de tâches, les travailleurs peuvent ouvrir un guide qui a été créé dans le Guide Microsoft Dynamics 365. De cette façon, ils peuvent obtenir des instructions visuelles sur un HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Connexion à l’interface d’exécution de l’atelier de production en tant que collaborateur

Avant que les travailleurs puissent commencer à utiliser l’appareil, un superviseur ou un membre du personnel technique doit le préparer et ouvrir la bonne page dans Dynamics 365 Supply Chain Management. Pour plus d’informations sur le paramétrage de l’appareil, consultez [Configurer un appareil pour exécuter l’interface d’exécution de l’atelier de production](production-floor-execution-setup.md).

Une fois l’appareil préparé, la page de connexion apparaît dessus. Cette page affiche des informations sur le statut des tâches pour la cellule de travail locale. Ces informations sont mises à jour périodiquement. Sur la page, les employés utilisent leur ID badge pour se connecter. Bien que les employés ne soient pas obligés d’avoir un compte utilisateur pour Supply Chain Management, ils doivent avoir un compte *collaborateur à temps enregistré* qu’ils peuvent utiliser lorsqu’ils se connectent.

![Page de connexion à l’interface d’exécution de l’atelier de production.](media/pfei-sign-in-page.png "Page de connexion à l’interface d’exécution de l’atelier de production")

Les sections restantes de cette rubrique décrivent comment les travailleurs interagissent avec l’interface.

## <a name="all-jobs-tab"></a>Onglet Toutes les tâches

L’onglet **Toutes les tâches** fournit une liste de tâches qui affiche toutes les tâches de production dont le statut est *Non commencé*, *Arrêté* ou *Commencé*. (Ce nom d’onglet est personnalisable et peut être différent pour votre système.)

![Onglet Toutes les tâches.](media/pfei-all-jobs-tab.png "Onglet Toutes les tâches")

La liste des tâches comprend les colonnes suivantes. Les numéros correspondent aux numéros dans l’illustration précédente.

1. **Colonne de sélection** - La colonne la plus à gauche utilise des coches pour indiquer les tâches qui ont été sélectionnés par le travailleur. Les travailleurs peuvent sélectionner plusieurs tâches dans la liste en même temps. Pour sélectionner toutes les tâches de la liste, cochez la case dans l’en-tête de colonne. Lorsqu’une seule tâche est sélectionnée, les détails de cette tâche sont affichés dans la partie inférieure de la page.
1. **Colonne de statut de la tâche** - Cette colonne utilise des symboles pour indiquer le statut de chaque tâche. Les tâche qui n’ont pas de symbole dans cette colonne ont un statut *Non commencé*. Un triangle vert indique les tâches dont le statut est *Commencé*. Deux lignes verticales jaunes indiquent les tâches dont le statut est *Arrêté*.
1. **Colonne haute priorité** - Cette colonne utilise des points d’exclamation pour indiquer les tâches qui ont une priorité élevée.
1. **Ordre** - Cette colonne affiche le numéro d’ordre de fabrication d’une tâche.
1. **Description** - Cette colonne affiche une description de l’opération dont fait partie une tâche.
1. **Demandé** - Cette colonne indique la quantité qu’une tâche est prévue pour produire.
1. **Commencé** - Cette colonne indique la quantité déjà démarrée pour une tâche.
1. **Terminé** - Cette colonne indique la quantité déjà terminée pour une tâche.
1. **Mis au rebut** - Cette colonne indique la quantité déjà mise au rebut pour une tâche.
1. **Restant** - Cette colonne indique la quantité qui reste à terminer pour une tâche.

## <a name="active-jobs-tab"></a>Onglet Tâches actives

L’onglet **Tâches actives** affiche une liste de toutes les tâches que le collaborateur connecté a déjà commencées. (Ce nom d’onglet est personnalisable et peut être différent pour votre système.)

![Onglet Tâches actives.](media/pfei-active-jobs-tab.png "Onglet Tâches actives")

La liste des tâches actives comprend les colonnes suivantes :

- **Colonne de sélection** - La colonne la plus à gauche utilise des coches pour indiquer les tâches qui ont été sélectionnés par le travailleur. Les travailleurs peuvent sélectionner plusieurs tâches dans la liste en même temps. Pour sélectionner toutes les tâches de la liste, cochez la case dans l’en-tête de colonne. Lorsqu’une seule tâche est sélectionnée, les détails de cette tâche sont affichés dans la partie inférieure de la page.
- **Ordre** - Cette colonne affiche le numéro d’ordre de fabrication d’une tâche.
- **Description** - Cette colonne affiche une description de l’opération dont fait partie une tâche.
- **Demandé** - Cette colonne indique la quantité qu’une tâche est prévue pour produire.
- **Commencé** - Cette colonne indique la quantité déjà démarrée pour une tâche.
- **Terminé** - Cette colonne indique la quantité déjà terminée pour une tâche.
- **Mis au rebut** - Cette colonne indique la quantité déjà mise au rebut pour une tâche.
- **Restant** - Cette colonne indique la quantité qui reste à terminer pour une tâche.

## <a name="my-machine-tab"></a>Onglet Ma machine

L’onglet **Ma machine** permet aux collaborateurs de sélectionner un actif connecté à une ressource de machine dans le filtre défini sur l’onglet **Toutes les tâches**. Le collaborateur peut ensuite voir l’état et l’intégrité de l’actif sélectionné en lisant les valeurs de quatre compteurs sélectionnés au maximum et les listes des demandes de maintenance récentes et des temps d’arret enregistrés. Le collaborateur peut également demander la maintenance de l’actif sélectionné et enregistrer et modifier les temps d’arrêt de la machine. (Ce nom d’onglet est personnalisable et peut être différent pour votre système.)
 
![Onglet Ma machine.](media/pfei-my-machine-tab.png "Onglet Ma machine")

L’onglet **Ma machine** contient les colonnes suivantes. Les numéros correspondent aux numéros dans l’illustration précédente.

1. **Actif de machine** : sélectionnez l’actif de machine que vous souhaitez suivre. Commencez à saisir un nom pour choisir dans une liste d’actifs correspondants, ou sélectionnez l’icône en forme de loupe pour choisir dans une liste de tous les actifs associés aux ressources qui se trouvent dans le filtre de la liste de tâches.

    > [!NOTE]
    > Les utilisateurs de Supply Chain Management peuvent attribuer une ressource à chaque actif selon les besoins en utilisant la page **Tous les actifs** (dans l’onglet **Immobilisation**, en utilisant la liste déroulante **Ressource**). Pour plus d’informations, voir [Créer un actif](../asset-management/objects/create-an-object.md).

1. **Paramètres** : sélectionnez l’icône d’engrenage pour ouvrir une boîte de dialogue dans laquelle vous pouvez choisir les compteurs à afficher pour l’actif de machine sélectionné. Les valeurs de ces compteurs sont affichées en haut de l’onglet **Gestion des actifs**. Le menu **Paramètres** (illustré dans la capture d’écran suivante) vous permet d’activer jusqu’à quatre compteurs. Pour chaque compteur que vous souhaitez activer, utilisez le champ de recherche en haut de la vignette pour sélectionner un compteur. Le champ de recherche répertorie tous les compteurs associés à l’actif sélectionné en haut de la page **Gestion des actifs**. Définissez chaque compteur pour surveiller la valeur **Agrégée** ou la valeur **Réelle** la plus récente du compteur. Par exemple, si vous définissez un compteur qui suit le nombre d’heures de fonctionnement de la machine, vous devez le définir sur **Agrégé**. Si vous définissez un compteur pour mesurer la dernière température ou pression mise à jour, vous devez le définir sur **Réel**. Sélectionnez **OK** pour enregistrer vos paramètres et fermer la boîte de dialogue.

    ![Paramètres de l’onglet Ma machine.](media/pfei-my-machine-tab-settings.png "Paramètres de l’onglet Ma machine")

1. **Faire une demande de maintenance** : sélectionnez ce bouton pour ouvrir une boîte de dialogue dans laquelle vous pouvez créer une demande de maintenance. Vous pourrez fournir une description et une note. La demande sera présentée à un utilisateur de Supply Chain Management, qui pourra alors convertir la demande de maintenance en ordre de travail de maintenance.
1. **Enregistrer les temps d’arrêt** : sélectionnez ce bouton pour ouvrir une boîte de dialogue dans laquelle vous pouvez enregistrer les temps d’arrêt de la machine. Vous pourrez sélectionner un code motif et entrer un intervalle de dates ou d’heures pour le temps d’arrêt. L’enregistrement des temps d’arrêt de la machine est utilisé pour calculer l’efficacité de l’actif de machine.
1. **Afficher ou modifier** : sélectionnez ce bouton pour ouvrir une boîte de dialogue dans laquelle vous pouvez modifier ou afficher les enregistrements de temps d’arrêt existants.

## <a name="starting-and-completing-production-jobs"></a>Démarrer et terminer les tâches de production

Les travailleurs démarrent une tâche de production en sélectionnant une tâche sur l’onglet **Toutes les tâches** puis en sélectionnant **Commencer la tâche** pour ouvrir la boite de dialogue **Commencer la tâche**.

![Boîte de dialogue Commencer la tâche.](media/pfei-start-job-dialog.png "Boîte de dialogue Commencer la tâche")

Les travailleurs utilisent la boîte de dialogue **Commencer la tâche** pour confirmer la quantité de production, puis démarrer la tâche. Les travailleurs peuvent ajuster la quantité en sélectionnant le champ **Quantité** puis en utilisant le clavier numérique qui apparaît. Les travailleurs sélectionnent ensuite **Démarrer** pour commencer à travailler sur la tâche. La boîte de dialogue **Commencer la tâche** se ferme et la tâche est ajoutée à l’onglet **Tâches actives**.

Les travailleurs peuvent démarrer une tâche qui a n’importe quel statut. Lorsqu’un travailleur commence une tâche dont le statut est *Non commencé*, le champ **Quantité** dans la boîte de dialogue **Commencer la tâche** affiche initialement la quantité totale. Lorsqu’un travailleur commence une tâche dont le statut est *Commencé* ou *Arrêté*, le champ **Quantité** affiche initialement la quantité restante.

## <a name="reporting-good-quantities"></a>Déclarer les bonnes quantités

Lorsqu’un travailleur termine ou termine partiellement une tâche, il peut déclarer les bonnes quantités produites en sélectionnant une tâche sur l’onglet **Tâches actives** puis en sélectionnant **Saisie de l’avancement**. Puis, dans la boîte de dialogue **Saisie de l’avancement**, le travailleur entre la bonne quantité à l’aide du clavier numérique. La quantité est vide par défaut. Une fois qu’une quantité est entrée, le travailleur peut mettre à jour le statut de la tâche sur *En cours*, *Arrêté* ou *Terminé*.

![Boîte de dialogue Saisie de l’avancement.](media/pfei-report-progress-dialog.png "Boîte de dialogue Saisie de l’avancement")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Rapporter les bonnes quantités sur les commandes par lots qui ont des co-produits et des sous-produits

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)] 
<!--KFM: Preview until GA with 10.0.23 -->

Les collaborateurs peuvent utiliser l'interface d'exécution de l'atelier de production pour signaler l'avancement des commandes par lots. Ce reporting inclut le reporting sur les co-produits et les sous-produits.

Certains fabricants, en particulier dans les industries de transformation, utilisent des commandes par lots pour gérer leurs processus de production. Les commandes par lots sont créées à partir de formules, et ces formules peuvent être définies de manière à avoir des co-produits et des sous-produits en sortie. Lorsque des commentaires sur ces commandes par lots sont signalés, la quantité de sortie doit être enregistrée sur l'élément de formule, ainsi que sur les co-produits et sous-produits.

Lorsqu'un collaborateur termine ou termine partiellement une tâche sur une commande par lots, il peut signaler les quantités bonnes ou rebutées pour chaque produit défini comme sortie pour la commande. Les produits définis comme sortie pour une commande par lots peuvent être du type *Formule*, *Co-produit* ou *Sous-produit*.

Pour déclarer de bonnes quantités sur les produits, un collaborateur sélectionne un travail sur l'onglet **Emplois actifs**, puis sélectionne **Saisie de l’avancement**.

Ensuite, dans la boîte de dialogue **Saisie de l’avancement**, le collaborateur peut sélectionner parmi les produits définis comme sortie pour la commande par lots sur laquelle il doit générer un rapport. Le collaborateur peut sélectionner un ou plusieurs produits dans la liste, puis sélectionner **Saisie de l’avancement**. Pour chaque produit, la quantité est vide par défaut et le collaborateur peut utiliser le clavier numérique pour saisir la quantité. Le collaborateur peut utiliser les boutons **Précédent** et **Suivant** pour vous déplacer entre les produits sélectionnés. Une fois la quantité saisie pour chaque produit, le collaborateur peut mettre à jour le statut de la tâche sur *En cours*, *Arrêté* ou *Terminé*.

![Générer un rapport sur les co-produits et sous-produits.](media/report-co-by-products.png "Générer un rapport sur les co-produits et sous-produits")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Rapports sur les commandes par lots pour les articles de planification

Lorsqu'un collaborateur termine un travail sur une commande par lots pour un article de planification, il rapportera uniquement les quantités sur les co-produits et les sous-produits, car les articles de planification ne contiennent pas d'article du type *Formule*.

### <a name="reporting-co-product-variation"></a>Signalement de la variation des coproduits

Si une commande par lots est créée à partir d'une version de formule où l'option **Variantes de co-produits** est définie sur *Oui*, le collaborateur peut générer des rapports sur les co-produits qui ne font pas partie de la définition des commandes par lots. Cette fonctionnalité est utilisée dans des scénarios où une sortie de produit inattendue peut se produire dans le processus de production.

Dans ce cas, le collaborateur peut spécifier le co-produit et la quantité à déclarer en sélectionnant **Variantes de co-produits** dans la boîte de dialogue de progression du rapport. L'ouvrier peut alors sélectionner parmi tous les produits lancés qui sont définis comme co-produits.

## <a name="reporting-scrap"></a>Déclarer le rebut

Lorsqu’un travailleur termine ou termine partiellement une tâche, il peut déclarer le rebut en sélectionnant une tâche sur l’onglet **Tâches actives** puis en sélectionnant **Saisie du rebut**. Puis, dans la boîte de dialogue **Saisie du rebut**, le travailleur entre la quantité mise au rebut à l’aide du clavier numérique. Le travailleur sélectionne également une raison (*Aucune*, *Machine*, *Opérateur* ou *Matériel*).

![Boîte de dialogue Saisie du rebut.](media/pfei-report-scrap-dialog.png "Boîte de dialogue Saisie du rebut")

## <a name="completing-a-job-and-starting-a-new-job"></a>Terminer une tâche et commencer une nouvelle tâche

Habituellement, les travailleurs terminent une tâche en sélectionnant une ou plusieurs tâche en cours sur l’onglet **Tâches actives**, puis en sélectionnant **Saisie de l’avancement**. Ils saisissent ensuite la quantité produite (la bonne quantité) et définissent le statut sur *Achevé*. Si plusieurs tâches ont été sélectionnées, un travailleur utilise alors les boutons **Précédent** et **Suivant** pour se déplacer parmi eux. Pour démarrer une nouvelle tâche, le travailleur la sélectionne sur l’onglet **Toutes les tâches**, puis sélectionne **Commencer la tâche**.

Un travailleur peut également commencer une nouvelle tâche pendant que sa tâche précédente est toujours en cours. Encore une fois, le travailleur sélectionne la nouvelle tâche sur l’onglet **Toutes les tâches**, puis sélectionne **Commencer la tâche**. Cependant, dans ce cas, la boîte de dialogue **Commencer la tâche** informe le travailleur qu’il travaille actuellement sur une tâche et qu’il doit par conséquent arrêter ou terminer cette tâche avant de commencer la nouvelle tâche.

## <a name="working-on-multiple-jobs-in-parallel"></a>Travailler sur plusieurs tâches en parallèle

Un travailleur peut travailler sur plusieurs tâches en même temps (c’est-à-dire en parallèle). Dans ce cas, l’ensemble des tâches sur lesquelles le travailleur travaille est appelé une *offre groupée de tâches*. Le collaborateur peut ajouter de nouvelles tâches au groupe ou terminer une ou plusieurs tâches de l’offre groupée. Les deux scénarios suivants montrent comment un travailleur peut travailler sur des tâches en parallèle.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scénario 1 : Un travailleur qui n’a pas de tâche active veut démarrer deux tâches et y travailler en parallèle

Le travailleur sélectionne les deux tâches sur l’onglet **Toutes les tâches**, puis sélectionne **Commencer la tâche**. La boîte de dialogue **Commencer la tâche** affiche les deux tâches sélectionnées et le travailleur peut ajuster la quantité à démarrer pour chaque tâche. Le travailleur confirme alors la boîte de dialogue et peut démarrer les deux tâches.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scénario 2 : Un travailleur qui a deux tâches actives en cours veut commencer une troisième tâche et y travailler en parallèle avec les deux autres

Le travailleur sélectionne la troisième tâche sur l’onglet **Toutes les tâches**, puis sélectionne **Offre groupée**. Dans la boîte de dialogue **Offre groupée**, le travailleur peut ajuster la quantité à démarrer. Le travailleur confirme ensuite la boîte de dialogue en sélectionnant **Offre groupée**.

## <a name="working-on-indirect-activities"></a>Travailler sur des activités indirectes

Les activités indirectes sont des activités qui ne sont pas directement liées à un ordre de fabrication. Les activités indirectes peuvent être définies de manière flexible, comme décrit dans [Paramétrage des activités indirectes de pointage](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Par exemple, Shannon, employé de l’atelier chez Contoso, souhaite assister à une réunion d’entreprise et les réunions sont considérées comme une activité indirecte. L’un des deux scénarios suivants s’applique :

- **Shannon travaille sur une ou plusieurs tâches actives.** Shannon sélectionne **Activité**, identifie l’activité (réunion) et confirme sa sélection. Un message qui apparaît l’informe qu’elle a des tâches en cours. À partir du message, Shannon peut choisir de terminer ou d’arrêter les tâches sur lesquelles elle travaille avant de se rendre à la réunion.
- **Shannon n’a pas de tâches actives.** Shannon sélectionne **Activité**, identifie l’activité (réunion) et elle confirme sa sélection. Elle est maintenant enregistrée comme étant à la réunion.

Dans les deux scénarios, une fois que Shannon a confirmé sa sélection, elle accède soit à la page de connexion, soit à une page qui attendra qu’elle confirme qu’elle est revenue de son activité indirecte. La page qui s’affiche dépend de la configuration de l’interface d’exécution de l’atelier de production. (Pour plus d’informations, consultez [Configurer l’interface d’exécution de l’atelier de production](production-floor-execution-configure.md) .)

## <a name="registering-breaks"></a>Enregistrement des pauses

Les travailleurs peuvent enregistrer des pauses. Les pauses peuvent être définies de manière flexible, comme décrit dans [Salaire basé sur les enregistrements](pay-based-on-registrations.md).

Un travailleur enregistre une pause en sélectionnant **Pause** puis en sélectionnant la carte qui représente le type de pause (comme le déjeuner). Une fois que le travailleur a confirmé la sélection, l’appareil affiche la page de connexion ou une page qui attendra que le travailleur confirme son retour de la pause. La page qui s’affiche dépend de la configuration de l’interface d’exécution de l’atelier de production. (Pour plus d’informations, consultez [Configurer l’interface d’exécution de l’atelier de production](production-floor-execution-configure.md) .)

## <a name="opening-instructions"></a>Ouverture des instructions

Les travailleurs peuvent ouvrir un document associé à une tâche en sélectionnant **Instructions**. Le bouton **Instructions** est disponible uniquement si un document est associé à la tâche dans les données de base. Par exemple, un document joint à un produit sur la page **Produits lancés** dans Supply Chain Management pourra être ouvert par les travailleurs dans l’interface d’exécution de l’atelier.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Ouvertures des guides de réalité mixte pour HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) peut aider à autonomiser les travailleurs en offrant un apprentissage pratique qui utilise la réalité mixte. Vous pouvez définir des processus standardisés où des instructions détaillées guident vos employés vers les outils et les pièces dont ils ont besoin et leur montrent comment utiliser ces outils dans des situations de travail réelles. Voici une vue d’ensemble du processus.

1. Chaque fois qu’un collaborateur ouvre une liste de tâche dans l’interface d’exécution de l’atelier, l’interface recherche tous les guides appropriés pour les tâches affichées.
1. Le travailleur sélectionne **Guides** pour afficher la liste des guides.
1. Le travailleur sélectionne un guide pertinent dans la liste.
1. L’interface d’exécution de l’atelier affiche un code QR pour le guide sélectionné.
1. Le travailleur met un HoloLens et regarde le code QR pour démarrer le guide.
1. Le travailleur parcourt le guide pour apprendre la tâche.

Pour plus d’informations sur la création, l’attribution et l’utilisation de guides pour HoloLens, voir [Fournir des guides de réalité mixte aux collaborateurs de la production](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
