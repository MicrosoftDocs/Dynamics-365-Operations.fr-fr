---
title: "Réutiliser des configurations de produit"
description: "Vous pouvez spécifier que vous souhaitez réutiliser automatiquement une configuration existante pour un produit. Ensuite, lorsqu'un utilisateur a terminé une session de configuration, le système vérifie si une configuration qui correspond aux sélections effectuée par l'utilisateur existe déjà. Si une configuration correspondante est trouvée, l'ID configuration, la nomenclature correspondante et la gamme sont réutilisés."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a06b821bd8e23abb8af5e7e7ef93acc85e87386a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="reuse-product-configurations"></a>Réutiliser des configurations de produit

[!include[banner](../includes/banner.md)]


Vous pouvez spécifier que vous souhaitez réutiliser automatiquement une configuration existante pour un produit. Ensuite, lorsqu'un utilisateur a terminé une session de configuration, le système vérifie si une configuration qui correspond aux sélections effectuée par l'utilisateur existe déjà. Si une configuration correspondante est trouvée, l'ID configuration, la nomenclature correspondante et la gamme sont réutilisés.

<a name="requirements-for-reusing-configurations"></a>Critères de réutilisation des configurations
---------------------------------------

Pour activer les configurations à réutiliser, vous devez spécifier les informations suivantes pour les composants et les attributs sur la page **Détails de modélisation de configuration de produit** :

-   **Composants et sous-composants** – Dans l'organisateur **Général**, dans le champ **Réutiliser les configurations**, sélectionnez **Oui**.
-   **Attributs** – Sous l'organisateur **Attributs**, sélectionnez l'option **Inclure dans la réutilisation**. L'option ne s'affiche que si la réutilisation du composant associé est activée. Si vous ne sélectionnez aucun attribut pour la réutilisation, la configuration est toujours réutilisée, quelles que soient les sélections effectuées par l'utilisateur au cours d'une session de configuration. Les valeurs d'attributs de la configuration existante doivent correspondre aux sélections effectuées par l'utilisateur. Par exemple, si l'utilisateur sélectionne la couleur **Bleu** comme couleur lors d'une session de configuration, le système vérifie si une configuration existante du composant a la couleur Bleu.

## <a name="resetting-configuration-reuse"></a>Réinitialisation de la réutilisation de configuration
Lorsque vous réinitialisez la réutilisation de configuration, les configurations précédemment créées ne sont plus prises en compte. Vous pouvez réinitialiser la réutilisation de configuration si la nomenclature ou la gamme a été modifiée, mais aucun attribut associé n'a été modifié. Vous réinitialisez la réutilisation de configuration sur l'organisateur **Général** du composant.




