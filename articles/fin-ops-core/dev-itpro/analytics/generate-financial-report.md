---
title: Générer les états financiers
description: Cet article fournit des informations sur la génération d’un état financier.
author: jinniew
ms.date: 02/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 2f55fe1a23735d8631a5918fa49e08f74eee4d37
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802767"
---
# <a name="generate-financial-reports"></a>Générer les états financiers

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la génération d’un état financier.

Pour générer un état, ouvrez la définition d’état, puis dans la barre d’outils, sélectionnez **Générer**. La page **État de la file d’attente d’états** s’ouvre et indique l’emplacement de votre état dans la file d’attente.

Au fur et à mesure que la génération du rapport progresse, les indicateurs d’état de la file d’attente de rapports suivants peuvent être visibles sur la page **Signaler l’état de la file d’attente**.

| Statut          | État | Description|
|-----------------|--------|--------------------|
| Mise en file d’attente        | Provisoire |La définition du rapport est validée avant que le rapport ne soit placé dans la file d’attente de génération.                    |
| Mis en file d’attente          | Provisoire | Le rapport entre dans la file d’attente de génération de rapports et attend d’être traité.                      |
| Traitement en cours      | Provisoire | Ce statut suit généralement le statut **En file d’attente** et passe généralement à un état **Final** lorsque le traitement est terminé.       |
| Post-traitement | Provisoire | Ce statut fait suite à le statut **Traitement** et indique que toutes les données du rapport sont collectées, mais que des actions dérivées, telles que le calcul et le cumul, sont en cours d’exécution.            |
| Annulation en cours      | Provisoire | Le signalement est annulé à la demande de l’utilisateur. Cet état résulte d’une annulation demandée par l’utilisateur pour un rapport à l’état **En file d’attente** ou **Traitement**. Le système tente de placer le rapport à l’état **Annulé**, sauf si le système est trop avancé et doit le finaliser dans un autre état. |
| Annulé        | Final | Le traitement du rapport est terminé, mais n’a pas abouti en raison d’un arrêt demandé par l’utilisateur.            |
| Terminé       | Final | Le rapport est prêt à être utilisé.                      |
| Échec          | Final | Le rapport a terminé le traitement mais a échoué et ne doit pas être utilisé. |

Par défaut, l’état généré s’affiche dans la visionneuse Web. Les options suivantes sont disponibles pour la génération d’états :

- Paramétrer un calendrier pour générer un état ou un groupe d’états automatiquement
- Vérifier les comptes manquants ou les données manquants dans un état, et validez la précision d’un état

Lorsque vous générez un état, les options que vous avez spécifiées sous les onglets Définition d’état sont utilisées.

## <a name="generate-a-financial-report"></a>Générer un état financier

Pour générer un état financier, accédez à **Comptabilité** \> **Recherches et états** \> **États financiers**.

- Sélectionnez un état à générer, puis sélectionnez **Générer**.
- Renseignez le champ **Date de l’état** et sélectionnez **OK**.

Une fois que l’état a été généré, il est disponible dans la section **États**.

Vous pouvez choisir d’**Afficher** ou de **Supprimer** l’état.

Pour générer un état à l’aide du **Concepteurs d’états**, ouvrez la définition de l’état, puis sélectionnez le bouton **Générer** dans la barre d’outils. La page **État de la file d’attente d’états** s’ouvre et affiche l’emplacement de votre état dans la file d’attente. Par défaut, l’état généré s’affiche dans la visionneuse Web.

## <a name="report-groups"></a>Groupes d’états

Les groupes d’états constituent un moyen efficace de générer plusieurs états en même temps. Par exemple, supposons que vous sachiez qu’à la fin du mois, vos utilisateurs génèrent huit états par mois. Créez un groupe d’états et plutôt que de sélectionner **Générer** pour chacun des huit états du groupe, vous pouvez sélectionner **Générer** pour le groupe d’états et les huit états seront générés en une seule étape. Lorsque les états du groupe d’états sélectionné ont été générés, vous pouvez accéder à **États financiers** (**Comptabilité > Recherches et états > États financiers**) pour afficher les états individuels. Procédez comme suit pour paramétrer un groupe d’états.

1. Dans **Report designer**, sélectionnez **Groupes d’états**. 
2. Sélectionnez les définitions d’état existantes à inclure dans votre groupe d’états. 
3. Sélectionnez les paramètres de remplacement de la société, des détails et de la date dans chacun des états qui seront inclus dans le groupe.
   Nous vous recommandons de paramétrer les informations **Société**, **Période**, **Année** et **Niveau de détail** pour chaque état. 
4. Enregistrez le groupe d’états.

## <a name="schedule-report-generation"></a>Programme de génération des rapports
De nombreuses sociétés disposent d’un ensemble principal de rapports qui sont exécutés à intervalles planifiés correspondant à leurs processus métiers. Vous pouvez programmer la génération régulière d’un état, par exemple chaque jour, chaque semaine, chaque mois ou chaque année. Il peut s’agir d’un seul rapport ou d’un groupe de rapports incluant plusieurs sociétés. Vous devez entrer vos informations d’identification pour chaque société spécifiée, par exemple, chaque société de la définition d’organigramme d’entreprise. Si les informations d’identification ne sont pas valides, l’état affiche uniquement les informations auxquelles vous êtes autorisé à accéder, comme la société à laquelle vous êtes connecté. Les informations de sortie sont lues d’abord à partir du groupe d’état, puis à partir des états individuels.

À mesure que les programmations d’états sont créées et enregistrées, elles sont affichées dans le volet de navigation sous **Programmations d’états**. Vous pouvez créer des dossiers pour organiser les rapports. Même si l’un des rapports du programme n’est pas exécuté, les autres rapports continuent à être exécutés.

> [!IMPORTANT]
> Pour créer, modifier et supprimer les programmes des rapports, vous devez avoir le rôle Administrateur ou Concepteur. Lorsqu’un état est exécuté, les informations d’identification de l’utilisateur ayant créé le programme sont utilisées pour générer l’état.

### <a name="create-a-report-schedule"></a>Créer une programmation d’état

1. Dans **Report Designer**, dans le menu **Fichier**, sélectionnez **Nouveau**, puis sélectionnez **Programmation d’état**. La boîte de dialogue **Nouvelle programmation d’état** s’ouvre.
2. Sous **Paramètres**, sélectionnez un état individuel ou un groupe d’états à planifier. Seuls sont disponibles les rapports ou groupes de rapports de la société ou du bloc élémentaire auquel vous êtes connecté.
3. Activez la case à cocher **Actif** pour activer la programmation d’état. Seul le créateur du rapport ou un administrateur peut activer ou désactiver un programme des rapports.
4. Sélectionnez le bouton **Autorisations** pour entrer les informations d’identification de la société. Par défaut, vos informations de connexion sont utilisées pour la société à laquelle vous êtes connecté. Si d’autres sociétés sont incluses, comme dans les définitions de l’arborescence des états, sélectionnez **Utiliser d’autres informations d’identification**, puis entrez les informations d’identification des autres sociétés incluses dans la programmation d’état. Vous pouvez sélectionner **Authentification Windows** ou taper un nom d’utilisateur et un mot de passe pour chaque société. Activez la case à cocher **Enregistrer les informations d’identification** pour enregistrer les informations d’identification pour ces sociétés, puis sélectionnez **OK** pour fermer la boîte de dialogue.
5. Sous **Fréquence**, dans le champ **Début de la périodicité**, sélectionnez la date à laquelle le programme doit commencer. Par défaut, la date système actuelle de l’ordinateur client est sélectionnée.
6. Dans le champ **Exécuter l’état**, sélectionnez l’heure à laquelle l’état doit s’exécuter. Si vous entrez une heure située avant l’heure système actuelle, le rapport est exécuté à la prochaine date programmée.
7. Dans la zone **Périodicité**, spécifiez la fréquence à laquelle l’état est exécuté. Par défaut, **Quotidien** est sélectionné avec une valeur d’**intervalle (en jours)** de **1**. Les autres options disponibles sont **Hebdomadaire**, **Mensuel** et **Annuel**.
8. Dans la zone **Plage de répétitions**, sélectionnez à quel moment arrêter de générer l’état.

    - **Pas de date de fin** – La programmation d’état fonctionne indéfiniment.
    - **Nombre défini d’occurrences** – La programmation d’état est exécutée le nombre de fois spécifié, puis elle est désactivée.
    - **Fin le** – La programmation d’état se termine à la date spécifiée.

9. Cliquez sur **Enregistrer**. Dans la boîte de dialogue **Enregistrer sous**, spécifiez un nom unique et une description pour la programmation d’état.

Pour copier une programmation d’état, vous devez avoir le rôle de concepteur ou d’administrateur. Même si un administrateur modifie la programmation d’état, l’état contient toujours les informations d’identification de l’utilisateur qui l’a créé.

### <a name="copy-a-report-schedule"></a>Copier une programmation d’état

1. Dans le Report Designer, sélectionnez **Programmations d’états** dans le volet de navigation, puis ouvrez une programmation d’état à copier.
2. Dans le menu **Fichier**, sélectionnez **Enregistrer sous**, puis entrez un nouveau nom et une description pour la programmation dans la boîte de dialogue **Enregistrer sous**. Sélectionnez **OK**, et la nouvelle programmation s’affiche dans le volet de navigation.
3. Dans la nouvelle programmation, modifiez les champs et les informations si nécessaire, puis sélectionnez **Enregistrer** dans la barre d’outils, ou sélectionnez **Enregistrer** dans le menu **Fichier**.

Pour supprimer une programmation d’état, vous devez en être le propriétaire ou avoir un rôle d’administrateur.

### <a name="delete-a-report-schedule"></a>Supprimer une programmation d’état

1. Dans le Report Designer, sélectionnez **Programmations d’état** dans le volet de navigation.
2. Sélectionnez la programmation d’état à supprimer, puis sélectionnez **Supprimer** ou appuyez sur la touche **Supprimer**.
3. Dans la boîte de dialogue de vérification de suppression, sélectionnez **Oui** pour supprimer définitivement la programmation d’état. Si vous n’avez pas l’autorisation de supprimer la programmation, un message s’affiche et l’état n’est pas supprimé.

### <a name="credentials-and-report-schedules"></a>Informations d’identification et programmes des rapports

Si vous n’entrez pas les informations d’identification requises pour toutes les sociétés incluses dans les états, vous recevez le message suivant lorsque vous enregistrez la programmation d’état : « Vous devez entrer vos informations d’identification pour les sociétés contenues dans cette programmation d’état. Cliquez sur le bouton **Autorisations** pour entrer vos informations d’identification ».

Par exemple, un utilisateur se connecte à la Société A à l’aide d’un identifiant et d’un mot de passe. Il crée une programmation pour un état qui utilise une définition d’arborescence de génération d’états pour collecter les données de plusieurs sociétés. Lors de l’enregistrement de ce rapport, l’utilisateur est invité à entrer les informations d’identification des autres sociétés spécifiées dans la définition d’organigramme d’entreprise. Si vos informations d’identification arrivent à expiration, les états affectés dans la programmation d’état ne sont pas générés jusqu’à ce que les informations d’identification soient mises à jour. Un message s’affiche dans la file d’attente d’états pour indiquer que les autorisations doivent être mises à jour. La programmation d’état échoue si l’un des scénarios suivants se produit (car des informations d’identification sont requises) :

- Une nouvelle société a été ajoutée à une arborescence d’état pour un état individuel.
- Un rapport du groupe de rapports a été modifié.
- Un nouveau rapport pour une nouvelle société a été ajouté au groupe de rapports.

Pour continuer, sélectionnez le bouton **Autorisations** dans la boîte de dialogue **Planification d’état**, puis entrez les informations d’identification appropriées.

## <a name="missing-account-analysis-feature"></a>Fonction Analyse des comptes manquants
Vous pouvez rechercher des dimensions et des comptes financiers qui peuvent être manquants dans toutes les définitions de ligne, les définitions d’arborescence de génération d’états, et les définitions d’état dans un groupe de blocs élémentaires. Cela est utile lorsque vous créez ou mettez à jour plusieurs comptes ou blocs élémentaires pendant une courte période et que vous souhaitez vérifier que toutes les nouvelles informations sont incluses dans les états.

Les comptes manquants sont déterminés à l’aide des valeurs les plus basses et les plus élevées à partir de la définition de ligne ou de la définition d’arborescence de génération d’état, puis affiche la liste des comptes qui ne sont pas dans la définition de ligne ou la définition d’arborescence de génération d’état, mais qui figurent dans les données financières. Si un compte manquant est supérieur ou inférieur aux valeurs de la définition de ligne, il n’est pas inclus dans la liste des comptes manquants.

> [!TIP]
> À des fins de validation, ce processus doit être exécuté avant la génération des rapports mensuels et lorsque vous créez des blocs élémentaires.

Les états qui ont des plages des valeurs sont moins susceptibles d’avoir des comptes manquants. Si possible, utilisez les plages dans le bloc élémentaire pour inclure de nouveaux comptes lorsqu’ils sont créés. Si une définition de rapport est définie sur @ANY (n’importe quelle société), vous pouvez vous connecter à une société spécifique et exécuter l’analyse des comptes manquants pour cette société.

> [!NOTE]
> Si une nouvelle société a été ajoutée, vous devez l’ajouter dans les arborescences de génération d’états dans tous les états existants, sinon elle ne sera pas incluse dans l’analyse des comptes manquants.

### <a name="run-missing-account-analysis"></a>Exécuter une analyse de compte manquante

1. Dans Report Designer, sélectionnez **Outils**, puis **Analyse de compte manquante**.
2. Dans le champ **Filtre de société**, sélectionnez une société pour laquelle filtrer les résultats ou sélectionnez **Tout (aucun filtre)** pour afficher les résultats à partir de toutes les sociétés disponibles.
3. Dans le champ **Filtre de dimension**, sélectionnez une dimension pour laquelle filtrer les résultats ou sélectionnez **Tout (aucun filtre)** pour afficher toutes les informations de dimension pour toutes les dimensions disponibles.
4. Dans le champ **Grouper par**, sélectionnez une option pour trier les résultats. Vous pouvez trier les résultats en fonction du bloc élémentaire affecté, ou par ensembles de dimension et de valeur.
5. Passez en revue les résultats affichés. Lorsque vous sélectionnez un élément dans le volet supérieur, le volet inférieur affiche des informations supplémentaires sur l’exception, notamment les dimensions, valeurs et rapports associés.
6. Pour ouvrir le bloc associé, sélectionnez l’icône associée affichée dans le volet de liste, ou cliquez avec le bouton droit sur l’article et sélectionnez **Ouvrir**. Pour sélectionner plusieurs blocs, maintenez la touche **Ctrl** enfoncée et sélectionnez les blocs dans le volet inférieur.
7. Si des valeurs, des blocs de construction ou des états sont renvoyés alors qu’ils ne doivent pas être inclus dans l’analyse, cliquez avec le bouton droit sur le bloc et sélectionnez **Exclure** ou activez la case à cocher **Exclure** en regard du bloc pour le supprimer de la liste. Les blocs exclus ne sont pas inclus lorsque la liste est actualisée. Pour sélectionner plusieurs blocs, maintenez la touche **Ctrl** enfoncée et sélectionnez les blocs dans le volet inférieur. Pour afficher tous les éléments, y compris les résultats que vous avez précédemment exclus de l’analyse, activez la case à cocher **Afficher les valeurs et les blocs élémentaires exclus**, puis cliquez sur **Actualiser**.
8. Sélectionnez **Actualiser** pour actualiser les exceptions que vous avez résolues. Sélectionnez **Oui** pour effectuer une actualisation complète de tous les résultats, ou sélectionnez **Non** pour effectuer une actualisation partielle des blocs résolus.

    > [!NOTE]
    > Le formulaire est actualisé automatiquement lors de son ouverture, sauf si la page a été ouverte au cours des 15 dernières minutes.

9. Lorsque les problèmes sont résolus, sélectionnez **OK** pour fermer la boîte de dialogue.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Raccourcis clavier pour l’analyse de compte manquante
Lorsque vous exécutez une analyse de compte manquante, les raccourcis clavier suivants sont disponibles.

| Opération                           | Appuyer sur |
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
