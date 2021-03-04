---
title: Configurer les registres des baux
description: Cette rubrique décrit les informations gérées dans les registres de location. Les registres de location contiennent les méthodes comptables qui déterminent la façon dont une location est comptabilisé dans le système.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 28518341544327f1983e563b719b0f455b6e1c43
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443370"
---
# <a name="set-up-lease-books"></a>Configurer les registres des baux

[!include [banner](../includes/banner.md)]

Les registres de location contiennent les méthodes comptables qui déterminent la façon dont une location est comptabilisé dans le système. En plus de la comptabilité de caisse, la location d’actifs prend en charge les normes suivantes :

- Principes comptables généraux des États-Unis (GAAP)
- Article 842 sur la codification des normes comptables (ASC 842)
- ASC 840
- Norme internationale d’information financière 16 (IFRS 16)
- Norme comptable internationale 17 (IAS 17)

Pour créer un registre de location, procédez comme suit.

1. Accédez à **Location d’actifs \> Configuration \> registres de baux**.
2. Sélectionnez **Nouveau** pour ajouter un registre.
3. Définisse les champs suivants.

    | Nom                                     | Description |
    |------------------------------------------|-------------|
    | Couche de validation                            | Sélectionnez la couche de validation à utiliser. Chaque registre associé à un bail est configuré pour une couche de validation spécifique. Chaque couche de validation a des objectifs de publication différents. |
    | Type de bail                               | Sélectionnez si la location doit être classé automatiquement ou s’il doit être prédéfini en tant que location-financement ou location simple. |
    | Structure comptable                     | Sélectionnez le cadre associé au registre. |
    | Configuration Durée du bail/Durée de vie utile          | Le système classera le bail comme contrat de location-financement si le type de bail est défini sur **automatique** et si la durée du bail sur la durée de vie utile de l’actif est supérieure ou égale au pourcentage défini dans ce champ.  |
    | Configuration Valeur actuelle/Juste valeur de l’actif   | Entrez un nombre entier pour définir le seuil qui déterminera le type de bail. Si la valeur actuelle des futurs paiements minimaux au titre de la location est supérieure à la valeur définie par l’utilisateur à partir de la configuration comptable et si la classification des contrats de location du registre est définie sur automatique, le système classera le contrat de location comme contrat de location-financement. |
    | Seuil à court terme                     | Saisissez le nombre de mois à utiliser comme seuil pour les baux à court terme. Si la durée du bail est inférieure ou égale au nombre de mois que vous entrez ici, le système classera le bail comme un bail à court terme et le traitement du loyer différé sera appliqué. |
    | Seuil de faible valeur                      | Saisissez un montant à utiliser comme seuil pour les baux de faible valeur. Si la juste valeur de l’actif est inférieure ou égale ou la valeur que vous entrez ici, le système classera le bail comme un bail de faible valeur et le traitement du loyer différé sera appliqué. |
    | Payer au fournisseur                            | Définissez cette option sur **Oui** pour permettre que les paiements de location soient imputés, sous forme de facture, sur le compte fournisseur spécifié sur chaque contrat de location. Lorsqu’un paiement de location est validé, le compte fournisseur est crédité. Si cette option est définie sur **Non**, le compte spécifié pour le type de validation **Paiement de location** sur la page **Paramètres d’affichage du bail** sera créditée à la place. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]