---
title: Demandes de renseignements et déclarations de matières dangereuses
description: Cet article explique comment utiliser les différents états relatifs aux matières dangereuses. Bon nombre de ces états sont nécessaires pour que vous restiez en conformité avec diverses réglementations sur les matières dangereuses pendant le transport et le stockage.
author: t-benebo
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 782b1b4995af09a63c483d2b81ed255a5c11803a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846038"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Demandes de renseignements et déclarations de matières dangereuses

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management fournit divers états relatifs aux matières dangereuses. Bon nombre de ces états sont nécessaires pour que vous restiez en conformité avec diverses réglementations sur les matières dangereuses pendant le transport et le stockage.

Tous ces états, sauf **Marchandises dangereuses multimodales**, utilisent le mode de livraison défini pour l’expédition afin de trouver la réglementation à utiliser pour imprimer le texte d’expédition des articles. Le mode de livraison est associé au transporteur associé et au service de transporteur. Par conséquent, vous devez configurer un transporteur et un service de transporteur, et les lier à un mode de livraison. Le mode de livraison est lié à la réglementation sur les matières dangereuses.

L’illustration suivante montre la séquence des activités qui se produisent lorsque le système génère des états sur les matières dangereuses.

![Séquence des activités pour les états sur les matières dangereuses.](media/hazmat-report-sequence.png "Séquence des activités pour les états sur les matières dangereuses")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Paramétrer les états sur les matières dangereuses

Habituellement, si vous expédiez des articles contenant des matières dangereuses, vous devez générer des déclarations spécifiques permettant de préserver la sécurité et vous conformer aux réglementations sur les matières dangereuses. Pour paramétrer vos déclarations, procédez comme suit.

1. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**.
2. Ouvrez l’onglet **États**. Sur le raccourci **Paramètre de déclaration sur les matières dangereuses**, définissez les champs suivants.

    | Section | Champ | Description |
    |---|---|---|
    | Marchandises dangereuses multimodales | Code de réglementation | Sélectionnez la réglementation à utiliser lorsqu’un déclaration **Marchandises dangereuses multimodales** est générée. |
    | Limites des stocks de matières dangereuses | Code de réglementation | Sélectionnez la réglementation à utiliser lors de l’évaluation des limites de stock. |
    | Transport de marchandises par route | Produit du groupe CMT | CMT signifie « substances cancérigènes, mutagènes ou toxiques ». Définissez cette option sur **Oui** pour configurer le système afin d’imprimer des avertissements et des messages spécifiques liés à la manipulation de ces substances. |
    | Transport de marchandises par route | Description du groupe de matières dangereuses | Saisissez le texte des avertissements spécifiques liés aux CMT et au transport de marchandises par route. Ce texte sera inclus dans la déclaration. |
    | Déclaration des expéditeurs | Avertissement | Saisissez le texte d’un message d’avertissement qui doit être imprimé sur le formulaire de déclaration de l’expéditeur (par exemple, « Avertissement : marchandises dangereuses, produits inflammables »). |
    | Déclaration des expéditeurs | Déclaration en pied de page | Saisissez le texte d’un message qui doit être imprimé au bas du document de déclaration d’expédition. |
    | Langue de l’état des marchandises dangereuses | Langue de l’état domestique des marchandises dangereuses | Sélectionnez la langue par défaut pour les déclarations sur les matières dangereuses associées aux expéditions nationales. |
    | Langue de l’état des marchandises dangereuses | Langue de l’état d’exportation des marchandises dangereuses | Sélectionnez la langue par défaut pour les déclarations sur les matières dangereuses associées aux expéditions internationales. |

## <a name="hazardous-materials-report"></a>Déclaration sur les matières dangereuses

La déclaration **Matières dangereuses** affiche une liste de tous les articles configurés et définis de manière à contenir des informations sur les marchandises dangereuses. Vous pouvez utiliser cette déclaration pour surveiller et examiner les informations que vous devez conserver. La page de la déclaration affiche une sélection limitée de champs issus de la configuration des matières dangereuses. Cependant, vous pouvez la personnaliser pour ajouter des champs supplémentaires selon vos besoins.

Pour afficher cette déclaration, accédez à **Gestion des informations sur les produits \> Demandes de renseignements et déclarations \> Documentation d’expédition de matières dangereuses \> Matières dangereuses**.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>État sur la limites des stocks de matières dangereuses

La déclaration **Limite de stock de matières dangereuses** vous permet de surveiller les niveaux de stock des matières dangereuses dans vos entrepôts, pour vous assurer qu’ils restent sous les limites de sécurité établies. Ces limites proviennent des limites définies pour chaque produit lancé.

Pour afficher cette déclaration, accédez à **Gestion des informations sur les produits \> Demandes de renseignements et déclarations \> Documentation d’expédition de matières dangereuses \> Limites des stocks de matières dangereuses**.

Pour plus d’informations sur la définition des limites de stock sur un produit lancé, voir [Fixer des limites de stocks pour les produits dangereux](hazmat-items.md#stock-limits).

La réglementation utilisée pour les limites de stocks est définie sur la page **Paramètres de gestion des entrepôts**. Accédez à **Gestion des entrepôts \> Configuration \> Paramètres de gestion des entrepôts**, puis, sur l’onglet **États**, dans **Limite de stocks de matières dangereuses**, spécifiez un code de réglementation. Pour plus d’informations, voir [Paramétrer les états sur les matières dangereuses](#set-up) précédemment dans cet article.

## <a name="verified-gross-mass-report"></a>État sur la masse brute vérifiée

L’état **Masse brute vérifiée** vous permet d’imprimer des informations sur le poids d’une expédition.

Pour générer et imprimer cet état, accédez à **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**, et ouvrez l’expédition concernée. Ensuite, dans le volet Actions, sur l’onglet **Expéditions**, dans le groupe **Document sur les matières dangereuses**, sélectionnez **Masse brute vérifiée**.

## <a name="multimodal-dangerous-goods-report"></a>États sur les marchandises dangereuses multimodales

L’état **Marchandises dangereuses multimodales** est fourni pour les expéditions qui doivent être déplacées en utilisant une combinaison de modes de transport. Il est généralement utilisé lorsqu’une expédition est d’abord effectuée par la route, puis par voie maritime.

Pour générer et imprimer cet état, accédez à **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**, et ouvrez l’expédition concernée. Ensuite, dans le volet Actions, sur l’onglet **Expéditions**, dans le groupe **Document sur les matières dangereuses**, sélectionnez **Marchandises dangereuses multimodales**.

Lorsque vous générez cet état, les informations sont enregistrées afin que vous puissiez le modifier et/ou réimprimer l’état si nécessaire. Pour modifier un état généré, accédez à **Gestion des entrepôts \> Demandes de renseignements et déclarations \> Documentation d’expédition de matières dangereuses \> Marchandises dangereuses multimodales**, et recherchez l’état pertinent dans la liste. Une fois que vous avez terminé de modifier le contenu selon vos besoins, sélectionnez **Imprimer** dans le volet Actions pour imprimer l’état.

## <a name="shippers-declaration-report"></a>État sur la déclaration des expéditeurs

L’état **Déclaration sur les expéditeurs** vous permet d’imprimer des informations liées à une déclaration des matières incluses dans l’expédition.

Pour générer et imprimer cet état, accédez à **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**, et ouvrez l’expédition concernée. Ensuite, dans le volet Actions, sur l’onglet **Expéditions**, dans le groupe **Document sur les matières dangereuses**, sélectionnez **Déclaration sur les expéditeurs**.

## <a name="carriage-of-merchandise-by-road-report"></a>État sur les transport de marchandises par route

L’état **Transport de marchandises par route** ressemble à un connaissement, mais il est généralement utilisé pour le transport routier en Europe en vertu de l’Accord relatif au transport international des marchandises dangereuses par route (ADR). Ce rapport utilise le texte d’impression d’expédition pour un article, sauf si vous définissez le champ **Description du groupe de matières dangereuses** sur la page **Paramètres de gestion des entrepôts**.

Pour générer et imprimer cet état, accédez à **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**, et ouvrez l’expédition concernée. Ensuite, dans le volet Actions, sur l’onglet **Expéditions**, dans le groupe **Document sur les matières dangereuses**, sélectionnez **Transport de marchandises par route**.

Lorsque vous générez cet état, les informations sont enregistrées afin que vous puissiez le modifier et/ou réimprimer l’état si nécessaire. Pour modifier un état généré, accédez à **Gestion des entrepôts \> Demandes de renseignements et déclarations \> Documentation d’expédition de matières dangereuses \> Transport de marchandises par route**, et recherchez l’état pertinent dans la liste. Une fois que vous avez terminé de modifier le contenu selon vos besoins, sélectionnez **Imprimer** dans le volet Actions pour imprimer l’état.

## <a name="shipment-summary-report"></a>État du résumé des expéditions

L’état **Récapitulatif de l’expédition** fournit des informations résumées par la catégorie de transport liée aux articles lancés.

Pour générer et imprimer cet état, accédez à **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**, et ouvrez l’expédition concernée. Ensuite, dans le volet Actions, sur l’onglet **Expéditions**, dans le groupe **Document sur les matières dangereuses**, sélectionnez **Récapitulatif de l’expédition**.

## <a name="bill-of-lading-report"></a>état de feuille de chargement

Lorsque la fonctionnalité sur les matières dangereuses est activée dans votre système, la déclaration **feuille de chargement** comprend une colonne **Matières dangereuses** indiquant si une charge contient des matières dangereuses. Cet état est disponible sur la page **Toutes les charges**, comme d’habitude.

## <a name="packing-list-report"></a>État sur la liste d’emballage

Lorsque la fonctionnalité de matières dangereuses est activée sur votre système, les listes d’emballage incluent des informations supplémentaires liées au texte d’impression d’expédition d’un article. Cet état est disponible sur la page **Toutes les charges**, comme d’habitude.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]