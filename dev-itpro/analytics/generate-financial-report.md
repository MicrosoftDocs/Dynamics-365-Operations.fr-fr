---
title: "Générer un état financier"
description: "Cette rubrique fournit des informations sur la génération d&quot;un état financier."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 13bef3abc381a903bf48daa18ef01b07103ef9ea
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="generate-a-financial-report"></a>Générer un état financier

[!include[banner](../includes/banner.md)]


Cette rubrique fournit des informations sur la génération d'un état financier. 

Pour générer un état, ouvrez la définition d'état, puis cliquez sur le bouton Générer dans la barre d'outils. La fenêtre État de la file d'attente de rapports s'ouvre et affiche l'emplacement de votre état dans la file d'attente. Par défaut, l'état généré s'affiche dans la visionneuse Web.
| ![Remarque](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Remarque")**Remarque**        |
|------------------------------------------------------------------------------------------------|
| Vous pouvez générer des états uniquement dans les dossiers et les emplacements auxquels vous êtes autorisé à accéder. |

Le tableau suivant décrit les options disponibles pour générer des états.

| Option                                                                                | Plus d'informations |
|---------------------------------------------------------------------------------------|----------------------|
| Paramétrer un calendrier pour générer un état ou un groupe d'états automatiquement              |                      |
| Vérifier les comptes manquants ou les données manquants dans un état, et validez la précision d'un état |                      |

Lorsque vous générez un état, les options que vous avez spécifiées sous les onglets Définition d'état sont utilisées. L'onglet Sortie et distribution permet de spécifier un emplacement de bibliothèque d'états, qui fournit une manière unique de partager l'état.

## <a name="schedule-report-generation"></a> Programmer la génération d'états
De nombreuses sociétés ont des ensembles d'états qui sont exécutés à intervalles planifiés afin de s'aligner avec les processus d'entreprise. Vous pouvez programmer la génération régulière d'un état, par exemple chaque jour, chaque semaine, chaque mois ou chaque année. Il peut s'agir d'un état unique ou d'un groupe d'états qui comprend plusieurs sociétés. Vous devez entrer vos informations d'identification pour chacune des sociétés spécifiées, comme celles figurant dans une définition d'arborescence de génération d'états. Si les informations d'identification ne sont pas valides, l'état affiche uniquement les informations auxquelles vous êtes autorisé à accéder, comme la société à laquelle vous êtes connecté. Les informations de sortie sont lues d'abord à partir du groupe d'état, puis à partir des états individuels.

À mesure que les programmations d'états sont créées et enregistrées, elles sont affichées dans le volet de navigation sous Programmations d'états. Vous pouvez créer des dossiers pour organiser les états. Si un état unique dans un programme ne fonctionne pas, tous les autres états continueront à être exécutés.
| ![Important](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Important")**Important**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pour créer, modifier et supprimer des états, vous devez avoir le rôle de concepteur ou d'administrateur. Lorsqu'un état est exécuté, les informations d'identification de l'utilisateur ayant créé le programme sont utilisées pour générer l'état. |

### <a name="create-a-report-schedule"></a>Créer une programmation d'état

1.  Dans le générateur d'états, dans le menu Fichier, cliquez sur Nouveau, puis sélectionnez Planificateur d'état. La boîte de dialogue Nouveau planificateur d'état s'ouvre.
2.  Sous Paramètres, sélectionnez un état individuel ou un groupe d'états à planifier. Seuls les états ou les groupes d'états pour la société ou la sélection de blocs élémentaires auxquels vous êtes actuellement connecté sont disponibles.
3.  Activez la case à cocher Actif pour activer la programmation d'état. Seul le créateur de l'état ou un administrateur peut activer ou désactiver la programmation d'un état.
4.  Cliquez sur le bouton Autorisations pour entrer les informations d'identification de la société. Par défaut, les informations de connexion sont utilisées pour la société à laquelle vous êtes connecté. Si d'autres sociétés sont incluses, comme dans les définitions d'arborescence de génération d'états, sélectionnez Utiliser d'autres informations d'identification, puis entrez les informations d'identification des autres sociétés incluses dans la programmation d'état. Vous pouvez sélectionner Authentification Windows ou taper un nom d'utilisateur et un mot de passe pour chaque société. Activez la case à cocher Enregistrer les informations d'identification pour enregistrer les informations d'identification pour ces sociétés, puis cliquez sur OK pour fermer la boîte de dialogue.
5.  Sous Fréquence, dans le champ Début de la répétition, sélectionnez la date à laquelle la programmation doit commencer. Par défaut, la date système actuelle de l'ordinateur client est sélectionnée.
6.  Dans le champ Exécuter l'état le, sélectionnez l'heure à laquelle l'état doit s'exécuter. Si vous entrez une heure qui se situe avant l'heure système actuelle, l'état s'exécute à la date prévue suivante.
7.  Dans la zone Modèle de répétition, spécifiez la fréquence à laquelle l'état est exécuté. Par défaut, Quotidien est sélectionné avec une valeur d'intervalle (en jours) de 1. Les autres options disponibles sont Hebdomadaire, Mensuel et Annuel.
8.  Dans la zone Plage de répétitions, sélectionnez à quel moment arrêter de générer l'état.
    -   Pas de date de fin : La programmation d'état fonctionne indéfiniment.
    -   Nombre défini d'occurrences : La programmation d'état est exécutée le nombre de fois spécifié, puis elle est désactivée.
    -   Fin le : La programmation d'état se termine à la date spécifiée.

9.  Cliquez sur Enregistrer dans la barre d'outils. Dans la boîte de dialogue Enregistrer sous, spécifiez un nom unique et une description pour la programmation d'état.

Pour copier une programmation d'état, vous devez avoir le rôle de concepteur ou d'administrateur. Même si un administrateur modifie la programmation d'état, l'état contient toujours les informations d'identification de l'utilisateur qui l'a créé.
### <a name="copy-a-report-schedule"></a>Copier une programmation d'état

1.  Dans le générateur d'états, cliquez sur Programmations d'états dans le volet de navigation, puis ouvrez une programmation d'état à copier.
2.  Dans le menu Fichier, cliquez sur Enregistrer sous, puis entrez un nouveau nom et une description pour la programmation dans la boîte de dialogue Enregistrer sous. Cliquez sur OK, et la nouvelle programmation est affichée dans le volet de navigation.
3.  Dans la nouvelle programmation, modifiez les champs et les informations si nécessaire, puis cliquez sur Enregistrer dans la barre d'outils, ou sur Enregistrer dans le menu Fichier.

Pour supprimer une programmation d'état, vous devez en être le propriétaire ou avoir un rôle d'administrateur.
### <a name="delete-a-report-schedule"></a>Supprimer une programmation d'état

1.  Dans le générateur d'états, cliquez sur Programmations d'états dans le volet de navigation.
2.  Sélectionnez la programmation d'état à supprimer, puis cliquez sur Supprimer ou appuyez sur la touche Supprimer.
3.  Dans la boîte de dialogue de vérification de suppression, cliquez sur Oui pour supprimer définitivement la programmation d'état. Si vous n'avez pas l'autorisation de supprimer la programmation, un message s'affiche et l'état n'est pas supprimé.

### <a name="credentials-and-report-schedules"></a>Informations d'identification et programmations d'états

Si vous n'entrez pas les informations d'identification requises pour toutes les sociétés incluses dans les états, vous recevez le message suivant lorsque vous enregistrez la programmation d'état : « Vous devez entrer vos informations d'identification pour les sociétés contenues dans cette programmation d'état. Cliquez sur le bouton Autorisations pour entrer vos informations d'identification. »

Par exemple, Phyllis se connecte à la société A en utilisant son nom d'utilisateur et son mot de passe. Elle crée une programmation pour un état qui utilise une définition d'arborescence de génération d'états pour collecter les données de plusieurs sociétés. Lorsque cette programmation d'état est enregistrée, Phyllis est invitée à entrer des informations d'identification pour les autres sociétés spécifiées dans la définition d'arborescence de génération d'états. Si vos informations d'identification arrivent à expiration, les états affectés dans la programmation d'état ne sont pas générés jusqu'à ce que les informations d'identification soient mises à jour. Un message s'affiche dans la file d'attente d'états pour indiquer que les autorisations doivent être mises à jour. La programmation d'état échoue si l'un des scénarios suivants se produit (car des informations d'identification sont requises) :
-   Une nouvelle société a été ajoutée à une arborescence d'état pour un état individuel.
-   Un état d'un groupe d'états a été modifié.
-   Un nouvel état pour une société supplémentaire a été ajouté à un groupe d'états.

Pour continuer, cliquez sur le bouton Autorisations dans la boîte de dialogue Planification d'état, puis entrez les informations d'identification appropriées.

## <a name="missing-account-analysis-feature"></a> Fonctionnalité Analyse de compte manquante
Vous pouvez rechercher des dimensions et des comptes financiers qui peuvent être manquants dans toutes les définitions de ligne, les définitions d'arborescence de génération d'états, et les définitions d'état dans un groupe de blocs élémentaires. Cela est utile lorsque vous créez ou mettez à jour plusieurs comptes ou blocs élémentaires pendant une courte période et que vous souhaitez vérifier que toutes les nouvelles informations sont incluses dans les états.

Les comptes manquants sont déterminés à l'aide des valeurs les plus basses et les plus élevées à partir de la définition de ligne ou de la définition d'arborescence de génération d'état, puis affiche la liste des comptes qui ne sont pas dans la définition de ligne ou la définition d'arborescence de génération d'état, mais qui figurent dans les données financières. Si un compte manquant est supérieur ou inférieur aux valeurs de la définition de ligne, ce compte n'est pas inclus dans la liste des comptes manquants.
| ![Conseil](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Conseil")**Conseil**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| Pour la validation, ce processus doit être exécuté avant de générer les états mensuels et lors de la création de nouveaux blocs de construction. |

Les états qui ont des plages des valeurs sont moins susceptibles d'avoir des comptes manquants. Si possible, utilisez les plages dans le bloc élémentaire pour inclure de nouveaux comptes lorsqu'ils sont créés. Si une définition d'état est définie sur la société @ANY, vous pouvez alors vous connecter à une société spécifique et exécuter une analyse de compte manquante pour cette société.
| ![Remarque](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Remarque")**Remarque**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si une nouvelle société a été ajoutée, vous devez l'ajouter dans les arborescences de génération d'états dans tous les états existants, sinon elle ne sera pas incluse dans l'analyse des comptes manquants. |

### <a name="run-missing-account-analysis"></a>Exécuter une analyse de compte manquante

1.  Dans Report Designer, cliquez sur Outils, puis sur Analyse de compte manquante.
2.  Dans le champ Filtre de société, sélectionnez une société pour laquelle filtrer les résultats ou sélectionnez Tout (aucun filtre) pour afficher les résultats à partir de toutes les sociétés disponibles.
3.  Dans le champ Filtre de dimension, sélectionnez une dimension pour laquelle filtrer les résultats ou sélectionnez Tout (aucun filtre) pour afficher toutes les informations de dimension pour toutes les dimensions disponibles.
4.  Dans le champ Grouper par, sélectionnez une option pour trier les résultats. Vous pouvez trier les résultats en fonction du bloc élémentaire affecté ou en fonction des ensembles de dimensions et de valeurs.
5.  Réexaminez les résultats affichés. Lorsque vous sélectionnez un bloc dans le volet supérieur, les informations supplémentaires relatives à l'exception s'affichent dans le volet inférieur. Cela inclut les dimensions, les valeurs et les états associés.
6.  Pour ouvrir le bloc associé, cliquez sur l'icône associée affichée dans le volet de liste, ou cliquez avec le bouton droit sur l'article et sélectionnez Ouvrir. Pour sélectionner plusieurs blocs, maintenez la touche Ctrl enfoncée et sélectionnez les blocs dans le volet inférieur.
7.  Si des valeurs, des blocs de construction ou des états sont renvoyés alors qu'ils ne doivent pas être inclus dans l'analyse, cliquez avec le bouton droit sur le bloc et sélectionnez Exclure ou activez la case à cocher Exclure en regard du bloc pour le supprimer de la liste. Les blocs exclus ne sont pas inclus lorsque la liste est actualisée. Pour sélectionner plusieurs blocs, maintenez la touche Ctrl enfoncée alors que vous sélectionnez les blocs dans le volet inférieur. Pour afficher tous les blocs, notamment tous les résultats que vous avez précédemment sélectionnés pour les exclure de l'analyse, activez la case à cocher Afficher les blocs élémentaires et les valeurs, puis cliquez sur Actualiser.
8.  Cliquez sur Actualiser pour actualiser les exceptions que vous avez résolues. Cliquez sur Oui pour effectuer une actualisation complète de tous les résultats, ou cliquez sur Non pour effectuer une actualisation partielle des blocs résolus.
    | ![Remarque](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Remarque")**Remarque**                    |
    |------------------------------------------------------------------------------------------------------------|
    | L'écran est automatiquement actualisé lorsqu'il s'ouvre, sauf s'il a été ouvert dans les 15 dernières minutes. |

9.  Lorsque les problèmes sont résolus, cliquez sur OK pour fermer la boîte de dialogue.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Raccourcis clavier pour l'analyse de compte manquante
Lorsque vous exécutez une analyse de compte manquante, les raccourcis clavier suivants sont disponibles.

| Opération                           | Utiliser ce raccourci clavier |
|--------------------------------------|----------------------------|
| Filtrer par société                    | Alt+C                      |
| Filtrer par dimension                  | Alt+D                      |
| Sélectionnez le champ Grouper par             | Alt+G                      |
| Afficher les blocs et les valeurs exclus      | Alt+S                      |
| Actualiser les résultats                      | Alt+R                      |
| Exclure l'élément constitutif sélectionné  | Alt+X                      |
| Exclure la définition de ligne sélectionnée  | Ctrl+B                     |
| Exclure la valeur de dimension sélectionnée | Ctrl+D                     |
| Ouvrir la définition d'état sélectionnée  | Ctrl+R                     |
| Ouvrir la définition de ligne sélectionnée     | Ctrl+O                     |

 
<a name="see-also"></a>Voir également :
--------

[États financiers](financial-reporting-intro.md)

[Interface du Concepteur de rapports](report-designer-interface.md)



