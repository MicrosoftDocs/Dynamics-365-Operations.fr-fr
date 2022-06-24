---
title: Déplacer les fichiers XML NF-e en pièces jointes
description: Cet article explique comment déplacer des fichiers XML NF-e hors de votre base de données Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management et les rendre disponibles en tant que pièces jointes à la place.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ce9061896759efeb8e8960e84656d5fc1f0616ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877895"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>Déplacer les fichiers XML NF-e en pièces jointes

[!include [banner](../includes/banner.md)] 


Lors de l’émission de documents fiscaux électroniques (NF-e), des fichiers XML sont créés et stockés dans les bases de données Microsoft Dynamics 365 finance et Dynamics 365 Supply Chain Management. Dans la localisation brésilienne, vous pouvez utiliser la fonctionnalité **Déplacement XML NF-e en pièce jointe** pour libérer l’espace de base de données que ces fichiers XML consomment.

Pour une plage de dates et un établissement fiscal spécifiques, la fonctionnalité déplace les fichiers XML NF-e de votre base de données Finance ou Supply Chain Management vers le stockage Blob de votre abonnement Azure. Ce mouvement rend les fichiers disponibles uniquement en tant que pièces jointes. Une fois les fichiers XML déplacés avec succès vers le stockage Blob, les fichiers d’origine sont supprimés de la base de données Finance ou Supply Chain Management. Par conséquent, l’espace de base de données utilisé par ces fichiers est libéré.

Pour activer la fonctionnalité **Déplacement XML NF-e en pièce jointe**, procédez comme suit.

1. Dans Finance ou Supply Chain Management, ouvrez l’espace de travail **Gestion des fonctionnalités**.
2. Sur l’onglet **Tous**, recherchez et sélectionnez la fonctionnalité **Déplacement XML NF-e en pièce jointe**.
3. Sélectionnez **Activer maintenant**.

Suivez ces étapes pour déplacer les fichiers XML NF-e en tant que pièces jointes.

1. Aller à **Comptabilité client** \> **Documents fiscaux** \> **Documents fiscaux électroniques** \> **Déplacer NF-e XML en tant que pièces jointes**.
2. Dans les champs **Date de début** et **Date de fin**, entrez les dates de début et de fin.
3. Dans le champ **ID établissement fiscal**, sélectionnez une valeur.
4. Cliquez sur **OK**.

> [!IMPORTANT]
> Ce processus n’est pas réversible. Après avoir déplacé les fichiers XML NF-e, les utilisateurs ne peuvent les afficher qu’en sélectionnant **Pièces jointes** en haut de la page **Document fiscal**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
