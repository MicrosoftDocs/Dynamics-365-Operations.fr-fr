---
title: "Workflows d&quot;utilisation pour gérer les informations d&quot;employé"
description: "Cette rubrique explique comment utiliser la capacité de workflow pour les Ressources humaines gèrent les informations d&quot;employé. Par exemple, vous pouvez associer un workflow à un poste et de configurer un workflow d&quot;approbation qui démarre lorsque les employés de modifier l&quot;enregistrement."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Workflows d'utilisation pour gérer les informations d'employé

Cette rubrique explique comment utiliser la capacité de workflow pour les Ressources humaines gèrent les informations d'employé. Par exemple, vous pouvez associer un workflow à un poste et de configurer un workflow d'approbation qui démarre lorsque les employés de modifier l'enregistrement.

La capacité de workflow pour le module Ressources humaines fournit de nombreux workflows pour gérer les activités de ressources humaines. En outre, les nombreuses options sont disponibles dans lequel vous pouvez modifier les workflows spécifiques et les associer à une hiérarchie de génération d'états. Les workflows sont disponibles pour aider à la gestion des modifications à plusieurs types d'informations standard de l'employé. Vous pouvez associer un workflow avec un poste. Ensuite, si les employés de modifier l'enregistrement Employé, il commence un workflow qui nécessite l'approbation avant que la nouvelle informations enregistrées. Les workflows sont prédéfinis pour les types d'informations suivants permettent efficacement à gérer les changements et de tenir à jour les données de vos employés précises :

-   Numéros d'identifications
-   Cours
-   Formation
-   Image
-   Articles empruntés
-   Expérience professionnelle
-   Expérience de projet
-   Qualifications
-   Postes de confiance
-   Actions de Ressources humaines
-   Enregistrement de cours

Lorsque des employés sont engagés, transférés, ou terminés, le workflow peut inclure un processus de révision. Ainsi, un document peut être modifié ou les conditions d'une action peuvent être définies dans le cadre de le workflow. Lorsque le processus de révision est terminé, le document ou l'action est complété, puis le workflow se déplace dans une étape d'approbation finale.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associez un workflow avec une hiérarchie des postes
Vous pouvez associer un workflow avec toute hiérarchie que vous configurez. Par exemple, si un poste est associé à une hiérarchie de génération d'états matricielle, vous pouvez configurer un workflow en route des dépenses pour un projet spécifique à le prospect de projet au lieu du responsable de l'employé associé à ce poste. Pour créer un workflow ou modifier un workflow existant, dans ** workflow de Ressources humaines ** la page, cliquez sur ** nouveau **. Sélectionnez un workflow dans la liste pour démarrer le concepteur de workflow. Vous pouvez utiliser le Concepteur pour créer un workflow ou de modifier les étapes d'un workflow existant. Lorsque vous modifiez un workflow existant, les modifications sont enregistrées comme nouvelle version. Par conséquent, vous pouvez toujours renvoyée à une version précédente si nécessaire.

## <a name="configure-a-human-resources-workflow"></a>Configuration d'un workflow de Ressources humaines
Pour configurer un workflow de base démarré lorsque la demande d'employés devient son identification personnelle, procédez comme suit.

1.  Sous ** des workflows du module Ressources humaines ** la page, cliquez sur ** nouveau **.
2.  Dans la liste des workflows disponibles, sélectionnez ** des numéros d'identification **.
3.  Cliquez sur ** exécution ** pour démarrer le concepteur de workflow, puis entrez votre nom d'utilisateur et mot de passe lorsque vous êtes invité.
4.  Faites glisser ** numéro d'identification d'approuver ** l'élément de la liste des éléments de workflow sur le canevas Concepteur.
5.  Début connectez d'approbation élément ** ** et ** fin **.
6.  Double-cliquez sur ** élément d'approbation **, puis cliquez avec le bouton droit, puis sélectionnez ** des propriétés **.
7.  Procédez comme suit pour ajouter des instructions d'élément de travail :
    1.  Sélectionnez ** affectation **, puis sélectionnez ** hiérarchie ** sous le type d'affectation.
    2.  Sous ** hiérarchie ** la sélection, sélectionnez ** hiérarchie configurable **.
    3.  Ajoutez une condition d'arrêt, puis fermez la page.

8.  Effectuez les instructions supplémentaires (aucun avertissement supplémentaire ne doit exister).
9.  Cliquez sur **Enregistrer et fermer**. Activez le nouveau workflow lorsque la boîte de dialogue s'ouvre, puis sélectionnez ** faites Actif **.
10. Allez ** des Ressources humaines ** &gt; ** aux postes ** &gt; ** des types de hiérarchies des postes **.
11. Sélectionnez ** matrice **.
12. Ajoutez ** numéro d'identification du travailleur ** le workflow à la liste.



