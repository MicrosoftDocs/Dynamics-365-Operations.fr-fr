---
title: Utiliser des flux de travail pour gérer les informations relatives aux employés
description: Cet article explique comment utiliser les workflows pour gérer les informations des employés.
author: twheeloc
ms.date: 11/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750732"
---
# <a name="use-workflows-to-manage-employee-information"></a>Utiliser des flux de travail pour gérer les informations relatives aux employés

[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article explique comment les Ressources humaines peuvent utiliser la capacité de workflow pour gérer les informations des employés. Par exemple, vous pouvez associer un workflow avec un poste et configurer un workflow d’approbation qui démarre lorsque les employés modifient leur enregistrement.

La capacité de workflow pour les ressources humaines fournit de nombreux workflows pour gérer les activités des ressources humaines. En outre, de nombreuses options sont disponibles pour modifier des workflows spécifiques et les associer à une hiérarchie de génération d’états. Les workflows sont disponibles pour faciliter la gestion des modifications de plusieurs types d’informations des employés. Vous pouvez associer un workflow à un poste. Ensuite, si les employés modifient leur enregistrement d’employé, un workflow nécessitant une approbation démarre que les nouvelles informations soient enregistrées. Les workflows sont prédéfinis pour les types d’informations suivants, afin de vous aider à gérer efficacement les modifications et à tenir à jour les données des employés :

-   Numéros d’identifications
-   Formations
-   Éducation
-   Image
-   Articles empruntés
-   Expérience professionnelle
-   Expérience de projet
-   Qualifications
-   Postes de confiance
-   Actions des ressources humaines
-   Inscriptions aux cours

Lorsque des employés sont engagés, transférés ou licenciés, le workflow peut inclure un processus de révision. Ainsi, un document peut être révisé ou les conditions d’une action peuvent être définies dans le cadre du workflow. Lorsque le processus de révision est terminé, le document ou l’action est terminé, puis le workflow passe à l’étape d’approbation finale.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associer un workflow à une hiérarchie de postes

Vous pouvez associer un workflow avec n’importe quelle hiérarchie de postes que vous configurez. Deux types de hiérarchie sont utilisés pour l’acheminement du workflow : **Managériale** et **Configurable**.

- Une hierarchie **Managériale** représente la structure hiérarchique de la société ou de l’organisation. Pour plus d’informations sur ce type de hiérarchie, consultez [Poste de supérieur hiérarchique](hr-personnel-positions.md#reports-to-position).
- Ue hierarchie **Configurable** représente une hiérarchie matricielle ou personnalisée. Pour plus d’informations sur ce type de hiérarchie, consultez [Relations](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Exemple de hiérarchie managériale

Vous pouvez configurer un workflow de manière à ce que lorsqu’un employé soumet une demande d’achat pour un nouvel ordinateur, la demande soit envoyée au responsable de l’employé et au responsable de niveau supérieur. Lorsque vous configurez l’étape du workflow, définissez le champ **Type d’affectation** sur **Hiérarchie**. L’onglet **Type de hiérarchie** devient alors disponible. Pour cet exemple, sélectionnez la hiérarchie **Managériale**.

### <a name="configurable-hierarchy-example"></a>Exemple de hiérarchie configurable

Si un poste est associé à une hiérarchie de rapports matriciels, vous pouvez configurer un workflow qui achemine les dépenses pour un projet spécifique vers le chef du projet au lieu du responsable de l’employé. Dans ce cas, définissez le champ **Type d’affectation** sur **Hiérarchie**. Ensuite, dans l’onglet **Type de hiérarchie**, sélectionnez la hiérarchie **Configurable**. Une fois le workflow configuré, sélectionnez la hierarchie **Associé** sur la page **Configuration du workflow** pour sélectionner la hiérarchie à utiliser pour l’acheminement du workflow.

> [!IMPORTANT]
> Lorsqu’un document, une transaction ou un enregistrement principal est soumis à l’approbation du workflow, le poste principal de l’expéditeur sera utilisé pour déterminer à qui le document doit ensuite être envoyé.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Paramètre de hiérarchie dans les paramètres du workflow

1. Sur la page **Paramètres du workflow**, accédez à **Acheminement de la hiérarchie**.
2. Par défaut, l’option **Utiliser la hiérarchie des postes** est définie sur **Non**. Dans ce cas, le workflow utilisera le poste principal du travailleur lorsqu’il navigue dans la hiérarchie. Définissez l’option sur **Oui** pour que le workflow utilise le parent du poste lorsqu’il navigue dans la hiérarchie.

### <a name="additional-example"></a>Exemple supplémentaire 

L’employée Grace Sturman occupe deux postes : consultante et formatrice. Le poste principal de Grace est formatrice. Lorsqu’elle ne forme pas de nouveaux employés, elle est disponible comme consultante. Pour son poste principal, Grace rend compte à Claire, la directrice des ressources humaines. Claire rend compte à Charlie. Pour son poste de consultante, Grace a plusieurs relations fonctionnelles, selon le projet.

La société de Grace crée des règles d’acheminement du workflow basées sur une hierarchie **Configurable** (hiérarchies basées sur une matrice/un projet). Cette hiérarchie utilise le poste de consultante de Grace. Si l’option **Utiliser la hiérarchie des postes** est définie sur **Non**, lorsqu’un document est envoyé à Grace pour approbation, le workflow examine son poste principal (formatrice) pour déterminer où le document doit ensuite être envoyé. Dans ce cas, il sera d’abord envoyé à Claire puis à Charlie. Si l’option est définie sur **Oui** et le workflow utilise une hierarchie **Configurable**, le workflow examinera le poste de consultante de Grace et la relation hiérarchique pour déterminer où le document doit ensuite être envoyé.

### <a name="configure-a-human-resources-workflow"></a>Configurer un workflow des ressources humaines
Pour configurer un workflow de base qui démarre lorsque des employés demandent de modifier leur identification personnelle, procédez comme suit.

1.  Dans la page **Workflows des ressources humaines**, sélectionnez **Nouveau**.
2.  Dans la liste des workflows disponibles, sélectionnez **Numéros d’identification**.
3.  Sélectionnez **Exécuter** pour ouvrir le concepteur de workflow, puis entrez votre nom d’utilisateur et votre mot de passe.
4.  Déplacez l’élément **Approuver le numéro d’identification** de la liste des éléments de workflow vers le canevas du concepteur.
5.  Reliez l’élément d’approbation à **Démarrer** et **Terminer**.
6.  Appuyez deux fois (ou double-cliquez) sur **Approuver l’élément**, sélectionnez et maintenez appuyé (ou cliquez avec le bouton droit), puis sélectionnez **Propriétés**.
7.  Procédez comme suit pour ajouter des instructions relatives à un élément de travail :

    1.  Sélectionnez **Affectation**, puis sélectionnez **Hiérarchie** sous le type d’affectation.
    2.  Sous la sélection **Hiérarchie**, sélectionnez **Hiérarchie configurable**.
    3.  Ajoutez une condition d’arrêt, puis fermez la page.

8.  Suivez les instructions supplémentaires.
9.  Cliquez sur **Enregistrer et fermer**. Activez le nouveau workflow lorsque la boîte de dialogue s’ouvre, puis sélectionnez **Activer**.
10. Accédez à **Ressources humaines** &gt; **Postes** &gt; **Types de hiérarchie de postes**.
11. Sélectionnez **Matrice**.
12. Ajoutez le workflow **Numéro d’identification du collaborateur** à la liste.

## <a name="additional-resources"></a>Ressources supplémentaires

[Afficher et gérer les changements d’adresse](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
