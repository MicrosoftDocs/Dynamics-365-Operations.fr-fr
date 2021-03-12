---
title: Créer des entités juridiques
description: Cette rubrique décrit comment créer des entités juridiques dans Microsoft Dynamics 365 Commerce, qui doit être créé et configuré avant de créer des canaux.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9491feb004366a02155225bfb323773e130f3dc9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993601"
---
# <a name="create-legal-entities"></a>Créer des entités juridiques


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer des entités juridiques dans Microsoft Dynamics 365 Commerce, qui doit être créé et configuré avant de créer des canaux.

## <a name="overview"></a>Vue d'ensemble

Une entité juridique est une organisation qui dispose d'une structure juridique enregistrée ou légalement déclarée. Les entités juridiques peuvent passer des contrats juridiques et sont tenues de préparer des relevés faisant état de leurs performances.

Une société est un type d’entité juridique. Actuellement, les entreprises sont les seuls types d’entité juridique que vous pouvez créer et chaque entité juridique est associée à un ID société. Cette association existe car certaines zones fonctionnelles du programme utilisent un ID société, ou *DataAreaId*, dans leurs modèles de données. Dans ces zones fonctionnelles, les sociétés sont utilisées en tant que limite pour la sécurité des données. Les utilisateurs peuvent accéder aux données uniquement pour la société à laquelle ils sont actuellement connectés. 

Lors de la création d'un canal, vous devez spécifier à quelle entité juridique appartient ce canal.

## <a name="create-a-new-legal-entity"></a>Créer une entité juridique

Pour créer une entité juridique dans Dynamics 365 Commerce, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Configuration du siège \> Entités juridiques**.
1. Dans le volet Actions, sélectionnez **Nouveau**. Le volet **Nouvelle entité juridique** s'affiche à droite.
1. Dans le champ **Nom**, entrez une valeur.
1. Dans le champ **Société**, entrez une valeur.
1. Dans le champ **Pays/Région**, sélectionnez ou entrez une valeur.
1. Cliquez sur **OK**. 

   ![Création d'entité juridique](media/legal-entities.png)

1. Dans la section **Général**, indiquez les informations générales suivantes concernant l'entité juridique : 
   1. Entrez un nom de recherche si celui-ci est obligatoire. Il s’agit d’un nom alternatif pouvant être utilisé pour rechercher cette entité juridique. 
   1. Choisissez si cette entité juridique est utilisée en tant que société de consolidation.
   1. Choisissez si cette entité juridique est utilisée en tant que société d'élimination. 
   1. Sélectionnez la **langue par défaut** pour l'entité. 
   1. Sélectionnez le **fuseau horaire** pour l'entité.
1. Dans la section **Adresses**, sélectionnez **Modifier** pour saisir les informations d'adresse, telles que la rue, le numéro, le code postal et la ville.
1. Dans la section **Informations de contact**, entrez les informations relatives aux modes de communication, notamment les adresses e-mail, les URL et les numéros de téléphone.
1. Dans la section **Génération d'état statutaire**, entrez les numéros d'enregistrement utilisés pour la génération d'états statutaires.
1. Dans la section **Numéros d'enregistrement**, entrez toutes les informations requises par l'entité juridique.
1. Dans la section **Informations sur le compte en banque**, entrez les comptes bancaires et les numéros d'acheminement de l'entité juridique.
1. Dans la section **Commerce extérieur et logistique**, entrez les informations d'expédition pour l'entité juridique.
1. Dans la section **Séquences de nombres**, vous pouvez visualiser les souches de numéros associées à l'entité juridique. Ce sera vide pour commencer.
1. Dans la section **Image de tableau de bord**, affichez ou modifiez les images de logo et de tableau de bord associées à l'entité juridique.
1. Dans la section **Immatriculation fiscale**, entrez les numéros d'enregistrement utilisés pour les déclarations aux administrations fiscales.
1. Dans la section **Taxe sur les honoraires**, entrez les informations de déclaration des honoraires associées à l'entité juridique.
1. Dans la section **Informations fiscales**, entrez les informations fiscales associées à l'entité juridique.
1. Sélectionnez **Enregistrer**.

L'image suivante présente les détails d'un exemple d'entité juridique.

![Section générale de l'entité juridique](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des organisations et des hiérarchies d'organisation](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planifier votre hiérarchie d'organisation](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Hiérarchies de l'organisation](channels-org-hierarchies.md)

[Présentation des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)
