---
title: Espace de travail Gestion du personnel
description: Cette rubrique décrit les éléments conceptuels de l’espace de travail Gestion du personnel.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8b7493aa2df65b42d0da8a451c40cccafbc1cda8
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689464"
---
# <a name="personnel-management-workspace"></a>Espace de travail Gestion du personnel


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L’espace de travail **Gestion du personnel** comprend une grande quantité de contenu. Il contient les mouvements de personnel, suit les changements d’employés, les postes ouverts, les changements d’adresse, les enregistrements qui expirent et les analyses, et fournit des liens vers des informations spécifiques. Cette rubrique fournit des informations détaillées sur chaque partie de l’espace de travail.

## <a name="activity-tab"></a>Onglet Activité

L’onglet **Activité** contient des sections qui regroupent les employés en fonction de leur étape dans le processus d’embauche :

- **Candidats à l’embauche**
- **Affectation à venir**
- **Embauches récentes**
- **Quitter**
- **Ayant quitté la société**

Lorsqu’un employé est à l’une de ces étapes, des actions spécifiques sont disponibles sous forme de bouton sur la carte ou dans le menu qui apparaît lorsque vous sélectionnez les points de suspension (**...**) dans le coin supérieur droit. Les sous-sections suivantes décrivent les sections de l’onglet **Activité** et répertorient les actions disponibles.

### <a name="candidates-to-hire"></a>Candidats à l’embauche

La section **Candidats à embaucher** de l’espace de travail est remplie à partir de plusieurs sources :

- Une entité Open Data Protocol (OData)
- Intégration de LinkedIn
- Données saisies manuellement dans le produit

Lorsque les candidats apparaissent dans la section **Candidats à embaucher**, vous pouvez effectuer les actions suivantes en sélectionnant les points de suspension sur la carte du candidat :

- **Ignorer le candidat**
- **Ne pas embaucher**
- **Embaucher**

> [!NOTE]
> Si la liste des candidats est remplie à partir de Microsoft Dataverse, les mêmes candidats s’afficheront dans toutes les entités juridiques car aucune entité juridique n’a été associée au candidat.

### <a name="starting-soon"></a>Affectation à venir

La section **Début bientôt** répertorie les employés qui ont une date de début dans le futur. La liste est triée par date de début. La date de début la plus proche des données d’aujourd’hui est indiquée en premier.

Si le responsable n’apparaît pas sur la carte, cela signifie qu’un poste n’a pas été attribué à l’employé.

> [!NOTE] 
> Nous vous recommandons d’attribuer un poste à un collaborateur avant d’appliquer une liste de contrôle. Parfois, les tâches d’intégration sont attribuées au responsable d’un employé nouvellement embauché. Cependant, si aucun poste n’est attribué, le responsable du nouvel employé ne peut être déterminé. Dans ce cas, les tâches d’intégration destinées au responsable seront plutôt attribuées au propriétaire de la liste de contrôle.

Lorsque les employés apparaissent dans la section **Début bientôt**, les actions suivantes sont disponibles pour eux :

- Affecter un poste
- Vérifier les références d’emploi
- Affecter une rémunération fixe
- Affecter une rémunération variable
- Afficher dans la hiérarchie
- Appliquer la liste de contrôle\*\*

\*\* Il s’agit de l’action par défaut. Elle apparaît comme un bouton sur la carte.

### <a name="recent-hires"></a>Embauches récentes

La section **Embauches récentes** répertorie les employés qui ont une date de début dans un passé récent. La liste est triée par date de début. La date de début la plus proche de la date du jour est indiquée en premier.

Par défaut, la liste affiche les employés qui ont été embauchés au cours des sept derniers jours. Pour modifier ce paramètre, sur la page **Paramètres Human Resources**, sur l’onglet **Général**, définissez un laps de temps pour **Embauches récentes**. Les données de la section **Embauches récentes** peuvent être affichées pour un nombre spécifique de jours, de mois ou d’années. Par exemple, pour afficher la liste des employés qui ont été embauchés au cours des 14 derniers jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**.

> [!NOTE]
> Les paramètres de la page **Paramètres Human Resources** sont propres à l’entreprise. Par conséquent, la période pendant laquelle vous consultez les embauches récentes peut varier selon l’entreprise. Par exemple, dans la société USMF, vous souhaiterez peut-être afficher toutes les nouvelles recrues des sept derniers jours. Toutefois, dans la société USSI, vous souhaiterez peut-être afficher toutes les nouvelles recrues des 14 derniers jours. Dans ce cas, ouvrez la page **Paramètres Human Resources** dans chaque entreprise et définir les paramètres selon vos besoins.

Si le responsable n’apparaît pas sur la carte, cela signifie qu’un poste n’a pas été attribué à l’employé.

Lorsque les employés apparaissent dans la section **Recrues récentes**, les actions suivantes sont disponibles pour eux :

- Affecter un poste
- Vérifier les références d’emploi
- Rémunération fixe
- Affecter une rémunération variable
- Afficher dans la hiérarchie
- Appliquer la liste de contrôle\*\*

\*\* Il s’agit de l’action par défaut. Elle apparaît comme un bouton sur la carte.

### <a name="exiting"></a>Quitter

La section **Départ** répertorie les employés qui ont une date de départ dans le futur. La liste est triée par date de départ. La date de départ la plus proche de la date du jour est indiquée en premier. 

Par défaut, la liste affiche les employés qui ont une date de cessation d’emploi dans les sept prochains jours. Pour modifier ce paramètre, sur la page **Paramètres Human Resources**, sur l’onglet **Général**, définissez un laps de temps pour **Afficher les employés qui partent**. Les données de la section **Départ** peuvent être affichées pour un nombre spécifique de jours, de mois ou d’années. Par exemple, pour afficher la liste des employés qui partiront au cours des 14 derniers jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**.

Lorsque les employés apparaissent dans la section **Départ**, les actions suivantes sont disponibles pour eux :

- Appliquer la liste de contrôle\*\*
- Vérifier les références d’emploi
- Afficher dans la hiérarchie

\*\* Il s’agit de l’action par défaut. Elle apparaît comme un bouton sur la carte.

### <a name="exited"></a>Ayant quitté la société

La section **Départ** répertorie les employés qui ont une date de départ dans un passé récent. La liste est triée par date de départ. La date de départ la plus proche de la date du jour est indiquée en premier.

Par défaut, la liste affiche les employés qui ont une date de cessation d’emploi au cours des sept derniers jours. Pour modifier ce paramètre, sur la page **Paramètres Human Resources**, sur l’onglet **Général**, définissez un laps de temps pour **Afficher les employés qui sont partis**. Les données de la section **Partis** peuvent être affichées pour un nombre spécifique de jours, de mois ou d’années. Par exemple, pour afficher la liste des employés qui ont quitté l’entreprise au cours des 14 derniers jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**.

Lorsque les employés apparaissent dans la section **Partis**, les actions suivantes sont disponibles pour eux :

- Appliquer la liste de contrôle\*\*
- Vérifier les références d’emploi
- Afficher dans la hiérarchie

\*\* Il s’agit de l’action par défaut. Elle apparaît comme un bouton sur la carte.

## <a name="employee-changes-tab"></a>Onglet Changements pour l’employé

L’onglet **Changements pour l’employé** fournit une liste de toutes les actions de personnel pour l’employé. Cette liste n’est pas disponible par défaut. Pour activer la fonctionnalité, sur la page **Paramètres partagés des ressources humaines**, sur l’onglet **Actions personnelles**, définissez l’option **Activer les actions des employés** sur **Oui**.

## <a name="position-changes-tab"></a>Onglet Changements de poste

L’onglet **Changements de poste** fournit une liste de toutes les actions de personnel pour le poste. Cette liste n’est pas disponible par défaut. Pour activer la fonctionnalité, sur la page **Paramètres partagés des ressources humaines**, sur l’onglet **Actions personnelles**, définissez l’option **Activer les actions de poste** sur **Oui**.

## <a name="open-positions-tab"></a>Onglet Postes vacants

L’onglet **Postes vacants** répertorie tous les postes vacants. Pour apparaître dans la liste, les postes doivent avoir une date d’activation d’aujourd’hui ou antérieure, et ils ne doivent pas avoir d’affectation d’employé en cours.

> [!NOTE]
> La liste prend en compte l’affectation de l’employé à ce jour. Tout poste qui a une affectation d’employé à une date future continuera d’apparaître dans la liste. Cependant, une fois la date d’entrée en vigueur de l’affectation de l’employé atteinte, le poste sera retiré de la liste.

## <a name="expiring-records-tab"></a>Onglet Enregistrements expirés

L’onglet **Enregistrements expirés** répertorie tous les éléments qui ont expiré ou expireront pour les employés de l’entreprise à laquelle l’utilisateur est connecté. Les éléments suivants apparaissent dans la liste :

- **Certificats**
- **Identification**
- **Essais**
- **Filtrages**
- **Tests**

Pour spécifier si la liste affiche les enregistrements ayant expiré ou qui vont expirer, sur la page **Paramètres Human Resources**, sur l’onglet **Général**, définissez un délai pour **Enregistrements en cours d’expiration** ou **Enregistrements expirés**. Les données de l’onglet **Enregistrements en cours d’expiration** peuvent être affichées pour un nombre spécifique de jours. Par exemple, pour afficher la liste des enregistrements qui expireront dans les 14 prochains jours, définissez le champ **Nombre de jours** sur **14**.

> [!NOTE] 
> Si vous définissez le délai pour **Enregistrements expirés** ou **Enregistrements en cours d’expiration** sur **0** sur la page **Paramètres Human Resources**, la liste n’affichera aucun de ces enregistrements.

## <a name="employees-tile"></a>Vignette Employés

La vignette **Employés** fournit un décompte de tous les employés qui travaillent dans l’entreprise à laquelle l’utilisateur est actuellement connecté. Lorsque vous sélectionnez la vignette **Employés**, une nouvelle page affiche les détails des employés.

## <a name="contractors-tile"></a>Vignette Prestataires

La vignette **Prestataires** fournit un décompte de tous les prestataires qui travaillent dans l’entreprise à laquelle l’utilisateur est actuellement connecté. Lorsque vous sélectionnez la vignette **Prestataires**, une nouvelle page affiche les détails des prestataires.

## <a name="open-positions-tile"></a>Vignette Postes vacants

La vignette **Postes vacants** fournit un décompte de tous les postes vacants. Lorsque vous sélectionnez la vignette **Postes vacants**, une nouvelle page affiche les détails des postes vacants. Pour être inclus dans le décompte, les postes doivent avoir une date d’activation d’aujourd’hui ou antérieure, et ils ne doivent pas avoir d’affectation d’employé en cours.

> [!NOTE]
> La vignette prend en compte l’affectation de l’employé à ce jour. Tout poste qui a une affectation d’employé à une date future continuera d’être inclus dans le décompte. Cependant, une fois la date d’entrée en vigueur de l’affectation de l’employé atteinte, le poste sera exclu du décompte.

## <a name="approvals-tile"></a>Vignette Approbations

La vignette **Approbations** fournit un décompte de tous les éléments de workflow en attente d’approbation par l’utilisateur actuel. Lorsque vous sélectionnez la vignette **Approbations**, une nouvelle page affiche les détails des éléments de workflow qui nécessitent votre approbation.

## <a name="address-changes-tile"></a>Vignette Changements d’adresse

La vignette **Changements d’adresse** fournit un décompte de tous les changements d’adresse qui se sont produits pendant le nombre de jours qui est spécifié sur la page **Paramètres Human Resources**. Lorsque vous sélectionnez la vignette **Changements d’adresse**, une nouvelle page affiche les détails de tout changement d’adresse. Dans le coin supérieur droit, vous pouvez sélectionner **Inclure les futurs changements d’adresse** pour afficher les changements d’adresse avec une date future.

Pour plus d’informations sur l’affichage et la gestion des changements d’adresse, consultez [Afficher et gérer les changements d’adresse](hr-personnel-view-address-changes.md).
