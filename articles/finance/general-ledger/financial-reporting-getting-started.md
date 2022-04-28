---
title: Présentation de Financial Reporting
description: Cette rubrique explique où accéder à Financial Reporting dans Microsoft Dynamics 365 Finance et comment utiliser les fonctionnalités de Financial Reporting.
author: aprilolson
ms.date: 03/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "10444"
- intro-internal
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcdb5a934818468e00be960f9afe541966e5eabf
ms.sourcegitcommit: e8a2a1e34fa48a42afac9724828f4ec72b6d7085
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8573648"
---
# <a name="get-started-with-financial-reporting"></a>Démarrage de Financial Reporting 

[!include [banner](../includes/banner.md)]

Cette rubrique explique où accéder à Financial Reporting et comment utiliser les fonctionnalités de Financial Reporting. Elle inclut également une description des états financiers par défaut fournis.

## <a name="accessing-financial-reporting"></a>Accès à la génération d’états financiers

Vous pouvez trouver le menu **États financiers** dans les endroits suivants :

- **Comptabilité** &gt; **Recherches et états**
- **Budget** &gt; **Recherches et états** &gt; **Budget de base**
- **Budget** &gt; **Recherches et états** &gt; **Planification budgétaire**
- **Budget** &gt; **Recherches et états** &gt; **Contrôle budgétaire**
- Regroupements

Pour créer et générer des états financiers pour une entité juridique, vous devez paramétrer les informations suivantes pour cette entité juridique :

- Calendrier fiscal
- Registre
- Plan comptable
- Devise
- Imputer une transaction sur au moins un compte
- MainAccount est répertorié dans la colonne **Sélectionné** sur la page **Configuration des états financiers** (**Comptabilité > Configuration comptabilité > Configuration des états financiers**)

## <a name="granting-security-access-to-financial-reporting"></a>Accorder un accès sécurisé à la génération des états financiers

Les fonctions de génération d’états financiers sont disponibles aux utilisateurs ayant les droits et les devoirs appropriés par l’intermédiaire de leurs rôles de sécurité. Les sections suivantes décrivent ces privilèges et responsabilités, ainsi que les rôles associés.

### <a name="duties"></a>Droits

| Nom de la responsabilité                            | Description                                                             | Nom d’AOA                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Tenir à jour la sécurité des états financiers | Tenir à jour la sécurité de Financial Reporting et exécuter des tâches d’administration. | FinancialReportsSecurityMaintain |
| Tenir à jour les états financiers            | Créer et tenir à jour les états financiers.                                  | FinancialReportsMaintain         |
| Générer les états financiers            | Générer et actualiser les états financiers.                                 | FinancialReportsGenerate         |
| Examiner les performances financières          | Examiner et analyser les performances financières.                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>Privilèges

| Nom du privilège                       | Description                                                             | Nom d’AOA                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| Tenir à jour la sécurité des états financiers | Tenir à jour la sécurité de Financial Reporting et exécuter des tâches d’administration. | FinancialReportsSecuritySystemMaintain |
| Tenir à jour les états financiers            | Créer et tenir à jour les états financiers.                                  | FinancialReportsMaintainReports  |
| Générer les états financiers            | Générer et actualiser les états financiers.                                 | FinancialReportsGenerateReports  |
| Afficher les états financiers                | Afficher les états financiers.                                                 | FinancialReportsView             |

### <a name="roles"></a>Rôles

| Nom du privilège                       | Obligation                                  | Rôles                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| Tenir à jour la sécurité des états financiers | Tenir à jour la sécurité de Financial Reporting | Administrateur sécurité                                                          |
| Tenir à jour les états financiers            | Tenir à jour les états financiers            | Gestionnaire comptable, chef comptable, contrôleur financier, responsable du budget |
| Générer les états financiers            | Générer les états financiers            | PDG, directeur financier, comptable                                                            |
| Afficher les états financiers                | Examiner les performances financières          | Aucun affecté                                                                   |

Une fois qu’un utilisateur a été ajouté ou qu’un rôle a été modifié, l’utilisateur doit pouvoir accéder à la génération d’états financiers en quelques minutes. 

> [!NOTE]
> Le rôle sysadmin est ajouté à tous les rôles de la génération d’états financiers.

## <a name="report-deletions-and-expirations"></a>Signaler les suppressions et les expirations

Les utilisateurs qui génèrent un état peuvent supprimer leurs propres états. Les utilisateurs avec le droit **Tenir à jour la sécurité des états financiers** peuvent supprimer les états des autres. 

Dans la version 10.0.8, le concept de dates d’expiration a été introduit. Une nouvelle fonctionnalité requise est activée dans la page **Tous** dans l’espace de travail de gestion des fonctionnalités. La fonctionnalité **Stratégie de conservation des états financiers** contient les modifications suivantes :
* Les états nouvellement générés seront automatiquement marqués comme ayant une date d’expiration de 90 jours à compter de leur génération.
* Tous les états existants antérieurs à l’installation de la fonctionnalité auront une période d’expiration de 90 jours. La date peut s’afficher comme vide pendant une courte période jusqu’à ce que le service Financial Reporting s’exécute, qu’un état soit généré et que le service effectue la mise à jour des états existants avec une date d’expiration vide. 
* Les utilisateurs disposant du droit **Tenir à jour la sécurité des états financiers** ont accès à cette fonctionnalité. Tout utilisateur dans le droit **Tenir à jour la sécurité des états financiers** se voyant accorder le privilège **Tenir à jour l’expiration des états financiers** aura également la possibilité de modifier la période d’expiration. Actuellement, deux options de rétention sont disponibles : 

    * Une expiration au bout de 90 jours.
    * Une option pour que l’état n’expire jamais.

Lorsqu’une expiration de 90 jours est sélectionnée, elle s’applique pendant 90 jours à compter du jour en cours. C’est un comportement différent des 90 jours à partir de la date de génération d’origine définie lors de la génération de l’état. 

Des options supplémentaires seront envisagées dans les fonctionnalités futures. L’expiration au bout de 90 jours sera la valeur par défaut, et les utilisateurs disposant des autorisations appropriées peuvent remplacer la valeur par défaut sur la page de liste **États financiers**.

## <a name="default-reports"></a>États par défaut

Les états financiers fournissent 22 états financiers par défaut. Chaque rapport utilise les catégories de compte principal par défaut. Vous pouvez utiliser ces états tels quels ou en tant que point de départ pour vos besoins en matière d’états financiers. Outre les tableaux d’analyse traditionnels, tels que le rapport de revenus et le bilan de résultats, ces états par défaut incluent des états qui indiquent les différents types d’états financiers que vous pouvez créer. 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| État par défaut                                                                                         | Description                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Relevé des revenus sur 12 mois roulants à une seule colonne – Par défaut | Permet d’afficher la rentabilité d’une organisation pour les 12 derniers mois dans une colonne unique.                                                                                                                                                                                                                                      |
| Relevé des revenus, tendance sur 12 mois – Par défaut                 | Permet d’afficher la rentabilité d’une organisation pour chacun des 12 derniers mois. Ces 12 mois peuvent couvrir plus d’un exercice.                                                                                                                                                                                             |
| Comparatif Réel/Budget – Par défaut                                | Permet d’afficher les informations détaillées sur le solde pour tous les comptes pour le budget d’origine, et de comparer le budget révisé aux valeurs réelles présentant un écart.                                                                                                                                                                          |
| Détails d’audit – Par défaut                                  | Permet d’afficher les informations détaillées du solde pour tous les comptes. Cet état indique les soldes de débit et de crédit dans la devise de déclaration et la devise locale, ainsi que les informations des transactions supplémentaires, telles que l’ID utilisateur, l’utilisateur ayant modifié les données en dernier, la date de la dernière modification et l’ID de journal. |
| Liste de solde – Par défaut                                   | Permet d’afficher les informations détaillées du solde pour tous les comptes. Cet état indique les soldes d’ouverture et de clôture, et les soldes de débit et de crédit pour la période actuelle et l’année jusqu’à présent, ainsi que les informations des transactions supplémentaires, telles que le N° document.                                                                    |
| Bilan – Par défaut                                   | Permet d’afficher la position financière de l’organisation pour l’année.                                                                                                                                                                                                                                                             |
| Bilan et relevé des revenus côte à côte – Par défaut | Permet d’afficher la position financière et la rentabilité de l’organisation pour l’année, côte à côte.                                                                                                                                                                                                                              |
| Flux de trésorerie – Par défaut                                       | Renseigne sur la trésorerie entrante et sortante de l’organisation.                                                                                                                                                                                                                                   |
| Révision détaillée JE et TB – Par défaut                      | Permet d’afficher le solde d’ouverture et les informations d’activité pour tous les comptes.                                                                                                                                                                                                                                                      |
| [Balance comptable détaillée – Par défaut](trial-balance-financial-reports.md)| Permet d’afficher les informations de solde pour tous les comptes ayant des soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.                                                                                                                                  |
| Tendance des dépenses trimestrielles sur trois ans – Par défaut             | Renseigne sur les dépenses pour les 12 derniers trimestres des trois années précédentes.                                                                                                                                                                                                                                   |
| Révision JE et TB des légendes financières – Par défaut            | Donne la vue d’ensemble des soldes et de l’activité pour les légendes financières des immobilisations, du passif, des capitaux propres, du produit, des dépenses, des bénéfices, ou des pertes.                                                                                                                                                                           |
| [Relevé des revenus – Par défaut](income-statement-financial-report.md)| Permet d’afficher la rentabilité de l’organisation pour la période actuelle et l’année jusqu’à ce jour.                                                                                                                                                                                                                                   |
| Liste des écritures comptables – Par défaut                        | Permet d’afficher les informations détaillées du solde pour tous les comptes. Cet état affiche les soldes de débit et de crédit, ainsi que les informations de transaction supplémentaires, telles que la date de la transaction, le numéro de journal, le N° document, le type de validation et le numéro de suivi.                                                                            |
| Taux – Par défaut                                          | Permet d’afficher la solvabilité, la rentabilité et les taux de rendement de l’organisation pour l’année.                                                                                                                                                                                                                           |
| Dépenses sur 12 mois roulants – Défaut                       | Renseigne sur les dépenses de chacun des 12 derniers mois. Ces 12 mois peuvent couvrir plus d’un exercice.                                                                                                                                                                                                       |
| Relevé des revenus trimestriels roulants – Par défaut               | Permet d’afficher la rentabilité de l’organisation par trimestre, pour la dernière année et l’année jusqu’à ce jour.                                                                                                                                                                                                                   |
| Bilan côte à côte bilan – Par défaut                      | Permet d’afficher la position financière de l’organisation pour l’année. Cet état affiche les actifs et passifs et les capitaux propres des actionnaires côte à côte.                                                                                                                                                                                |
| [Synthèse de balance comptable– Par défaut](trial-balance-financial-reports.md)| Permet d’afficher les informations du solde pour tous les comptes ayant des soldes d’ouverture et de clôture, et les soldes de débit et de crédit ensemble avec leur différence nette.                                                                                                                                                                  |
| [Synthèse de balance comptable d’une année à l’autre – Par défaut](trial-balance-financial-reports.md)| Permet d’afficher les informations du solde pour tous les comptes ayant des soldes d’ouverture et de clôture, et les soldes de débit et de crédit ensemble avec leur différence nette pour l’année courante et l’année précédente.                                                                                                                           |
| Ventes et remises hebdomadaires – Par défaut                     | renseigne sur les ventes et les remises de chaque semaine d’un mois. Cet état inclut un total sur quatre semaines.                                                                                                                                                                                                              |
| Fonds budgétaires disponibles – Par défaut                         | Permet d’afficher une comparaison détaillée du budget révisé, des dépenses réelles, des réservations budgétaires et des fonds budgétaires disponibles pour tous les comptes                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>Ouverture d’états financiers

Lorsque vous sélectionnez le menu **États financiers**, la liste des états financiers par défaut pour la société s’affiche. Vous pouvez ensuite ouvrir ou modifier un état. Pour ouvrir un des états par défaut, sélectionnez le nom de l’état. La première fois que l’état est ouvert, il est automatiquement généré pour le mois précédent. Par exemple, si vous ouvrez un état pour la première fois en août 2019, l’état est généré pour le 31 juillet 2019. Après l’ouverture d’un état, vous pouvez démarrer l’exploration en accédant à des ensembles de données spécifiques et en modifiant les options d’état.

## <a name="creating-and-modifying-financial-reports"></a>Création et modification d’états financiers

Dans la liste des états financiers, vous pouvez créer un nouvel état ou modifier un état existant. Si vous disposez des autorisations appropriées, vous pouvez créer un état financier en sélectionnant **Nouveau** dans le volet Actions. Un programme de concepteur d’états est téléchargé sur votre périphérique. Une fois que le concepteur d’états démarre, vous pouvez créer l’état. Après avoir enregistré le nouvel état, il apparaît dans la liste des états financiers. La liste affiche uniquement les états créés pour la société utilisés dans Dynamics 365 Finance. 

## <a name="reporting-tree-definitions"></a>Définitions d’organigramme d’entreprise

L’un des composants utilisés pour générer des états financiers est une définition d’arborescence de génération d’états. Une définition de l’arborescence de génération d’états permet de définir la structure et la hiérarchie de votre organisation. Il s’agit d’une hiérarchie inter-dimensionnelles basée sur des relations dimensionnelles dans vos données financières. Elle fournit des informations au niveau de l’unité organisationnelle et à un niveau synthétique pour toutes les unités dans l’arborescence.

Vous pouvez créer un nombre illimité d’arborescences de génération d’état pour afficher les données de votre organisation de différentes manières. Chaque arborescence de génération d’états peut contenir n’importe quelle combinaison de services et d’unités de synthèse, mais une définition d’état ne peut être liée qu’à une seule arborescence de génération d’états à la fois. 

## <a name="update-the-financial-reporting-version-through-slipstreaming"></a>Mettre à jour la version de Financial Reporting via l’intégration

Les applications Finance et Opérations sont mises à jour tous les mois. Cependant, Financial Reporting n’est pas nécessairement mis à jour à cette cadence. De plus, les clients ont plus de possibilités quant au moment où ils implémentent les mises à jour pour les applications Finance et Opérations. Les mises à jour de Financial Reporting sont automatiquement installées. Financial Reporting a une version désignée qui est utilisée dans un environnement client lorsqu’une mise à jour de service est mise en œuvre, lorsqu’un temps d’arrêt est déclenché ou lorsque l’environnement d’un client est en mode Maintenance. Ce processus est connu sous le nom d’*intégration* ou d’*ajustement*, car toutes les implémentations client sont définies sur la même version de Financial Reporting.

Les changements qui sont publiés dans chaque version sont disponibles dans [Nouveautés ou modifications dans Dynamics 365 Finance](../../finance/get-started/whats-new-home-page.md). Les mises à jour de la plate-forme et les corrections de bogues sont disponibles dans la section « Ressources supplémentaires » en bas de la page pour chaque version.

La version intégrée sélectionnée est une version révisée et validée de Financial Reporting qui est prête pour la production. Elle est compatible avec toute version précédente ou ultérieure de Dynamics 365 Finance. Par exemple, Financial Reporting peut être sur la dernière version 10.0.19 alors que le client utilise toujours la version 10.0.16 de l’application.

> [!NOTE]
> La seule circonstance dans laquelle les clients peuvent passer à une version précédente (scénario de rétrogradation) se produit si Microsoft arrête un déploiement d’ajustement suite à un problème. Dès qu’un correctif est disponible, il est appliqué automatiquement.

Le processus d’intégration est entièrement automatisé et ne nécessite aucune action du client. Trois topologies utilisent l’intégration, chacune d’une manière légèrement différente :

- **Local** : les déploiements sur site ne prennent pas en charge l’intégration ni l’ajustement.
- **Infrastructure as a service (IaaS)**  : la logique d’intégration est appliquée lors de toute opération visant à mettre à jour Financial Reporting. Elle comprend des mises à jour binaires ou des diffusions contenant des mises à jour binaires.
- **Libre service** : toute opération nécessitant un temps d’arrêt de Financial Reporting applique la logique d’intégration :

    - Mises à jour binaires ou diffusions qui incluent les mises à jour binaires
    - Correction S ou autre temps d’arrêt de l’infrastructure
    - Déploiements du package AOT

## <a name="troubleshooting-issues-opening-report-designer"></a>Résolution des problèmes d’ouverture du Concepteur de rapports

Il existe quelques problèmes courants qui peuvent provoquer des problèmes lorsque vous ouvrez le Concepteur de rapports. Ces problèmes et les étapes pour les résoudre sont les suivants.

Problème 1 : le Concepteur de rapports ne démarre pas lorsque vous sélectionnez **Nouveau** ou **Modifier**.

* Dans Internet Explorer, sélectionnez **Paramètres**, puis sélectionnez **Options Internet**. Sélectionnez l’onglet **Sécurité**. Sélectionnez Sites de confiance, puis sélectionnez **Sites**. Dans la section **Ajouter ce site Web à la zone**, entrez « \*\.dynamics.com » (sans guillemets), puis sélectionnez **Ajouter**. 
* Dans Internet Explorer, sélectionnez **Paramètres**, puis sélectionnez **Options Internet**. Sélectionnez l’onglet **Sécurité**. Sélectionnez Sites de confiance. Dans la zone intitulée Niveau de sécurité pour cette zone, modifiez l’option en **Moyen-faible**.
* Désactivez le bloqueur de fenêtres publicitaires dans votre navigateur.
* Les postes de travail doivent installer Microsoft .NET Framework 4.7.2 ou version supérieure. Cette version de Microsoft .NET Framework peut être téléchargée et installée à partir du [Centre de téléchargement Microsoft](https://dotnet.microsoft.com/download/dotnet-framework/net472).
* Si vous utilisez le navigateur Chrome, vous devez installer une extension ClickOnce afin de télécharger le client Concepteur de rapports. Si vous utilisez Chrome en mode incognito, vérifiez que l’extension ClickOnce est activée pour le mode incognito. Pour plus d’informations sur l’extension ClickOnce de Chrome, voir [Configuration requise pour les déploiements Cloud](../../fin-ops-core/fin-ops/get-started/system-requirements.md).
* Si vous utilisez Microsoft Edge avec un navigateur Chrome, vous n’avez pas besoin d’installer une extension ClickOnce pour Edge Chromium. Cependant, vous devez activer l’option ClickOnce pour télécharger le client Report Designer. Si vous utilisez le mode incognito, vérifiez que l’extension ClickOnce est activée pour le mode incognito.

    1. Ouvrez un nouveau navigateur dans Microsoft Edge.
    2. Entrez **edge://flags** et sélectionnez **Entrée**.
    3. Recherchez l’option **Support ClickOnce** ou utilisez ce lien direct : **edge://flags/#edge-click-once**.
    4. Définissez l’option du menu déroulant sur **Activé**.
    5. Sélectionnez **Redémarrer le navigateur**.

Problème 2 : l’utilisateur n’a pas reçu les autorisations requises pour utiliser Financial Reporting. 

* Pour vérifier si l’utilisateur n’a pas l’autorisation, sélectionnez **Oui** sur l’erreur « Impossible de se connecter au serveur Financial Reporting. Sélectionnez Oui si vous souhaitez continuer et spécifier une adresse de serveur différente. » Sélectionnez ensuite **Tester la connexion**. Si vous n’avez pas l’autorisation, vous verrez un message indiquant : « La tentative de connexion a échoué. L’utilisateur ne dispose pas des autorisations appropriées pour se connecter au serveur. Contactez votre administrateur système. »
* Les autorisations requises sont répertoriées ci-dessus dans [Accorder un accès sécurisé à la génération des états financiers](#granting-security-access-to-financial-reporting). La sécurité dans Financial Reporting repose sur ces privilèges. Vous n’aurez pas accès à moins que ces privilèges (ou un autre rôle de sécurité qui inclut ces privilèges) ne vous soient attribués. 
* La tâche d’intégration **Fournisseur des utilisateurs de l’entreprise – Entreprise** (qui correspond également à l’intégration utilisateur) s’exécute selon un intervalle de 5 minutes. Il peut s’écouler jusqu’à 10 minutes pour que les modifications d’autorisation prennent effet dans Financial Reporting. 

    Si un autre utilisateur peut ouvrir le Concepteur de rapports, sélectionnez **Outils**, puis sélectionnez **Statut de l’intégration**. Vérifiez que la mappe d’intégration, « Fournisseur des utilisateurs de l’entreprise – Entreprise », s’est exécutée correctement car vous avez reçu l’autorisation d’utiliser Financial Reporting. 

* Il est possible qu’une autre erreur ait empêché l’achèvement de l’**intégration entre utilisateur Dynamics et utilisateur Financial Reporting**. Ou il est possible qu’une réinitialisation des données ait été lancée et ne soit pas encore terminée, ou qu’une autre erreur système se soit produite. Réessayez d’exécuter le processus plus tard. Si le problème persiste, contactez votre administrateur système.

Problème 3 : vous pouvez continuer au-delà de la page de connexion **ClickOnce Report Designer**, mais vous ne parviendrez pas à terminer la connexion dans Report Designer. 

* L’heure définie sur votre ordinateur local lorsque vous entrez vos informations de connexion doit être fidèle à cinq minutes près à l’heure sur le serveur Financial Reporting. Si la différence est supérieure à cinq minutes, le système n’autorisera pas la connexion. 
* Si l’heure sur votre ordinateur diffère de l’heure sur le serveur Final Reporting, nous vous recommandons d’activer l’option Windows pour régler l’heure de votre ordinateur automatiquement. 

## <a name="troubleshoot-report-designer-issues-with-event-viewer"></a>Résoudre les problèmes de Report Designer avec l’Observateur d’événements

Vous pouvez utiliser l’Observateur d’événements pour analyser certains des problèmes qui surviennent lors de l’utilisation de Financial Reporting. 

### <a name="what-happens-when-you-have-connections-issues-with-financial-reporting"></a>Que se passe-t-il lorsque vous rencontrez des problèmes de connexion avec Financial Reporting ? 

Voici quelques étapes que vous pouvez suivre pour rendre votre conversation avec le support Microsoft plus efficace et vous amener à une résolution plus rapide. 
 
Les étapes suivantes décrivent le processus d’activation des messages de l’Observateur d’événements pour Financial Reporting. Les journaux générés par l’Observateur d’événements aideront les ingénieurs du support à identifier rapidement la source du problème de connexion. Envoyez des copies de ces journaux avec votre ticket lorsque vous contactez le support.


1. Copiez le fichier RegisterETW.zip sur la station de travail client (de préférence sur le Bureau) et extrayez [RegisterETW.zip](https://mbs2.microsoft.com/fileexchange/?fileID=60b1106b-d5f8-4e0f-8041-039102505122).
2. Assurez-vous que l’Observateur d’événements Windows est fermé.
3. Ouvrez une invite de commande Administrateur PowerShell et accédez au répertoire où se trouve RegisterETW.ps1.
4. Exécutez la commande suivante : .\RegisterETW.ps1

    Une sortie réussie dans PowerShell sera vérifiée avec le message **Script RegisterETW complété**.

    Rouvrez l’Observateur d’événements et vous voyez maintenant ces journaux sous **Microsoft > Dynamics** :

    * MR-Client
    * MR-DVT
    * MR-Intégration
    * MR-Logger
    * MR-Reporting
    * MR_SchedulerTasks
    * MR-Sql
    * MR-TraceManager

5. Reproduisez le problème dans Report Designer.
6. Exportez les événements MR-Logger à l’aide de l’Observateur d’événements.

## <a name="troubleshoot-issues-connecting-to-financial-reporting"></a>Résoudre les problèmes de connexion à Financial Reporting

Problème : Vous recevez l’erreur « Impossible de se connecter au serveur Financial Reporting ».

* Déterminez si le problème se produit dans les navigateurs Internet Chrome et Edge.
* Si le problème ne se produit que dans un seul navigateur, il peut s’agir d’un problème ClickOnce. 
* Lorsque vous obtenez le message d’erreur de connexion, sélectionnez **Tester** pour tester la connexion et voir quel message apparaît. 
* Le problème peut être dû au fait qu’un autre utilisateur n’a pas accès à Financial Reporting. Si un utilisateur n’a pas accès, il recevra un message indiquant qu’il n’a pas l’autorisation.
* Si le problème se produit sur plusieurs navigateurs, assurez-vous que l’horloge sur votre station de travail est définie sur Auto.
* Travaillez avec un utilisateur disposant des droits d’administrateur de la sécurité dans Dynamics 365 Finance et des droits d’administrateur sur le domaine réseau pour se connecter à votre station de travail et vérifier qu’ils peuvent se connecter. S’ils peuvent se connecter, le problème peut être lié aux autorisations réseau.
* Sur la station de travail, désactivez temporairement le pare-feu. Si vous pouvez ensuite vous connecter à Report Designer, le problème vient de votre pare-feu. Collaborez avec le service informatique de votre organisation pour résoudre le problème.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Afficher les états financiers](view-financial-reports.md)
- [Définitions d’arborescence de génération d’états dans les états financiers](../../fin-ops-core/dev-itpro/analytics/financial-reporting-tree-definitions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
