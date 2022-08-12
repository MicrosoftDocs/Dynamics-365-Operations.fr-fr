---
title: Stockage de sauvegarde des modèles de gestion des états électroniques
description: Cet article décrit l’utilisation du stockage de sauvegarde de gestion des états électroniques pour la récupération des modèles.
author: NickSelin
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 635e7152bece91d5dee47f82cef7052730eb0c82
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108950"
---
# <a name="backup-storage-of-er-templates"></a>Stockage de sauvegarde des modèles de gestion des états électroniques

[!include [banner](../includes/banner.md)]

La [vue d’ensemble de gestion des états électroniques (ER)](general-electronic-reporting.md) permet aux utilisateurs professionnels de configurer des formats pour les documents sortants conformément aux obligations légales de différents pays/régions. Les formats de gestion des états électroniques configurés peuvent utiliser des modèles prédéfinis pour générer les documents sortants dans différents formats, tels que des classeurs Microsoft Excel, des documents Microsoft Word ou des documents PDF. Les modèles sont complétés avec les données que le flux de données configuré pour les documents générés exige.

Chaque format configuré peut être publié dans le cadre d’une solution de gestion des états électroniques. Chaque solution de gestion des états électroniques peut être exportée d’une instance de finances et d’opérations, puis importée vers une autre instance.

La structure de gestion des états électroniques utilise le [Configurer la gestion des documents](../../fin-ops/organization-administration/configure-document-management.md) pour conserver les modèles requis pour l’instance actuelle de finances et d’opérations. En fonction des paramètres de la structure de gestion des états électroniques, le stockage d’objets blob Microsoft Azure ou un dossier Microsoft SharePoint peut être sélectionné comme emplacement physique de stockage principal pour les modèles. (Pour plus d’informations, voir [Configuration de la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md).) La table de DocuValue tient à jour un enregistrement individuel pour chaque modèle. Dans chaque enregistrement, le champ **AccessInformation** enregistre le chemin d’un fichier de modèle situé à l’emplacement de stockage configuré.

Lorsque vous gérez vos instances de finances et d’opérations, vous pouvez décider de migrer l’instance actuelle vers un autre emplacement. Par exemple, vous pouvez migrer votre instance de production vers un nouvel environnement de bac à sable. So vous n’avez pas configuré la structure de la gestion des états électroniques pour stocker les modèles dans un stockage d’objets blob, la table DocuValue du nouvel environnement de bac à sable fait référence à l’instance de stockage d’objets blob dans l’environnement de production. Cependant, cette instance n’est pas accessible depuis l’environnement de bac à sable, car le processus de migration n’est pas compatible avec la migration des artefacts dans le stockage d’objets blob. Par conséquent, si vous essayez d’exécuter un format de gestion d’états électroniques qui utilise un modèle pour générer des documents commerciaux, une exception survient et vous êtes averti du modèle manquant. Vous êtes également invité à utiliser l’outil de nettoyage des états électroniques pour supprimer, puis réimporter la configuration du format des états électroniques qui contient le modèle. En raison des nombreuses configurations du format de gestion des états électroniques, ce processus peut se révéler chronophage.

Le stockage de sauvegarde de la fonctionnalité des modèles de gestion des états électroniques peut vous permettre de créer vos modèles afin qu’ils soient toujours disponibles pour générer des documents commerciaux.

> [!NOTE]
> Cette fonctionnalité peut être utilisée uniquement lorsque le stockage d’objets blob a été sélectionné comme emplacement de stockage physique pour les modèles de gestion des états électroniques.

## <a name="automated-recovery-and-notification"></a>Récupération et notification automatisées

Pour cette fonctionnalité, chaque modèle d’une nouvelle configuration de format de gestion des états électroniques dans l’environnement actuel est automatiquement enregistré sur l’emplacement de stockage de sauvegarde pour les modèles (la table de base de données ERDocuDatabaseStorage) lorsque les événements suivants se produisent :

- Vous importez une nouvelle configuration du format de gestion des états électroniques qui contient un modèle.
- Vous terminez la version d’ébauche d’une configuration du format de gestion des états électroniques qui contient un modèle.

Les copies de sauvegarde des modèles sont migrées vers une nouvelle instance de finances et d’opérations dans le cadre de la base de données de l’application.

Si un modèle d’un format de gestion des états électroniques est requis pour la génération de documents sortants, pour traiter les paiements aux fournisseurs, y compris la génération de conseils de paiement et les rapports de contrôle, par exemple, mais si le modèle requis est introuvable dans le principal emplacement de stockage, les événements suivants se produisent :

- Si le modèle est disponible dans l’emplacement de stockage de sauvegarde, il est automatiquement extrait de l’emplacement de stockage de sauvegarde, puis restauré à l’emplacement de stockage principal et utilisé pour l’exécution actuelle.
- Chaque utilisateur assigné au rôle de **Développeur gestion des états électroniques** ou d’**administrateur système** reçoit une notification relative au problème de modèle manquant via le centre d’actions. Le message qui s’affiche dépend de la valeur du paramètre **Exécuter automatiquement la procédure de restauration des modèles endommagés dans le traitement par lots** :

    - Si ce paramètre est défini sur **Désactivé**, le message vous recommande de lancer le processus de traitement par lots pour corriger automatiquement les problèmes similaires pour les autres modèle de configuration du format des états électroniques. Le message contient un lien que vous pouvez utiliser pour lancer le processus de traitement par lots.
    - Si ce paramètre est défini sur **Activé**, le message vous indique qu’un problème de modèles manquants a été décelé et qu’un nouveau processus de traitement par lots, **Restaurer les modèles endommagés depuis la sauvegarde de la base de données interne**, a été automatiquement planifié. Ce processus de traitement par lots corrigera automatiquement les problèmes similaires pour les autres modèles.

Pour configurer le paramètre **Exécuter automatiquement la procédure de restauration des modèles endommagés dans le traitement par lots**, procédez comme suit :

1. Dans finances et opérations, ouvrez la page **Administration d’organisation \> Gestion des états électroniques \> Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres d’utilisateur**, définissez la valeur requise pour le paramètre **Exécuter automatiquement la procédure de restauration des modèles endommagés dans le traitement par lots**.

> [!NOTE]
> Ce paramètre est défini comme spécifique à la société connectée et à l’utilisateur de l’application.

![Page Configurations ER.](./media/GER-BackupTemplates-1.png)

L’illustration suivante présente un exemple du message qui s’affiche lorsque le paramètre **Exécuter automatiquement la procédure de restauration des modèles endommagés dans le traitement par lots** est défini sur **Activé**.

![Page du journal des paiements fournisseur.](./media/GER-BackupTemplates-2.png)

L’illustration ci-dessous indique le processus de traitement par lots **Restaurer les modèles endommagés depuis la sauvegarde de la base de données interne** sur la page **Processus de traitement par lots**.

![Page Traitement par lots.](./media/GER-BackupTemplates-3.png)

Le journal d’exécution du processus de traitement par lots terminé **Restaurer les modèles endommagés depuis la sauvegarde de la base de données interne** contient des informations sur les modèles qui ont été restaurés depuis l’emplacement de stockage de sauvegarde vers l’emplacement de stockage principal.

![Page Historique du traitement par lots.](./media/GER-BackupTemplates-4.png)

Par défaut, le processus de création automatique des copies de sauvegarde des modèles qui résident dans les configurations du format de gestion des états électroniques est activé. Pour arrêter de réaliser des copies de sauvegarde des modèles, définissez l’option **Arrêter de créer des copies de sauvegarde des modèles** sur **Activé** sous l’onglet **Pièces jointes** de la page **Paramètres des états électroniques**. Vous pouvez ouvrir cette page depuis l’espace de travail **Gestion des états électroniques**.

Si vous définissez l’option **Arrêter de créer des copies de sauvegarde des modèles** sur **Activé** et si vous ne souhaitez pas conserver les copies de sauvegarde précédemment faites de modèles, sélectionnez **Nettoyer le stockage de sauvegarde** sur la page **Paramètres des états électroniques**.

Si vous avez mis votre environnement à niveau avec finances et opérations version 10.0.5 (octobre 2019) et si vous souhaitez migrer vers un nouvel environnement comprenant des configurations de format de gestion des états électroniques pouvant être exécutées, sélectionnez **Compléter le stockage de sauvegarde** sur la page **Paramètres des états électroniques** avant la migration. Ce bouton lance le processus de création de copies de sauvegarde de tous les modèles disponibles afin qu’ils puissent être stockés dans l’emplacement de stockage de sauvegarde de gestion des états électroniques pour les modèles.

![Page Paramètres de la gestion des états électroniques.](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Récupération manuelle

Accédez à **Administration de l’organisation** \> **Rapports électroniques** \> **Restaurer des modèles endommagés** pour lancer manuellement le processus de restauration des modèles ER de l’emplacement de stockage de sauvegarde vers l’emplacement de stockage principal. Avant de commencer ce processus, dans la page **Restaurer des modèles endommagés**, vous pouvez spécifier si elle sera effectuée de manière interactive ou si le traitement par lots sera planifié pour cela.

## <a name="supported-deployments"></a>Déploiements pris en charge

Dans finances et opérations version 10.0.5, le stockage de sauvegarde de la fonctionnalité des modèles de gestion des états électroniques est disponible uniquement dans les déploiements sur le cloud.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)

[Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
