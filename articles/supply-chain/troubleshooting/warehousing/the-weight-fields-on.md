---
title: Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge
description: Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924349"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge

Codes d'erreur : WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Les champs de poids sur les lignes de charge ne correspondent pas à ceux situés sur la charge %1. Exécutez le contrôle de la cohérence du poids de la charge de l’entrepôt pour recalculer les champs de poids.

## <a name="cause"></a>Cause

Les champs **Poids net** et **Tare** sont définis sur *0* (zéro) sur la ligne de charge. Cependant, les champs de poids ne sont pas définis sur *0* pour les mesures de poids sur le produit. Lorsque les champs de poids ne sont pas définis sur la ligne de charge, toute correction de la quantité sur la ligne de charge peut entraîner un calcul de poids incorrect sur la charge. Ce problème peut se produire si les poids du produit ont été modifiés depuis la création de la ligne de charge.

## <a name="resolution"></a>Résolution

Par défaut, lorsqu'une ligne de charge est créée, les champs de poids du produit y sont saisis. Si le poids est nul, vous pouvez le recalculer en utilisant la fonctionnalité *Vérification de la cohérence du poids de la charge de l’entrepôt*.

1. Accédez à **Administration système \> Tâches périodiques \> Base de données \> Contrôle de cohérence**.
1. Dans la boîte de dialogue **Contrôle de cohérence**, définissez le champ **Module** sur *Gestion des entrepôts*.
1. Définissez le champ **Vérifier/réparer** sur *Corriger les erreurs*.
1. Dans la liste des cases à cocher, cochez la case **Vérification de la cohérence du poids de la charge de l’entrepôt** et assurez-vous que seule la ligne correspondant à cette case est mise en surbrillance.
1. En haut de la liste des cases à cocher, sélectionnez le bouton points de suspension (**...**), puis sélectionnez **Boîte de dialogue** dans le menu.
1. Dans la boîte de dialogue **Vérification de la cohérence du poids de la charge de l’entrepôt**, définissez les champs suivants pour spécifier les critères pour lesquels la vérification de cohérence doit s'exécuter :

    - **ID de chargement :** Spécifiez un ID de chargement. Laissez ce champ vide pour vérifier tous les ID de chargement.
    - **Numéro d'article :** Spécifiez un numéro d'article. Laissez ce champ vide pour vérifier tous les articles.
    - **Toujours recalculer le poids sur les charges :** Définissez cette option sur *Oui*.
    - **Autoriser l'écrasement du poids sur les lignes de charge :** Définissez cette option sur *Oui*.

1. Cliquez sur **OK** pour fermer la boite de dialogue **Vérification de la cohérence du poids de la charge de l’entrepôt**.
1. Sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Exécuter** dans le menu.

Le poids est recalculé en fonction des critères que vous avez spécifiés. Cliquez sur le lien **Détails du message** pour afficher le résultat du contrôle de cohérence.
