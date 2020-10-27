---
title: Vue d'ensemble du conseiller en optimisation
description: Cette rubrique décrit comment utiliser le conseiller en optimisation pour garantir une configuration optimale de Finance and Operations.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 25ca62466c00b038e0d7e1758fd4f13f776cb2f0
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982550"
---
# <a name="optimization-advisor-overview"></a>Vue d’ensemble du conseiller en optimisation

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment utiliser le conseiller en optimisation pour garantir une configuration optimale de Finance and Operations.

## <a name="overview"></a>Vue d’ensemble

La configuration et le paramétrage incorrects d'un module peuvent compromettre la disponibilité des fonctions de l'application, les performances du système et le bon fonctionnement des processus d'entreprise. La qualité des données d'entreprise (par exemple, l'exactitude, l'exhaustivité et l'intégrité des données) affecte également les performances du système, les capacités de prise de décision d'une organisation, la productivité, etc.

L'espace de travail **Conseiller en optimisation** est un outil qui permet aux utilisateurs avancés, aux analystes d'entreprise, aux consultants fonctionnels et au support informatique d'identifier les problèmes liés à la configuration du module et aux données d'entreprise. Le conseiller en optimisation suggère les pratiques recommandées pour la configuration du module et identifie les données d'entreprise obsolètes ou incorrectes.

Le conseiller en optimisation exécute périodiquement un ensemble de règles de recommandation. Un ensemble de règles est disponible, toutefois, les utilisateurs peuvent également créer des règles spécifiques à leurs personnalisations, aux solutions des éditeurs de logiciels indépendants (ISV) et aux données d'entreprise. Pour plus d'informations sur la création de règles, voir [Créer des règles pour le conseiller en optimisation](./create-rules-optimization-advisor.md).

Lorsqu'une violation d'une règle est détectée, une opportunité d'optimisation est générée et apparaît dans l'espace de travail **Conseiller en optimisation**. Un utilisateur peut prendre les mesures correctives appropriées directement dans l'espace de travail **Conseiller en optimisation**.

Les opportunités peuvent être spécifiques à une société ou être créées entre des sociétés, selon le type de paramétrage et les données validées. Les opportunités entre sociétés peuvent être affichées à partir de toutes les sociétés. Pour afficher les opportunités pour une société spécifique, vous devez d'abord sélectionner la société.

Les stratégies de sécurité standard s'appliquent aux opportunités d'optimisation. Par exemple, les opportunités d'optimisation associées à la configuration du module **Gestion des entrepôts** sont visibles uniquement par les utilisateurs qui ont accès au module Gestion des entrepôts et peuvent modifier son paramétrage.

Lorsque vous prenez des mesures sur certaines opportunités d'optimisation, le système calcule l'impact de l'opportunité en termes de réduction sur l'exécution des processus d'entreprise. Malheureusement, cette fonction n'est pas disponible pour toutes les opportunités d'optimisation.

Pour en savoir plus sur le conseiller en optimisation, consultez le vidéo [Conseiller en optimisation dans Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ).

## <a name="optimization-rules"></a>Règles d'optimisation

Pour afficher la liste complète des règles du conseiller en optimisation et afficher la fréquence d'évaluation des règles, accédez à **Administration du système** &gt; **Tâches périodiques** &gt; **Mettre à jour la règle de validation de diagnostic**. Seules les règles avec le statut **Actif** sont évaluées. La fréquence d'évaluation peut être définie sur **Quotidien**, **Hebdomadaire**, **Mensuel** ou **Non planifié**.

Pour déclencher l'évaluation des règles non planifiées, ou pour réévaluer les règles périodiques en dehors de leur calendrier prédéfini, accédez à **Administration du système** &gt; **Tâches périodiques** &gt; **Planifier la règle de validation de diagnostic**. Ensuite, dans la boîte de dialogue **Validation des règles de diagnostic**, sélectionnez une fréquence d'évaluation. Toutes les règles avec la fréquence spécifiée sont réévaluées.

L'ensemble actuel de règles d'optimisation peut être divisé en plusieurs catégories.

### <a name="module-configuration-and-setup"></a>Configuration et paramétrage d'un module

Le paramétrage du module Gestion des entrepôts est un processus compliqué. Pour faciliter le processus, certaines règles ont été introduites pour valider l'exactitude du paramétrage. Par exemple, une règle valide le paramétrage des instructions d'emplacement d'entrepôt pour les emplacements de variante de produit fixes pour les commandes client et les ordres de transfert.

En outre, certaines règles vérifient si les fonctions activées sont réellement utilisées. Par exemple, une règle détermine si vous utilisez le module **Planification**. Si la règle détermine que vous n'utilisez pas le module, une opportunité d'optimisation est générée pour vous suggérer de désactiver les processus de planification.

### <a name="system-configuration"></a>Configuration du système

Si une fonctionnalité spécifique contrôlée par une clé de configuration n'est pas utilisée, une opportunité d'optimisation est générée pour vous suggérer de désactiver la clé de configuration. Les exemples de clés de configuration sont **Poids variable**, **Planification budgétaire**, **Projet** et **Liste des fournisseurs approuvés**.

### <a name="business-data-consistency-and-cleanup"></a>Cohérence et nettoyage des données d'entreprise

Si les données principales ne sont pas correctes (par exemple, si des conversions d'unités de mesure n'ont pas été définies, ou si des conversions d'unités de mesure ont une division par 0 \[zéro\]), une opportunité d'optimisation est générée pour vous suggérer de corriger les données. 

Si vous avez trop d'écritures d'historique des traitements par lots, d'articles obsolètes, d'écritures disponibles clôturées pour les articles activés en entrepôt, etc., ou si ces écritures et articles sont trop anciens, des opportunités d'optimisation sont générées pour vous suggérer de nettoyer les données. En gardant vos données propres, vous pouvez améliorer les performances globales du système.

### <a name="best-practices"></a>Utilisation optimale

Si vous n'exécutez pas certains processus d'entreprise selon les pratiques recommandées (par exemple, si vous exécutez la pré-clôture du stock avant que le stock ne soit clôturé, ou si vous utilisez le traitement par lots planifié pour le transfert des lots du journal de comptabilité auxiliaire), les opportunités d'optimisation vous informent de la pratique recommandée que vous devez suivre.

## <a name="optimization-opportunities"></a>Opportunités d'optimisation

Pour afficher les opportunités d'optimisation générées lors de l'évaluation des règles d'optimisation, ouvrez l'espace de travail **Conseiller en optimisation**.

Dans cet espace de travail, vous pouvez afficher des informations supplémentaires sur une opportunité en sélectionnant **Informations supplémentaires**. Si vous souhaitez que le système prenne des mesures et corrige le paramétrage, nettoie les données, etc., de manière à ce que vous n'ayez pas à ouvrir les pages correspondantes, sélectionnez **Agir**.

Il n'existe aucun workflow pour les opportunités d'optimisation. Après avoir sélectionné **Agir** ou utilisé le chemin de navigation indiqué dans la boîte de dialogue **Informations supplémentaires**, l'opportunité d'optimisation disparaît de la liste. Si la mesure corrective ne résout pas complètement un problème, l'opportunité est régénérée lors de la prochaine évaluation de la règle.

Si une opportunité ne s'applique pas à votre rôle, vous pouvez sélectionner **Masquer de ma liste**. Même si la règle à l'origine de cette opportunité est déclenchée à nouveau par la suite, l'opportunité ne s'affichera pas dans votre liste.

Pour désactiver l'évaluation de règles spécifiques, sélectionnez l'opportunité générée par la règle, puis sélectionnez **Désactiver l'analyse**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer des règles pour le conseiller en optimisation](./create-rules-optimization-advisor.md)

[Conseiller en optimisation dans Dynamics 365 for Finance and Operations (vidéo)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)
