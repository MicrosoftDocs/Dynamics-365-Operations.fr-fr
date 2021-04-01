---
title: Paramètres de gestion des actifs
description: Dans la gestion des actifs, des paramètres concernant les actifs, les ordres de travail, et la planification des ordres de travail doivent être configurés.
author: josaw1
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99ef5169d2c6a31efd3e7a7c92beade994f6e5f5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252007"
---
# <a name="asset-management-parameters"></a>Paramètres de gestion des actifs

[!include [banner](../../includes/banner.md)]

Dans la gestion des actifs, des paramètres concernant les actifs, les ordres de travail, et la planification des ordres de travail doivent être configurés. Cette rubrique explique comment les paramétrer. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Paramètres de gestion des actifs** pour ouvrir la page.

> [!NOTE]
> Si vous souhaitez configurer un système incluant des données de démonstration pour tester les fonctionnalités de gestion des actifs, consultez [Déployer un environnement de démonstration](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) pour obtenir des instructions.

## <a name="the-assets-tab"></a>Onglet Actifs

L’onglet **Actifs** fournit les paramètres suivants :

- **Poste technique par défaut** est le poste technique standard, qui est automatiquement sélectionné sur les actifs lors de la création d’actifs.  
- Dans le champ **Calendrier standard**, sélectionnez un calendrier à utiliser pour le calcul des indicateurs de performance clés des actifs si aucune ressource n’est sélectionnée sur un actif.  
- Dans le champ **Afficher**, sélectionnez la vue standard qui s’affiche lorsque vous ouvrez la page **Vue Actif** (**Gestion des actifs** > **Commun** > **Actifs** > **Vue Actifs**).
- Le **Type de demande par défaut** est le type de demande de maintenance standard, qui est automatiquement sélectionné lorsque vous créez une demande.  
- Les prévisions sur les types de tâches sont stockées sur le projet sélectionné dans le champ **Projet de prévision**. Pour chaque type de tâche, une activité est automatiquement créée dans le projet de prévision. Les prévisions sur le type de tâche sont ensuite enregistrées dans le projet de prévision.  
- Dans le champ **Modèle**, sélectionnez le modèle de prévision utilisé pour les prévisions de type de tâche et d’ordre de travail.

## <a name="the-work-orders-tab"></a>Onglet Ordres de travail

L’onglet **Ordres de travail** fournit les paramètres suivants :

- **Type d’ordre de travail par défaut** définit les paramètres standard lors de la création d’un ordre de travail.  
- **Type d’ordre de travail préventif** définit le type d’ordre de travail utilisé lors de la création d’ordres de travail à partir de plans de maintenance. Si ce champ est laissé vide, le type d’ordre de travail dans le champ **Type d’ordre de travail par défaut** est utilisé.  
- Dans le champ **Masque d’ordre de travail associé**, définissez le nombre maximal d’ordres de travail qui peuvent être liés à un ordre de travail. Par exemple, ## vous permet d’avoir jusqu’à 99 ordres de travail associés. Si vous définissez un masque comme décrit dans cette rubrique, les ordres de travail associés sont comptabilisés [ID d’ordre de travail de l’ordre de travail auquel un ordre de travail est associé]-01, -02, -03, etc. Si vous ne définissez pas de masque dans ce champ, un ordre de travail associé obtient le prochain ID d’ordre de travail séquentiel.  
- Sélectionnez **Oui** pour **Copier les pannes** si vous souhaitez copier automatiquement les pannes enregistrées sur les ordres de travail dans les demandes de maintenance connexes. 
- Dans le champ **Niveau**, vous définissez le niveau de poste technique automatiquement inséré sur un ordre de travail si toutes les tâches d’ordre de travail associées se réfèrent au même poste technique. Si toutes les tâches d’ordre de travail ne sont pas associées au même poste technique sur le niveau défini, le champ **Poste technique** reste vide sur l’ordre de travail. Par exemple, si vous insérez le nombre « 1 » dans ce champ, c’est le niveau supérieur d’une structure de poste technique. Si vous insérez le nombre « 0 » dans ce champ, vous n’avez pas défini de niveau de poste technique spécifique, uniquement que toutes les tâches d’ordre de travail sur un ordre de travail doivent être associées au même poste technique pour que celui-ci soit ajouté à l’ordre de travail.  
- Les journaux utilisés lors de la validation de la consommation sur un ordre de travail peuvent être sélectionnés dans l’organisateur **Général** dans les champs **Heure**, **Article** et **Dépenses**.  
- Dans le champ **Source de la langue du produit**, sélectionnez la langue à utiliser pour les noms de produit dans les états de gestion des actifs. Vous pouvez sélectionner la langue paramétrée sur le compte de la société, ou la langue paramétrée pour l’utilisateur actuellement connecté.  
- Sélectionnez **Oui** pour **Mise à jour en temps réel** si vous souhaitez mettre à jour automatiquement les modifications apportées aux valeurs par défaut du type de tâche, aux plans de maintenance et aux visites de maintenance.
  - Si vous sélectionnez **Non**, les modifications apportées au type de tâche par défaut, aux plans de maintenance et aux visites de maintenance ne sont pas mises à jour automatiquement dans la gestion des actifs.
  - Sélectionnez **Non** si un grand nombre de données sont en cours de synchronisation, par exemple, plusieurs actifs ou postes techniques configurés sur les plans de maintenance ou les visites de maintenance ou un grand nombre de plans ou de visites de maintenance.  
  - Si vous apportez des modifications aux valeurs par défaut du type de tâche ou aux plans de maintenance ou aux visites de maintenance, et que vous avez sélectionné l’option **Non** pour la mise à jour en temps réel, un avertissement peut ne pas être affiché si les modifications affectent :
    - Les postes techniques paramétrés sur les plans ou les visites de maintenance  
    - Les objets paramétrés sur les plans ou les visites de maintenance  
    - Le paramétrage des plans de maintenance  
    - Le paramétrage des visites de maintenance  
- Dans l’organisateur **Catégorie**, les catégories par défaut en relation avec la consommation sur les ordres de travail peuvent être définies.  

## <a name="the-work-order-scheduling-tab"></a>Onglet Planification des ordres de travail

L’onglet **Planification des ordres de travail** fournit les paramètres suivants sur l’organisateur **Général** :

- **Planifier la plage de gestion** définit la période en jours, calculée à partir de la date de début prévue de l’ordre de travail, pendant laquelle les tâches de l’ordre de travail sont planifiées.  
- Le **Plan général** correspond aux ressources dans le module **Administration de l’organisation**. Si vous sélectionnez un plan général dans ce champ, vous pourrez consulter les réservations de capacité associées aux ordres de travail dans **Réservations de capacité** (**Administration de l’organisation** > **Ressources** > **Ressources** > sélectionnez la ressource > onglet **Ressource** > bouton **Réservations de capacité**). Si vous laissez le champ vide, vous pourrez consulter la charge de la capacité associée aux ordres de travail dans **Charge de la capacité** (**Administration de l’organisation** \> **Ressources** \> **Ressources** \> sélectionnez la ressource \> onglet **Ressource** \> bouton **Charge de la capacité**).  

>[!NOTE]
>La sélection relative à l’utilisation d’un plan général dans le module **Gestion des actifs**, et l’écran correspondant qui permet d’obtenir une vue d’ensemble des réservations de capacité ou de la charge maximale est la configuration standard. En fonction de votre paramétrage dans le champ **Plan général**, vous pourrez accéder aux informations de capacité dans **Réservations de capacité** ou **Charge de la capacité** dans le module **Administration de l’organisation**. Il n’est pas possible de créer un paramétrage dans lequel les réservations de capacité s’affichent dans les deux vues.  

Les champs décrits dans la liste suivante se rapportent tous aux scores calculés, qui permettent de calculer la priorité des ordres de travail lors de la planification des ordres de travail.

- **Priorité** : score calculé avec le score des champs **Élément critique** et **Date de début**. Le nombre dans ce champ est divisé par le nombre spécifié dans le champ **Priorité** sur un ordre de travail. Par exemple, si la valeur « 5,00 » est insérée dans ce champ, et qu’un ordre de travail a la priorité « 20 », le score de la priorité est de 0,25.  
- **Élément critique** : score calculé avec le score des champs **Priorité** et **Date de début**. Le nombre dans ce champ est multiplié par le nombre spécifié dans le champ **Élément critique** sur un ordre de travail. Par exemple, si la valeur « 10,00 » est insérée dans ce champ, et qu’un ordre de travail a l’élément critique « 5 », le score de l’élément critique est de 50.  
- **Date de début** : score calculé avec le score des champs **Priorité** et **Élément critique**. Ce champ indique le score quotidien comme valeur négative et est comparé au champ **Début prévu** sur un ordre de travail. Par exemple, si la valeur « 10,00 » est insérée dans ce champ, et que la date de début prévue d’un ordre de travail est de trois jours à partir de maintenant, le résultat du score est moins 30,00. Ajouter des résultats de 0,25 et de 50 à partir des exemples dans les champs **Priorité** et **Élément critique** décrits ci-dessus fournit un total de plus 20,25. Ce nombre est comparé aux autre scores des ordres de travail lors de la planification des ordres de travail, et les scores les plus élevés sont planifiés en premier.  
- **Collaborateur responsable** : score calculé avec les valeurs de score de **Groupe de collaborateur responsables**, **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Emplacement des actifs** et **Date de début**. Si la valeur « 50,00 » est insérée dans ce champ, et qu’un collaborateur responsable a été sélectionné sur un ordre de travail, le collaborateur obtient 50 points dans le calcul global du collaborateur durant la planification de l’ordre de travail.  
- **Groupe de collaborateurs responsables** : score calculé avec les valeurs de score de **Groupe de collaborateur responsables**, **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Emplacement des actifs** et **Date de début**. Si la valeur « 50,00 » est insérée dans ce champ, et qu’un collaborateur responsable a été sélectionné sur un ordre de travail, le collaborateur obtient 50 points dans le calcul global du collaborateur durant la planification de l’ordre de travail.  
- **Limiter au responsable** : limite le nombre de collaborateurs disponibles pour la planification d’un ordre de travail. Sélectionnez **Non** si vous souhaitez calculer un score pour tous les collaborateurs, qu’ils soient paramétrés en tant que collaborateurs responsables ou qu’ils fassent partie d’un groupe de collaborateurs responsables. Sélectionnez **Oui** si vous souhaitez calculer un score pour les collaborateurs paramétrés en tant que collaborateur responsable sur l’ordre de travail, et/ou inclus dans un groupe de collaborateurs responsables sélectionné sur l’ordre de travail.  
- **Collaborateur préféré** : score calculé avec les valeurs de score de **Collaborateur responsable**, **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Emplacement des actifs** et **Date de début**. Les quatre scores sont calculés et additionnés pour fournir un score utilisé pour sélectionner le collaborateur à affecter selon l’ordre de travail lors de la planification des ordres de travail. Si la valeur « 10,00 » est insérée dans ce champ, et qu’un collaborateur a été sélectionné comme collaborateur préféré sur un ordre de travail, ce collaborateur obtient 10 points dans le calcul global du collaborateur durant la planification de l’ordre de travail.  
- **Groupe de collaborateurs préférés** : score calculé avec les valeurs de score de **Collaborateur responsable**, **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Emplacement des actifs** et **Date de début**. Si la valeur « 10,00 » est insérée dans ce champ, et qu’un collaborateur a été affecté à un groupe de collaborateurs préférés sélectionné sur un ordre de travail, ce collaborateur obtient 10 points dans le calcul global du collaborateur durant la planification de l’ordre de travail.  
- **Limiter au préféré** : limite le nombre de collaborateurs disponibles pour la planification d’un ordre de travail. Sélectionnez **Non** si vous souhaitez calculer un score pour tous les collaborateurs, qu’ils soient paramétrés en tant que collaborateurs préférés ou qu’ils fassent partie d’un groupe de collaborateurs préférés. Sélectionnez **Oui** si vous souhaitez uniquement calculer un score pour les collaborateurs qui sont paramétrés en tant que collaborateurs préférés et/ou qui font partie d’un groupe de collaborateurs préférés.  
- **Lieu** : score calculé avec les valeurs de score de **Collaborateur responsable**, **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Emplacement des actifs** et **Date de début**. Si la valeur « 3 000,00 » est insérée dans ce champ, un collaborateur obtient 3 000 points dans le calcul s’il est situé dans la même usine ou le même établissement que l’actif sur lequel une tâche doit être planifiée.  
  - Si votre société utilise des postes techniques, les collaborateurs reçoivent le score total s’ils sont situés au poste technique lié à l’actif. Si le poste technique de l’actif a un actif parent, les collaborateurs à ce poste technique obtiennent le score de 1/2. Si cet emplacement a également un parent, les collaborateurs sous cet emplacement obtiennent un score de 1/3. Si cet emplacement a également un parent, les collaborateurs sous cet emplacement obtiennent un score de 1/4, etc.  
  - Si votre société utilise l’emplacement de l’actif, ce que nous ne recommandons pas, le lieu, la zone, et la région sont utilisés pour calculer les scores du lieu. Les collaborateurs reçoivent le score total s’ils sont situés au lieu, dans la zone et dans la région liés à l’actif. Si le lieu du collaborateur correspond uniquement au lieu et à la région, le score du collaborateur est de 2/3 du score total. Si le lieu du collaborateur correspond uniquement au lieu, le score du collaborateur est de 1/3 du score total.  
- **Limiter au lieu** : limite le nombre de collaborateurs disponibles pour la planification d’un ordre de travail. Sélectionnez **Non** si vous souhaitez calculer un score pour tous les collaborateurs dans tous les postes techniques. Sélectionnez **Oui** si vous souhaitez calculer uniquement un score pour les collaborateurs associés au poste technique de l’ordre de travail.

>[!NOTE]
>Les champs « Limiter à... » augmentent la vitesse de la planification des ordres de travail en limitant le nombre de scores calculés pour les collaborateurs.

**Date de début du collaborateur** : score calculé avec les valeurs de score de **Collaborateur responsable**, **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Emplacement des actifs** et **Date de début**. Ce champ indique le score quotidien comme valeur négative et est comparé au champ **Début prévu** sur un ordre de travail. Si la valeur « 10,00 » est insérée dans ce champ, et que la date de début prévue d’un ordre de travail est demain, le résultat du score est moins 10,00.

  - En supposant qu’aucun collaborateur responsable et groupe de collaborateurs responsables n’ont été sélectionnés sur un ordre de travail à planifier - vous additionnez et soustrayez les valeurs de score dans les exemples des champs **Collaborateur préféré**, **Groupe de collaborateurs préférés**, **Lieu de l’actif**, et **Date de début** ci-dessus, vous obtenez un total de 3 010,00. Cela signifie un score élevé pour le collaborateur déjà sélectionné en tant que collaborateur préféré ainsi que faisant partie du groupe de collaborateurs préférés sur l’ordre de travail, et le collaborateur est également situé au même établissement que l’actif pour lequel une tâche doit être planifiée. Cela signifie qu’il y a de fortes chances que le collaborateur en question soit sélectionné pour exécuter la tâche lors de la planification de l’ordre de travail.  
  - Si la valeur « 0,00 » est insérée dans l’un des huit champs ci-dessus, ce score n’est pas utilisé lors de la planification de l’ordre de travail.  

## <a name="the-document-types-tab"></a>Onglet Types de document

Sélectionnez les types de document qui doivent être disponibles pour imprimer des pièces jointes associées à un état d’ordre de travail. Cela s’effectue en sélectionnant un type de document dans la section **Disponible** et en sélectionnant ![flèche Suivant](media/15-setup-for-objects.png). Si vous souhaitez supprimer un type de document sélectionné, sélectionnez le type de document dans la section **Sélectionné** et sélectionnez ![flèche Précédent](media/16-setup-for-objects.png).

## <a name="the-number-sequences-tab"></a>Onglet Souches de numéros

Sélectionnez les souches de numéros requises dans cette section. Il existe deux souches de numéros pour les actifs : une pour les actifs créés manuellement, et une pour les actifs créés via les actifs en attente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]