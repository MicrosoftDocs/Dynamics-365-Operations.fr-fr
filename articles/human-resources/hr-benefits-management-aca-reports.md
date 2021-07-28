---
title: Générer des rapports sur la Loi sur les soins abordables dans l’espace de travail Gestion des avantages
description: Ces rubriques décrivent comment Gestion des avantages vous aide à suivre les informations qui sont déclarées sur le formulaire 1095-B et le formulaire 1095-C pour le mandat de l’employeur de la Loi sur les soins abordables (ACA).
author: andreabichsel
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b8a83982ad36abfe9032cae50fe4f09339985dc8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353660"
---
# <a name="generate-aca-reports-in-benefits-management"></a>Générer des rapports ACA dans Gestion des avantages

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Gestion des avantages vous aide à suivre les informations qui sont déclarées sur le formulaire 1095-B et le formulaire 1095-C pour le mandat de l’employeur de la Loi sur les soins abordables (ACA). Comme la fonctionnalité de génération d’états ACA dans l’ancien espace de travail **Avantages**, cette fonctionnalité s’applique uniquement aux entités juridiques aux États-Unis.

Pour utiliser cette fonctionnalité, vous devez d’abord activer **Gestion avancée des avantages**. Pour plus d’informations, y compris des mises en garde importantes sur la Gestion des avantages, voir [Activer ou désactiver la gestion des avantages](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Vous pouvez utiliser la génération d’états ACA uniquement à partir de l’espace de travail **Gestion des avantages** ou de l’ancien espace de travail **Avantages**, pas les deux. Par exemple, si vous êtes passé à la Gestion des avantages, la génération d’états ACA est disponible uniquement à partir de l’espace de travail **Gestion des avantages**, pas de l’ancien espace de travail **Avantages**.
>
> Si vous passez à la Gestion des avantages au milieu d’une année d’inscription, vous devez configurer correctement les données des employés pour toute l’année dans la Gestion des avantages. De cette manière, vous avez la garantie de recevoir des informations de génération d’états précises pour toute l’année.

## <a name="getting-started"></a>Mise en route

Pour suivre les informations sur les formulaires 1095, vous devez d’abord créer un ou plusieurs groupes de couverture liés à la Loi sur les soins abordables. Ces groupes indiquent les informations suivantes :

- L’offre de protection qui a été fournie à un employé
- La part de l’employé sur la prime mensuelle la moins coûteuse, si le coût est supérieur au seuil de pauvreté fédéral
- La mesure Safe Harbor utilisée par l’employeur, le cas échéant

Les groupes de couverture de soins abordables vous aident à gérer ces informations pour plusieurs dossiers d’employés qui présentent les mêmes conditions. Vous pouvez facilement attribuer des groupes à un ou plusieurs employés.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Créer ou modifier un groupe de couverture de soins abordables

1. Dans l’espace de travail **Gestion des avantages**, sélectionnez **Groupe de couverture de soins abordables**.

    ![Sélection d’un groupe de couverture de soins abordables.](./media/hr-benefits-management-aca-coverage-group.png)

2. Sélectionnez **Nouveau** pour créer un nouveau groupe de couverture de soins abordables ou **Modifier** pour modifier un groupe existant.

    ![Sélectionner Nouveau ou Modifier.](./media/hr-benefits-management-aca-new.png)

3. Définisse les champs suivants.

    | Champ | Description  |
    |---|---|
    | Nom | Entrez un nom pour le groupe. |
    | Description | Permet d’entrer une description du groupe. |
    | Offre de couverture | La protection offerte aux employés, à leur conjoint ou partenaire et à leurs personnes à charge. |
    | Part de coût de l’employé | Le montant qui incombe à l’employé. |
    | Mesures Safe Harbor section 4980H applicables | La sphère de sécurité 4980H ou le code de secours de transition. |
    | Mois de début du plan | Sélectionnez le mois civil où commence l’année de votre régime de prestations. |
    | Groupe valable à partir de | La première date à laquelle cet enregistrement est valide. |
    | Groupe valable jusqu’en | La dernière date à laquelle cet enregistrement est valide. S’il n’y a pas de date d’expiration, saisissez **Jamais**. |

    ![Création d’un groupe de couverture.](./media/hr-benefits-management-aca-new-group.png)

4. Sélectionnez **Enregistrer**.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Affecter plusieurs employés à un groupe de couverture de soins abordables

1. Dans l’espace de travail **Gestion des avantages**, sélectionnez **Groupe de couverture de soins abordables**.
2. Sélectionnez le groupe auquel affecter les employés.
3. Sélectionnez **Affectation en masse**.

    ![Sélection d’Affectation en masse.](./media/hr-benefits-management-aca-mass-assignment.png)

4. Sélectionnez les employés dans la liste, puis sélectionnez **Attribuer**.

    ![Affectation des employés sélectionnés à un groupe.](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Tenir à jour plusieurs versions des options de couverture

Vous pouvez tenir à jour plusieurs versions d’un groupe de couverture quelconque. Lorsque quelque chose change dans votre organisation ou les avantages offerts, vous pouvez garder les informations du groupe à jour sans avoir à créer de nouveau groupe et à y réaffecter des employés.

Une fois que vous avez créé des groupes de couverture de soins abordables, vous pouvez leur affecter en masse des employés. Vous pouvez également affecter individuellement des employés à des groupes et indiquer si les informations ACA font l’objet d’un suivi et d’une déclaration.

Si vous n’avez pas à suivre et à signaler les informations ACA pour un employé, vous pouvez définir l’option **Couverture d’état** sur **Non**. Par exemple, vous pourriez avoir des employés à temps partiel qui n’ont pas besoin de rapports ACA.

### <a name="override-default-values-for-an-employee"></a>Remplacer les valeurs par défaut pour un employé

Pour les employés affectés à un groupe de couverture de soins abordables, vous pouvez modifier les options suivantes pour tous les mois qui nécessitent des valeurs différentes :

- Offre de couverture
- Part de coût de l’employé
- Mesures Safe Harbor section 4980H applicables

> [!NOTE]
> Pour les rapports ACA 2020, vous devez déclarer les codes postaux professionnels et personnels sur le formulaire 1095-C. Les valeurs sont automatiquement renseignées, en fonction des emplacements actifs actuels. Si l’un des deux emplacements était différent pendant une partie de l’année, vous devez remplacer la valeur. Le champ **Code postal** (ligne 17) du rapport 1095-C est renseigné uniquement si le code **Offre de couverture** va de **1 L** à **1Q**, comme suit :
>
> - **1L, 1M ou 1N :** Le code postal de la résidence principale
> - **1O, 1P, 1Q :** Le code postal de l’emploi principal

Pour saisir des exceptions pour les valeurs d’un groupe de couverture de soins abordables, procédez comme suit :

1. Dans l’espace de travail **Gestion du personnel**, sélectionnez **Liens**, puis **Collaborateurs**.
2. Sélectionnez l’employé dans la liste.
3. Sur l’onglet **Emploi**, dans la section **Plus d’information**, sélectionnez **Couverture de soins abordables**.

    ![Changer les options pour un employé.](./media/hr-benefits-management-aca-change-single-employee.png)

4. Sélectionnez **Modifier**.
5. Pour chaque mois nécessitant des modifications, activez la case à cocher **Remplacer par défaut**, puis modifiez les autres valeurs selon vos besoins.

    ![Remplacer les valeurs par défaut.](./media/hr-benefits-management-aca-override-default.png)

6. Sélectionnez **Enregistrer**.

## <a name="report-health-care-coverage"></a>État sur la couverture des soins de santé

Vous devez suivre toute couverture de soins de santé auto-assurée parrainée par l’employeur pour les employés à temps plein et à temps partiel. Vous devez inclure chaque employé, ainsi que leurs personnes à charge, sur le rapport 1095-C pour les mois où ils étaient couverts.

Pour indiquer si un régime de prestations sociales doit être déclaré, procédez comme suit :

1. Dans l’espace de travail **Gestion des avantages**, sélectionnez **Régimes de prestations**.
2. Sélectionnez le régime de prestations à signaler.
3. Sélectionnez **Modifier**.
4. Définissez l’option **Déclaré en vertu de la Loi sur les soins abordables** sur **Oui**.

    ![Génération d’états sur la couverture des soins de santé.](./media/hr-benefits-management-aca-report-coverage.png)

5. Sélectionnez **Enregistrer**.

Si un employé choisit la couverture des soins de santé pour une personne à charge, la période de couverture de la personne à charge est déterminée selon la date à laquelle elle a été inscrite ou retirée. Les dates de couverture pour les personnes à charge sont automatiquement calculées en fonction de la période pendant laquelle la personne à charge était admissible et active dans un régime au cours de l’année d’adhésion.

## <a name="generate-1095-b-and-1095-c-forms"></a>Générer des formulaires 1095-B et 1095-C

Vous pouvez générer les formulaires ACA 1095-B et 1095-C et les distribuer à chacun de vos employés. Vous pouvez également générer électroniquement le formulaire 1095-C et les fichiers de transmission 1094-C correspondants à envoyer à l’Internal Revenue Service (IRS).

1. Dans l’espace de travail **Gestion des avantages**, sélectionnez **Formulaire ACA 1095-B** ou **Formulaire ACA 1095-C**.
2. Modifiez les paramètres selon vos besoins, puis cliquez sur **OK**.

    > [!NOTE]
    > Si vous imprimez des formulaires 1095-C pour plus de 500 employés, vous recevrez plusieurs fichiers PDF. Nous vous recommandons d’augmenter la valeur du champ **Taille maximale du fichier en mégaoctets** sur la page **Paramètres de gestion des documents** sur **150**. (Pour ouvrir rapidement cette page, vous pouvez utiliser le champ de recherche de la barre de navigation.)
    >
    > ![Modification de la taille maximale du fichier.](./media/hr-benefits-management-aca-maximum-file-size.png)

3. Pour vérifier l’état de vos rapports et les afficher, utilisez le champ de recherche de la barre de navigation pour ouvrir la page **Tâches de gestion des états électroniques**.

    ![Recherche de la page Tâches de gestion des états électroniques.](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Sélectionnez le rapport à afficher, puis sélectionnez **Afficher les fichiers**.

    ![Affichage des fichiers.](./media/hr-benefits-management-aca-show-files.png)

5. Cliquez sur **Ouvrir**.

    ![Ouverture d’un fichier.](./media/hr-benefits-management-aca-open-file.png)

6. Dans la barre de notification qui apparaît au bas de la fenêtre du navigateur, ouvrez le fichier zip, puis sélectionnez le rapport. Vous pouvez afficher ou imprimer le fichier PDF.

    ![Exemple de formulaire 1095-C.](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>Afficher les informations de couverture ACA

La page **Couverture du collaborateur en matière de soins abordables** affiche les informations suivantes :

- Employés affectés à chaque groupe de protection
- Employés qui ne doivent pas être inclus dans un rapport
- Employés non affectés

Pour afficher ces informations, procédez comme suit :

1. Dans l’espace de travail **Gestion des avantages**, sélectionnez **Couverture du collaborateur en matière de soins abordables**.
2. Sélectionnez un groupe dans le champ **Nom de groupe**.

    ![Affichage de la couverture ACA.](./media/hr-benefits-management-aca-view-coverage.png)

Si l’une des valeurs par défaut du groupe de couverture lié aux soins abordables est remplacée, un astérisque apparaît en regard de la valeur modifiée. Si les valeurs des 12 mois sont identiques et ne sont pas remplacées, la valeur apparaît dans la colonne **Tous les 12 mois**.

Vous pouvez afficher les employés qui sont marqués comme non déclarables à l’ACA et qui n’auront pas besoin d’un formulaire 1095-C. Dans le champ **Filtrer par**, sélectionnez **À ne pas déclarer dans le cadre de la loi sur les soins abordables**.

Vous pouvez afficher les employés qui ne sont pas affectés à un groupe ou qui sont affectés à un groupe expiré. Dans le champ **Filtrer par**, sélectionnez **Groupe non attribué ou expiré**.

### <a name="export-to-excel"></a>Exporter vers Excel

Pour exporter l’une des listes vers Microsoft Excel, procédez comme suit :

1. Sélectionnez le bouton **Ouvrir dans Microsoft Office**.
2. Sélectionnez **Table temporaire HCM Human Resources à usage interne**.
3. Sélectionnez **Télécharger**.

### <a name="view-aca-reportable-dependents"></a>Afficher les personnes à charge déclarables à l’ACA

Si vous devez déclarer des personnes prises en charge par une couverte personnelle employeur, vous pouvez également consulter qui sont couvertes par les régimes d’avantages sociaux avec la mention **Déclarer dans le cadre de la loi sur les soins abordables**. Sélectionnez **Afficher la couverture des personnes à charge** dans le volet Actions.

![Affichage de la couverture des personnes à charge.](./media/hr-benefits-management-aca-view-dependent-coverage.png)

Les informations de couverture pour les personnes à charge de l’employé sont affichées.

![Couverture des personnes à charge.](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> La page affiche uniquement les régimes d’avantages qui sont marqués comme **ACA déclarables**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]