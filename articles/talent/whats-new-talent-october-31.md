---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (31 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d6942f8e4dc86f18a081b347df0567b1358a87ab
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858788"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-31-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (31 octobre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.2031**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="create-links-from-talent-to-finance-and-operations"></a>Créer des liens entre Talent et Finance and Operations
Cette nouvelle fonctionnalité de navigation vous permet de créer des liens entre Talent et Finance and Operations, ce qui vous permet de gérer la navigation dans les pages de Finance and Operations. Lorsque des liens sont configurés, vous pouvez spécifier le nom et le groupe du lien, dans lequel le lien doit s'afficher dans Talent, et la page cible à ouvrir dans Finance and Operations.

#### <a name="coming-soon"></a>Prochainement
Le contexte du champ sera ajouté à l'avenir pour autoriser une navigation directe vers les enregistrements correspondants dans Finance and Operations. Par exemple, vous pouvez utiliser **Lier au champ** pour fournir le contexte permettant d'accéder directement à un employé ou à un poste spécifique dans Finance and Operations.

### <a name="configure-target-systems"></a>Configurer les systèmes cibles

Dans Talent, les administrateurs système peuvent définir des liens qui seront affichés via l'espace de travail Administration du système. Une partie de la configuration est les environnements de Finance and Operations auxquels vous souhaitez accéder comme « cible » du lien. Pour ce faire, vous attribuez au système cible un nom et fournissez l'URL de l'environnement Finance and Operations. Voici un exemple d'URL Finance and Operations que vous pourriez fournir : https://devax00124aos.cloud.test.dynamics.com/. Après avoir configuré vos systèmes cibles, vous pouvez définir vos liens.

### <a name="configure-links"></a>Configurer les liens

Chaque lien créé aura les informations suivantes définies.

- Lien - Nom du lien, utilisé pour l'identification uniquement.

- Activer ce lien - Définissez sur **Oui** si vous souhaitez afficher le lien pour les utilisateurs de Talent.

- Nom complet - Définissez le nom qui s'affichera comme lien dans Finance and Operations. Ces données ne sont actuellement pas traduites.

- Afficher le lien sur l'écran - Choisissez la page sur laquelle afficher le lien.

- Groupe - Les groupes ne sont pas requis, mais si vous souhaitez organiser vos liens à l'aide de groupes, sélectionnez un groupe existant ou créez-en un à l'aide du champ **Groupe**.

- Système cible - Sélectionnez le système cible créé à l'aide de l'option **Configurer le système cible**. Il s'agit de l'environnement Finance and Operations utilisé lors de la navigation avec le lien.

- Utiliser la société actuelle de l'utilisateur - Sélectionnez **Oui** si vous souhaitez utiliser le contexte de la société actuelle de l'utilisateur en accédant à Finance and Operations. Si **Non** est sélectionné, vous pouvez activer la société qui doit être utilisée.

- Option de menu cible - Entrez l'option de menu Finance and Operations que le lien doit utiliser lors de la navigation. Des options de menu auxquelles vous pouvez accéder directement sont disponibles. Pour trouver l'option de menu requise, ouvrez Finance and Operations et ouvrez la page cible de la navigation. Copiez l'option de menu de l'URL. Par exemple, si vous souhaitez que le lien vous dirige vers la liste des employés dans Finance and Operations, entrez la valeur qui s'affiche après le « &mi » dans l'URL. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. L'option de menu permettant d'accéder à la page de la liste des employés dans cet exemple est : HcmWorkerListPage_Employees.

- Lien vers la source de données - Sélectionnez la source des données à laquelle le lien fait référence. Les sources les plus courantes comme **Collaborateur** et **Poste** sont disponibles.

- Lien vers le champ - (Prochainement) Cette sélection de champ permettre d'accéder directement d'un enregistrement unique dans Talent vers un enregistrement unique dans Finance and Operations.

### <a name="access-to-links"></a>Accès aux liens

Les administrateurs système afficheront les liens nouvellement créés sur les pages définies, même si l'option **Activer ce lien** est définie sur **Non**. Cela peut être utilisé pour tester des liens avant de les afficher pour d'autres employés. Tous les autres rôles n'affichent que les liens configurés une fois l'option **Activer ce lien** définie sur **Oui**. Les employés ayant accès aux pages sur lesquelles les liens sont affichés auront accès aux liens.

Les utilisateurs peuvent également disposer de droits de sécurité dans Finance and Operations définis pour accéder aux pages de Finance and Operations. Si ce n'est pas le cas, une boîte de dialogue de sécurité s'affiche lorsque vous utilisez le lien.


## <a name="other-changesfixes"></a>Autres modifications/corrections

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>Les postes avec une date de début à venir ne peuvent pas être affectés à un nouvel employé

Des modifications ont été apportées pour autoriser des affectations d'employés à des postes futurs. Les postes ayant des dates de début dans le futur peuvent être sélectionnés et l'affectation de l'employé sera effectué lors de l'enregistrement ou de l'achèvement du workflow (si le workflow est activé).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>Le nouvel employé ne peut pas être affecté à un poste existant

Des modifications ont été apportées afin qu'une nouvelle affectation d'employé puisse désormais être affectée aux postes existants.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>Date d'ancienneté/Emplacement du bureau disparaît lorsque la date de début de l'emploi est passée et que l'enregistrement est enregistré

Des modifications ont été apportées pour corriger la visibilité de **Date d'ancienneté** et d'**Emplacement du bureau** lors de l'enregistrement de modifications pour les employés passés.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>Impossible d'entrer des données pour des emplois futurs sur la page du collaborateur

Les données d'emploi pour les emplois futurs ont été désactivées sur la page principale du collaborateur. Les données d'emploi peuvent être entrées sur les pages **Gestionnaire de dates**. Des modifications supplémentaires seront effectués dans de futures versions pour activer la saisie des données d'emploi directement au cours du processus de workflow.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>Ajouter ValidFrom et ValidTo à HcmPersonalContactPersonEntity

L'entité Data Management Framework (DMF) HcmPersonalContactPersonEntity a été mise à jour pour inclure des dates « valide « et « valide jusqu'au » pour activer certains scénarios d'intégration d'avantage. 

## <a name="known-issue"></a>Problème connu
- **Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. 
- **Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)
