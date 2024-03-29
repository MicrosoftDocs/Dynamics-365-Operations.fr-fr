---
title: Paramétrer le prélèvement de groupement
description: Cet article décrit la procédure de paramétrage du prélèvement de groupement et comment appliquer la confirmation d’article avec le prélèvement de groupement.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ec3de073def2ff63af3c04b5696cbcec4f09948
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014718"
---
# <a name="set-up-cluster-picking"></a>Paramétrer le prélèvement de groupement

[!include[banner](../includes/banner.md)]

Cet article décrit comment permettre aux collaborateurs d’utiliser leurs appareils mobiles pour regrouper les travaux de prélèvement en groupements, afin de pouvoir prélever des articles depuis un même emplacement pour plusieurs ordres de fabrication simultanément. On parle alors de *prélèvement de groupement*.

## <a name="about-cluster-picking"></a>À propos du prélèvement de groupement

Une fois les ordres de fabrication lancés dans l’entrepôt, le collaborateur peut utiliser un appareil mobile pour affecter les ordres à un groupement. Le groupement organisera le travail de prélèvement pour le collaborateur. Lorsqu’un ordre de fabrication est affecté à un groupement, le collaborateur doit utiliser le prélèvement de groupement pour effectuer le travail de prélèvement pour l’ordre. Le collaborateur ne peut pas utiliser d’autres méthodes de prélèvement. Si un ordre de fabrication est affecté à un groupement par erreur, le collaborateur doit rompre le groupement et le recréer.

Si nécessaire, un collaborateur peut transmettre un groupement à un autre collaborateur. Le statut du groupement devient alors Transmis. Lorsque le collaborateur utilise un appareil mobile pour indiquer que le travail de prélèvement et de rangement est terminé, l’expédition ou le chargement doit être confirmé dans le client.

## <a name="enable-cluster-picking"></a>Activer le prélèvement du groupement

Pour activer le prélèvement de groupement, vous devez paramétrer les éléments suivants :

- **Profils de groupement** – Permet de spécifier si les ID groupement sont générés automatiquement, le nombre de postes à utiliser, quand rompre les groupements, et comment séquencer et vérifier le travail de prélèvement.

- **Modèles de travail** – Permet de définir comment créer le travail de prélèvement pour le prélèvement de groupement.

- **Instructions d’emplacement** – Permet de spécifier où prélever les articles, et où les ranger.

- **Options de menu d’appareil mobile** – Permet de configurer une option de menu d’appareil mobile pour utiliser le travail existant qui est dirigé par le prélèvement de groupement. Vous devez ensuite ajouter l’option de menu à un menu d’appareil mobile afin qu’il soit affiché sur les appareils mobiles.

- **Paramètres de gestion des entrepôts** – Permet de spécifier la souche de numéros à utiliser si vous souhaitez générer des identificateurs pour les groupements.

## <a name="set-up-a-cluster-profile"></a>Paramétrer un profil de groupement

Pour paramétrer un profil de groupement, procédez comme suit :

1. Cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Profils de groupement**.

1. Cliquez sur **Nouveau** pour créer un profil.

1. Cliquez sur **Créer un groupement** et, sous **Tri de groupement**, cliquez sur **Nouveau** pour paramétrer les critères de tri du groupement. Les critères de tri contrôlent l’ordre dans lequel le collaborateur réalisera le travail de prélèvement. Vous pouvez ajouter autant de critères que nécessaire.

1. Dans le champ **Souche de N°**, entrez un nombre pour définir l’ordre dans lequel les critères de tri sont traités.

1. Dans le champ **Nom de champ**, sélectionnez le champ qui déterminera le tri. Par exemple, si vous sélectionnez le champ **WMSLocationId**, le travail sera trié par emplacement.

1. Dans le champ **Tri**, sélectionnez l’une des options suivantes.

| **Option**     | **Description**                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Croissant**  | Le travail de prélèvement est séquencé dans l’ordre croissant sur la base des critères de tri. Par exemple, si vous utilisez le champ **WMSLocationId** comme critères de tri, et que les ID d’emplacement sont 1, 2, 3, et 4, vous prélèverez depuis l’emplacement 4 en premier. |
| **Décroissant** | Le travail de prélèvement est séquencé dans l’ordre décroissant sur la base des critères de tri. Par exemple, si vous utilisez le champ **WMSLocationId** comme critères de tri, et que les ID d’emplacement sont 1, 2, 3, et 4, vous prélèverez depuis l’emplacement 1 en premier. |

## <a name="item-confirmation"></a>Confirmation d’article

Lorsque la sélection du groupement est appliqué, la confirmation d’article est cruciale pour vérifier les articles qui sont ajoutés aux clusters. Vous pouvez vérifier les articles de la sélection du groupement lors du processus de sélection du groupement. Le paramétrage est basé sur le paramétrage de code-barres de produit.

### <a name="set-up-item-verification-with-cluster-picking"></a>Paramétrage de la vérification d’article avec la sélection du groupement

1. Accédez à **Gestion des entrepôts** > **Configuration** > **Appareil mobile** > **Options de menu d’appareil mobile**.
1. Dans le volet de liste, sélectionnez l’option de menu que vous souhaitez configurer.
1. Dans le volet Actions, sélectionnez **Configuration de la confirmation de travail**.
1. Effectuez l’une des actions suivantes :
    - S’il existe déjà une ligne pour le **Type de travail** que vous souhaitez configurer, sélectionnez-le, puis sélectionnez **Modifier** dans le volet Actions.
    - Si une ligne appropriée n’existe pas, sélectionnez **Nouveau** dans le volet Actions, puis définissez le **Type de travail** sur le type approprié.
1. Cochez la case **Confirmation du produit** pour votre ligne nouvelle ou sélectionnée. Cela permettra aux collaborateurs de vérifier chaque pièce du stock à l’aide de l’appareil mobile.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]