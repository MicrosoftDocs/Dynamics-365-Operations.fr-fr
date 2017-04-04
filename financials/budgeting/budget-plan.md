---
title: "Planification budgétaire"
description: "L&quot;objectif de ce laboratoire est de fournir une vue pour Microsoft Dynamics 365 pour les mises à jour de fonctionnalité d&quot;opérations dans la zone de planification budgétaire. Cet atelier pratique consiste à illustrer un exemple de configuration rapide du module planification budgétaire et à présenter l&quot;accomplissement de la planification budgétaire à l&quot;aide de cette configuration.  Ce laboratoire se concentrera spécifiquement sur les processus entreprise ou les tâches suivants - - créant la hiérarchie d&quot;organisation pour la planification budgétaire et configuration de la sécurité d&quot;utilisateur - définissant des scénarios de plan budgétaire, des colonnes de plan budgétaire, les mises en page et des modèles Excel - créant et activation d&quot;un processus de planification budgétaire - de la création du document de plan budgétaire en extrayant dans la réalité de la Comptabilité - par les répartitions pour ajuster les données de document de plan budgétaire - données de document de plan budgétaire de modification dans Excel"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Planification budgétaire

L'objectif de ce laboratoire est de fournir une vue pour Microsoft Dynamics 365 pour les mises à jour de fonctionnalité d'opérations dans la zone de planification budgétaire. Cet atelier pratique consiste à illustrer un exemple de configuration rapide du module planification budgétaire et à présenter l'accomplissement de la planification budgétaire à l'aide de cette configuration.  Ce laboratoire se concentrera spécifiquement sur les processus entreprise ou les tâches suivants - - créant la hiérarchie d'organisation pour la planification budgétaire et configuration de la sécurité d'utilisateur - définissant des scénarios de plan budgétaire, des colonnes de plan budgétaire, les mises en page et des modèles Excel - créant et activation d'un processus de planification budgétaire - de la création du document de plan budgétaire en extrayant dans la réalité de la Comptabilité - par les répartitions pour ajuster les données de document de plan budgétaire - données de document de plan budgétaire de modification dans Excel 

<a name="prerequisites"></a>Conditions préalables 
------------------

Pour ce didacticiel, vous devez accéder Dynamics 365 pour l'environnement d'opérations avec les données de démonstration de Contoso, et sont mis en service comme administrateur sur l'instance. Ne pas utiliser {{en:In}} mode privé du navigateur pour ce laboratoire - signe de tout autre compte dans le navigateur si nécessaire et connectez à Dynamics 365 pour les informations d'identification administrateur d'opérations. En signature dans Dynamics 365 pour les opérations, vous ** DEVEZ ** vérifiez « me mise à jour de signature dans la case à cocher. Cette opération crée un cookie persistant dont l'application Excel a besoin actuellement. Si vous vous connectez à Dynamics 365 pour les opérations à l'aide d'un navigateur autre que l'IE, vous êtes invité à signer dans de l'application de calcul Excel. Lorsque vous cliquez sur « Connexion » dans l'application Excel, une fenêtre contextuelle d'IE s'ouvre et lors de la connexion, vous **DEVEZ** activer la case à cocher « Maintenir la connexion ». Si cliquer dans « Connexion » dans l'application Excel ne produit aucun effet, alors vous devez désactiver le cache des cookies d'IE.

## <a name="scenario-overview"></a>**Scenario overview**
Julia travaille en tant que gestionnaire des finances dans les parcs de divertissements de Contoso en Allemagne (DEMF). À mesure que l'exercice fiscal 2016 s'approche, elle doit travailler sur le paramétrage du budget de la société pour l'année suivante. La préparation de budget se présente comme suit :

1.  Julia utilise les montants réels de l'année précédente comme point de départ pour créer le budget.
2.  Selon les chiffres réels de l'année précédente, elle crée des estimations pour 12 mois dans l'année suivante
3.  Julia examine le budget avec le directeur financier. Cela fait, elle fait les ajustements nécessaires au plan budgétaire et finalise la préparation du budget.

Le schéma de configuration de planification budgétaire pour le scénario cherche comme suit :

![Capture d'écran 1](./media/screenshot1-300x152.png)

Julia utilise le modèle Excel suivant permet de préparer le budget :

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Exercice 1 : Configuration
=========================

## <a name="task-1-create-organizational-hierarchy"></a>** Tâche 1 : Créez la hiérarchie organisationnelle **
Comme tout le processus de budgétisation se produit au département Finances, par conséquent Julia doit créer une hiérarchie organisationnelle très simple – se composant du département Finances uniquement. 1.1. Accédez aux hiérarchies d'organisation (hiérarchies d'organisation d'organisations &gt; Administration &gt; d'organisation) et cliquez sur le bouton Créer

![Capture d'écran 3](./media/screenshot3.png) 

1.2. Tapez le nom de la hiérarchie organisationnelle et cliquez sur l'un des objectifs de l'affectation de boutons

![Screenshot4 [] (. - capture 4.png de /media/screen)](. - capture 4.png de /media/screen) 

1.3. Sélectionnez l'objectif de planification budgétaire, cliquer sur le bouton Ajouter et affectent la hiérarchie organisationnelle de nouvelles : 

![Screenshot5 [] (. - capture 5.png de /media/screen)](. - capture 5.png de /media/screen)

1.4. Répétez l'étape ci-dessus pour l'objectif d'organisation de sécurité. Fermez l'écran une fois terminé.

![Screenshot6 [] (. - capture 6.png de /media/screen)](. - capture 6.png de /media/screen)

1.5. Dans l'écran des hiérarchies d'organisation, cliquez sur le bouton Afficher. Cliquez sur Modifier dans le Concepteur de hiérarchies et créez une hiérarchie en cliquant sur le bouton Insérer.

![Screenshot7 [] (. - capture 7.png de /media/screen)](. - capture 7.png de /media/screen) 

1.6. Sélectionnez le département Finances pour la hiérarchie de budgétisation. 

![Screenshot8 [] (. - capture 8.png de /media/screen)](. - capture 8.png de /media/screen)

1.7. Une fois terminé, cliquez sur le bouton Publier et fermer Sélectionnez 1/1/2015 comme date d'effet de la validation de hiérarchie.

![Screenshot9 [] (. - capture 9.png de /media/screen)](. - capture 9.png de /media/screen)

## <a name="task-2-configure-user-security"></a>Tâche 2 : Configurez la sécurité des utilisateurs
La planification budgétaire utilise des stratégies de sécurité spéciales pour configurer l'accès aux données des plans budgétaires. Julia doit octroyer l'accès aux plans budgétaires des Finances pour elle-même. 2.1. Basculez vers le contexte d'entité juridique de DEMF :![Screenshot10 [] (. - capture 10.png de /media/screen)](. - capture 10.png) 2,2 sur /media/screen. Accédez à expliquer &gt; la configuration &gt; définie de planification budgétaire de planification budgétaire. Sous l'onglet de paramètres, définissez la valeur du modèle de sécurité en aux organisations de sécurité![Screenshot11 [] (. - capture 11.png de /media/screen)](. - capture 11.png) 2,3 sur /media/screen. Accédez aux utilisateurs d'utilisateurs &gt; Administration &gt; du système. Donnez à l'utilisateur Administrateur (Julia Funderburk) le rôle de Responsable du budget. ![Screenshot12 [] (. - capture 12.png de /media/screen)](. - capture 12.png) 2,4 sur /media/screen. Prélevez le rôle utilisateur et cliquez sur les organisations d'affecter![Screenshot13 [] (. - capture 13.png de /media/screen)](. - capture 13.png) 2,5 sur /media/screen. Sélectionnez « Accorder l'accès à des organisations spécifiques ». Choisissez une Hiérarchie d'organisation créée dans la première étape. Prélevez le nœud de Finances et cliquez sur la subvention avec le *** de bouton enfants important ! *** * – Assurez-vous d'avoir dans le contexte d'entité juridique de DEMF en effectuant cette tâche, comme sécurité organisationnelle est appliqué par entity* juridique![Screenshot14 [] (. - capture 14.png de /media/screen)](. - capture 14.png de /media/screen)

## <a name="task-3-create-scenarios"></a>Tâche 3 : Créez des scénarios
3.1. Accédez à la configuration&gt;&gt; de planification budgétaire &gt; de planification budgétaire de BudgetingSetup. Dans la page Scénarios notez les scénarios que nous allons utiliser plus loin dans cet atelier pratique : Chiffres réels de l'année précédente et Budgété. *Remarque : vous pouvez créer des scénarios pour cet exercice si vous le voulez et les utiliser à la place.* ![Screenshot15 [] (. - capture 15.png de /media/screen)](. *Note de capture 15.png de /media/screen) : car Julia n'utilise pas le processus d'approbation officielle pour la liste de budget, nous paramétrage ignorerons de workflows, de stades de workflow et stades dans ce laboratoire et utilisons le paramétrage de l'automatique – Permet d'approuver le workflow. Voir l'annexe pour ce workflow configuration.*

## <a name="task-4-create-budget-plan-columns"></a>Tâche 4 : Créez les colonnes du plan budgétaire
Les colonnes du plan budgétaire sont des colonnes monétaires ou basées sur la quantité utilisables dans la structure de document du plan budgétaire. Dans notre exemple nous devons créer une colonne pour les Chiffres réels de l'année précédente et 12 colonnes pour représenter chaque mois de l'année budgétisée. Les colonnes peuvent être créées en cliquant simplement sur le bouton Ajouter et en renseignant les valeurs, ou avec l'aide d'une Entité de données. Dans cet atelier pratique nous emploierons l'Entité de données pour renseigner les valeurs. 4.1. Dans la page&gt;&gt; de colonnes &gt; en cours de configuration de planification budgétaire de planification budgétaire de BudgetingSetup. Cliquez sur le bouton Office dans le coin supérieur droit de l'écran et prélevez les colonnes (non filtrées) [![Screenshot16] (. - capture 16.png de /media/screen)](. - capture 16.png) 4,2 sur /media/screen. Le système ouvre le classeur Excel à utiliser pour renseigner les valeurs. Si invité, cliquez sur pour activer la modification et faites confiance à cette application![Screenshot18 [] (. - capture 18.png de /media/screen)](. - capture 18.png) []![Screenshot17 de (/media/screen. - capture 17.png de /media/screen)](. - capture 17.png) 4,3 sur /media/screen. Il aurons besoin de plus de colonnes complétez les valeurs. Cliquez sur la conception dans le volet de partie droite pour ajouter des colonnes à la grille :![Screenshot19 [] (. - capture 19.png de /media/screen)](. - capture 19.png) 4,4 sur /media/screen. Cliquez sur un nombre restreint de bouton de crayon située en regard de PlanColumns pour voir les colonnes disponibles à ajouter à la grille![Screenshot20 [] (. - capture 20.png de /media/screen)](. - capture 20.png) 4,5 sur /media/screen. Double-cliquez sur chaque champ disponible pour les ajouter aux champs et la mise à jour sélectionnés cliquez sur![Screenshot21 [] (. - capture 21.png de /media/screen)](. - capture 21.png) 4,6 sur /media/screen. Dans le tableau Excel, ajoutez toutes les colonnes qui doivent être créées. Utilisez la fonction Remplissage automatique d'Excel pour ajouter les lignes rapidement. Vérifiez que les lignes sont ajoutées dans le cadre de la table (lorsque vous utilisez le défilement vertical, vous devriez pouvoir afficher les en-têtes de colonne sous le haut de la grille) [![Screenshot22] (. - capture 22.png de /media/screen)](. - capture 22.png) 4,7 sur /media/screen. Revenez à Dynamics 365 pour les opérations et actualiser la page. Les valeurs émises s'affichent dans Dynamics 365 pour les opérations. ![Screenshot23 [] (. - capture 23.png de /media/screen)](. - capture 23.png de /media/screen)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Tâche 5 : Créez des structures et des modèles de document de plan budgétaire
La structure définit à quoi la grille de lignes de document du plan budgétaire ressemble lorsque l'utilisateur ouvre le document de plan budgétaire. Il est également possible de changer la structure de document du plan budgétaire pour afficher les mêmes données dans différents angles. À présent qu'elle a défini les colonnes à utiliser avec notre document de plan budgétaire, Julia doit créer une structure de document du plan budgétaire similaire au tableau Excel qu'elle utilise pour créer les données du budget (voir la section Vue d'ensemble du scénario dans cet atelier pratique) 5.1. En page&gt;&gt; en &gt; cours de mises en page Configuration de planification budgétaire de planification budgétaire de BudgetingSetup. Créez une structure pour l'écriture budgétaire mensuelle :

-   Choisissez l'ensemble de dimensions de MA+BU pour inclure les comptes principaux et les unités commerciales dans la structure.
-   Répertoriez toutes les colonnes du plan budgétaire créées dans l'étape précédente dans la section Éléments. Rendez tous les chiffres, saufs ceux de l'année précédente, modifiables.
-   Cliquez sur le bouton Description pour sélectionner les dimensions financières qui doivent afficher des descriptions dans la grille.

![Screenshot24 [] (. - capture 24.png de /media/screen)](. /media/screen a créé 24.png) selon la définition de mise en page du plan budgétaire que nous pouvons créer un modèle Excel à utiliser comme méthode alternative de modifier les données du budget. Comme le modèle Excel doit correspondre à la définition de la structure de plan budgétaire, vous ne pourrez pas modifier la structure du plan budgétaire après avoir généré le modèle Excel, donc cette tâche doit être effectuée après que tous les composants de la structure sont définis. 5.2. Pour la mise en page créée dans les 5,1. l'étape, Modèle de bouton cliquez sur &gt; se produisent. Confirmer le message d'avertissement. Pour afficher le modèle, vue de modèle &gt; de cliquez sur. *Note : Veillez à sélectionner la « Enregistrer comme » puis sélectionner l'endroit où le modèle doit être enregistré pour la modifier. S'il sélectionne « en cours » dans la boîte de dialogue sans enregistrer, les modifications effectuées au fichier ne seront pas conservées lorsque le fichier est closed.* ![Screenshot25 [] (. - capture 25.png de /media/screen)](. - capture 25.png) 5,3 sur /media/screen. &lt; L'étape facultative&gt; de modifier le modèle Excel pour le faire les présentation plus convivial – Permet d'ajouter des formules de total, champs d'en-tête, mise en forme, et ainsi de suite. enregistrez les modifications et téléchargez le fichier à la mise en page du plan budgétaire en cliquant sur le chargement &gt; de mise en page![Screenshot26 [] (. - capture 26.png de /media/screen)](. - capture 26.png de /media/screen)

## <a name="task-6-create-a-budget-planning-process"></a>Tâche 6 : Créez un processus de planification budgétaire
Julia doit créer et activer un nouveau processus de planification budgétaire en combinant le paramétrage ci-dessus pour commencer à entrer des plans budgétaires. Le processus de planification budgétaire définit les organisations, le workflow, les structures et les modèles de budgétisation qui seront utilisés pour créer des plans budgétaires. 6.1. Accédez à expliquer &gt; le processus &gt; de planification budgétaire paramétré &gt; de planification budgétaire et de créer un nouvel enregistrement.

-   Processus de planification budgétaire – Budgétisation DEMF exercice 2016
-   Cycle budgétaire – Exercice 2016
-   Comptabilité – DEMF
-   Structure de compte par défaut – Fabrication P&L
-   Hiérarchie d'organisation – Choisissez la hiérarchie créée au début de l'atelier pratique
-   Workflow de planification budgétaire – affecter Automatique – Approuver le workflow pour le département Finances
-   Dans les règles et les modèles de la phase de planification budgétaire, pour chaque phase de planification budgétaire choisissez si l'ajout de lignes et la modification des lignes sont autorisées et la structure à utiliser par défaut

*Remarque : vous pouvez créer des structures supplémentaires de document et les affecter pour qu'elles soient disponibles au stade du workflow de planification budgétaire en cliquant sur le bouton Autres structures.* ![Screenshot27 [] (. - capture 27.png de /media/screen)](. - capture 27.png) 6,2 sur /media/screen. Sélectionnez les actions &gt; à activer pour activer ce workflow de planification budgétaire![Screenshot28 [] (. - capture 28.png de /media/screen)](. - capture 28.png de /media/screen)

<a name="exercise-2-process-simulation"></a>Exercice 2 : Simulation du processus
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Tâche 7 : Générez des données initiales pour le plan budgétaire à partir de la comptabilité
7.1. Accédez à la budgétisation &gt; périodique &gt; génèrent le plan budgétaire de la comptabilité. Renseignez les paramètres du processus périodique et cliquez sur le bouton Générer. ![Screenshot29 [] (. - capture 29.png de /media/screen)](. - capture 29.png) 7,2 sur /media/screen. Accédez aux plans budgétaires &gt; de trouver un plan budgétaire créé par processus Generate. ![Screenshot30 [] (. - capture 30.png de /media/screen)](. - capture 30.png) 7,3 sur /media/screen. Ouvrez les détails du document en cliquant sur le lien hypertexte du numéro de document. Le plan budgétaire est affiché comme défini dans la mise en page pendant ce laboratoire![Screenshot31 [] (. - capture 31.png de /media/screen)](. - capture 31.png de /media/screen)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Tâche 8 : Créez un budget de l'année en cours basé sur les chiffres réels de l'année précédente
Les méthodes de répartition peuvent être utilisées dans le plan budgétaire pour copier facilement les informations des plans budgétaires d'un scénario à un autre / les répartir sur des périodes / répartir sur des dimensions. Nous emploierons des répartitions pour créer le budget de l'année en cours à partir des chiffres réels de l'année précédente. 8.1. Prélevez toutes les lignes dans la grille de document de plan budgétaire et cliquer sur le bouton éventuelle budget le![Screenshot32 [] (. - capture 32.png de /media/screen)](. - capture 32.png) 8,2 sur /media/screen. Sélectionnez le mode de répartition, clé de période, source et scénarios et cliquez de destination éventuelle 

![Screenshot33 [] (. - capture 33.png de /media/screen)](. - capture 33.png de /media/screen)

Les montants réels d'année précédente sont copiés dans le budget de l'année en cours et les répartir sur plusieurs périodes à l'aide de la clé de période de courbe de ventes. 

![Screenshot34 [] (. - capture 34.png de /media/screen)](. - capture 34.png de /media/screen)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Tâche 9 : Ajustez le document de plan budgétaire à l'aide d'Excel et finalisez le document
9.1. Cliquez sur la feuille de calcul de bouton dans le contenu du document en cours dans Excel

![Screenshot35 [] (. - capture 35.png de /media/screen)](. - capture 35.png de /media/screen)

9.2. Lorsque le classeur Excel s'ouvre, ajustez les numéros dans le document de plan budgétaire et cliquez sur le bouton Publier.

![Screenshot36 [] (. - capture 36.png de /media/screen)](. - capture 36.png de /media/screen)

9.3. Retour au document de plan budgétaire dans Dynamics 365 pour les opérations. Le workflow de sur &gt; l'envoi automatique d'approuver le document

![Screenshot37 [] (. - capture 37.png de /media/screen)](. - capture 37.png de /media/screen) 

Une fois le workflow complète, la phase de document de plan budgétaire change à approuvé. ![Screenshot38 [] (. - capture 38.png de /media/screen)](. - capture 38.png de /media/screen)

<a name="appendix"></a>Annexe
========

### <a name="auto-approve-workflow-configuration"></a>Configuration du workflow d'approbation automatique.

A. Les workflows &gt; de budgétisation &gt; paramétrés &gt; de budgétisation de planification budgétaire créer un nouveau workflow avec des workflows de planification budgétaire de modèle :

![Screenshot39 [] (. - capture 39.png de /media/screen)](. - capture 39.png de /media/screen)

Ce workflow ne contient une tâche – plan budgétaire de transition de stade 

![Screenshot40 [] (. - capture 40.png de /media/screen)](. - capture 40.png de /media/screen) 

Enregistrez et d'activer le workflow. 

B. Accédez à expliquer &gt; la configuration &gt; définie de planification budgétaire de planification budgétaire. Sous l'onglet de stades créez 2 stades – d'origine et envoyés 

![Screenshot41 [] (. - capture 41.png de /media/screen)](. - capture 41.png de /media/screen)

C. Accédez à expliquer &gt; la configuration &gt; définie de planification budgétaire de planification budgétaire. Dans l'associer d'onglet de stades de workflow le workflow automatique (approuver créé à l'étape A à l'origine de stades et envoyé 

![Screenshot42 [] (. - capture 42.png de /media/screen)](. - capture 42.png de /media/screen)  


