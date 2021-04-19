---
title: Réutiliser des configurations de produit
description: Vous pouvez spécifier que vous souhaitez réutiliser automatiquement une configuration existante pour un produit. Ensuite, lorsqu’un utilisateur a terminé une session de configuration, le système vérifie si une configuration qui correspond aux sélections effectuée par l’utilisateur existe déjà. Si une configuration correspondante est trouvée, l’ID configuration, la nomenclature correspondante et la gamme sont réutilisés.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a3aca07388a440ce5168fa4106d90d931f7f194
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812785"
---
# <a name="reuse-product-configurations"></a>Réutiliser des configurations de produit

[!include [banner](../includes/banner.md)]

Vous pouvez spécifier que vous souhaitez réutiliser automatiquement une configuration existante pour un produit. Ensuite, lorsqu’un utilisateur a terminé une session de configuration, le système vérifie si une configuration qui correspond aux sélections effectuée par l’utilisateur existe déjà. Si une configuration correspondante est trouvée, l’ID configuration, la nomenclature correspondante et la gamme sont réutilisés.

<a name="requirements-for-reusing-configurations"></a>Critères de réutilisation des configurations
---------------------------------------

Pour activer les configurations à réutiliser, vous devez spécifier les informations suivantes pour les composants et les attributs sur la page **Détails de modélisation de configuration de produit** :

-   **Composants et sous-composants** – Dans l’organisateur **Général**, dans le champ **Réutiliser les configurations**, sélectionnez **Oui**.
-   **Attributs** – Sous l’organisateur **Attributs**, sélectionnez l’option **Inclure dans la réutilisation**. L’option ne s’affiche que si la réutilisation du composant associé est activée. Si vous ne sélectionnez aucun attribut pour la réutilisation, la configuration est toujours réutilisée, quelles que soient les sélections effectuées par l’utilisateur au cours d’une session de configuration. Les valeurs d’attributs de la configuration existante doivent correspondre aux sélections effectuées par l’utilisateur. Par exemple, si l’utilisateur sélectionne la couleur **Bleu** comme couleur lors d’une session de configuration, le système vérifie si une configuration existante du composant a la couleur Bleu.

## <a name="resetting-configuration-reuse"></a>Réinitialisation de la réutilisation de configuration
Lorsque vous réinitialisez la réutilisation de configuration, les configurations précédemment créées ne sont plus prises en compte. Vous pouvez réinitialiser la réutilisation de configuration si la nomenclature ou la gamme a été modifiée, mais aucun attribut associé n’a été modifié. Vous réinitialisez la réutilisation de configuration sur l’organisateur **Général** du composant.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]