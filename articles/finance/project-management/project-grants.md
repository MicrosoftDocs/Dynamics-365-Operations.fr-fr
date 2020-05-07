---
title: Subventions de projet
description: Cette rubrique illustre la création ou la modification d'une subvention.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282826"
---
# <a name="project-grants"></a>Subventions de projet

[!include [banner](../includes/banner.md)]

Une subvention est un don d'argent pour un objectif ou un projet spécifique. Généralement, il existe des restrictions sur la manière dont une subvention peut être dépensée. Dans Gestion et comptabilité du projet, vous pouvez entrer des subventions et les suivre, mais aussi définir leurs relations aux projets et aux contrats de projet. Par exemple, vous pouvez effectuer les tâches suivantes :

- Associer des subventions à des projets et des sources de financement via des liens vers les pages **Projet** et **Détails du contrat de projet**.
- entrer et suivre les modifications d'une subvention durant pendant qu'elle passe d'un statut à un autre ;
- entrer et suivre les coûts, les montants demandés, et les montants attribués ;
- créer des subventions principales et leur attribuer des subventions secondaires ;

Vous pouvez créer une subvention en entrant tous les détails dans un nouvel enregistrement ou vous pouvez copier les détails d'une subvention existante et les mettre à jour.

## <a name="create-a-new-grant"></a>Créer une nouvelle subvention

1. Accédez à **Intégration dans Gestion de projets et comptabilité** \> **Subventions** \> **Subventions**.
2. Sélectionnez **Nouveau** \> **Subvention**.
3. Sur la page des détails de la subvention, sur l'organisateur **Général**, dans le champ **ID de subvention**, entrez un identifiant alphanumérique pour la subvention.
4. Entrez un nom pour la subvention dans le champ **Nom de la subvention**.
5. Dans le champ **Description**, ajoutez des détails sur la nouvelle subvention.

    La plupart des autres champs de la page sont facultatifs et vous pouvez entrer autant d'informations que nécessaire.

    La liste suivante décrit les informations spécifiées sur chaque organisateur de la page des détails de la subvention :

    - **Général** - Saisissez le nom, le statut, la description, le but et le montant de la subvention.
    - **Informations de contact** - Permet d'entrer des détails sur les membres du personnel et du département qui gèrent la subvention, puis sur le client subventionné ou l'organisation, source de la subvention. Vous pouvez également indiquer si votre organisation est une entité de validation qui reçoit la subvention puis la transmet à un autre destinataire. Cliquez sur **Ajouter** pour ajouter des informations de contact comme les numéros de téléphone et adresses e-mail de l'organisation qui fournit la subvention.
    - **Dates et délais de livraison** - Permet d'entrer les dates liées à la subvention et à la demande de subvention. Les exemples incluent la date d'échéance de la demande, la date de soumission et la date à laquelle la subvention est approuvée ou rejetée.
    - **Projets associés et contrats de projets** - Vous ne pouvez saisir des informations sur cet onglet que si le champ **Statut de la subvention** sur l'organisateur **Général** est défini sur **Actif** ou **Décerné**. Sélectionnez parmi les options suivantes pour terminer la tâche connexe :

        - **Ajouter une source de financement** - Ajouter une nouvelle source de financement pour la subvention. Vous pouvez entrer tous les détails immédiatement ou utiliser les informations par défaut et procéder ensuite à une mise à jour ultérieurement.
        - **Ajouter un contrat de projet** - Ajouter ou mettre à jour les informations du contrat de projet.
        - **Ajouter un projet** - Ajouter ou mettre à jour les détails du projet.

    - **Installer** - Entrez des détails sur les fonds correspondants, si ces informations sont nécessaires. Plusieurs organisations qui octroient des subventions demandent que les bénéficiaires engagent un montant spécifique de leur propre argent ou de leurs ressources pour rapprocher le montant octroyé dans la subvention. Dans le champ **ID de projet local ou de suivi**, vous pouvez saisir un identifiant différent de l'identifiant du projet.

        > [!NOTE]
        > Si une partie de la subvention est attribuée à une autre organisation, définissez l'option **Sous-donateur** sur **Oui**. Pour les subventions attribuées aux États-Unis, vous pouvez spécifier si une subvention sera attribuée sous un mandat d'état ou fédéral.

    - **Détails attirés** - Permettent d'ajouter des informations sur la fréquence de retrait, la facturation ou la dépense des fonds de subvention, ou de mettre à jour les informations existantes.

## <a name="create-a-new-grant-from-a-copy"></a>Créer une subvention à partir d'une copie

1. Accédez à **Intégration dans Gestion de projets et comptabilité** \> **Subventions** \> **Subventions**.
2. Sélectionnez **Nouveau** \> **Copie de la subvention**.
3. Entrez un ID alphanumérique et un nom pour la nouvelle subvention, puis cliquez sur **OK**.
4. Sur la page des détails de la subvention, passez en revue les détails de la subvention copiée et apportez les modifications nécessaires. La plupart des champs de la page sont facultatifs.

## <a name="view-or-modify-grant-details"></a>Afficher ou modifier les détails de la subvention

1. Accédez à **Intégration dans Gestion de projets et comptabilité** \> **Subventions** \> **Subventions**.
2. Sélectionnez la subvention à modifier.
3. Dans le volet Actions, sous l'onglet **Subvention**, dans le groupe **Tenir à jour**, cliquez sur **Modifier**.
4. Vérifiez les détails de la subvention et apportez les modifications nécessaires.
