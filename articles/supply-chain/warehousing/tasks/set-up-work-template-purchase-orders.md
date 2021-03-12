---
title: Paramétrer un modèle de travail pour les commandes fournisseur
description: Cette rubrique décrit comment paramétrer un modèle de travail simple à utiliser pour le rangement des articles reçus.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9acf6db9138a009527c6662f1cbb7e5fedc8778
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976861"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Paramétrer un modèle de travail pour les commandes fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment paramétrer un modèle de travail simple à utiliser pour le rangement des articles reçus. Les modèles de travail déterminent l'ensemble des instructions fournies à l'employé de l'entrepôt sur un appareil mobile lorsqu'il déplace des articles à partir de la zone de réception. Vous pouvez utiliser cette procédure avec les données fournies avec la société fictive de démonstration USMF. Avant de lancer ce guide, créez un ID de pool de travail. Dans cet exemple, on utilise un ID de pool de travail appelé Entrant. Cette procédure est destinée au gestionnaire d'entrepôts.

1. Dans le volet de navigation, accédez à **Volet de navigation > Modules > Gestion des entrepôts > Paramétrage > Travail > Modèles de travail**.
2. Dans le champ **Type d'ordre de travail**, sélectionnez **Commandes fournisseurs**.

## <a name="create-a-work-template-header"></a>Créer un en-tête de modèle de travail
1. Sélectionnez **Nouveau**.
2. Entrez un nombre dans le champ **Numéro de souche**. Il s'agit de l'ordre dans lequel les modèles de travail sont évalués. Vous pouvez modifier la séquence, au besoin.  
3. Dans le champ **Modèle de travail**, tapez une valeur. Il s'agit de l'identificateur unique pour ce modèle.  
4. Dans le champ **Description du modèle de travail**, tapez une valeur.
    - L'option **Valide** ne sera pas activée tant que vous n'aurez pas renseigné toutes les informations nécessaires au modèle et n'aurez pas sélectionné **Enregistrer**.  
    - Un ordre d'exécution du type **Commande fournisseur** ne peut pas être traité automatiquement, alors laissez l'option **Traiter automatiquement** sur **Non**.  
5. Tapez une valeur dans le champ **ID de pool de travail**. Les ID de pool de travail vous permettent d'organiser le travail en groupes. La valeur que vous définissez ici sera la valeur par défaut pour tout travail créé à l'aide de ce modèle.  
6. Dans le champ **Priorité du travail**, entrez `1`. Cela indique l'importance du travail, et la valeur que vous définissez ici sera la valeur par défaut pour tout travail créé à l'aide de ce modèle.  
7. Sélectionnez **Enregistrer**. Vous devez enregistrer l'en-tête du modèle de travail avant que le bouton **Modifier la requête** devienne disponible.  

## <a name="set-up-the-query-for-the-work-template"></a>Définissez la requête utilisée pour le modèle de travail.
1. Sélectionnez **Modifier une requête**. Nous définirons une limitation spécifiant que le modèle ne peut être utilisé que dans un entrepôt particulier.  
2. Sélectionnez **Ajouter**.
3. Dans le champ **Champ** de la nouvelle ligne, entrez `warehouse`.
4. Tapez une valeur dans le champ **Critères**.
5. Cliquez sur **OK**.
6. Cliquez sur **Oui**.

## <a name="set-work-template-details"></a>Définissez les détails du modèle de travail
1. Sélectionnez **Nouveau**.
2. Dans le champ **Type de travail**, sélectionnez **Prélever**.
3. Dans le champ **ID classe de travail**, saisissez `purchase`. La classe de travail que vous définissez ici sera la valeur par défaut sur toutes les lignes de travail de type Prélèvement créées à l'aide de ce modèle. La classe de travail ne peut pas être remplacée à partir des lignes d'ordre d'exécution. Les classes de travail sont utilisées pour diriger et/ou limiter le type de lignes de commande de travail qu'un employé de l'entrepôt peut traiter sur un appareil mobile.  
4. Sélectionnez **Nouveau**.
5. Dans le champ **Type de travail**, sélectionnez **Put**.
6. Dans le champ **ID classe de travail**, saisissez une valeur. Les instructions de prélèvement et de placement sont un ensemble. Chaque ensemble prélever/placer doit avoir la même classe de travail. Utilisez la même classe de travail que vous avez fournie pour l'instruction de prélèvement.  
7. Sélectionnez **Enregistrer**. Notez que la case à cocher **Valide** est maintenant activée.  

