---
title: Paramétrage des administrations fiscales
description: Les administrations fiscales sont des entités auprès desquelles les taxes doivent être déclarées et payées.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb0b30be91e33cb50af0ae5c2e4dcd75bd12599b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175419"
---
# <a name="set-up-sales-tax-authorities"></a>Paramétrage des administrations fiscales

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les administrations fiscales sont des entités auprès desquelles les taxes doivent être déclarées et payées. Vous pouvez payer des taxes à l'administration directement ou via un compte fournisseur que vous créez pour l'administration fiscale. Dans ce cas, la société peut utiliser ses routines de paiement habituelles pour payer l'administration fiscale à temps. Si vous ne paramétrez pas l'administration fiscale comme fournisseur, un paiement manuel doit être préparé, à remettre à l'administration fiscale à la date d'échéance appropriée. La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Taxe > Taxes indirectes > Taxes > Administrations fiscales.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Administration.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Sélectionnez la présentation d'état pour votre pays/région, si elle est disponible. Si les états de valeur ne correspondent pas aux exigences de l'administration fiscale, utilisez la structure par défaut.
9. Entrez des valeurs dans les champs Type d'arrondi et Arrondi pour spécifier la manière dont le montant total de la taxe à payer doit être arrondi. Les différences d'arrondi seront validées sur les comptes pour les transactions automatiques paramétrées dans Comptabilité.
10. Entrez un nombre dans le champ Arrondi.
11. Cliquez sur Enregistrer.

