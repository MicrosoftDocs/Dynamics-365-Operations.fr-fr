---
title: Créer des actifs basés sur les commandes fournisseur
description: Cette rubrique explique comment créer une liste d'éléments d'actifs pouvant servir de base à la création d'actifs pour les travaux de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectItem, EntAssetPendingAssets
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83419fa5c6b6aee0b321c526565c3518deaf4bd0
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016982"
---
# <a name="create-assets-based-on-purchase-orders"></a>Créer des actifs basés sur les commandes fournisseur

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique comment créer une liste d'éléments d'actifs pouvant servir de base à la création d'actifs pour les travaux de maintenance dans le module Gestion des actifs. En fonction des actifs, vous pouvez afficher une liste des lignes de commande créées sur ces articles. Le but de cette fonctionnalité est de créer facilement un actif dans le module Gestion des actifs basé sur une commande fournisseur.

Premièrement, vous définissez les articles à utiliser pour créer les actifs d'une commande fournisseur dans **Articles d'actifs**. Après avoir créé une ligne de commande fournisseur, créez les actifs dans **Actifs en attente**. Il est possible de déterminer à quel stade de la commande fournisseur l'actif doit être créé.


## <a name="select-asset-items"></a>Sélectionner des éléments d'actifs

1. Cliquez sur **Gestion des actifs** > **Paramétrage** > **Actifs** > **Articles**.
2. Cliquez sur **Nouveau** pour créer un élément d'actif.
3. Sélectionnez l'élément dans le champ **Numéro d'article**. Lorsque vous laissez ce champ, le nom d'article est automatiquement inséré dans le champ **Nom du produit**.
4. Dans l'organisateur **Général**, sélectionnez un type d'actif pour l'article.
5. Sélectionnez le fabricant et le modèle d'actif pour l'article.
6. Enregistrez l'élément.


## <a name="create-assets-from-pending-assets"></a>Créer des actifs à partir des actifs en attente

1. Cliquez sur **Gestion des actifs** > **Commun** > **Actifs** > **Actifs en attente**.
2. Vous verrez une liste mise à jour des commandes d'achat basée sur les articles sélectionnés dans **Articles d'actifs**.
3. Vous pouvez filtrer le statut des commandes d'achat pour sélectionner le statut de cycle de vie auquel l'actif doit être créé. Par exemple, vous souhaiterez peut-être créer des actifs uniquement lorsqu'un reçu de produit aura été enregistré lors d'une commande d'achat.
4. Sélectionnez le lien **Numéro de référence** dans une ligne de commande fournisseur pour afficher des informations détaillées sur l'article.
5. Si vous souhaitez modifier les dimensions à afficher sous l'organisateur **Dimensions de stock**, cliquez sur le bouton **Affichage des dimensions**, puis effectuez vos sélections.
6. Si vous souhaitez créer un actif sur une ligne de commande fournisseur, activez la case à cocher dans la colonne **Marquer** pour cette ligne sur la page de liste, puis cliquez sur **Créer des actifs**. Un message s'affiche vous informant de l'ID d'actif.
7. Sélectionnez l'actif dans la liste **Tous les actifs**, puis cliquez sur **Modifier** pour ajouter davantage d'informations à l'actif.
8. Dans **Actifs en attente**, si vous souhaitez supprimer une ligne car vous ne souhaitez pas créer d'actif, activez la case à cocher dans la colonne **Marquer** pour cette ligne, puis cliquez sur **Ignorer les actifs en attente**. Un message s'affiche vous informant de l'ID d'actif. Vous ne supprimez pas la commande fournisseur ou la commande client, juste l'enregistrement à partir duquel vous auriez pu créer un actif dans **Gestion des actifs**.

>[!NOTE]
>Toutes les dimensions de produit (taille, couleur, configuration, etc.) sont transférées automatiquement dans les attributs d'actifs. Les dimensions de suivi (numéro de série) sont enregistrés directement sur l'actif lors de sa création.


## <a name="find-pending-assets"></a>Rechercher des actifs en attente

Vous pouvez exécuter un **nombre d'actifs en attente** pour vérifier les actifs en attente. Par exemple, cette fonction peut être utilisée pour recevoir une notification chaque fois qu'un actif en attente est prêt à être créé en tant qu'actif.

1. Cliquez sur **Gestion des actifs** > **Périodique** > **Actifs** > **Nombre d'actifs en attente**.
2. Cliquez sur **Ajouter** pour exécuter la tâche et mettre à jour la liste dans **Actifs en attente**.
3. Vous pouvez configurer l'exécution de ce travail en tant que traitement par lots, par exemple une fois par jour.

**Attention :** Si les données sont modifiées dans une commande fournisseur *une fois que* vous avez créé un actif en fonction de l'élément concerné, ces modifications ne sont pas répercutées sur l'actif.
