---
title: Publication d'emplois sur des sites de carrière externes à partir d'Attract
description: Cette rubrique explique comment utiliser Dynamics 365 for Talent - Attract pour publier des offres d'emploi sur des sites de recrutement externes
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517999"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Publication d'emplois sur des sites de carrière externes à partir d'Attract

[!include [banner](../includes/banner.md)]

Vous souhaitez présenter vos postes vacants à autant de candidats qualifiés que possible. Les sites de recrutement comme Broadbean vous aident à y parvenir. Microsoft Dynamics 365 Talent - Attract vous permet désormais de publier des offres sur Broadbean, et Microsoft propose continuellement de nouvelles options dans ce domaine.

## <a name="post-jobs-to-broadbean"></a>Publier des offres sur Broadbean

Avant de publier des offres sur Broadbean, vous devez configurer l'intégration de Broadbean.

> [!NOTE]
> - Pour publier des offres sur des sites externes, vous devez avoir le [Module complémentaire Recrutement complet](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Cette fonctionnalité est actuellement en mode aperçu. Si vous souhaitez l'essayer, vous devez [l'activer dans les paramètres administrateur d'Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Configurer l'intégration de Broadbean

1. Connectez-vous à Attract en tant qu'administrateur.
2. Sélectionnez le bouton **Paramètres** (le symbole d'engrenage) dans le coin supérieur droit de la page, puis sélectionnez **Centre d'administration**.
3. Dans l'onglet **Paramètres des offres d'emploi**, dans la section **Activer l'intégration de Broadbean**, activez l'intégration.
4. Contactez Broadbean, puis entrez vos informations dans **Nom d'utilisateur, ID client, jeton de chiffrement**.

> [!WARNING]
> Les informations d'identification Broadbean sont précieuses et confidentielles. Conservez-les et partagez-les de manière responsable en conséquence. Toute personne disposant du rôle Administrateur dans Attract peut afficher ces informations d'identification.

> [!NOTE]
> Microsoft et Attract ne sont pas impliqués dans la création et la conservation de ces valeurs. Il est de votre responsabilité de les garder à jour dans Attract et de faire appel à Broadbean pour résoudre éventuels les problèmes impliquant vos informations d'identification.

### <a name="post-a-job-to-broadbean"></a>Publication d'une offre sur Broadbean

Une fois Broadbean activé, les recruteurs et les administrateurs peuvent y publier une offre d'emploi. Vous devez posséder une URL de candidature pour l'emploi.

1. Dans Attract, ouvrez l'emploi que vous souhaitez publier dans Broadbean.
2. Dans la section **Publications**, sélectionnez le bouton **Publier maintenant** correspondant à Broadbean.
3. Suivez les instructions de la fenêtre Broadbean.

Attract transmet les informations suivantes à Broadbean :

- ID demande
- Titre du poste
- Description du poste
- Emplacement du poste
- URL de candidature
- Informations sur le recruteur

Une fois la publication terminée avec succès dans Broadbean, la section **Validations** de l'emploi dans Attract affiche le statut de Broadbean comme **Publié**.

> [!NOTE]
> - Broadbean nécessite le champ **Secteur**. Actuellement, ce champ est défini sur **IT** par défaut. Toutefois, vous pouvez modifier la valeur sur le secteur approprié dans la fenêtre de publication d'emploi dans Broadbean.
> - Il faut un certain temps pour que Broadbean mène à bien la publication de votre offre sur tous les sites d'emplois que vous avez sélectionnés. Par conséquent, il peut y avoir un léger délai avant qu'Attract ne mette à jour le statut de l'offre d'emploi.

### <a name="view-a-broadbean-job-posting"></a>Afficher une publication d'offre d'emploi Broadbean

Après avoir publié une offre dans Broadbean, vous pouvez la voir depuis Attract.

1. Dans Attract, ouvrez l'emploi que vous souhaitez afficher dans Broadbean.
2. Dans la section **Publications**, sélectionnez le bouton représentant des points de suspension (**...**) qui correspond Broadbean, puis sélectionnez **Afficher**.

La publication d'offre d'emploi Broadbean apparaît dans une nouvelle fenêtre.

### <a name="update-a-broadbean-job-posting"></a>Mise à jour d'une publication d'offre d'emploi Broadbean

Vous pouvez mettre à jour une publication d'offre d'emploi Broadbean de deux manières.

1. Dans Attract, ouvrez l'emploi que vous souhaitez mettre à jour.
2. Dans la section **Publications**, sélectionnez le bouton **Mettre à jour la publication** correspondant à Broadbean.
3. Modifiez la publication dans la fenêtre Broadbean.

- ou -

1. Dans Attract, ouvrez l'emploi que vous souhaitez afficher dans Broadbean.
2. Dans la section **Publications**, sélectionnez le bouton représentant des points de suspension (**...**) qui correspond Broadbean, puis sélectionnez **Afficher**.
3. Dans la fenêtre Broadbean, modifiez les détails de l'emploi, puis publiez à nouveau l'offre d'emploi. Les détails de l'emploi dans Attract ne sont pas modifiés.

### <a name="remove-a-broadbean-job-posting"></a>Supprimer une publication d'offre d'emploi Broadbean

Vous pouvez supprimer une publication d'offre d'emploi de Broadbean comme bon vous semble.

1. Dans Attract, ouvrez l'emploi que vous souhaitez supprimer.
2. Dans la section **Publications**, sélectionnez le bouton représentant des points de suspension (**...**) qui correspond Broadbean, puis sélectionnez **Supprimer la publication**.

Une fois que Broadbean a supprimé l'offre d'emploi, l'article Broadbean dans Attract a un bouton **Publier maintenant**. La présence de ce bouton indique que l'offre d'emploi a été supprimée et peut être publiée de nouveau.

### <a name="troubleshoot-the-broadbean-integration"></a>Résoudre les problèmes d'intégration de Broadbean

Si vous avez des problèmes pour publier une offre d'emploi sur Broadbean, essayez ce qui suit.

1. Vérifiez que les informations d'identification Broadbean entrées dans Attract sont valides et correctes.
2. Si les informations d'identification sont valides et cerrectes, contactez le [Support Broadbean](https://www.broadbean.com/resources/support/).
3. Si le problème persiste, contactez le [Support Microsoft](./talent-support.md).
