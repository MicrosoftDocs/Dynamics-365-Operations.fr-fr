---
title: Configuration en double écriture à partir de Lifecycle Services
description: Cette rubrique explique comment configurer une connexion en double écriture entre un nouvel environnement Finance and Operations et un nouvel environnement Dataverse de Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 25db9c58c3d09e44dcf11b48cae1a9eda4241c35
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683522"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuration en double écriture à partir de Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique explique comment configurer une connexion en double écriture entre un nouvel environnement Finance and Operations et un nouvel environnement Dataverse de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Conditions préalables

Vous devez être administrateur pour configurer une connexion en double écriture.

+ Vous devez avoir accès au client.
+ Vous devez être administrateur dans les deux environnements Finance and Operations et Dataverse.

## <a name="set-up-a-dual-write-connection"></a>Configurer une connexion en double écriture

Procédez comme suit pour configurer la connexion en double écriture.

1. Dans LCS, accédez à votre projet.
2. Sélectionnez **Configurer** pour déployer un nouvel environnement.
3. Sélectionnez la version. 
4. Sélectionnez la topologie. Si une seule topologie est disponible, elle est automatiquement sélectionnée.
5. Suivez les premières étapes de l’assistant **Paramètres de déploiement**.
6. Sur l’onglet **Dataverse**, suivez une des étapes suivantes :

    - Si un environnement Dataverse est déjà configuré pour votre client, vous pouvez le sélectionner.

        1. Définissez l’option **Configurer Dataverse** sur **Oui**.
        2. Dans le champ **Environnements disponibles**, sélectionnez l’environnement à intégrer avec vos données Finance and Operations. La liste comprend tous les environnements dans lesquels vous disposez de privilèges d’administrateur.
        3. Sélectionnez la case à cocher **Accepter** pour indiquer que vous acceptez les termes et conditions.

        ![Onglet Dataverse lorsqu’un environnement Dataverse est déjà configuré pour votre client.](../dual-write/media/lcs_setup_1.png)

    - Si votre client n’a pas encore d’environnement Dataverse, un nouvel environnement sera mis à disposition.

        1. Définissez l’option **Configurer Dataverse** sur **Oui**.
        2. Entrez un nom pour l’environnement Dataverse.
        3. Sélectionnez la région dans laquelle déployer l’environnement.
        4. Sélectionnez la langue et la devise par défaut pour l’environnement.

            > [!NOTE]
            > Vous ne pouvez pas modifier la langue et la devise ultérieurement.

        5. Sélectionnez la case à cocher **Accepter** pour indiquer que vous acceptez les termes et conditions.

        ![Onglet Dataverse lorsque votre client n’a pas déjà un environnement Dataverse](../dual-write/media/lcs_setup_2.png)

7. Suivez les étapes restantes de l’assistant **Paramètres de déploiement**.
8. Une fois que l’environnement a le statut **Déployé**, ouvrez la page des détails de l’environnement. La section **Informations de l’environnement Dataverse** montre les noms de l’environnement Finance and Operations et de l’environnement Dataverse associés.

    ![Section Information d’environnement Dataverse](../dual-write/media/lcs_setup_3.png)

9. Un administrateur de l’environnement Finance and Operations doit se connecter à LCS et sélectionner **Lien vers CDS pour les applications** pour compléter le lien. La page des détails de l’environnement affiche les informations de contact de l’administrateur.

    Une fois le lien terminé, le statut est mis à jour vers **Association à l’environnement terminée avec succès**.

10. Pour ouvrir l’espace de travail **Intégration de données** dans l’environnement Finance and Operations et contrôler les modèles disponibles, sélectionnez **Lien vers CDS pour les applications**.

    ![Lien vers le bouton CDS pour les applications dans la section Informations d’environnement Dataverse](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Vous ne pouvez pas dissocier des environnements à l’aide de LCS. Pour dissocier un environnement, ouvrez l’espace de travail **Intégration des données** dans l’environnement Finance and Operations, puis sélectionnez **Dissocier**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]