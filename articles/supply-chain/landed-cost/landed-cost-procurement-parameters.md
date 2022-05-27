---
title: Paramètres d’approvisionnement pour le coût au débarquement
description: Cette rubrique décrit comment configurer les paramètres d’approvisionnement appropriés lorsque vous utilisez le module de coût au débarquement.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 6e0ceb84423d7adc9c37da1b0b35a486627c0ce3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690412"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Paramètres d’approvisionnement pour le coût au débarquement

[!include [banner](../../includes/banner.md)]

La page **Paramètres d’approvisionnement** a quelques paramètres qui sont particulièrement pertinents lorsque vous utilisez le module **coût au débarquement**. Utilisez la boîte de dialogue **Mettre à jour les lignes de commande** qui s’ouvre à partir de la page **Paramètres d’approvisionnement** pour spécifier si les lignes de commande fournisseur doivent être automatiquement mises à jour lorsque des modifications sont apportées à l’en-tête de la commande fournisseur.

Pour terminer ce paramétrage, procédez comme suit.

1. Accédez à **Approvisionnements \> Paramétrage \> Paramètres d’approvisionnements**.
1. Sur l’onglet **Général**, sélectionnez le lien **Mettre à jour les lignes de commande**.
1. La boîte de dialogue **Mettre à jour les lignes de commande** répertorie les champs de l’en-tête de commande qui peuvent également appliquer des mises à jour automatiques aux champs associés sur les lignes de commande. Définissez chaque champ de la liste sur l’une des valeurs suivantes :

    - **Toujours** – Les lignes de commande doivent être mises à jour automatiquement lorsque l’en-tête de la commande est mis à jour.
    - **Jamais** – Les lignes de commande ne doivent jamais être mises à jour lorsque l’en-tête de la commande est mis à jour.
    - **Inviter** – L’utilisateur sera invité à choisir si les lignes de commande doivent être mises à jour.
