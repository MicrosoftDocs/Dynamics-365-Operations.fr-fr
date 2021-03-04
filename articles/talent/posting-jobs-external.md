---
title: Publier des postes sur Broadbean à partir de Attract
description: Cette rubrique explique comment utiliser Dynamics 365 Talent - Attract pour publier des offres d'emploi sur Broadbean.
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: 41fa057606887069a9ea0f1f2178eeaff59f33ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461206"
---
# <a name="post-jobs-to-broadbean-from-attract"></a>Publier des postes sur Broadbean à partir de Attract

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Attract vous aide à acquérir le talent dont vous avez besoin en vous permettant de publier vos offres d'emploi directement d'Attract vers Broadbean. Après avoir [créé une offre d'emploi](./creating-jobs-attract.md), il vous suffit de cliquer sur un bouton pour rendre votre offre d'emploi accessible à tous les candidats potentiels sur Broadbean.

La publication d'offres d'emploi sur Broadbean nécessite une licence Broadbean appropriée. Broadbean offre différents produits et plans. Pour plus d'informations sur les licences et les tarifs Broadbean, [contactez Broadbean](https://www.broadbean.com/contact-us/).

Si vous êtes administrateur et que vous avez besoin de plus d'informations sur la configuration de l'intégration de Broadbean avec Attract, consultez [Paramétrer l'intégration avec Broadbean dans Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md).

## <a name="post-jobs-to-broadbean"></a>Publier des postes sur Broadbean

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
2. Sous l'onglet **Publications**, sélectionnez le bouton de sélection (**...**) correspondant à Broadbean, puis sélectionnez **Afficher**.

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

### <a name="troubleshoot-job-posting-to-broadbean"></a>Résoudre les problèmes liés à la publication d'offres d'emploi sur Broadbean

Si vous avez des problèmes pour publier une offre d'emploi sur Broadbean, essayez ce qui suit.

1. Vérifiez que les informations d'identification Broadbean entrées dans Attract sont valides et correctes.
2. Si les informations d'identification sont valides et cerrectes, contactez le [Support Broadbean](https://www.broadbean.com/resources/support/).
3. Si le problème persiste, contactez le [Support Microsoft](./talent-support.md).

## <a name="see-also"></a>Voir également :

[Créer, approuver et publier des postes dans Attract](./creating-jobs-attract.md)

[Activer l'intégration à Broadbean dans Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]