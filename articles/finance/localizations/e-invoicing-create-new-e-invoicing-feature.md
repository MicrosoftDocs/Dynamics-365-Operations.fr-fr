---
title: Créer une fonctionnalité de facturation électronique
description: Cette rubrique explique comment créer une fonctionnalité de facturation électronique lorsqu’aucune fonctionnalité configurable n’est prête à l’emploi pour votre pays ou votre région.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744933"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Créer une fonctionnalité de facturation électronique

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer une fonctionnalité de facturation électronique lorsqu’aucune fonctionnalité configurable n’est prête à l’emploi pour votre pays ou votre région.

Pour créer une fonctionnalité de facturation électronique, effectuez les tâches suivantes :

1. Créez une configuration de format de fichier en utilisant la configuration de modèle de facture fournie et en tirant parti du mappage de facture existant pour la fonctionnalité que vous souhaitez créer.
2. Ajoutez les configurations de format de fichier aux configurations de la fonctionnalité de facturation électronique.
3. Créez le paramétrage de la fonctionnalité de facturation électronique.
4. Complétez la nouvelle fonctionnalité de facturation électronique et publiez-la dans le référentiel global de votre organisation.
5. Déployez la nouvelle fonctionnalité de facturation électronique dans l’environnement de service.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Créer des configurations de format de fichier dérivées du modèle de facture existant

Dans cette procédure, vous allez créer les configurations de format de fichier requises pour la nouvelle fonctionnalité de facturation électronique que vous souhaitez créer. Vous pouvez créer la configuration de format de fichier de facture électronique et toute autre configuration de format de fichier que votre nouvelle fonctionnalité de facturation électronique peut nécessiter.

Avant de commencer cette procédure, connectez-vous à votre compte Regulatory Configuration Service (RCS).

1. Dans Microsoft Dynamics 365 Finance, dans l’espace de travail **Gestion des états électroniques**, sélectionnez **Référentiels** pour le fournisseur de configuration **Microsoft**.
2. Sélectionnez **Global**, puis **Ouvert**, puis, dans le volet de gauche, sélectionnez la configuration **Modèle de facture**.

    > [!IMPORTANT]
    > Pour le Brésil, sélectionnez à la place la configuration de modèle **Documents fiscaux**.

3. Dans l’onglet **Configurations**, sélectionnez **Importer**.
4. Fermez la page.
5. Fermez la page.
6. Sélectionnez la vignette **Configurations des états**, puis sélectionnez le modèle de facture que vous avez importé.
7. Sélectionnez **Créer une configuration**, puis **Format basé sur le modèle de contexte de facture**.
8. Entrez un nom et une description pour la configuration de format.
9. Dans le champ **Type de demande**, sélectionnez le type d’extension de fichier.
10. Sélectionnez **Créer la configuration**, puis sélectionnez la configuration de format que vous avez créée.
11. Sélectionnez **Concepteur** et utilisez l’outil Concepteur de format pour configurer la mise en page de fichier afin qu’elle respecte les spécifications de format de fichier.
12. Fermez la page.
13. Dans l’onglet **Versions**, sélectionnez **Modifier le statut** \> **Terminer**.
14. Sélectionnez **Modifier le statut** \> **Partager** pour publier la configuration de format dans le référentiel global.

La nouvelle configuration de format de fichier doit être partagée avec le domaine Microsoft avant que la configuration puisse être utilisée par le service de facturation électronique.

1. Sélectionnez la configuration de format que vous utilisez. Le statut de la configuration doit être **Partagé**.
2. Dans l’onglet **Versions**, sélectionnez **Partage avancé** \> **Référentiel global**.
3. Dans l’onglet **Partagé avec**, sélectionnez **Organisation**.
4. Dans le champ **Paramètres**, entrez **Microsoft.com** pour partager la configuration de format avec le domaine Microsoft.
5. Cliquez sur **OK**.

## <a name="create-the-new-electronic-invoicing-feature"></a>Créer la fonctionnalité de facturation électronique

1. Dans RCS, dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
2. Sélectionnez **Ajouter**, puis **Nouvelle fonctionnalité**.
3. Entrez un nom et une description pour la fonctionnalité de facturation électronique.
4. Sélectionnez **Créer une fonctionnalité**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Ajout de configurations à la fonctionnalité de facturation électronique

1. Sélectionnez la fonctionnalité de facturation électronique que vous utilisez.
2. Dans l’onglet **Configurations**, sélectionnez **Ajouter**.
3. Dans la grille **Configurations**, parcourez et sélectionnez les configurations de format de fichier requises par votre fonctionnalité de facturation électronique pour générer le fichier de facture électronique.
4. Cliquez sur **OK**.

## <a name="add-electronic-invoicing-feature-setups"></a>Ajout de paramétrages à la fonctionnalité de facturation électronique

1. Dans l’onglet **Paramétrages**, sélectionnez **Ajouter**, puis sélectionnez **Paramétrage personnalisé**.
2. Entrez un nom et une description pour le paramétrage de la fonctionnalité.
3. Dans le champ **Type de paramétrage**, sélectionnez **Pipeline de traitement**.
4. Sélectionnez **Créer**.
5. Sélectionnez le paramétrage que vous utilisez, puis sélectionnez **Modifier**.
6. Dans l’onglet **Pipeline de traitement**, sélectionnez **Nouveau** pour ajouter une action de pipeline. Pour plus d’informations sur les pipelines, voir [Actions](e-invoicing-configuration-rcs.md#actions).
7. Dans l’onglet **Règle d’applicabilité**, sélectionnez **Nouveau** pour ajouter des clauses à la règle d’applicabilité. Pour plus d’informations sur les règles d’applicabilité, voir [Règles d’applicabilité](e-invoicing-configuration-rcs.md#applicability-rules).
8. Dans l’onglet **Variables**, sélectionnez **Nouveau** pour ajouter des variables au besoin.
9. Cliquez sur **Enregistrer**, puis sélectionnez **Valider** pour vérifier la cohérence de la configuration.
10. Fermez la page.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Déployer la nouvelle fonctionnalité de facturation électronique dans l’environnement de service

Pour plus d’informations sur l’exécution de cette tâche, voir [Déployer la fonctionnalité de facturation électronique dans l’environnement de service](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Déployer la fonctionnalité de facturation électronique dans une application connectée

Pour plus d’informations sur l’exécution de cette tâche, voir [Configurer la paramétrage de l’application](e-invoicing-get-started.md#configure-the-application-setup) et [Déployer la fonctionnalité de facturation électronique dans une application connectée](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
