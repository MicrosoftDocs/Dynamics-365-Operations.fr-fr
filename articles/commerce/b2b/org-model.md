---
title: Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B
description: Cette rubrique décrit comment créer des hiérarchies de modélisation organisationnelle pour les organisations B2B (business-to-business).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035905"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment créer des hiérarchies de modélisation organisationnelle pour les organisations B2B (business-to-business) dans Microsoft Dynamics 365 Commerce.

Dans Commerce Headquarters, les organisations partenaires sont représentées par des clients et des entités de hiérarchie cliente. L'organisation partenaire et ses utilisateurs sont représentés par des clients et les hiérarchies de clients sont utilisées pour associer ces clients les uns aux autres.

Lorsqu'une demande de partenaire commercial pour rejoindre un site de commerce électronique B2B est approuvée, les actions suivantes sont effectuées :

- Deux nouveaux enregistrements client sont créés dans le système : un enregistrement client **Type d'organisation** pour l'organisation partenaire et un enregistrement client **Type de personne** pour le demandeur (c'est-à-dire l'utilisateur partenaire qui a soumis la demande).
- Un nouvel enregistrement de hiérarchie client est créé sous **Client \> Hiérarchie des clients**. Cet enregistrement a les propriétés d'en-tête suivantes :

    - **ID de la hiérarchie client** - Un identifiant unique pour la hiérarchie client. Cet ID utilise la souche de numéros définie dans les paramètres partagés de Commerce dans Commerce Headquarters.
    - **Nom** - Le nom de l'organisation du partenaire commercial, tel que spécifié dans la demande d'intégration.
    - **Objectif** - Cette propriété est définie sur la valeur prédéfinie **Organisation B2B**.
    - **Organisation** - L'ID client du partenaire commercial.

Voici les détails de l'enregistrement de la hiérarchie client :

- L'enregistrement client du demandeur est associé à la hiérarchie client.
- Le rôle d'administrateur est associé au demandeur.

Lorsque l'administrateur ajoute plus d'utilisateurs à l'organisation partenaire sur un site B2B, un nouvel enregistrement client pour chaque utilisateur est créé dans Commerce Headquarters. Cet enregistrement client est également ajouté à l'enregistrement de hiérarchie client correspondant pour le partenaire et a le rôle d'un « utilisateur ».

> [!NOTE]
> Dans la plupart des cas, les valeurs de propriété correspondantes de tous les enregistrements client d'une hiérarchie doivent correspondre. Par exemple, étant donné que tous les utilisateurs partenaires doivent obtenir des prix similaires pour les produits, leur groupe de prix et les configurations associées doivent correspondre. Cependant, le système n'applique pas cette cohérence. Par conséquent, les utilisateurs de Commerce Headquarters concernés sont responsables de s'assurer que les valeurs de propriété et les configurations correspondent pour tous les clients d'une hiérarchie donnée.

Les utilisateurs de Commerce Headquarters peuvent consulter les valeurs de propriété de tous les enregistrements client de la hiérarchie dans une vue côte à côte. Sélectionnez les propriétés d'enregistrement client pertinentes en sélectionnant les noms d'onglet dans le menu déroulant. Les utilisateurs peuvent directement afficher et modifier les valeurs de propriété à partir de cette vue. Sinon, si vous souhaitez appliquer toutes les valeurs de l'enregistrement client administrateur à tous les enregistrements client utilisateur, sélectionnez **Remplacer** dans les détails de la hiérarchie client.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un site d'e-commerce B2B](set-up-b2b-site.md)

[Gérer les partenaires commerciaux sur les sites de commerce électronique B2B](manage-b2b-users.md)

[Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B](payment-method.md)

[Définir des limites de quantité de produits pour les sites de commerce électronique B2B](quantity-limits.md)
