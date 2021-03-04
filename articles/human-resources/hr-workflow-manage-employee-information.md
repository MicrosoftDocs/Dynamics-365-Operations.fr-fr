---
title: Utiliser des workflows pour gérer les informations relatives aux employés
description: Cet article explique comment les Ressources humaines peuvent utiliser la capacité de workflow pour gérer les informations des employés. Par exemple, vous pouvez associer un workflow avec un poste et configurer un workflow d’approbation qui démarre lorsque les employés modifient leur enregistrement.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 250b214372a12f99d2ababc97c5edf4456cadcad
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418549"
---
# <a name="use-workflows-to-manage-employee-information"></a>Utiliser des workflows pour gérer les informations relatives aux employés

Cet article explique comment les Ressources humaines peuvent utiliser la capacité de workflow pour gérer les informations des employés. Par exemple, vous pouvez associer un workflow avec un poste et configurer un workflow d’approbation qui démarre lorsque les employés modifient leur enregistrement.

La capacité de workflow pour les ressources humaines fournit de nombreux workflows pour gérer les activités des ressources humaines. En outre, de nombreuses options sont disponibles pour modifier des workflows spécifiques et les associer à une hiérarchie de génération d’états. Les workflows sont disponibles pour faciliter la gestion des modifications de plusieurs types standard d’informations des employés. Vous pouvez associer un workflow à un poste. Ensuite, si les employés modifient leur enregistrement d’employé, un workflow nécessitant une approbation démarre que les nouvelles informations soient enregistrées. Les workflows sont prédéfinis pour les types d’informations suivants, afin de vous aider à gérer efficacement les modifications et à tenir à jour les données des employés :

-   Numéros d’identifications
-   Cours
-   Formation
-   Image
-   Articles empruntés
-   Expérience professionnelle
-   Expérience de projet
-   Qualifications
-   Postes de confiance
-   Actions des ressources humaines
-   Inscriptions aux cours

Lorsque des employés sont engagés, transférés ou licenciés, le workflow peut inclure un processus de révision. Ainsi, un document peut être révisé, ou les conditions d’une action peuvent être définies dans le cadre du workflow. Lorsque le processus de révision est terminé, le document ou l’action est terminé, puis le workflow passe à l’étape d’approbation finale.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associer un workflow à une hiérarchie de postes
Vous pouvez associer un workflow avec n’importe quelle hiérarchie que vous configurez. Par exemple, si un poste est associé à une hiérarchie de génération d’états matricielle, vous pouvez configurer un workflow qui achemine les dépenses pour un projet spécifique vers le chef du projet au lieu du responsable de l’employé associé à ce poste. Pour créer un workflow ou modifier un workflow existant, dans la page **Workflow des ressources humaines**, cliquez sur **Nouveau**. Sélectionnez un workflow dans la liste pour démarrer le concepteur de workflow. Vous pouvez utiliser le concepteur pour créer un workflow ou modifier les étapes d’un workflow existant. Lorsque vous modifiez un workflow existant, vos modifications sont enregistrées sous une nouvelle version. Par conséquent, vous pouvez toujours revenir à une version précédente, si nécessaire.

## <a name="configure-a-human-resources-workflow"></a>Configurer un workflow des ressources humaines
Pour configurer un workflow de base qui démarre lorsque des employés demandent de modifier leur identification personnelle, procédez comme suit.

1.  Dans la page **Workflows des ressources humaines**, cliquez sur **Nouveau**.
2.  Dans la liste des workflows disponibles, sélectionnez **Numéros d’identification**.
3.  Cliquez sur **Exécuter** pour démarrer le concepteur de workflow, puis entrez votre nom d’utilisateur et votre mot de passe à l’invite.
4.  Faites glisser l’élément **Approuver le numéro d’identification** de la liste des éléments de workflow vers le canevas du concepteur.
5.  Reliez l’élément d’approbation à **Démarrer** et **Terminer**.
6.  Double-cliquez sur **Approuver l’élément**, puis cliquez avec le bouton droit et sélectionnez **Propriétés**.
7.  Procédez comme suit pour ajouter des instructions relatives à un élément de travail :
    1.  Sélectionnez **Affectation**, puis sélectionnez **Hiérarchie** sous le type d’affectation.
    2.  Sous la sélection **Hiérarchie**, sélectionnez **Hiérarchie configurable**.
    3.  Ajoutez une condition d’arrêt, puis fermez la page.

8.  Entrez les instructions supplémentaires (il ne doit exister aucun avertissement supplémentaire).
9.  Cliquez sur **Enregistrer et fermer**. Activez le nouveau workflow lorsque la boîte de dialogue s’ouvre, puis sélectionnez **Activer**.
10. Accédez à **Ressources humaines** &gt; **Postes** &gt; **Types de hiérarchie de postes**.
11. Sélectionnez **Matrice**.
12. Ajoutez le workflow **Numéro d’identification du collaborateur** à la liste.

## <a name="additional-resources"></a>Ressources supplémentaires

[Afficher et gérer les changements d’adresse](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]