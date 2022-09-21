---
title: Contrôle d’en-tête du collaborateur
description: Cet article fournit des informations sur le contrôle d’en-tête personnalisable dans l’espace collaborateur, dans le hub Contacts et sur la page Collaborateur dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445946"
---
# <a name="worker-header-control"></a>Contrôle d’en-tête du collaborateur

Microsoft Dynamics 365 Human Resources fournit des informations sur le contrôle d’en-tête personnalisable dans l’**espace collaborateur**, dans le hub **Contacts** et sur la page **Collaborateur** simplifiée. L’en-tête contient des informations clés sur le collaborateur, ainsi que des actions en un seul clic telles que l’envoi d’e-mails, les appels ou la messagerie. L’en-tête peut être modifié en supprimant des champs ou en ajoutant des champs, y compris des champs personnalisés, pour afficher des informations supplémentaires. Pour utiliser le nouveau contrôle d’en-tête, accédez à **Gestion des fonctionnalités**, et activez la fonctionnalité **Contrôle d’en-tête de collaborateur**.

## <a name="personalization"></a>Personnalisation

L’un des principaux avantages du contrôle d’en-tête de collaborateur est la possibilité de personnaliser les informations qui apparaissent sur l’en-tête.

Dans le coin supérieur droit de l’en-tête se trouve un groupe de trois champs qui affichent des données différentes, selon le statut de l’employé. Ce groupe de champs est appelé la partie Spotlight de l’en-tête. Vous pouvez personnaliser la partie Spotlight de l’en-tête en supprimant les champs actuels ou en ajoutant des champs. Les champs qui peuvent être ajoutés à la partie Spotlight dans le contrôle d’en-tête diffèrent pour **Espace collaborateur**, le hub **Contacts** et la page **Collaborateur**.

## <a name="employee-self-service"></a>Libre-service pour employés

L’en-tête de collaborateur sur la page **Espace collaborateur** contient les informations suivantes :

- Nom du collaborateur
- Matricule d’employé
- Titre du poste
- Départements
- Type de collaborateur
- Entité juridique de collaboration
- Années de service
- Fait des rapports au (responsable)
- Type de poste

L’en-tête contient également une action en un seul clic pour modifier les informations personnelles de l’individu. Sélectionnez **Modifier les détails personnels** pour ouvrir la page **Renseignements personnels** dans **Espace collaborateur**.

## <a name="people-hub"></a>Transbordement de personnes

L’en-tête de travail dans le hub **Contact** (la page **Espace de travail Contacts**) contient les informations suivantes :

- Nom du collaborateur
- Matricule d’employé
- Titre du poste
- Départements
- Type de collaborateur
- Entité juridique de collaboration
- Années de service
- Fait des rapports au (responsable)
- Type de poste

L’en-tête contient également des actions en un seul clic telles que l’envoi d’e-mails, les appels ou la messagerie. Si un utilisateur consulte ses propres informations sur la page **Espace de travail Contacts**, la section d’action en un seul clic comprend le bouton **Modifier les détails personnels**. L’utilisateur peut sélectionner ce bouton pour ouvrir la page **Renseignements personnels** dans **Espace collaborateur**.

## <a name="streamlined-worker-page"></a>Page Collaborateur simplifiée

L’en-tête de collaborateur sur la page **Collaborateur** simplifiée contient les informations suivantes :

- Nom du collaborateur
- Matricule d’employé
- Titre du poste
- Départements
- Type de collaborateur
- Entité juridique de collaboration

Selon le statut de l’employé, les données de l’en-tête peuvent changer. Par exemple, si le salarié a quitté l’entreprise, le champ d’en-tête contient un badge **Ayant quitté la société**, la date de fin d’emploi et le motif de la résiliation.

Le tableau ci-dessous présente les données qui apparaissent sur l’en-tête pour différents statuts d’employé.

| Statut de l'employé | Données affichées | Note |
|-----------------|--------------------|------|
| En attente | <ul><li>Name</li><li>Matricule d’employé</li><li>Titre du poste</li><li>Département</li><li>Type de collaborateur</li><li>Entité juridique</li><li>Badge en attente</li><li>Date de début</li><li>Génère un état pour</li><li>Type de poste</li></ul> | |
| Embauche récente | <ul><li>Name</li><li>Matricule d’employé</li><li>Titre du poste</li><li>Département</li><li>Type de collaborateur</li><li>Entité juridique</li><li>Badge Embauche récente</li><li>Années de service</li><li>Génère un état pour</li><li>Type de poste</li></ul> | Par défaut, le badge **Embauche récente** est affiché pour les employés qui ont été embauchés au cours des sept derniers jours. Pour modifier ce paramètre, sur la page **Paramètres des ressources humaines**, sur l’onglet **Général**, dans la section **Plage de dates des embauches récentes**, définissez un laps de temps. Par exemple, pour afficher le badge **Embauche récente** pour les employés qui ont été embauchés au cours des 14 derniers jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**. |
| Employé actif | <ul><li>Name</li><li>Matricule d’employé</li><li>Titre du poste</li><li>Département</li><li>Type de collaborateur</li><li>Entité juridique</li><li>Date de début</li><li>Génère un état pour</li><li>Type de poste</li></ul> | |
| Quitter | <ul><li>Name</li><li>Matricule d’employé</li><li>Titre du poste</li><li>Département</li><li>Type de collaborateur</li><li>Entité juridique</li><li>Badge de sortie</li><li>Années de service</li><li>Génère un état pour</li><li>Type de poste</li></ul> | Par défaut, le badge de **Sortie** est affiché pour les employés qui partiront dans les sept prochains jours. Pour modifier ce paramètre, sur la page **Paramètres des ressources humaines**, sur l’onglet **Général**, dans la section **Plage de dates des collaborateurs sortants**, définissez un laps de temps. Par exemple, pour afficher le badge **Sortie** pour les employés qui vont quitter l’entreprise au cours des 14 prochains jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**. |
| Ayant quitté la société | <ul><li>Badge Ayant quitté la société</li><li>Matricule d’employé</li><li>Date de fin de l’emploi</li><li>Code motif</li></ul> | Par défaut, le badge **Ayant quitté la société** est affiché pour les employés qui ont quitté l’entreprise au cours des sept derniers jours. Pour modifier ce paramètre, sur la page **Paramètres des ressources humaines**, sur l’onglet **Général**, dans la section **Plage de dates des collaborateurs ayant quitté la société**, définissez un laps de temps. Par exemple, pour afficher le badge **Ayant quitté la société** pour les employés qui ont quitté l’entreprise au cours des 14 derniers jours, définissez le champ **Période** sur **14** et le champ **Unité** sur **Jours**. |
