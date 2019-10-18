---
title: Générer les états financiers
description: Cette rubrique fournit des informations sur la génération d'un état financier.
author: aprilolson
manager: AnnBe
ms.date: 09/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c682ed96e47c718d3a9af1eb10aada75c59d3156
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181839"
---
# <a name="generate-financial-reports"></a>Générer les états financiers

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur la génération d'un état financier.

Pour générer un état, ouvrez la définition d'état, puis cliquez sur le bouton Générer dans la barre d'outils. La fenêtre État de la file d'attente de rapports s'ouvre et affiche l'emplacement de votre état dans la file d'attente. Par défaut, l'état généré s'affiche dans la visionneuse Web.

Les options suivantes sont disponibles pour la génération d'états :

- Paramétrer un calendrier pour générer un état ou un groupe d'états automatiquement
- Vérifier les comptes manquants ou les données manquants dans un état, et validez la précision d'un état

Lorsque vous générez un état, les options que vous avez spécifiées sous les onglets Définition d'état sont utilisées.

## <a name="generate-a-financial-report"></a>Générer un état financier

Pour générer un état financier avec , accédez à **Comptabilité** \> **Recherches et états** \> **États financiers**.

- Sélectionnez un état à générer, puis cliquez sur **Générer**.
- Renseignez le champ **Date de l'état** et cliquez sur **OK**.

Une fois que l'état a été généré, il est disponible dans la section **États**.

Vous pouvez choisir d'**Afficher** ou de **Supprimer** l'état.

Pour générer un état à l'aide du **Concepteurs d'états**, ouvrez la définition de l'état, puis cliquez sur le bouton Générer dans la barre d'outils. La fenêtre État de la file d'attente de rapports s'ouvre et affiche l'emplacement de votre état dans la file d'attente. Par défaut, l'état généré s'affiche dans la visionneuse Web.

## <a name="schedule-report-generation"></a>Programme de génération des rapports
De nombreuses sociétés disposent d'un ensemble principal de rapports qui sont exécutés à intervalles planifiés correspondant à leurs processus métiers. Vous pouvez programmer la génération régulière d'un état, par exemple chaque jour, chaque semaine, chaque mois ou chaque année. Il peut s'agir d'un seul rapport ou d'un groupe de rapports incluant plusieurs sociétés. Vous devez entrer vos informations d'identification pour chaque société spécifiée, par exemple, chaque société de la définition d'organigramme d'entreprise. Si les informations d'identification ne sont pas valides, l'état affiche uniquement les informations auxquelles vous êtes autorisé à accéder, comme la société à laquelle vous êtes connecté. Les informations de sortie sont lues d'abord à partir du groupe d'état, puis à partir des états individuels.

À mesure que les programmations d'états sont créées et enregistrées, elles sont affichées dans le volet de navigation sous Programmations d'états. Vous pouvez créer des dossiers pour organiser les rapports. Même si l'un des rapports du programme n'est pas exécuté, les autres rapports continuent à être exécutés.

> [!IMPORTANT]
> Pour créer, modifier et supprimer les programmes des rapports, vous devez avoir le rôle Administrateur ou Concepteur. Lorsqu'un état est exécuté, les informations d'identification de l'utilisateur ayant créé le programme sont utilisées pour générer l'état.

### <a name="create-a-report-schedule"></a>Créer une programmation d'état

1. Dans le générateur d'états, dans le menu Fichier, cliquez sur Nouveau, puis sélectionnez Planificateur d'état. La boîte de dialogue Nouveau planificateur d'état s'ouvre.
2. Sous Paramètres, sélectionnez un état individuel ou un groupe d'états à planifier. Seuls sont disponibles les rapports ou groupes de rapports de la société ou du bloc élémentaire auquel vous êtes connecté.
3. Activez la case à cocher Actif pour activer le programme des rapports. Seul le créateur du rapport ou un administrateur peut activer ou désactiver un programme des rapports.
4. Cliquez sur le bouton Autorisations pour entrer les informations d'identification de la société. Par défaut, vos informations de connexion sont utilisées pour la société à laquelle vous êtes connecté. Si d'autres sociétés sont incluses, par exemple dans des définitions d'organigramme d'entreprise, sélectionnez Utiliser d'autres informations d'identification, puis entrez les informations d'identification d'une autre société incluse dans le programme des rapports. Vous pouvez sélectionner Authentification Windows ou taper un nom d'utilisateur et un mot de passe pour chaque société. Activez la case à cocher Enregistrer les informations d'identification pour enregistrer les informations d'identification pour ces sociétés, puis cliquez sur OK pour fermer la boîte de dialogue.
5. Sous Fréquence, dans le champ Début de la répétition, sélectionnez la date à laquelle la programmation doit commencer. Par défaut, la date système actuelle de l'ordinateur client est sélectionnée.
6. Dans le champ Exécuter le rapport, sélectionnez l'heure à laquelle le rapport doit être exécuté. Si vous entrez une heure située avant l'heure système actuelle, le rapport est exécuté à la prochaine date programmée.
7. Dans la zone Périodicité, spécifiez la fréquence d'exécution du rapport. Par défaut, Quotidien est sélectionné avec une valeur d'intervalle (en jours) de 1. Les autres options disponibles sont Hebdomadaire, Mensuel et Annuel.
8. Dans la zone Plage de périodicité, sélectionnez le moment auquel la génération du rapport doit être interrompue.

    - Pas de date de fin – Le programme des rapports est exécuté indéfiniment.
    - Définir le nombre d'occurrences – Le programme des rapports est exécuté le nombre de fois spécifié, puis désactivé.
    - Terminé pour – Le programme des rapports se termine à la date spécifiée.

9. Dans la barre d'outils, cliquez sur Enregistrer. Dans la boîte de dialogue Enregistrer sous, spécifiez un nom unique et une description pour la programmation d'état.

Pour copier une programmation d'état, vous devez avoir le rôle de concepteur ou d'administrateur. Même si un administrateur modifie la programmation d'état, l'état contient toujours les informations d'identification de l'utilisateur qui l'a créé.

### <a name="copy-a-report-schedule"></a>Copier une programmation d'état

1. Dans le générateur d'états, cliquez sur Programmations d'états dans le volet de navigation, puis ouvrez une programmation d'état à copier.
2. Dans le menu Fichier, cliquez sur Enregistrer sous, puis entrez un nouveau nom et une nouvelle description pour le programme dans la boîte de dialogue Enregistrer sous. Cliquez sur OK. Le nouveau programme est affiché dans le volet de navigation.
3. Dans la nouvelle programmation, modifiez les champs et les informations si nécessaire, puis cliquez sur Enregistrer dans la barre d'outils, ou sur Enregistrer dans le menu Fichier.

Pour supprimer une programmation d'état, vous devez en être le propriétaire ou avoir un rôle d'administrateur.

### <a name="delete-a-report-schedule"></a>Supprimer une programmation d'état

1. Dans le générateur d'états, cliquez sur Programmations d'états dans le volet de navigation.
2. Sélectionnez le programme des rapports à supprimer, puis cliquez sur Supprimer ou appuyez sur la touche Suppr.
3. Dans la boîte de dialogue de confirmation de la suppression, cliquez sur Oui pour supprimer définitivement le programme des rapports. Si vous n'avez pas l'autorisation de supprimer la programmation, un message s'affiche et l'état n'est pas supprimé.

### <a name="credentials-and-report-schedules"></a>Informations d'identification et programmes des rapports

Si vous n'entrez pas les informations d'identification requises pour toutes les sociétés incluses dans les états, vous recevez le message suivant lorsque vous enregistrez la programmation d'état : « Vous devez entrer vos informations d'identification pour les sociétés contenues dans cette programmation d'état. Cliquez sur le bouton Autorisations pour entrer vos informations d'identification ».

Par exemple, Phyllis se connecte à la Société A à l'aide de son identifiant et de son mot de passe. Elle crée une programmation pour un état qui utilise une définition d'arborescence de génération d'états pour collecter les données de plusieurs sociétés. Lors de l'enregistrement de ce rapport, Phyllis est invitée à entrer les informations d'identification des autres sociétés spécifiées dans la définition d'organigramme d'entreprise. Si vos informations d'identification arrivent à expiration, les états affectés dans la programmation d'état ne sont pas générés jusqu'à ce que les informations d'identification soient mises à jour. Un message s'affiche dans la file d'attente d'états pour indiquer que les autorisations doivent être mises à jour. La programmation d'état échoue si l'un des scénarios suivants se produit (car des informations d'identification sont requises) :

- Une nouvelle société a été ajoutée à une arborescence d'état pour un état individuel.
- Un rapport du groupe de rapports a été modifié.
- Un nouveau rapport pour une nouvelle société a été ajouté au groupe de rapports.

Pour continuer, cliquez sur le bouton Autorisations dans la boîte de dialogue Planification d'état, puis entrez les informations d'identification appropriées.

## <a name="missing-account-analysis-feature"></a>Fonction Analyse des comptes manquants
Vous pouvez rechercher des dimensions et des comptes financiers qui peuvent être manquants dans toutes les définitions de ligne, les définitions d'arborescence de génération d'états, et les définitions d'état dans un groupe de blocs élémentaires. Cela est utile lorsque vous créez ou mettez à jour plusieurs comptes ou blocs élémentaires pendant une courte période et que vous souhaitez vérifier que toutes les nouvelles informations sont incluses dans les états.

Les comptes manquants sont déterminés à l'aide des valeurs les plus basses et les plus élevées à partir de la définition de ligne ou de la définition d'arborescence de génération d'état, puis affiche la liste des comptes qui ne sont pas dans la définition de ligne ou la définition d'arborescence de génération d'état, mais qui figurent dans les données financières. Si un compte manquant est supérieur ou inférieur aux valeurs de la définition de ligne, il n'est pas inclus dans la liste des comptes manquants.

> [!TIP]
> À des fins de validation, ce processus doit être exécuté avant la génération des rapports mensuels et lorsque vous créez des blocs élémentaires.

Les états qui ont des plages des valeurs sont moins susceptibles d'avoir des comptes manquants. Si possible, utilisez les plages dans le bloc élémentaire pour inclure de nouveaux comptes lorsqu'ils sont créés. Si une définition de rapport est définie sur @ANY (n'importe quelle société), vous pouvez vous connecter à une société spécifique et exécuter l'analyse des comptes manquants pour cette société.

> [!NOTE]
> Si une nouvelle société a été ajoutée, vous devez l'ajouter dans les arborescences de génération d'états dans tous les états existants, sinon elle ne sera pas incluse dans l'analyse des comptes manquants.

### <a name="run-missing-account-analysis"></a>Exécuter une analyse de compte manquante

1. Dans Report Designer, cliquez sur Outils, puis sur Analyse de compte manquante.
2. Dans le champ Filtre de société, sélectionnez la société sur laquelle filtrer les résultats ou sélectionnez Tout (aucun filtre) pour afficher les résultats de toutes les sociétés disponibles.
3. Dans le champ Filtre de dimension, sélectionnez la dimension sur laquelle filtrer les résultats ou sélectionnez Tout (aucun filtre) pour afficher toutes les informations sur les dimensions de l'ensemble des sociétés disponibles.
4. Dans le champ Regrouper par, sélectionnez une option de tri des résultats. Vous pouvez trier les résultats en fonction du bloc élémentaire affecté, ou par ensembles de dimension et de valeur.
5. Passez en revue les résultats affichés. Lorsque vous sélectionnez un élément dans le volet supérieur, le volet inférieur affiche des informations supplémentaires sur l'exception, notamment les dimensions, valeurs et rapports associés.
6. Pour ouvrir le bloc associé, cliquez sur l'icône associée affichée dans le volet de liste, ou cliquez avec le bouton droit sur l'article et sélectionnez Ouvrir. Pour sélectionner plusieurs blocs, maintenez la touche Ctrl enfoncée et sélectionnez les blocs dans le volet inférieur.
7. Si des valeurs, des blocs de construction ou des états sont renvoyés alors qu'ils ne doivent pas être inclus dans l'analyse, cliquez avec le bouton droit sur le bloc et sélectionnez Exclure ou activez la case à cocher Exclure en regard du bloc pour le supprimer de la liste. Les blocs exclus ne sont pas inclus lorsque la liste est actualisée. Pour sélectionner plusieurs éléments, maintenez la touche Ctrl enfoncée tout en les sélectionnant dans le volet inférieur. Pour afficher tous les éléments, y compris les résultats que vous avez précédemment exclus de l'analyse, activez la case à cocher Afficher les valeurs et les blocs élémentaires exclus, puis cliquez sur Actualiser.
8. Pour actualiser les exceptions traitées, cliquez sur Actualiser. Cliquez sur Oui pour actualiser l'ensemble des résultats ou sur Non pour actualiser une partie seulement des éléments traités.

    > [!NOTE]
    > Le formulaire est actualisé automatiquement lors de son ouverture, sauf s'il a été ouvert au cours des 15 dernières minutes.

9. Lorsque les problèmes sont résolus, cliquez sur OK pour fermer la boîte de dialogue.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Raccourcis clavier pour l'analyse de compte manquante
Lorsque vous exécutez une analyse de compte manquante, les raccourcis clavier suivants sont disponibles.

| Opération                           | Utiliser ce raccourci clavier |
|--------------------------------------|----------------------------|
| Filtrer par société                    | Alt+C                      |
| Filtre de dimension                  | Alt + D                      |
| Sélectionner le champ Regrouper par            | Alt + G                      |
| Afficher les valeurs et les blocs exclus      | Alt + S                      |
| Actualiser les résultats                      | Alt + R                      |
| Exclure le bloc élémentaire sélectionné  | Alt + X                      |
| Exclure la définition de ligne sélectionnée  | Ctrl + B                     |
| Exclure la valeur de dimension sélectionnée | Ctrl + D                     |
| Ouvrir la définition de rapport sélectionnée  | Ctrl + R                     |
| Ouvrir la définition de ligne sélectionnée     | Ctrl + O                     |


## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](financial-reporting-intro.md)

[Interface du Concepteur de rapports](report-designer-interface.md)
