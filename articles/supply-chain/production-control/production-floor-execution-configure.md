---
title: Configurer l’interface d’exécution de l’atelier de production
description: Cette rubrique décrit comment créer une ou plusieurs configurations pour l’interface d’exécution de l’atelier de production. Lorsque vous ouvrez l’interface d’exécution de l’atelier de production, elle charge automatiquement une configuration sélectionnée et un filtre de tâches spécifiques au navigateur et à l’appareil. Dans la configuration, vous définissez les stratégies qui doivent être applicables pour une utilisation spécifique.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5a0ead85eaeb6b96b80716614990af8c8e5e70f7
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384745"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurer l’interface d’exécution de l’atelier de production

[!include [banner](../includes/banner.md)]

Les collaborateurs de l’atelier utilisent l’interface d’exécution de l’atelier de production pour enregistrer leur travail quotidien : heure de début d’une tâche, générer des commentaires sur les tâches, enregistrer des activités indirectes et signaler des absences. Ces enregistrements servent de base pour suivre l’avancement et le coût des ordres de fabrication et pour calculer la base de la rémunération des collaborateurs.

Lorsque vous ouvrez l’interface d’exécution de l’atelier de production, elle charge automatiquement une configuration sélectionnée et un filtre de tâches spécifiques au navigateur et à l’appareil. Dans la configuration, vous définissez les stratégies qui doivent être applicables pour une utilisation spécifique. Voici quelques exemples d’utilisation :

- Sur un appareil situé dans le hall de l’entreprise, les employés pointent lorsqu’ils entrent dans le bureau et lorsqu’ils partent pour la journée.
- Sur un appareil de l’atelier, les opérateurs de machines enregistrent lorsqu’ils démarrent et terminent des tâches. Ils enregistrent également les pauses et les activités indirectes.

Cette rubrique décrit les différentes options de configuration d’une interface d’exécution d’atelier de production pour chaque périphérique utilisé sur votre site.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Activez l’interface d’exécution de l’atelier de production et ses fonctionnalités optionnelles associées

L’interface d’exécution de l’atelier de production elle-même, ainsi que plusieurs des paramètres facultatifs décrits dans cette rubrique, doivent être activés dans votre système avant de pouvoir les utiliser. Utilisez la page [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer tout ou partie des fonctionnalités décrites dans les sous-sections suivantes, le cas échéant.

### <a name="the-production-floor-execution-interface"></a>Interface d’exécution de l’atelier de production

Il s’agit de la fonctionnalité principale décrite dans cette rubrique et c’est un prérequis pour toutes les autres fonctionnalités mentionnées dans cette section. Depuis la version 10.0.25 de Supply Chain Management, elle est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Exécution de l’atelier de production* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="generate-license-plates"></a>Générer des contenants

Ces fonctionnalités rendent la fonctionnalité de contenant disponible pour l’interface d’exécution de l’atelier de production. Si vous souhaitez les utiliser, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre suivant) :

1. *Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail*<br>Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est activée par défaut. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire.
1. *Activer la génération automatique du numéro de contenant lors de la déclaration de fin dans le périphérique de bon de travail*<br>(Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire.)

### <a name="print-labels"></a>Imprimer les étiquettes

Ces fonctionnalités rendent la fonctionnalité d’impression d’étiquettes disponible pour l’interface d’exécution de l’atelier de production. Si vous souhaitez les utiliser, activez les fonctionnalités suivantes dans la [gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans l’ordre suivant) :

1. *Contenant pour la déclaration ajouté comme finalisé au périphérique pour bons de travail*<br>Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est activée par défaut. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire.
1. *Imprimer une étiquette à partir d’un périphérique de bons de travail*<br>(Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire.)

### <a name="allow-locking-the-touch-screen"></a>Autoriser le verrouillage de l’écran tactile

Cette fonctionnalité permet de permettre aux travailleurs de verrouiller l’écran tactile afin qu’ils puissent le désinfecter.

À compter de la version 10.0.21 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est obligatoire et peut être désactivée. Si vous exécutez une version antérieure à 10.0.25, les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la *Fonction de verrouillage du dispositif de carte de travail et du terminal de carte de travail afin qu’ils puissent être désinfectés* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Fonctionnalité de gestion d’actifs pour l’interface d’exécution de l’atelier de production

Cette fonctionnalité ajoute un onglet de gestion des actifs à l’interface d’exécution de l’atelier de production. Les collaborateurs peuvent utiliser cet onglet pour sélectionner un actif connecté à une ressource de machine qui se trouve dans le filtre sélectionné de la liste des tâches. Pour l’actif de machine sélectionné, le collaborateur peut afficher l’état et l’intégrité de l’actif à partir des valeurs de compteur de quatre compteurs sélectionnés au maximum. Si vous souhaitez utiliser cette fonctionnalité, activez la fonctionnalité suivante dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- *Fonctionnalité de gestion d’actifs pour l’interface d’exécution de l’atelier de production*<br>(Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est activée par défaut.)

### <a name="enable-job-search"></a>Activer la recherche de tâches

Cette fonctionnalité permet d’ajouter un champ de recherche à la liste des tâches. Les collaborateurs peuvent rechercher une tâche spécifique en entrant l’ID de la tâche ou en recherchant toutes les tâches pour une commande spécifique en entrant l’ID de la commande. Les collaborateurs peuvent entrer l’ID en utilisant un pavé numérique ou en scannant un code-barres. Pour l’utiliser, activez la fonctionnalité suivante dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- *Recherche de tâche pour l’interface d’exécution de l’atelier de production*<br>(Depuis la version 10.0.25 de Supply Chain Management, cette fonctionnalité est activée par défaut.)

### <a name="enable-reporting-on-co-products-and-by-products"></a>Activer la génération de rapport sur les co-produits et sous-produits

Cette fonctionnalité permet aux collaborateurs d’utiliser l’interface d’exécution de l’atelier de production pour signaler l’avancement des commandes par lots. Ce reporting inclut le reporting sur les co-produits et les sous-produits. Pour utiliser cette fonctionnalité, activez la fonctionnalité suivantes dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- *État sur les co-produits et sous-produits de l’interface d’exécution de l’atelier de production*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>Activer l’affichage des numéros de série, de lot et de plaque d’immatriculation complets

Cette fonctionnalité offre une expérience améliorée pour l’affichage des listes de n° de série, n° lot et numéros de contenant dans l’interface d’exécution de l’atelier de production. L’affichage passe d’une vue de carte avec un nombre limité de caractères à une vue de liste qui offre suffisamment d’espace pour afficher les valeurs complètes. La liste offre également la possibilité de rechercher des numéros spécifiques.

À compter de la version 10.0.25 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Afficher les numéros de série, de traitements par lots et de contenants complets dans l’interface d’exécution de l’atelier de production* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="enable-registering-of-material-consumption"></a>Activer l’enregistrement de la consommation de matières

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Cette fonctionnalité permet aux travailleurs d’utiliser l’interface d’exécution de l’atelier de production pour enregistrer la consommation de matériaux, les numéros de lot et les numéros de série. Certains fabricants, en particulier ceux des industries de transformation, doivent enregistrer explicitement la quantité de matière consommée pour chaque lot ou ordre de fabrication. Par exemple, les travailleurs peuvent utiliser une balance pour peser la quantité de matière consommée pendant qu’ils travaillent. Pour assurer une traçabilité totale des matériaux, ces organisations doivent également enregistrer les numéros de lots consommés lors de la fabrication de chaque produit.

Il existe deux versions de cette fonctionnalité. L’une prend en charge les articles qui ne *sont pas* activés pour utiliser les processus d’entrepôt avancés (WMS). L’autre prend en charge les éléments qui *sont* activés pour utiliser WMS. Pour utiliser cette fonctionnalité, activez une ou les deux fonctionnalités suivantes dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (dans cet ordre), selon que vous avez ou non des éléments activés pour WMS :

- *(Version préliminaire) Enregistrer la consommation des matériaux sur l’interface d’exécution de l’atelier de production (autre que WMS)*
- *(Aperçu) Enregistrer la consommation de matières sur l’interface d’exécution de l’atelier de production (compatible WMS)*

> [!IMPORTANT]
> Vous pouvez utiliser la fonctionnalité non-WMS seule. Cependant, si vous utilisez WMS, vous devez activer les deux fonctionnalités.

### <a name="enable-reporting-on-catch-weight-items"></a>Activer les rapports sur les éléments de poids variable

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Les collaborateurs peuvent utiliser l’interface d’exécution de l’atelier de production pour signaler l’avancement des commandes par lots pour les éléments de poids variable. Les commandes par lots sont créées à partir de formules, et ces formules peuvent être définies de manière à avoir des éléments à poids variable en tant qu’éléments de formule, co-produits et sous-produits en sortie. Une formule peut également être définie pour avoir des lignes de formule pour les ingrédients qui sont définis pour le poids variable. Les éléments à poids variable utilisent deux unités de mesure pour suivre l’inventaire : la quantité de poids variable et la quantité de stock. Par exemple, dans l’industrie alimentaire, la viande en boîte peut être définie comme un élément à poids variable, où la quantité de poids variable est utilisée pour suivre le nombre de boîtes et la quantité d’inventaire est utilisée pour suivre le poids des boîtes.

Pour utiliser cette fonctionnalité, activez la fonctionnalité suivantes dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) :

- *(Aperçu) État sur les articles en poids variable à partir de l’interface d’exécution de l’atelier de production*

## <a name="work-with-production-floor-execution-configurations"></a>Utiliser les configurations de l’exécution de l’atelier de production

Pour créer et gérer des configurations de l’exécution de l’atelier de production, accédez à **Contrôle de la production \> Configuration \> Contrôle et suivi de la production \> Configurer l’exécution de l’atelier de production**. La page **Configurer l’exécution de l’atelier de production** affiche une liste des configurations existantes. Sur cette page, vous pouvez effectuer l’une des actions suivantes :

- Sélectionner n’importe quelle configuration d’atelier de production répertoriée dans la colonne de gauche pour la visualiser et la modifier.
- Sélectionner **Nouveau** dans le volet Actions pour ajouter une nouvelle configuration à la liste. Ensuite, dans le champ **Configuration**, entrez alors un nom pour identifier la nouvelle configuration. Le nom que vous entrez ici doit être unique parmi toutes les configurations et vous ne pourrez pas le modifier ultérieurement.

Ensuite, configurez les différents paramètres pour la configuration sélectionnée. Les champs disponibles sont les suivants :

- **Pointer et sortir uniquement** – Réglez cette option sur *Oui* pour créer une interface simplifiée qui ne fournit que des fonctionnalités d’horloge d’entrée et de sortie. Cela désactive la plupart des autres options de cette page. Vous devez supprimer toutes les lignes du raccourci **Sélection d’onglets** avant de pouvoir activer cette option.
- **Activer la recherche** : définissez cette option sur *Oui* pour inclure un champ de recherche dans la liste des tâches. Les collaborateurs peuvent rechercher une tâche spécifique en entrant l’ID de la tâche ou en recherchant toutes les tâches pour une commande spécifique en entrant l’ID de la commande. Les collaborateurs peuvent entrer l’ID en utilisant un pavé numérique ou en scannant un code-barres.
- **Déclarer la quantité à la sortie** – Définissez cette option sur *Oui* pour inviter les collaborateurs à faire part de leurs commentaires sur les travaux en cours lorsqu’ils pointent à la sortie. Lorsque cette option est définie sur *Non*, les collaborateurs ne reçoivent pas d’invite.
- **Verrouiller l’employé** – Lorsque cette option est définie sur *Non*, les travailleurs seront déconnectés immédiatement après avoir effectué un enregistrement (comme un nouveau travail). L’interface retournera ensuite à la page de connexion. Lorsque cette option est définie sur *Oui*, les collaborateurs resteront connectés à l’interface d’exécution de l’atelier de production. Cependant, un collaborateur peut se déconnecter manuellement afin qu’un autre collaborateur puisse se connecter pendant que l’interface d’exécution de l’atelier de production continue de s’exécuter sous le même compte d’utilisateur système. Pour plus d’informations sur ces types de compte, voir [Utilisateurs affectés](config-job-card-device.md#assigned-users).
- **Utiliser l’heure réelle d’enregistrement** – Définissez cette option sur *Oui* pour définir l’heure de chaque nouvel enregistrement sur l’heure exacte à laquelle le collaborateur a soumis l’enregistrement. Lorsque cette option est définie sur *Non*, l’heure de connexion est utilisée à la place. Vous souhaiterez généralement définir cette option sur *Oui* si vous avez défini les options **Verrouiller le collaborateur** et/ou **Collaborateur unique** sur *Oui* dans les cas où les collaborateurs restent souvent connectés pendant de longues périodes.
- **Collaborateur unique** – Définissez cette option sur *Oui* si un seul collaborateur utilise chaque interface d’exécution de l’atelier de production sur laquelle cette configuration est active. Lorsque cette option est définie sur *Oui*, l’option **Verrouiller le collaborateur** est automatiquement définie sur *Oui*. De plus, ce paramètre supprime le besoin (et la capacité) pour le collaborateur de se connecter à l’aide d’un ID badge (ou autre ID similaire). Au lieu de cela, le collaborateur se connecte à Microsoft Dynamics 365 Supply Chain Management à l’aide d’un compte utilisateur système lié à un collaborateur *à temps enregistré* (issu de la table *collaborateurs*) et se connecte à l’interface d’exécution de l’atelier de production en tant que collaborateur en même temps.
- **Autoriser le verrouillage de l’écran tactile** – Définissez cette option sur *Oui* pour permettre aux collaborateurs de verrouiller l’écran tactile de l’interface d’exécution de l’atelier de production afin de pouvoir le désinfecter. Lorsque cette option est définie sur *Oui*, un bouton **Verrouiller l’écran pour la désinfection** est ajouté à la page de connexion. Lorsqu’un collaborateur sélectionne ce bouton, l’écran tactile est verrouillé temporairement pour empêcher toute entrée involontaire. Un compte à rebours est également affiché. Le collaborateur peut ensuite nettoyer en toute sécurité l’appareil et l’écran. Une fois le compte à rebours terminé, l’écran tactile est déverrouillé automatiquement.
- **Durée de verrouillage de l’écran** – Quand l’option **Autoriser le verrouillage de l’écran tactile** est définie sur *Oui*, utilisez cette option pour spécifier le nombre de secondes pendant lesquelles l’écran tactile doit être verrouillé pour la désinfection. La durée doit être un nombre compris entre 5 et 120 secondes.
- **Générer un contenant** – Définissez cette option sur *Oui* pour générer un nouveau contenant chaque fois qu’un collaborateur utilise l’interface d’exécution de l’atelier de fabrication pour effectuer une déclaration de fin. Le numéro du contenant est généré à partir d’une séquence de numéros configurée sur la page **Paramètres de gestion de l’entrepôt**. Quand cette option est définie sur *Non*, les collaborateurs doivent spécifier un contenant existant lorsqu’ils font une déclaration de fin.
- **Imprimer l’étiquette** – Définissez cette option sur *Oui* pour imprimer une étiquette de contenant quand un collaborateur utilise l’interface d’exécution de l’atelier de production pour effectuer une déclaration de fin. La configuration de l’étiquette est définie dans l’acheminement des documents, comme décrit dans [Mise en page d’acheminement de document pour les étiquettes de contenant](../warehousing/document-routing-layout-for-license-plates.md).
- **Sélection d’onglets** – Utilisez les paramètres de cette section pour choisir les onglets à afficher par l’interface d’exécution de l’atelier de production lorsque la configuration actuelle est active. Vous pouvez concevoir autant d’onglets que vous le souhaitez, puis les ajouter et les organiser ici selon vos besoins. Pour plus d’informations sur la conception des onglets et l’utilisation des paramètres ici, consultez [Concevoir l’interface d’exécution de l’atelier de production](production-floor-execution-tabs.md).

## <a name="clean-up-job-configurations"></a>Nettoyage des configurations de tâches

Lorsque le superviseur d’atelier configure l’interface d’exécution de l’atelier de production, il sélectionne une configuration et un filtre de tâche. Ces sélections sont stockées dans une table de référence dans Supply Chain Management et le navigateur utilise un ID qui est stocké dans un cookie local pour trouver la ligne correcte dans cette table. La table enregistre également la date et l’heure de la dernière connexion d’un travailleur sur chaque appareil.

Un traitement par lots nettoie périodiquement les entrées de la table des références pour les appareils qui n’ont enregistré aucune activité au cours des 60 derniers jours. Vous pouvez également nettoyer manuellement les entrées à tout moment en suivant ces étapes.

1. Accédez à **Contrôle de la production \> Paramétrage \> Contrôle et suivi de la production \> Configurer l’exécution de l’atelier de production**.
1. Dans le volet Actions, sélectionnez **Nettoyer les configurations du client**.
1. Dans la boîte de dialogue **Nettoyer la configuration du client**, définissez le champ **Nombre de jours** sur le nombre de jours d’inactivité (avant aujourd’hui) à prendre en compte. Vous supprimerez toutes les configurations et les enregistrements de connexion pour les appareils qui n’ont pas été actifs pendant cette période.
1. Sélectionnez **OK** pour nettoyer les configurations pertinentes, en fonction du paramètre **Nombre de jours**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
