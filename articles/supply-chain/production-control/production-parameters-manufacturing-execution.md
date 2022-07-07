---
title: Paramètres de production dans Contrôle et suivi de la production
description: Cet article fournit des informations sur la configuration des paramètres de production dans Contrôle et suivi de la production.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8d9c756d8aaf2e7b2f6593e78fbb645dafee4552
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016157"
---
# <a name="production-parameters-in-manufacturing-execution"></a>Paramètres de production dans Contrôle et suivi de la production

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur la configuration des paramètres de production dans Contrôle et suivi de la production.

Le module **Contrôle et suivi de la production** est principalement destiné aux sociétés de fabrication. Il permet d’enregistrer la consommation de temps et d’articles sur des tâches de production ou des projets. Avant de commencer à utiliser le module Contrôle et suivi de la production pour des enregistrements de tâches, vous devez définir différents paramètres de production qui déterminent quand et comment les enregistrements sont validés pendant le processus de production. Les paramètres de production affectent la gestion des stocks, la gestion de la production et le calcul des coûts.

Avant que les collaborateurs commencent à faire des enregistrements sur les tâches de production, Vous devez tenir compte soigneusement de tous les paramètres sur la page **Paramètres de production**. Cliquez sur **Contrôle de la production** &gt; **Paramétrage** &gt; **Contrôle et suivi de la production** &gt; **Valeurs par défaut de l’ordre de fabrication**. Si votre société utilise la fonctionnalité multisite, vous pouvez définir différents paramètres de production pour chaque site. Les paramètres d’intégration au module **Production** sont configurés dans les onglets suivants de la page **Paramètres de production** :

- **Général** – Paramètres généraux pour les tâches de production dans Contrôle et suivi de la production.
- **Début** – Paramètres utilisés lorsque les opérations de production ont commencé.
- **Opérations** – Paramètres appliqués aux opérations de production et aux commentaires sur les opérations durant le processus de production.
- **Déclaration de fin** – Paramètres utilisés lorsque les articles sont déclarés comme terminés lors de la dernière opération d’un ordre de fabrication.
- **Contrôle de la quantité** – Paramètres utilisés pour contrôler les quantités de départ et en rétroaction sur les ordres de fabrication.

## <a name="types-of-production-jobs"></a>Types de tâches de production
Sous l’onglet **Opérations**, sélectionnez les types de tâches de production qui nécessitent un enregistrement sur la page **Enregistrement de tâche**.

Généralement, les travailleurs effectuent des enregistrements sur des tâches de paramétrage et de traitement. Toutefois, en cas d’application de la planification de tâche, vous pouvez sélectionner d’autres types de tâches, sur lesquelles les collaborateurs doivent effectuer des enregistrements lors du traitement des ordres de fabrication. Par exemple, vous pouvez demander des enregistrements sur les tâches de transport.

> [!IMPORTANT]
> Assurez-vous de sélectionner tous les types de tâches appropriés. Sinon, les tâches ne sont pas disponibles pour l’enregistrement sur la page **Enregistrement de tâche**. Vos sélections doivent correspondre aux sélections effectuées dans la colonne **Gestion des tâches** de l’onglet **Paramétrage** de la page **Groupes de gammes** (**Contrôle de la production** &gt; **Paramétrage** &gt; **Gammes** &gt; **Groupes de gammes**).

Si l’option **Gestion des tâches** est sélectionnée pour le groupe de gammes, ce type de tâche est déclaré comme terminé dans l’ordre de fabrication lorsque la tâche est déclarée comme terminée dans le module Contrôle et suivi de la production. Si tous les types de tâches pour lesquels l’option **Gestion des tâches** est sélectionnée sont déclarés terminés sur une opération, le module Contrôle et suivi de la production signale l’opération comme terminée.

> [!NOTE]
> Certains types de tâches peuvent être signalés manuellement via les journaux de production. Dans ce cas, sélectionnez **Gestion des tâches** pour le type de tâche, mais ne sélectionnez pas le type de tâche pour l’enregistrement sous l’onglet **Opérations** de la page **Paramètres de production** du module Contrôle et suivi de la production.

## <a name="bom-consumption-and-picking-list-journals"></a>Consommation de nomenclature et journaux des prélèvements
Un paramétrage cohérent de la consommation de nomenclature est important, car cela permet de garantir une gestion efficace des stocks. Par exemple, si les paramètres de consommation de nomenclature ne sont par correctement définis dans le module Contrôle et suivi de la production, des matières peuvent être déduites du stock deux fois ou pas du tout.

Dans la page **Paramètres de production**, la consommation automatique de nomenclature est paramétrée en trois étapes :

- Au début d’une production. Paramétrez cette étape sous l’onglet **Début**.
- Durant le processus de production quand une opération est terminée. Paramétrez cette étape sous l’onglet **Opérations**.
- Quand un ordre de fabrication est déclaré comme terminé. Paramétrez cette étape sous l’onglet **Déclaration de fin**.

Pour chaque étape, le champ **Consommation automatique de nomenclature** permet de sélectionner une des trois méthodes de prélèvement d’articles pour un ordre de fabrication :

- **Principe d’effacement** – Cette option est utilisée en combinaison avec une option définie pour la nomenclature dans le module **Production**. Cliquez sur **Contrôle de la production** &gt; **Ordres de fabrication** &gt; **Tous les ordres de fabrication**. Dans la page **Tous les ordres de fabrication**, sélectionnez un ordre de fabrication dans la liste, puis, dans le volet Actions, cliquez sur **Nomenclature**. Dans la page **Nomenclature**, sous l’onglet **Paramétrage**, dans le champ **Principe d’effacement**, sélectionnez l’une des options suivantes :

  - **Début**
  - **Terminer**
  - **Manuel**
  - Vide (Aucune option n’est sélectionnée.)
  - **Disponible à l’emplacement**

    Dans le module Contrôle et suivi de la production, si l’option **Principe d’effacement** est sélectionnée dans le champ **Consommation automatique de nomenclature** de l’onglet **Début**, toutes les matières définies sur **Début** dans la nomenclature sont déduites du stock lorsque l’opération est démarrée. L’option **Disponible à l’emplacement** est utilisée pour les produits activés pour les processus d’entrepôt avancés. Si vous sélectionnez ce principe d’effacement, les matières sont vidées lorsque le travail d’entrepôt pour le prélèvement de matières premières est terminé. Les matières sont également vidées lorsqu’une ligne de nomenclature qui utilise ce principe d’effacement est libérée dans l’entrepôt et les matières sont disponibles à l’emplacement de l’entrée en production.

    > [!NOTE]
    > Si le champ **Principe d’effacement** est défini sur l’onglet **Démarrer** dans Contrôle et suivi de la production, vous devez sélectionner le même principe dans l’onglet **Opérations** ou l’onglet **Déclarer comme terminé**. Cette exigence permet de garantir que les matériaux sont déduits de l’inventaire des nomenclatures qui utilisent **Terminer** comme principe d’effacement pour l’ordre de fabrication. Si le même principe d’effacement n’est pas sélectionné dans l’onglet **Opérations** ou l’onglet **Déclaration de fin**, les matières peuvent être déduites du stock deux fois.

- **Toujours** – Si vous activez cette option pour un étape, les matières sont toujours déduites du stock à ce stade. Par exemples, les matières destinées à la production sont déduites lors du lancement de l’ordre de fabrication. Ce paramètre requiert que **Jamais** soit sélectionné dans les onglets **Opérations** et **Déclaration de fin**. Cela permet d’empêcher que des articles soient déduits du stock deux fois.
- **Jamais** – Si vous sélectionnez cette option pour un stade, aucune consommation de nomenclature n’a lieu à ce stade. Par exemple, si vous sélectionnez **Jamais** dans les trois onglets (**Début**, **Opérations** et **Déclaration de fin**), les matières doivent être déduites manuellement du stock.

> [!IMPORTANT]
> Considérez soigneusement la configuration des paramètres de production et assurez-vous que les paramètres sélectionnés dans les différents onglets de la page **Paramètres de production** ne sont pas contradictoires.

Les exemples suivants présentent des paramétrages qui prennent en charge divers principes de consommation de nomenclature : Les paramètres sont configurés dans la page **Paramètres de production** du module Contrôle et suivi de la production.

### <a name="example-1-backflushing-on-operations"></a>Exemple 1 : Postconsommation des opérations

Utilisez les paramètres suivants si les journaux des prélèvements et la consommation des articles de nomenclature doivent être générés lorsque des articles sont déclarés comme terminés sur une opération.

| Onglet                | Champ                          | Paramètre                             |
|--------------------|--------------------------------|-------------------------------------|
| Commencement              | Mettre à jour commencement en ligne           | **Statut** ou **Statut + quantité** |
| Commencement              | Consommation de nomenclature automatique      | **Jamais**                           |
| Operations         | Consommation de nomenclature automatique      | **Toujours**                          |
| Déclaration de fin | Consommation de nomenclature automatique      | **Jamais**                           |
| Déclaration de fin | Mettre à jour déclaration de fin en ligne | **Statut + quantité**               |

### <a name="example-2-backflushing-on-production"></a>Exemple 2 : Postconsommation dans la production

Utilisez les paramètres suivants si les journaux des prélèvements et la consommation des articles de nomenclature doivent être générés lorsque des articles sont déclarés comme terminés sur l’ordre de fabrication.

| Onglet                | Champ                          | Paramètre                             |
|--------------------|--------------------------------|-------------------------------------|
| Commencement              | Mettre à jour commencement en ligne           | **Statut** ou **Statut + quantité** |
| Commencement              | Consommation de nomenclature automatique      | **Jamais**                           |
| Operations         | Consommation de nomenclature automatique      | **Jamais**                           |
| Déclaration de fin | Consommation de nomenclature automatique      | **Toujours**                          |
| Déclaration de fin | Mettre à jour déclaration de fin en ligne | **Statut + quantité**               |

### <a name="example-3-flushing-principle"></a>Exemple 3 : Principe d’effacement

Utilisez les paramètres suivants si les journaux des prélèvements et la consommation des articles de nomenclature doivent être générés conformément au principe d’effacement paramétré pour les articles de nomenclature.

| Onglet                | Champ                          | Paramètre                |
|--------------------|--------------------------------|------------------------|
| Commencement              | Mettre à jour commencement en ligne           | **Statut + quantité**  |
| Commencement              | Consommation de nomenclature automatique      | **Principe d’effacement** |
| Operations         | Consommation de nomenclature automatique      | **Principe d’effacement** |
| Déclaration de fin | Consommation de nomenclature automatique      | **Jamais**              |
| Déclaration de fin | Mettre à jour déclaration de fin en ligne | **Statut + quantité**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>Exemple 4 : Déduction de matières lors du démarrage d’un ordre de fabrication

Utilisez les paramètres suivants si les journaux des prélèvements et la consommation des articles de nomenclature doivent être générés au début d’une production.

| Onglet                | Champ                          | Paramètre                             |
|--------------------|--------------------------------|-------------------------------------|
| Commencement              | Mettre à jour commencement en ligne           | **Statut + quantité**               |
| Commencement              | Consommation de nomenclature automatique      | **Toujours**                          |
| Operations         | Consommation de nomenclature automatique      | **Jamais**                           |
| Déclaration de fin | Consommation de nomenclature automatique      | **Jamais**                           |
| Déclaration de fin | Mettre à jour déclaration de fin en ligne | **Statut** ou **Statut + quantité** |

Sur la base des sélections décrites plus haut dans cette section, les journaux des prélèvements sont validés à diverses étapes du processus d’ordre de fabrication :

- lorsqu’une opération est commencée ;
- lorsqu’une rétroaction de quantité est signalée dans l’opération ;
- lorsque les articles sont signalés comme terminés dans l’ordre de fabrication.

### <a name="example-5-manual-bom-consumption"></a>Exemple 5 : Consommation de nomenclature manuelle

Vous pouvez utiliser les paramètres suivants si des matières doivent être déduites manuellement du stock. Dans ce cas, les journaux des prélèvements ne sont pas validés.


|        Onglet         |             Champ              |         Paramètre         |
|--------------------|--------------------------------|-------------------------|
|       Commencement        |      Mettre à jour commencement en ligne      | <strong>Statut</strong> |
|       Commencement        |   Consommation de nomenclature automatique    | <strong>Jamais</strong>  |
|     Operations     |   Consommation de nomenclature automatique    | <strong>Jamais</strong>  |
| Déclaration de fin |   Consommation de nomenclature automatique    | <strong>Jamais</strong>  |
| Déclaration de fin | Mettre à jour déclaration de fin en ligne | <strong>Statut</strong> |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]