---
title: Dépenses intersociétés
description: Un travailleur qui est employé par une seule entité juridique au sein d'une organisation peut travailler pour une autre entité juridique au sein de la même organisation. Dans ce cas, vous pouvez utiliser la fonctionnalité de dépense intersociétés pour affecter les dépenses du travailleur à l'entité juridique pour laquelle le travail a été effectué.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390882"
---
# <a name="intercompany-expenses"></a>Dépenses intersociétés

[!include [banner](../includes/banner.md)]

Un travailleur qui est employé par une seule entité juridique au sein d'une organisation peut travailler pour une autre entité juridique au sein de la même organisation. Dans ce cas, vous pouvez utiliser la fonctionnalité de dépense intersociétés pour affecter les dépenses du travailleur à l'entité juridique pour laquelle le travail a été effectué. L'entité juridique qui emploie le travailleur est l'entité juridique prêteuse. L'entité juridique pour laquelle le travailleur engage les dépenses est appelée entité juridique emprunteuse. 

Avant qu'un collaborateur puisse créer et soumettre des dépenses pour le travail réalisé par une autre entité juridique, dans l'entité juridique prêteuse, sur la page **Paramètres de gestion des dépenses**, sélectionnez l'option **Autoriser les lignes de dépense intersociétés**. 

## <a name="tax-posting-for-intercompany-expenses"></a>Enregistrement fiscal pour les dépenses intersociétés

[!include [banner](../includes/banner.md)]

Pour utiliser des groupes de taxes associés à l'entité juridique prêteuse (source) au lieu de l'entité juridique emprunteuse (destination) dans votre état de dépenses, vous devrez configurer cela dans la configuration de la taxe de vente de la comptabilité. Lorsque le paramètre de comptabilité **Entité juridique pour la validation intersociétés de taxe** est défini sur **Source** et que **Appliquer les règles de taxe** est défini sur **Non**, la combinaison fiscale pour l'entité juridique prêteuse sera utilisée. Lorsque le même paramètre est défini sur **Destination**, la combinaison fiscale pour l'entité juridique emprunteuse sera utilisée. Pour les entités juridiques aux États-Unis, lorsque le paramètre est défini sur **Source**, le champ **Taxe déductible** doit également être configuré sur la nouvelle page **Groupes de validation dans la comptabilité**. Le moteur comptable utilisera les informations de ce champ pour la saisie comptable liée à la taxe.   
Le comportement est cohérent pour les lignes de dépenses validées avec ou sans projet.  
