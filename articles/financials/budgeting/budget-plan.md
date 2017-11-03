---
title: "Planification budgétaire"
description: "L'objectif de cet atelier consiste à fournir une vue guidée des mises à jour de fonctionnalités Microsoft Dynamics 365 for Finance and Operations, Enterprise edition dans la zone de planification budgétaire. Cet atelier pratique consiste à illustrer un exemple de configuration rapide du module planification budgétaire et à présenter l'accomplissement de la planification budgétaire à l'aide de cette configuration.  Cet atelier pratique se concentrera spécifiquement sur les processus ou les tâches d'entreprise : - Création de la hiérarchie d'organisation pour la planification budgétaire et la configuration de la sécurité utilisateur - Définition de scénarios de plan budgétaire, de colonnes de plan budgétaire, de mises en page et de modèles Excel - Création et activation du processus de planification budgétaire - Création de document de plan budgétaire par l'extraction de chiffres réels de la comptabilité - Utilisation des répartitions pour ajuster les données du document de plan budgétaire - Modification de données de document de plan budgétaire dans Excel"
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 608ec87233acb05b0d46e367bcb7cd14985d7813
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="budget-planning"></a>Planification budgétaire

[!include[banner](../includes/banner.md)]


L'objectif de cet atelier consiste à fournir une vue guidée des mises à jour de fonctionnalités Microsoft Dynamics 365 for Finance and Operations, Enterprise edition dans la zone de planification budgétaire. Cet atelier pratique consiste à illustrer un exemple de configuration rapide du module planification budgétaire et à présenter l'accomplissement de la planification budgétaire à l'aide de cette configuration.  Cet atelier pratique se concentrera spécifiquement sur les processus ou les tâches d'entreprise : - Création de la hiérarchie d'organisation pour la planification budgétaire et la configuration de la sécurité utilisateur - Définition de scénarios de plan budgétaire, de colonnes de plan budgétaire, de mises en page et de modèles Excel - Création et activation du processus de planification budgétaire - Création de document de plan budgétaire par l'extraction de chiffres réels de la comptabilité - Utilisation des répartitions pour ajuster les données du document de plan budgétaire - Modification de données de document de plan budgétaire dans Excel 

<a name="prerequisites"></a>Conditions préalables 
------------------

Pour ce didacticiel, vous devez accéder à l'environnement Finance and Operations avec les données de démonstration de Contoso, et bénéficier des droits d'administrateur sur l'instance. N'utilisez pas le mode privé du navigateur pour l'atelier pratique - déconnectez-vous de tout autre compte dans le navigateur si nécessaire et connectez-vous à l'aide des informations d'identification de l'administrateur de Finance and Operations. Lors de la connexion à Finance and Operations, vous **DEVEZ** activer la case à cocher « Maintenir la connexion ». Cette opération crée un cookie persistant dont l'application Excel a besoin actuellement. Si vous vous connectez à Finance and Operations via un navigateur autre qu'IE, vous êtes invité à vous connecter dans l'application Excel. Lorsque vous cliquez sur « Connexion » dans l'application Excel, une fenêtre contextuelle d'IE s'ouvre et lors de la connexion, vous **DEVEZ** activer la case à cocher « Maintenir la connexion ». Si cliquer dans « Connexion » dans l'application Excel ne produit aucun effet, alors vous devez désactiver le cache des cookies d'IE.

## <a name="scenario-overview"></a>**Vue d'ensemble du scénario**
Julia travaille en tant que gestionnaire des finances dans les parcs de divertissements de Contoso en Allemagne (DEMF). À mesure que l'exercice fiscal 2016 s'approche, elle doit travailler sur le paramétrage du budget de la société pour l'année suivante. La préparation de budget se présente comme suit :

1.  Julia utilise les montants réels de l'année précédente comme point de départ pour créer le budget.
2.  Selon les chiffres réels de l'année précédente, elle crée des estimations pour 12 mois dans l'année suivante
3.  Julia examine le budget avec le directeur financier. Cela fait, elle fait les ajustements nécessaires au plan budgétaire et finalise la préparation du budget.

Le schéma de configuration de la planification budgétaire pour le scénario se présente comme suit :

![Schéma de configuration de planification budgétaire](./media/screenshot1-300x152.png)

Julia utilise le modèle Excel suivant pour préparer le budget :

[![Modèle Excel](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Exercice 1 : Configuration
=========================

## <a name="task-1-create-organizational-hierarchy"></a>**Tâche 1 : Créer une hiérarchie d'organisation**
Comme tout le processus de budgétisation se produit au département Finances, par conséquent Julia doit créer une hiérarchie organisationnelle très simple – se composant du département Finances uniquement. 1.1. Accédez aux hiérarchies d'organisation (Administration d'organisation &gt; Organisations &gt; Hiérarchies d'organisation) et cliquez sur le bouton Nouveau

![Hiérarchie de l'organisation](./media/screenshot3.png) 

1.2. Entrez le nom de la hiérarchie d'organisation et cliquez sur le bouton Affecter un objectif

[![Nom](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Sélectionnez l'objectif de la planification de budget, cliquez sur le bouton Ajouter et affectez la hiérarchie d'organisation nouvellement créée : 

[![Affecter un objectif](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Répétez l'étape ci-dessus pour l'objectif d'organisation de sécurité. Fermez l'écran une fois terminé.

[![Organisations de sécurité](./media/screenshot6.png)](./media/screenshot6.png)

1.5. Dans l'écran des hiérarchies d'organisation, cliquez sur le bouton Afficher. Cliquez sur Modifier dans le Concepteur de hiérarchies et créez une hiérarchie en cliquant sur le bouton Insérer.

[![Insérer](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Sélectionnez le département Finances pour la hiérarchie de budgétisation. 

[![Finances](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Une fois terminé, cliquez sur le bouton Publier et fermer Sélectionnez 1/1/2015 comme date d'effet de la validation de hiérarchie.

[![Date d'effet](./media/screenshot9.png)](./media/screenshot9.png)

## <a name="task-2-configure-user-security"></a>Tâche 2 : Configurez la sécurité des utilisateurs
La planification budgétaire utilise des stratégies de sécurité spéciales pour configurer l'accès aux données des plans budgétaires. Julia doit octroyer l'accès aux plans budgétaires des Finances pour elle-même. 

2.1. Passez au contexte d'entité juridique DEMF. 


2.2. Accédez à Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Configuration de la planification budgétaire. Dans l'onglet Paramètres, définissez la valeur Modèle de sécurité sur En fonction des organisations de sécurité. 

[![Paramètres](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Accédez à Administration système &gt; Utilisateurs &gt; Utilisateurs. Donnez à l'utilisateur Administrateur (Julia Funderburk) le rôle de Responsable du budget. 

[![Responsable du budget](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Choisissez un rôle d'utilisateur et cliquez sur Affecter des organisations 

[![Affecter des organisations](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Sélectionnez « Accorder l'accès à des organisations spécifiques ». Choisissez une Hiérarchie d'organisation créée dans la première étape. Choisissez le nœud Finances et cliquez sur le bouton Accorder à l'organisation enfant 

***Important !*** *Assurez-vous que vous êtes dans le contexte d'entité juridique DEMF en effectuant cette tâche, car la Sécurité d'organisation est appliquée par entité juridique* 

[![Accorder l'accès](./media/screenshot14.png)](./media/screenshot14.png)

## <a name="task-3-create-scenarios"></a>Tâche 3 : Créez des scénarios
3.1. Accédez à Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Configuration de la planification budgétaire. Dans la page Scénarios notez les scénarios que nous allons utiliser plus loin dans cet atelier pratique : Chiffres réels de l'année précédente et Budgété. 

*Remarque : vous pouvez créer des scénarios pour cet exercice si vous le voulez et les utiliser à la place.* 

[![Nouveaux scénarios](./media/screenshot15.png)](./media/screenshot15.png) 

*Remarque : comme Julia n'utilise pas le processus d'approbation officielle pour la préparation de budget, nous ignorerons les stades et les workflows paramétrés dans cet atelier pratique et utiliserons le paramétrage existant pour approuver automatiquement cette configuration de workflow.*

## <a name="task-4-create-budget-plan-columns"></a>Tâche 4 : Créez les colonnes du plan budgétaire
Les colonnes du plan budgétaire sont des colonnes monétaires ou basées sur la quantité utilisables dans la structure de document du plan budgétaire. Dans notre exemple nous devons créer une colonne pour les Chiffres réels de l'année précédente et 12 colonnes pour représenter chaque mois de l'année budgétisée. Les colonnes peuvent être créées en cliquant simplement sur le bouton Ajouter et en renseignant les valeurs, ou avec l'aide d'une Entité de données. Dans cet atelier pratique nous emploierons l'Entité de données pour renseigner les valeurs. 

4.1. Dans Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Configuration de la planification budgétaire, ouvrez la page Colonnes. Cliquez sur le bouton Agence dans le coin supérieur droit de l'écran et choisissez Colonnes (non filtrées) 

[![Colonnes non filtrées](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. Le système ouvre le classeur Excel à utiliser pour renseigner les valeurs. Si une invite s'affiche, cliquez sur Autoriser la modification et Faire confiance à cette application 

[![Activer la modification](./media/screenshot18.png)](./media/screenshot18.png) 

[![Faire confiance à cette application](./media/screenshot17.png)](./media/screenshot17.png)

4.3. Nous aurons besoin de plus de colonnes pour renseigner les valeurs. Cliquez sur Conception dans le volet de droite pour ajouter les colonnes dans la grille : 

[![Configuration](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Cliquez sur le petit bouton en forme de crayon situé en regard de Colonnes du plan pour afficher les colonnes disponibles à ajouter dans la grille 

[![Éditer](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Double cliquez sur chaque champ disponible pour les ajouter aux champs sélectionnés et cliquez sur Mettre à jour 

![Mise à jour](./media/screenshot21.png)](./media/screenshot21.png) 

4.6. Dans le tableau Excel, ajoutez toutes les colonnes qui doivent être créées. Utilisez la fonction Remplissage automatique d'Excel pour ajouter les lignes rapidement. Vérifiez que les lignes sont ajoutées comme partie du tableau (lors de l'utilisation du défilement vertical, vous devez pouvoir voir les en-têtes de colonnes dans le haut de la grille) 

[![Remplissage automatique](./media/screenshot22.png)](./media/screenshot22.png) 

4.7. Revenez à Finance and Operations et actualisez la page. Les valeurs publiées figurent dans Finance and Operations. 

[![Actualiser](./media/screenshot23.png)](./media/screenshot23.png)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Tâche 5 : Créez des structures et des modèles de document de plan budgétaire
La structure définit à quoi la grille de lignes de document du plan budgétaire ressemble lorsque l'utilisateur ouvre le document de plan budgétaire. Il est également possible de changer la structure de document du plan budgétaire pour afficher les mêmes données dans différents angles. À présent qu'elle a défini les colonnes à utiliser avec notre document de plan budgétaire, Julia doit créer une structure de document du plan budgétaire similaire au tableau Excel qu'elle utilise pour créer les données du budget (voir la section Vue d'ensemble du scénario dans cet atelier pratique) 

5.1. Dans Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Configuration de la planification budgétaire, ouvrez la page Structures. Créez une structure pour l'écriture budgétaire mensuelle :

-   Choisissez l'ensemble de dimensions de MA+BU pour inclure les comptes principaux et les unités commerciales dans la structure.
-   Répertoriez toutes les colonnes du plan budgétaire créées dans l'étape précédente dans la section Éléments. Rendez tous les chiffres, saufs ceux de l'année précédente, modifiables.
-   Cliquez sur le bouton Description pour sélectionner les dimensions financières qui doivent afficher des descriptions dans la grille.

[![Description](./media/screenshot24.png)](./media/screenshot24.png) 

En s'appuyant sur la définition de la structure du plan budgétaire, nous pouvons créer un modèle Excel à utiliser comme autre manière de modifier les données du budget. Comme le modèle Excel doit correspondre à la définition de la structure de plan budgétaire, vous ne pourrez pas modifier la structure du plan budgétaire après avoir généré le modèle Excel, donc cette tâche doit être effectuée après que tous les composants de la structure sont définis. 

5.2. Pour la structure créée dans l'étape 5.1, cliquez sur le bouton Modèle &gt; Générer. Confirmer le message d'avertissement. Pour afficher le modèle, cliquez sur Modèle &gt; Afficher. 

*Remarque : veillez à sélectionner « Enregistrer sous » et sélectionnez l'emplacement dans lequel le modèle doit être enregistré afin de le modifier. Si l'utilisateur sélectionne « Ouvrir » dans la boîte de dialogue sans enregistrer, les modifications effectuées dans le fichier ne sont pas conservées lorsque le fichier est fermé.* 
[![Vue du modèle](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt;Étape facultative&gt; Modifiez le modèle Excel pour le rendre plus convivial – ajoutez des formules de total, des champs d'en-tête, une mise en forme, etc. Sauvegardez les modifications et téléchargez le fichier dans la structure du plan budgétaire en cliquant sur Présentation &gt; Télécharger [![Télécharger](./media/screenshot26.png)](./media/screenshot26.png)

## <a name="task-6-create-a-budget-planning-process"></a>Tâche 6 : Créez un processus de planification budgétaire
Julia doit créer et activer un nouveau processus de planification budgétaire en combinant le paramétrage ci-dessus pour commencer à entrer des plans budgétaires. Le processus de planification budgétaire définit les organisations, le workflow, les structures et les modèles de budgétisation qui seront utilisés pour créer des plans budgétaires. 

6.1. Accédez à Budgétisation &gt; Paramétrage &gt; Planification de budget &gt; Processus de planification budgétaire et créez un enregistrement.

-   Processus de planification budgétaire – Budgétisation DEMF exercice 2016
-   Cycle budgétaire – Exercice 2016
-   Comptabilité – DEMF
-   Structure de compte par défaut – Fabrication P&L
-   Hiérarchie d'organisation – Choisissez la hiérarchie créée au début de l'atelier pratique
-   Workflow de planification budgétaire – affecter Automatique – Approuver le workflow pour le département Finances
-   Dans les règles et les modèles de la phase de planification budgétaire, pour chaque phase de planification budgétaire choisissez si l'ajout de lignes et la modification des lignes sont autorisées et la structure à utiliser par défaut

*Remarque : vous pouvez créer des structures supplémentaires de document et les affecter pour qu'elles soient disponibles au stade du workflow de planification budgétaire en cliquant sur le bouton Autres structures.* 

[![Autres mises en page](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Sélectionnez Actions &gt; Activer pour activer ce workflow de planification budgétaire 

[![Activer](./media/screenshot28.png)](./media/screenshot28.png)

<a name="exercise-2-process-simulation"></a>Exercice 2 : Simulation du processus
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Tâche 7 : Générez des données initiales pour le plan budgétaire à partir de la comptabilité
7.1. Accédez à Budgétisation &gt; Périodique &gt; Générer le plan budgétaire à partir de la comptabilité. Renseignez les paramètres du processus périodique et cliquez sur le bouton Générer. 

[![Générer](./media/screenshot29.png)](./media/screenshot29.png) 

7.2. Accédez à Budgétisation &gt; Plans budgétaires pour rechercher un plan budgétaire créé par le processus Générer. 

[![Plan budgétaire](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. Ouvrez les détails du document en cliquant sur le lien hypertexte du numéro de document. Le plan budgétaire est affiché comme défini dans la structure créée lors de cet atelier pratique 

[![Affichage de plan budgétaire](./media/screenshot31.png)](./media/screenshot31.png)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Tâche 8 : Créez un budget de l'année en cours basé sur les chiffres réels de l'année précédente
Les méthodes de répartition peuvent être utilisées dans le plan budgétaire pour copier facilement les informations des plans budgétaires d'un scénario à un autre / les répartir sur des périodes / répartir sur des dimensions. Nous emploierons des répartitions pour créer le budget de l'année en cours à partir des chiffres réels de l'année précédente. 

8.1. Choisissez toutes les lignes de la grille de document du plan budgétaire et cliquez sur le bouton répartir le budget 

[![Toutes les lignes](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Sélectionnez la méthode de répartition, la clé de période, la source et les scénarios de destination et cliquez sur Répartir 

[![Répartir](./media/screenshot33.png)](./media/screenshot33.png)

Les montants effectifs de l'année précédente seront copiés dans le budget de l'année en cours et répartis sur plusieurs périodes en utilisant la clé de période de courbe de vente. 

[![Courbe de vente](./media/screenshot34.png)](./media/screenshot34.png)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Tâche 9 : Ajustez le document de plan budgétaire à l'aide d'Excel et finalisez le document
9.1. Cliquez sur le bouton feuille de calcul pour ouvrir le contenu du document dans Excel

[![Excel](./media/screenshot35.png)](./media/screenshot35.png)

9.2. Lorsque le classeur Excel s'ouvre, ajustez les numéros dans le document de plan budgétaire et cliquez sur le bouton Publier.

[![Publier](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Retournez au document de plan budgétaire dans Finance and Operations. Cliquez sur Workflow &gt; Envoyer pour approuver automatiquement le document

[![Approbation automatique](./media/screenshot37.png)](./media/screenshot37.png) 

Une fois le workflow terminé, le stade du document de plan budgétaire devient Approuvé. [![Approuvé](./media/screenshot38.png)](./media/screenshot38.png)

<a name="appendix"></a>Annexe
========

### <a name="auto-approve-workflow-configuration"></a>Configuration du workflow d'approbation automatique.

A. Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Workflows de budgétisation Créez un workflow à l'aide du modèle Workflows de planification budgétaire :

[![Créer un workflow](./media/screenshot39.png)](./media/screenshot39.png)

Ce workflow contient uniquement une tâche – Plan budgétaire de transition échelonnée 

[![Plan budgétaire de transition échelonnée](./media/screenshot40.png)](./media/screenshot40.png) 

Enregistrez et activez le workflow. 

B. Accédez à Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Configuration de la planification budgétaire. Dans l'onglet Stades, créez 2 stades : Initial et Envoyé 

[![Initial et envoyé](./media/screenshot41.png)](./media/screenshot41.png)

C. Accédez à Budgétisation &gt; Paramétrage &gt; Planification budgétaire &gt; Configuration de la planification budgétaire. Dans l'onglet Stades de workflow, associez le workflow Approbation automatique créé à l'étape A aux stades Initial et Envoyé 

[![Budgétisation et planification budgétaire](./media/screenshot42.png)](./media/screenshot42.png)  




