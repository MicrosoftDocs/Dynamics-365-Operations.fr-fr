---
title: Réaliser, publier et déployer une fonctionnalité de globalisation
description: Cet article fournit des informations sur le cycle de vie des fonctionnalités de globalisation.
author: gionoder
ms.date: 12/15/2021
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
ms.openlocfilehash: 9d4a408f2169b220fefd9ab7e9f3b37217fb3cfe
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710833"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Réaliser, publier et déployer une fonctionnalité de globalisation

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Versions de la fonctionnalité de facturation électronique

Les fonctionnalités de facturation électronique font l’objet d’une version. Lorsqu’une nouvelle version est créée, le numéro de version est automatiquement incrémenté.

Les versions des fonctionnalités de facturation électronique suivent un cycle de vie qui a jusqu’à trois statuts :

- **Brouillon** – Si une version de fonctionnalité est définie sur ce statut, vous pouvez modifier ses attributs de configuration et n’importe lequel de ses artefacts (par exemple, les configurations de format de fichier).
- **Terminé** – Ce statut indique que vous avez terminé de modifier la version de la fonctionnalité et que vous n’avez pas l’intention d’y apporter d’autres mises à jour. Lorsqu’une version de fonctionnalité est définie sur ce statut, vous ne pouvez plus modifier la version de la fonctionnalité ou l’un de ses composants.
- **Publié** – Ce statut indique que la version de la fonctionnalité a été publiée dans le référentiel global associé à votre organisation. Lorsqu’une version de fonctionnalité est définie sur ce statut, vous ne pouvez plus modifier la version de la fonctionnalité ou l’un de ses composants.

Vous pouvez spécifier une date **À compter de** pour une nouvelle version d’une fonctionnalité de facturation électronique. De cette manière, vous pouvez définir une version par défaut qui peut être utilisée ou qui peut être remplacée lorsque la fonctionnalité est déployée dans l’environnement de service.

Pour modifier le statut d’une version de la fonctionnalité de facturation électronique, procédez comme suit.

1. Connectez-vous à votre compte RCS (Regulatory Configuration Service).
2. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. À gauche de la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité de facturation électronique.
4. Sur l’onglet **Versions** sur le côté droit de la page, sélectionnez la version.
5. Sélectionnez **Modifier le statut**, puis **Terminé** (si le statut actuel est **Brouillon**) ou **Publié** (si le statut actuel est **Terminé**).
6. Dans la zone de message, cliquez sur **Oui** pour confirmer la requête.

Le changement manuel du statut **Terminé** vers le statut **Publié** est facultatif. Les versions de la fonctionnalité de facturation électronique sont automatiquement mises à jour sur le statut **Publié** lorsqu’ils sont déployés vers l’environnement de service.

Vous pouvez suivre le statut dans la colonne **Statut de version de la fonctionnalité** sur l’onglet **Versions**.

## <a name="deploy-feature-versions"></a>Déployer des versions de fonctionnalité

Dans RCS, vous utilisez la commande **Déployer** pour publier une version de la fonctionnalité de facturation électronique dans l’environnement de service cible ou l’application connectée.

1. À gauche de la page **Fonctionnalités de facturation électronique**, sélectionnez la fonctionnalité de facturation électronique.
2. Sur l’onglet **Versions** sur le côté droit de la page, sélectionnez la version de la fonctionnalité de facturation électronique que vous souhaitez déployer dans l’environnement de service ou l’application connectée. La version sélectionnée doit être définie sur le statut **Terminé** ou **Publié**.
3. Sélectionnez **Déployer**, puis l’une des options suivantes pour définir la cible du déploiement :

    - **Application connectée** – Option facultative, mais doit être utilisée si vous souhaitez que la configuration fournie par le programme d’installation de l’application soit écrite dans l’instance de Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management qui lui était auparavant associée. Ignorer ce type de déploiement nécessite une configuration manuelle des paramètres définis dans la configuration de l’application de Finance ou Supply Chain Management.
    - **Environnement de service** – Déploie la version de la fonctionnalité de facturation électronique dans l’environnement de service. La facturation électronique est alors prête à recevoir et à traiter les documents électroniques envoyés par Finance ou Supply Chain Management.

> [!NOTE]
> En règle générale, vous modifierez les paramètres de la fonctionnalité de gestion des états électroniques (ER) qui doit être déployée dans l’environnement de service. Les modifications de l’application connectée seront rares. Vous devez déployer de nouvelles versions sur l’application connectée uniquement lorsque vous modifiez les paramètres correspondants de votre application.

Pour déterminer si une version spécifique d’une fonction de facturation électronique est déployée dans un environnement spécifique, consultez les informations sur l’onglet **Environnements**.

## <a name="remove-feature-versions"></a>Supprimer les versions de fonctionnalités

Dans RCS, vous pouvez sélectionner **Annuler** pour supprimer une version spécifique de la fonction de facturation électronique d’un environnement de service si elle a été déployée là.

> [!IMPORTANT]
> Le bouton **Annuler** ne fonctionne que pour les environnements de service. Elle ne supprime rien de l’appplication connectée pour la fonctionnalité de facturation électronique actuelle.

## <a name="rebase-electronic-invoicing-features"></a>Redéfinir la base des fonctionnalités de facturation électronique

Lorsqu’une fonctionnalité de facturation électronique est dérivée d’une autre, vous pouvez sélectionner **Redéfinir** pour mettre à jour la fonctionnalité dérivée avec les modifications qui ont été introduites dans la fonctionnalité (parente) d’origine.

Pour redéfinir la base d’une version dérivée d’une fonctionnalité que vous avez créée, procédez comme suit.

1. Obtenez la dernière version de la fonctionnalité en l’important depuis le référentiel global. Pour plus d’informations, voir [Importer la fonctionnalité depuis le référentiel global](e-invoicing-import-feature-global-repository.md).
2. Dans la liste des fonctionnalités, sélectionnez la fonctionnalité à redéfinir.
3. Dans l’onglet **Versions**, sélectionnez **Nouveau** pour créer une version de brouillon.
4. Sélectionnez **Redéfinir**.
5. Dans la boîte de dialogue **Redéfinir**, sélectionnez la version de la fonctionnalité à redéfinir.
6. Cliquez sur **OK**.
7. Passez en revue les composants de la fonctionnalité et apportez les modifications nécessaires.
8. Sélectionnez **Modifier le statut** pour terminer la fonctionnalité redéfinie. Une fois la redéfinition terminée, vous pouvez effectuer des actions supplémentaires.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Obtenir une version spécifique des fonctionnalités de facturation électronique

Lorsque vous créez une nouvelle version d’une fonctionnalité de facturation électronique, le système crée une copie de la dernière version de la fonctionnalité. Pour utiliser une version antérieure de la fonctionnalité comme base d’une nouvelle version, sélectionnez la version, puis **Obtenir cette commande de version**. Une nouvelle version brouillon de la fonctionnalité est créée. Il s’agit d’une copie de la version sélectionnée.
