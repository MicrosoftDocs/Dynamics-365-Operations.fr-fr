---
title: Créer une fonctionnalité de globalisation
description: Cet article explique comment créer une fonctionnalité de globalisation.
author: gionoder
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5432de8f8a70a4e6a0facd546083b37fd8690556
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283173"
---
# <a name="create-a-globalization-feature"></a>Créer une fonctionnalité de globalisation

[!include [banner](../includes/banner.md)]

Vous pouvez créer une fonctionnalité de facturation électronique à partir de zéro ou la définir sur une fonctionnalité existante. Lorsque vous créez une fonctionnalité de facturation électronique à partir de rien, vous devez ajouter manuellement les configurations et autres composants de gestion des états électroniques (ER) comme la configuration de la fonctionnalité et les détails de configuration de l’application. Lorsque vous créez une fonctionnalité basée sur une fonctionnalité existante, la nouvelle fonctionnalité hérite de toutes les configurations et de tous les paramètres de la fonctionnalité de base. Vous pouvez vérifier ce qui est copié de la fonctionnalité de base vers la nouvelle fonctionnalité.

## <a name="create-a-feature-from-scratch"></a>Créer une fonctionnalité à partir de rien

Cette section explique comment créer une fonctionnalité de facturation électronique lorsqu’aucune fonctionnalité de globalisation n’est disponible dans le référentiel global pour vos scénarios professionnels prêts à l’emploi.

Pour créer une fonctionnalité de facturation électronique, procédez comme suit.

1. Connectez-vous à votre compte RCS (Regulatory Configuration Service).
2. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sélectionnez **Ajouter** puis, dans la boîte de dialogue déroulante, sélectionnez l’option **Nouvelle fonctionnalité**.
4. Entrez un nom et une description pour la fonctionnalité de facturation électronique.
5. Sélectionnez **Créer une fonctionnalité**. La première version de la nouvelle fonctionnalité apparaît sur le côté droit de la page et a un statut **Brouillon**.

    Ensuite, vous devez ajouter des configurations de gestion des états électroniques (ER) et des configurations de fonctionnalités. Avant d’ajouter de nouvelles configurations de format de gestion des états électroniques (ER) ou des configurations existantes, assurez-vous qu’elles existent dans votre référentiel RCS local.

6. Sélectionnez la fonctionnalité de facturation électronique que vous utilisez.
7. Dans l’onglet **Configurations**, sélectionnez **Ajouter**.
8. Dans la grille **Configurations**, recherchez et sélectionnez les configurations de format requises pour le pipeline de traitement (par exemple, pour générer des fichiers de factures électroniques ou traiter les réponses de services Web externes).
9. Cliquez sur **OK**. Vous pouvez maintenant utiliser les configurations dans les actions du pipeline de traitement. Pour en savoir plus, consultez [Utiliser des configurations](e-invoicing-work-configurations.md).
10. Pour ajouter un paramétrage de fonctionnalité de facturation électronique, créez-le sur l’onglet **Configurations** de la page **Nouvelle fonctionnalité**. Pour en savoir plus, consultez [Utiliser des configurations de fonctionnalité](e-invoicing-feature-setup.md).
11. Terminez la configuration, et déployez la fonctionnalité de facturation électronique dans l’environnement de service. Pour en savoir plus, voir [Réaliser, publier et déployer une fonctionnalité de globalisation](e-invoicing-complete-publish-deploy-globalization-feature.md).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Créer des configurations de format de fichier dérivées du modèle de facture existant

Vous pouvez ignorer cette section si vous n’avez pas à créer de configurations de gestion des états électroniques (ER), mais vous pouvez réutiliser des versions existantes comme base.

Cette procédure montre comment créer les configurations de format de fichier requises pour la nouvelle fonctionnalité de facturation électronique que vous souhaitez créer. Créez la configuration de format de fichier de facture électronique et toute autre configuration de format de fichier que votre nouvelle fonctionnalité de facturation électronique peut nécessiter.

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Génération des états électronique**, sélectionnez la vignette **Configurations des états**.
3. Sélectionnez le **Modèle de facture** ou, pour les scénarios brésiliens, sélectionnez le **Modèle fiscal**.
4. Sélectionnez **Créer une configuration**, puis, dans la boîte de dialogue déroulante, sélectionnez l’option **Format basé sur le modèle de données de facture**.
5. Entrez un nom et une description pour la configuration de format.
6. Dans le champ **Type de demande**, sélectionnez le type d’extension de fichier.
7. Dans le champ **Définition du modèle de données**, sélectionnez la structure racine sur laquelle mapper votre format. Par exemple, **InvoiceCustomer** est utilisé pour les formats de facture client.
8. Sélectionnez **Créer une configuration**.
9. Sélectionnez la nouvelle configuration de format.
10. Sélectionnez **Concepteur** et utilisez l’outil Concepteur de format pour configurer la mise en page de fichier afin qu’elle respecte les spécifications de format de fichier.
11. Fermez la page.
12. Dans l’onglet **Versions**, sélectionnez **Modifier le statut** \> **Terminer**.
13. Sélectionnez **Modifier le statut** \> **Partager** pour publier la configuration de format dans le référentiel global.

Les nouvelles configurations de format de fichier doit être partagée avec le domaine Microsoft avant que les configurations puissent être utilisées par le service de facturation électronique.

1. Sélectionnez la configuration de format que vous utilisez. Le statut de la configuration doit être **Partagé**.
2. Dans l’onglet **Versions**, sélectionnez **Partage avancé** \> **Référentiel global**.
3. Dans l’onglet **Partagé avec**, sélectionnez **Organisation**.
4. Dans le champ **Paramètres**, entrez **microsoft.com** pour partager la configuration de format avec le domaine Microsoft.
5. Cliquez sur **OK**.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Créer une fonctionnalité basée sur une fonctionnalité existante

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Dans le champ **Fournisseur de configuration**, veillez à ce que votre fournisseur de configuration actif soit sélectionné. Ainsi, la nouvelle fonctionnalité de facturation électronique apparaîtra dans la liste après sa création. Si votre fournisseur de configuration actif n’est pas sélectionné, la nouvelle fonctionnalité sera filtrée de la liste.
4. Sélectionnez **Ajouter** puis, dans la boîte de dialogue déroulante, sélectionnez l’option **Basé sur une version existante**.
5. Entrez un nom et une description de la fonctionnalité.
6. Dans le champ **Fonctionnalité de base**, sélectionnez la version de base de la fonctionnalité.
7. Sélectionnez **Créer une fonctionnalité**. La fonctionnalité est créée et a le statut **Brouillon**.
8. Passez en revue les composants de la fonctionnalité pour déterminer si des mises à jour sont requises :

    - Passez en revue les configurations, au cas où vous deviez personnaliser les formats de gestion des états électroniques (ER) et leur liaison avec les mappages de format pour la version de la fonctionnalité.
    - Passez en revue la configuration, au cas où vous deviez personnaliser l’onglet **Actions**, l’onglet **Règles d’applicabilité** ou l’onglet **Variables** pour la version de la fonctionnalité.

9. Terminez la configuration, et déployez la fonctionnalité de facturation électronique dans l’environnement de service. Pour en savoir plus, voir [Réaliser, publier et déployer une fonctionnalité de globalisation](e-invoicing-complete-publish-deploy-globalization-feature.md).
