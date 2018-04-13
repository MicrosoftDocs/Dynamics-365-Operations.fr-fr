---
title: "Vue d'ensemble du contrôle budgétaire"
description: "Cet article présente le contrôle budgétaire et fournit des informations vous permettant de configurer le contrôle budgétaire dans Microsoft Dynamics 365 for Finance and Operations afin de pouvoir gérer les ressources financières."
author: twheeloc
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 60493
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e77760d6729b8faf3099590c60ea7673cfcb18ec
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="budget-control-overview"></a>Vue d'ensemble des contrôles budgétaires 

[!INCLUDE [banner](../includes/banner.md)]

Cet article présente le contrôle budgétaire et fournit des informations vous permettant de configurer le contrôle budgétaire dans Microsoft Dynamics 365 for Finance and Operations afin de pouvoir gérer les ressources financières.

<a name="overview"></a>Vue d'ensemble
--------

Le contrôle budgétaire dans Microsoft Dynamics 365 for Finance and Operations prend en charge la gestion des ressources financières d'une organisation via le plan de comptes, les workflows, les groupes d'utilisateurs, les documents source et les journaux, le calcul des fonds disponibles configurable, les cycles budgétaires et les seuils. Lorsque les contrôles sont en place, une organisation peut planifier, mesurer, gérer et prévoir ses ressources financières au cours de son exercice. 

Une fois les budgets approuvés dans Finance and Operations, vous pouvez utiliser les plans budgétaires pour générer des écritures de registre budgétaires pour enregistrer le budget des dépenses pour une organisation. Sinon, vous pouvez créer ou importer des écritures de registre budgétaires depuis un programme tiers au lieu d'utiliser la fonctionnalité de planification de budget. 

Les dépenses peuvent être enregistrées à l'aide des comptes principaux et des dimensions financières. Vous pouvez configurer le contrôle de la dépense globale pour répondre aux stratégies et aux exigences de l'organisation en regroupant des combinaisons de dimensions financières et de comptes principaux. 

Le graphique suivant illustre la place du contrôle budgétaire dans les étapes du cycle budgétaire traditionnel.

[![BudgetingCycle](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

Vous pouvez configurer le contrôle budgétaire en fonction de plusieurs facteurs :

-   **Dimensions financières** - Quelles dimensions financières doivent être utilisées pour déclarer l'activité budgétaire et l'activité réelle, et quelles dimensions financières sont requises pour contrôler le budget ? Certaines combinaisons de dimensions spécifiques ou certains comptes principaux nécessitent-ils une attention particulière ? Par exemple, faut-il suivre l'activité budgétaire par rapport à l'activité réelle par centre de coût et programme ? Les dépenses de déplacement requièrent-elles une attention particulière ?
-   **Temps** - Quel cadre temporel (période fiscale, période fiscale en cours, etc.) sera utilisé pour évaluer les fonds budgétaires disponibles ?
-   **Documents sources** – Quels documents source doivent être évalués à des fins de contrôle budgétaire ? Les documents doivent-ils être évalués par ligne ou par document ?
-   **Calcul des fonds disponibles** - Les documents tels que les demandes d'achat (engagements préalables) et les commandes fournisseur (engagements) doivent-ils être pris en compte dans le calcul des fonds disponibles ? Les documents présentant le statut de Brouillon doivent-ils être pris en compte dans le calcul ?
-   **Autorisation de dépassement** - Qui est autorisé à dépasser le budget disponible ?

Le contrôle budgétaire est entièrement intégré à Finance and Operations. Par conséquent, vous pouvez évaluer le budget disponible pour les achats prévisionnels et les achats réels. Les demandes et les états budgétaires sont disponibles. Par conséquent, les utilisateurs peuvent évaluer le budget durant le cycle budgétaire, et faire les ajutsements requis sous la forme de révisions ou de transferts budgétaires. Un responsable du budget peut également exporter l'activité budgétaire et l'activité réelle dans Microsoft Excel pour une analyse et des prévisions plus pointues au besoin.

## <a name="configuring-budget-control"></a>Configuration du contrôle budgétaire
### <a name="budget-cycle-time-span"></a>Période de cycle budgétaire

Une fois la budgétisation de base configurée, vous pouvez définir le moment ou les périodes de début et de fin de la budgétisation et du contrôle budgétaire sur la page **Période de cycle budgétaire**. Les cycles budgétaires correspondent souvent aux calendriers fiscaux, mais peuvent couvrir des exercices.

Les prochaines étapes du processus de configuration sont terminées sur les différents onglets de la page **Configuration du contrôle budgétaire**.

### <a name="define-parameters"></a>Définir les paramètres

Selon les dimensions financières activées pour le budget, vous pouvez utiliser la totalité ou un sous-ensemble de dimensions financières pour le contrôle budgétaire. 

En outre, vous pouvez spécifier l'intervalle par défaut (par exemple, **Exercice**, **Exercice à date**, **Période fiscale** ou **Trimestriel**) au cours duquel ce contrôle budgétaire est exécuté dans la période de cycle budgétaire associée. Vous pouvez également spécifier un responsable budgétaire par défaut et le seuil utilisé pour informer les utilisateurs une fois le seuil atteint. Les valeurs dans ces champs sont utilisées comme valeurs par défaut de n'importe quelle règle de contrôle budgétaire ou groupe budgétaire créé. Toutefois, les valeurs par défaut peuvent être modifiées pour des groupes ou règles distincts. 

La manière dont les budgets sont créés et enregistrés dans le registre budgétaire permet de déterminer la période sélectionnée lors de l'évaluation des fonds budgétaires disponibles. Si un montant calculé sur une année pour une combinaison de valeurs de dimensions est développé et utilisé, une approche de type Exercice ou Exercice en cours peut être logique. Toutefois, si une organisation crée des budgets par période fiscale, ou fait des répartitions selon les périodes fiscales, et souhaite un contrôle plus détaillé, elle peut envisager des périodes de type Période fiscale en cours ou Trimestriel. 

En outre, la culture d'une organisation, du fait de sa relation au budget et au contrôle budgétaire, permet de définir la configuration.

### <a name="over-budget-permissions"></a>Autorisations de dépassement de budget

Ensuite, sur l'onglet **Autorisations de dépassement de budget**, vous pouvez spécifier des groupes d'utilisateurs. Vous pouvez également indiquer si les utilisateurs qui sont membres d'un groupe sont autorisés à dépasser le budget. Vous pouvez empêcher les utilisateurs de dépasser le budget une fois le seuil budgétaire défini sur la page **Paramètres de budget**, ou bien vous pouvez les empêcher de dépasser le budget de n'importe quel montant, quel que soit le seuil. Selon la manière dont une organisation gère proactivement ses dépenses, ces autorisations peuvent l'aider à gérer ses ressources financières. 

### <a name="budget-funds-available"></a>Fonds budgétaires disponibles

Ensuite, sous l'onglet **Fonds budgétaires disponibles**, vous pouvez définir la formule utilisée pour calculer les fonds budgétaires disponibles. Selon la manière dont une organisation gère ses ressources financières par précaution, ou selon les règlementations ou les exigences du secteur, le calcul peut inclure le brouillon ou des documents non validés. 

> [!NOTE] 
> Si le calcul est modifié lors d'un cycle budgétaire, les modifications n'affecteront pas les documents qui ont pu passer précédemment des examens de contrôle budgétaire et qui ont été validés ou complétés.

### <a name="documents-and-journals"></a>Documents et journaux

Puis, sur la page **Documents et journaux**, vous pouvez sélectionner les documents source et les journaux qui seront soumis à des examens de contrôle budgétaire et si les examens surviendront au niveau d'entrée de ligne ou pour l'intégralité du document. 

Vous devez mettre en correspondance les documents source qui sont sélectionnés avec les cases à cocher pour les soldes inclus dans le calcul des fonds budgétaires disponibles. Par exemple, si vous avez sélectionné **Réservations budgétaires pour les engagements**, vous devez sélectionner l'option **Commandes fournisseur**. Lors de l'exécution d'une vérification budgétaire pour les montants et les comptes d'une ligne d'achat, la catégorie de contrôle budgétaire affectée à la réservation est **Engagement**. Lors de l'exécution d'une vérification budgétaire pour les montants et les comptes d'une ligne d'achat, la catégorie de contrôle budgétaire affectée à la réservation est **Engagement préalable**. 

Si les options **Réservations budgétaires pour les engagements** et/ou **Réservations budgétaires pour les engagements préalables** sont incluses dans le calcul des fonds budgétaires disponibles et doivent être reflétées dans la comptabilité via les validations, vous devez activer la comptabilité d'engagements sur la page **Paramètres de comptabilité**.  

### <a name="assign-budget-models"></a>Affecter des modèles de budget

Puis, sur la page **Affecter des modèles de budget**, il convient d'affecter des modèles de budget aux périodes de cycle budgétaire devant être incluses dans le contrôle budgétaire.

### <a name="define-budget-control-rules"></a>Définir les règles de contrôle budgétaire

Puis, sur l'onglet **Définir les règles de contrôle budgétaire**, vous devez créer des règles spécifiques basées sur les dimensions financières qui sont activées pour le contrôle budgétaire. Par exemple, si une priorité est donnée aux dépenses ou à l'étendue des dépenses d'un département, vous pouvez utiliser les paramètres de cet onglet pour définir et évaluer ces dépenses. Vous pouvez définir différents seuils pour chaque règle de contrôle budgétaire. 

> [!Important]
> Le contrôle budgétaire est activé pour tout compte principal de type **Résultat**, **Dépense**, **Produit, Bilan, Passif, Capitaux propres** ou **Actif**. Si cet onglet contient une règle qui a des critères vides, le contrôle budgétaire est activé pour **toutes** les combinaisons de dimensions financières qui incluent des comptes principaux de ces types. Par conséquent, assurez-vous de créer des règles budgétaires de contrôle définissant uniquement les plages de combinaisons de dimensions financières où il est essentiel que le contrôle budgétaire soit activé.  

### <a name="select-main-accounts"></a>Sélectionner les comptes principaux

Si le **Compte principal** n'est pas sélectionné comme dimension de contrôle budgétaire sur la page **Définir les paramètres**, mais que des dépenses spécifiques sont gérées, vous pouvez sélectionner ces dépenses pour l'onglet **Sélectionner les comptes principaux**. Si le **Compte principal** est sélectionné comme dimension de contrôle budgétaire, aucune valeur n'est requise.  

### <a name="define-budget-groups"></a>Définir des groupes budgétaires

Puis, sur l'onglet **Définir des groupes budgétaires**, vous pouvez définir de manière facultative des combinaisons uniques de dimensions financières où les ressources budgétaires sont mises en commun pour un deuxième contrôle budgétaire. Vous pouvez créer un enregistrement unique qui inclut l'intégralité de l'organisation, ou définir plusieurs groupes pour représenter chaque département ou centre de coût.  

### <a name="define-message-levels"></a>Définir les niveaux de message

Si les messages d'avertissement de contrôle budgétaire sont supprimés pour les groupes d'utilisateurs, vous pouvez spécifier ces groupes sur la page **Définir les niveaux de message**. Les membres des groupes d'utilisateurs continueront à recevoir les messages d'erreur lors du dépassement des fonds budgétaires disponibles, en fonction de leurs autorisations de dépassement de budget.

### <a name="activate-budget-control"></a>Activer le contrôle budgétaire

Une fois le contrôle budgétaire configuré, vous pouvez l'activer dans l'onglet **Activer le contrôle budgétaire**. La version provisoire deviendra alors effective.
> [!Important]
> Une fois le contrôle budgétaire activé et actif et une fois les transactions validées, il ne doit pas être désactivé en milieu d'année. Lorsque le contrôle budgétaire est désactivé, les activités ne sont pas enregistrées à des fins de contrôle budgétaire, et les vérifications budgétaires ne sont plus exécutées. Par conséquent, les documents qui ont déjà été validés ne peuvent refléter correctement aucun montant d'exonération ou solde figurant dans les recherches et les états concernant le contrôle budgétaire. Cela inclut les statistiques de contrôle budgétaire pour les documents et journaux en aval ou d'ajustement. 

De plus, notez que les transactions, notamment les entrées de registre budgétaires, validées avant l'activation du contrôle budgétaire ne sont pas prises en compte dans le contrôle budgétaire. Par conséquent, il est recommandé de désactiver le contrôle budgétaire uniquement au début du nouveau cycle budgétaire. Vérifiez que les entrées de registre budgétaires contenant les soldes budgétaires de départ pour le contrôle budgétaire obtiennent des soldes mis à jour uniquement après l'activation du contrôle budgétaire. Tout document en cours (par exemple, une commande fournisseur) sera examiné pour connaître les fonds budgétaires disponibles et obtiendra une réservation budgétaire pour le contrôle budgétaire, lorsque l'utilisateur déclenche manuellement une vérification du contrôle budgétaire dans le document.

## <a name="using-budget-control"></a>Utilisation du contrôle budgétaire
Une fois le contrôle budgétaire activé, les utilisateurs recevront des messages d'avertissement et d'erreur de contrôle budgétaire dans les documents et journaux configurés pour le contrôle budgétaire. N'oubliez pas, vous pouvez configurer le contrôle budgétaire afin que les utilisateurs soient prévenus lorsqu'ils dépassent les fonds budgétaires, mais puissent toujours confirmer ou valider la transaction. Les utilisateurs peuvent afficher les détails des contrôles budgétaires qui ont échoué sur la page **Erreurs ou avertissements du contrôle budgétaire**.   

Depuis cette page, les utilisateurs peuvent explorer la page **Statistiques du contrôle budgétaire par période** pour découvrir les détails concernant la disponibilité budgétaire et les réservations pour une combinaison de dimensions de contrôle budgétaire sélectionnée. Les utilisateurs peuvent également explorer la page **Statistiques de contrôle budgétaire** pour afficher la disponibilité budgétaire de toutes les combinaisons de dimensions financières utilisées dans le contrôle budgétaire. 

Si le contrôle budgétaire est activé pour les commandes fournisseur, le responsable du budget peut utiliser l'espace de travail **Budgets comptables et prévisions** pour passer en revue la file d'attente de toutes les commandes fournisseur non confirmées avec des avertissements ou des erreurs du contrôle budgétaire. Si le responsable du budget est autorisé à dépasser le budget, il peut confirmer les commandes fournisseur directement dans l'espace de travail.    

