---
title: "Mettre à niveau Dynamics AX 2012 vers Dynamics 365 for Finance and Operations, Enterprise Edition"
description: "Cette rubrique décrit le processus que les clients exécutant actuellement Microsoft Dynamics AX 2012 peuvent utiliser pour déplacer leurs données et leur code vers Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: fr-fr
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Mettre à niveau Microsoft Dynamics AX 2012 vers Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition

[!include[banner](../includes/banner.md)]

Dans la mise à jour 8 de la plateforme, Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, fournit un chemin de mise à niveau que les clients exécutant actuellement Microsoft Dynamics AX 2012 peuvent utiliser pour déplacer leurs données et leur code vers Finance and Operations. Le processus de mise à niveau repose sur les éléments suivants :

- Des outils qui vous aident à transférer le code d'application personnalisé existant à partir d'AX 2012.
- Un processus de mise à niveau des données que vous pouvez utiliser pour transférer votre base de données. Ainsi, vous pouvez mettre à niveau votre historique transactionnel complet.

## <a name="overview"></a>Vue d'ensemble

Le processus de mise à niveau global peut être visualisé en trois grandes phases : analyser, exécuter et valider.

Le diagramme suivant présente le processus de mise à niveau de bout en bout, et les activités incluses dans chaque phase. 

![Processus de mise à niveau](./media/upgrade-process.png)

## <a name="analyze"></a>Analyser

Les activités de la phase d'analyse vous aident à estimer les efforts nécessaires pour la mise à niveau. Elles aident également à préparer un plan de projet. Ces activités peuvent être effectuées avant d'acheter Finance and Operations. Elles vous aident à prendre une décision d'achat avisée en fournissant un point de données sur les efforts et les ressources nécessaires.

### <a name="sign-up-for-a-public-preview-in-lcs"></a>S'inscrire à une version préliminaire publique dans LCS

Pour effectuer les activités d'analyse avant d'acheter Finance and Operations, vous pouvez vous inscrire à une version préliminaire publique. La version préliminaire publique vous permet de déployer vos propres environnements Finance and Operations. Elle vous donne également accès aux outils de Microsoft Dynamics Lifecycle Services (LCS) permettant d'évaluer votre environnement AX 2012 et votre code personnalisé existant.

Si vous disposez d'un projet LCS existant pour AX 2012, vous devez quand même vous inscrire à un projet supplémentaire pour évaluer Finance and Operations.

Pour plus d'informations sur l'obtention d'une version préliminaire publique pour les clients, accédez à https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Pour plus d'informations sur l'obtention d'une version préliminaire publique pour les partenaires, accédez à https://mbs.microsoft.com/partnersource/global/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Notez que cette version préliminaire publique est différent d'une [version d'évaluation de 30 jours](https://aka.ms/D365OperationTrials). Les versions d'évaluation de trente jours fournissent une instance déployée de Finance and Operations que vous pouvez utiliser pour explorer et évaluer l'application. Toutefois, les activités d'analyse nécessitent une expérience et des outils LCS complets.

### <a name="select-the-upgrade-methodology"></a>Sélectionner la méthodologie de mise à niveau
Dans votre nouveau projet LCS, définissez la méthodologie du projet sur **Mettre à niveau AX 2012 vers Dynamics 365 for Operations**. Cette méthodologie est conçue spécialement pour les clients AX 2012 qui effectuent une mise à niveau. Elle décrit les trois phases en détail et fournit des liens vers l'ensemble des documents associés au processus.

![Méthodologie de mise à niveau(./media/methodology.png)
 
### <a name="run-the-upgrade-analyzer"></a>Exécuter l'analyseur de mise à niveau
L'analyseur de mise à niveau s'exécute sur votre environnement AX 2012 et identifie les tâches que vous devez effectuer pour préparer l'environnement AX 2012, afin que l'expérience de mise à niveau se déroule en douceur et à moindre coût :

- **Nettoyage des données** – Ce processus permet d'identifier les données que vous pouvez supprimer sans risque de perte de fonctionnalité. L'outil identifie différents types de données que vous pouvez réduire en exécutant un processus de nettoyage. Pour chaque type de données, une explication est fournie sur l'impact du nettoyage. Vous décidez ensuite si le processus de nettoyage doit être exécuté. Une partie du coût de votre abonnement Finance and Operations est basée sur la taille de la base de données. Par conséquent, en réduisant la taille, vous diminuez le coût d'abonnement du composant et réduisez également le temps nécessaire au processus de lancement de la mise à niveau. Une base de données de plus petite taille garantit une mise à niveau plus rapide.
- **Configuration SQL** – Ce processus examine la configuration SQL et recommande des optimisations. En assurant le fonctionnement optimal de SQL, ce processus réduit le temps nécessaire au processus de lancement de la mise à niveau.
- **Fonctionnalités obsolètes** – Ce processus identifie les fonctionnalités que vous utilisez actuellement, mais qui ne sont pas disponibles dans Finance and Operations. Ainsi, le processus vous aide à détecter à l'avance les lacunes dans les fonctionnalités. Il fournit également des solutions de remplacement.

En outre, dans le cadre de cette étape, vous devez installer KBXXXXXXX dans l'environnement AX 2012. Ce correctif fournit une liste de contrôle préalable à la mise à niveau. Dans l'environnement AX 2012, vous pouvez utiliser cette liste de contrôle pour entrer les données qui seront nécessaires pour la procédure de mise à niveau. Par exemple, dans une tâche de la liste de contrôle préalable à la mise à niveau, vous fournissez les informations de connexion Microsoft Azure Active Directory (Azure AD) pour chaque utilisateur AX 2012 actuel, afin que chaque utilisateur puisse se connecter à Finance and Operations.

Le résultat de cette étape devient le flux de travail dans le plan du projet de mise à niveau pour les administrateurs du système AX 2012.

Pour plus d'informations, voir [Analyse : utiliser l'analyseur de mise à niveau pour planifier le travail de migration](upgrade-analyzer-tool.md).

### <a name="run-the-code-upgrade-estimation-tools"></a>Exécuter les outils d'estimation de la mise à niveau du code
Cette étape extrait votre code d'AX 2012, le convertit dans le nouveau format et fournit des commentaires sur les conflits qu'un développeur doit résoudre ultérieurement. Cette étape sert de base à l'estimation du coût de la mise à niveau de votre code.

Pour effectuer cette étape, vous devez exporter votre code à partir d'AX 2012 en tant qu'exportation de magasin de modèles et le télécharger dans l'outil de mise à niveau du code LCS. L'outil de mise à niveau du code génère une version mise à niveau de votre code et un état sur les conflits restants qui doivent être résolus. Votre développeur peut ensuite examiner le code mis à niveau et l'état pour déterminer les efforts nécessaires pour mettre à niveau votre base de code.

Le résultat de cette étape représente le flux de travail dans le plan du projet de mise à niveau pour les développeurs Microsoft Dynamics AX.

Pour plus d'informations, voir [Analyse : estimer les efforts nécessaires à la mise à niveau du code](analyze-code-upgrade.md)

### <a name="deploy-a-demo-environment"></a>Déployer un environnement de démonstration
Les environnements de démonstration sont des environnements par défaut qui contiennent des données de démonstration (pas vos propres données) et un code standard (aucune personnalisation). Il est recommandé de déployer un environnement de démonstration pour évaluer les nouvelles fonctions, et d'exécuter une analyse concordance-écart des processus standard qui sont utilisés dans AX 2012 mais qui ont peut-être été modifiés dans Finance and Operations. Vous pouvez déployer ces environnements de démonstration dans Azure ou les télécharger en tant qu'ordinateur virtuel que vous exécutez sur votre propre matériel. Si vous les déployez dans Azure, vous devez fournir votre abonnement Azure, car vous utilisez toujours un projet préliminaire public et n'avez pas encore acheté un abonnement Finance and Operations.

Le résultat de cette étape représente le flux de travail dans le plan du projet de mise à niveau pour les utilisateurs fonctionnels ou professionnels.

Pour plus d'informations, voir [Analyse : déployer un environnement de bac à sable (sandbox)](analysis-sandbox.md)

### <a name="create-a-project-plan"></a>Créer un plan de projet
Un modèle de plan de projet est fourni dans la méthodologie de mise à niveau. Dans cette étape, le résultat des étapes précédentes de la phase d'analyse est utilisé pour remplir le plan de projet pour le projet de mise à niveau. Le plan de projet contient également les détails des tests : le test de mise à niveau des données, le test de basculement, les itérations de la passe de tests fonctionnels et les détails des différentes affectations de ressources pour ces tâches.

À ce stade, le plan de projet fournit un point de données pour vous aider à comprendre la durée et le coût d'une mise à niveau vers Finance and Operations.

## <a name="execute"></a>Exécuter
Pendant la phase d'exécution, vous exécutez les tâches que vous avez planifiées pendant la phase d'analyse. Pour passer à la phase d'exécution, vous devez acheter Finance and Operations, et des ressources doivent être disponibles pour la mise à niveau.

### <a name="switch-to-the-lcs-implementation-project"></a>Basculer vers le projet d'implémentation LCS
Le projet préliminaire public que vous avez utilisé pour la phase d'analyse a rempli son objectif. Vous pouvez maintenant l'ignorer. Pour les étapes restantes, vous avez uniquement besoin du plan de projet que vous avez créé dans l'étape finale de la phase d'analyse.

Lorsque vous achetez un abonnement Finance and Operations, vous recevez des détails sur la procédure d'inscription à un nouveau projet LCS. Ce projet est appelé Projet d'implémentation et sera le nouveau projet LCS permanent pour votre abonnement, aussi longtemps que vous disposerez de cet abonnement. Ce projet est différent du projet préliminaire public, car il est géré par Microsoft. Ainsi, ce projet présente les caractéristiques suivantes :

- Tous les environnements du projet sont hébergés dans Azure.
- L'abonnement Azure associé au projet est géré par Microsoft. Par conséquent, il n'y a de facture séparée pour les coûts Azure. Les coûts seront couverts par votre abonnement Finance and Operations.
- L'environnement de production du projet est tenu à jour par Microsoft. Par conséquent, les déploiements du code, les mises à niveau et la maintenance de l'infrastructure sont exécutés directement par Microsoft, et non par votre personnel. 

### <a name="perform-the-ax-2012-preparation-tasks"></a>Exécuter les tâches de préparation AX 2012
Exécutez les tâches détectées par l'analyseur de mise à niveau, qui sont documentées dans le plan du projet de mise à niveau. Votre administrateur système et votre administrateur de base de données Microsoft Dynamics AX doivent effectuer ces tâches.

[Mise à niveau des données d'AX 2012 vers Dynamics 365 for Operations – Liste de contrôle préalable à la mise à niveau dans AX 2012](prepare-data-upgrade.md)

### <a name="perform-code-upgrade"></a>Exécuter la mise à niveau du code
Exécutez les tâches qui ont été planifiées pendant l'étape d'estimation de la mise à niveau du code de la phase d'analyse. Les développeurs doivent exécuter ces tâches.

Les modifications du code dans AX 2012 doivent être ensuite bloquées. Seules les modifications d'urgence du code doivent être autorisées dans AX 2012. Si une modification est effectuée, elle doit être importée manuellement dans la nouvelle base de code.

### <a name="develop-new-code"></a>Développer un nouveau code
Exécutez les tâches de l'analyse concordance-écart qui a été effectuée pendant l'étape « Déployer un environnement de démonstration » de la phase d'analyse. Ces tâches seront probablement une combinaison de tâches fonctionnelles qui définissent les tâches de configuration et de développement pour les personnalisations associées aux nouvelles fonctionnalités proposées.

### <a name="data-upgrade-development-environment"></a>Mise à niveau des données (environnement de développement)
Une fois que les tâches de mise à niveau du code sont exécutées, vous pouvez mettre à niveau votre base de données AX 2012 vers Finance and Operations pour la première fois. La première mise à niveau a lieu dans un environnement de développement, afin que vous puissiez corriger et déboguer plus facilement les problèmes détectés à ce stade. Dans un environnement de développement, un problème peut être débogué immédiatement, le code peut être ajusté et la mise à niveau peut être réexécutée en quelques minutes. Les environnements de bac à sable (sandbox) plus grands n'offrent pas cette flexibilité, et il faut plusieurs heures pour déboguer et résoudre les problèmes, mettre à jour le code, déployer le code mis à jour et réexécuter la mise à niveau.

L'illustration suivante présente le processus. Sauvegardez la base de données AX 2012, téléchargez-la dans Azure, restaurez-la dans l'environnement Finance and Operations et exécutez la mise à niveau des données.

![Mise à niveau des données dans un environnement de développement](./media/data-upgrade-dev.png)
 
La mise à niveau des données est effectuée via un type spécial de package déployable. Le même mécanisme permet de déployer le nouveau code Finance and Operations d'un environnement à un autre.

L'infrastructure sous-jacente utilisée pour convertir les données dans la base de données pendant ce processus est largement identique à l'infrastructure de mise à niveau dans AX 2012 qui est basée sur les traitements par lots X++ qui exécutent les classes **ReleaseUpdatexxx**.

Pour plus d'informations, voir [Mise à niveau des données d'AX 2012 vers Dynamics 365 for Operations dans un environnement de développement](data-upgrade-2012.md).

### <a name="data-upgrade-sandbox-environments"></a>Mise à niveau des données (environnements de bac à sable (sandbox))
Lorsque la mise à niveau des données dans un environnement de développement est terminée, le même processus peut être exécuté dans un environnement de bac à sable (sandbox). L'environnement de bac à sable (sandbox) est l'environnement dans lequel les utilisateurs professionnels et les membres de l'équipe fonctionnelle peuvent tester les processus d'entreprise à l'aide des données et du code AX 2012 mis à niveau.

L'illustration suivante présente le processus d'exécution de la mise à niveau des données dans un environnement de bac à sable (sandbox). La différence ici est que l'outil bacpac est utilisé à la place d'une sauvegarde SQL traditionnelle. Cet outil est nécessaire pour convertir la base de données Microsoft SQL Server et Azure SQL. Il s'agit d'un outil SQL standard qui n'est pas spécifique à Finance and Operations.

![Mise à niveau des données dans un environnement de bac à sable (sandbox)](./media/data-upgrade-sandbox.png)

Pour plus d'informations, voir [Mise à niveau des données d'AX 2012 vers Dynamics 365 for Operations dans un environnement de bac à sable (sandbox)](upgrade-data-sandbox.md).
 
## <a name="validate"></a>Contrôler la saisie
Lorsque vous activez la phase de validation, les environnements disponibles affichent votre code personnalisé mis à niveau et vos données mises à niveau. Cette phase consiste à valider et tester que l'environnement mis à niveau fonctionne comme souhaité. Elle décrit également le processus de préparation à la mise en service.

### <a name="perform-cutover-testing-and-create-a-cutover-plan"></a>Exécuter le test de basculement et créer un plan de basculement
Le terme _basculement_ est utilisé ici pour décrire le processus final de mise en service du nouveau système. Ce processus comprend les tâches qui ont lieu après la désactivation d'AX 2012 et avant l'activation de Finance and Operations. 

L'objectif est de tester le processus de basculement. Vous pouvez ainsi garantir que le basculement réel vers la mise en service se passera en douceur pour toutes les personnes impliquées.

Il existe deux flux de travail principaux :

- **Flux de travail technique** – Ce flux de travail est le processus d'exécution de la mise à niveau des données. Votre entreprise appliquera une limite au temps d'arrêt autorisé. Pendant ce temps d'arrêt, ni AX 2012 ni Finance and Operations ne seront disponibles. Le flux de travail technique devra peut-être ajuster sa procédure de mise à niveau des données pour respecter la limite de temps d'arrêt de l'entreprise. 
- **Flux de travail fonctionnel** – Après la mise à niveau des données, plusieurs tâches de configuration seront nécessaires dans l'environnement Finance and Operations. Toutes ces tâches doivent être documentées et quantifiées, et une ressource doit leur être affectée, car elles doivent s'intégrer avec les tâches techniques dans la limite de temps d'arrêt de l'entreprise.

Pour plus d'informations, voir 
- [Validation : Test de basculement](upgrade-cutover-testing.md)
- [Validation : Processus de validation d'application](app-validation-process.md)

### <a name="functional-test-pass"></a>Passe de tests fonctionnels
Exécutez une passe complète de tests fonctionnels de tous les processus d'entreprise. Cette passe de tests sera un nouveau test complet de l'ensemble des processus d'entreprise impliquant Finance and Operations. Ces processus d'entreprise incluent les anciens processus qui ont été importés à partir d'AX 2012 et les nouveaux processus qui impliquent de nouvelles fonctionnalités qui ont été utilisées pour la première fois dans Finance and Operations. 

Selon la qualité du code, les actions correctives et les nouveaux tests peuvent nécessiter plusieurs itérations de la passe de tests fonctionnels. Lorsqu'un problème est résolu, assurez-vous de tester à nouveau tous les processus concernés, afin de garantir que le processus en amont ou en aval n'est pas affecté par la modification.

Pour plus d'informations, voir [Validation : Test fonctionnel](upgrade-functional-validation.md).

### <a name="pre-go-live-checklist"></a>Liste de contrôle préalable à la mise en service
La liste de contrôle préalable à la mise en service est une procédure recommandée qui permet de réduire le risque d'erreurs pendant le basculement final vers la mise en service. Une semaine avant la mise en service, arrêtez les modifications de configuration dans AX 2012 (c'est-à-dire, sous \<module\>\Paramétrage). Cette restriction des modifications de configuration est une simple procédure. Les administrateurs système Microsoft Dynamics AX conviennent de mettre en attente les modifications de ce type à ce stade.

Il est également recommandé de geler les modifications du code dans la base de code de Finance and Operations. Aucune autre modification ne doit être autorisée tant qu'elle n'a pas été évaluée et qu'elle ne bloque pas la mise en service.  

Une fois la restriction de configuration et le gel du code mis en place, la mise à niveau des données doit être exécutée pour la dernière fois avant le basculement. Vous pouvez ainsi vérifier que tout fonctionne toujours comme prévu. 

Pour plus d'informations, voir [Validation : Préparation à la mise en service](upgrade-go-live-prep.md).



### <a name="supported-upgrade-paths"></a>Chemins de mise à niveau pris en charge
À partir de juin 2017, la mise à niveau vers Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, version 0617, est prise en charge à partir de Microsoft Dynamics AX 2012 R3. Toutes les mises à jour cumulatives d'AX 2012 R3 sont prises en charge.

Microsoft Dynamics AX 2012 R2 et Microsoft Dynamics AX 2012 RTM ne sont pas actuellement pris en charge. La prise en charge sera ajoutée ultérieurement en 2017.

Seule la mise à niveau vers la version déployée dans le cloud de Finance and Operations est prise en charge. La mise à niveau vers la version locale n'est pas prise en charge. La prise en charge de la mise à niveau vers la version locale sera ajoutée ultérieurement en 2017.

