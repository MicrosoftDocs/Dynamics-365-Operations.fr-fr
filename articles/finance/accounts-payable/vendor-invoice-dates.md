---
title: Dates de facture fournisseur
description: Cet article décrit les dates qui apparaissent sur les factures des fournisseurs. Il explique également comment ajuster automatiquement la date de validation.
author: sunfzam
ms.date: 2/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 022fd0ce07fbb4c54afcf7334c1c9411e01dcf26
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775266"
---
# <a name="vendor-invoice-dates"></a>Dates de facture fournisseur

[!include [banner](../includes/banner.md)]

Cet article décrit les dates qui apparaissent sur les factures des fournisseurs. Il explique également comment ajuster automatiquement la date de validation.

Sur la page **Facture fournisseur en attente détaillée**, l’en-tête de la facture affiche quatre dates : **Date de réception de la facture**, **Date de la facture**, **Date de validation** et **Date d’échéance**. Lors de la création d’une facture fournisseur, les dates suivantes sont saisies par défaut :

- **Date de réception de la facture** – Ce champ est défini sur la date système actuelle.
- **Date de validation** – Ce champ est défini sur la date système actuelle. 
- **Date d’échéance** – La date de ce champ est calculée en fonction de la date comptable et des conditions de paiement.
- **Date de la facture** – Par défaut, ce champ est vide. Cependant, vous pouvez entrer une valeur selon vos besoins. Dans ce cas, la date dans le champ **Date d’échéance** est recalculée en fonction de la date de facture et les conditions de paiement.

Parfois, une facture fournisseur peut être en attente pendant longtemps après la clôture de la période. Lorsqu’il est prêt pour la publication, l’ancienne date comptable de la période comptable précédente est toujours utilisée. Cependant, cette période est maintenant close. Par conséquent, un commis aux comptes fournisseurs (AP) doit modifier manuellement toutes les dates de comptabilisation à la nouvelle période de comptabilisation pour toutes les factures en attente qui ont été créées précédemment.

La fonctionnalité décrite dans cet article permet d’ajuster automatiquement la date de validation en fonction des besoins de l’entreprise.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Paramètre d’ajustement automatique de la date de comptabilisation de la facture fournisseur

Suivez ces étapes pour ajuster automatiquement la date de validation des factures fournisseur.

1.  Accédez à **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
2.  Dans l’onglet **Comptabilité et taxe**, dans le champ **Ajuster la date de publication automatiquement**, sélectionnez l’une des valeurs suivantes :

    - **Pas de changement** – Le système ne modifie pas automatiquement la date comptable lors de la comptabilisation. Cette valeur est sélectionnée par défaut.
    - **Toujours changer la date de validation par la date système** : la date de validation est automatiquement changée par la date système lors de la validation.
    - **Changer la date de validation par la date système lorsque la période de date de validation est clôturée ou en attente** : la date de validation est automatiquement changée par la date système lors de la validation, mais uniquement si la période correspondante de la date de validation a le statut **Clôturé** ou **En attente**.
    - **Changer la date de validation par le premier jour de la nouvelle période lorsque la période de validation est clôturée ou en attente** : la date de validation est changée par le premier jour de la nouvelle période ouverte, mais uniquement si la période correspondante de la date de validation a le statut **Clôturé** ou **En attente**.

> [!NOTE]
> Si la nouvelle date comptable qui a été ajustée automatiquement se situe dans un nouvel exercice comptable, la date comptable de la facture ne sera pas mise à jour. L’utilisateur recevra une erreur "L’année fiscale a changé. Veuillez vérifier et resentrer la date de publication. » La date de comptabilisation de la facture doit être mise à jour avec la nouvelle date de l’exercice comptable pour pouvoir la comptabiliser.

## <a name="impact-of-posting-date-changes"></a>Impact des changements de date comptable

Lorsque la date comptable sur une facture fournisseur en attente est modifiée, la modification a les effets suivants :

- **Date d’échéance**

    - Si le champ **Date de la facture** est vide, la date d’échéance est recalculée en fonction de la nouvelle date de validation et les conditions de paiement.
    - Si le champ **Date de la facture** a été défini précédemment, le changement de date comptable n’affecte pas la date d’échéance.

- **Date d’escompte de règlement**

    - Si le champ **Date de la facture** est vide, la nouvelle date comptable est utilisée pour calculer l’escompte.
    - Si le champ **Date de la facture** a été défini précédemment, l’escompte de règlement n’est pas modifié.

- **Taux de change** – La date du taux de change est déterminée par la fixation de l’option **Mettre à jour la comptabilité fournisseur à l’aide de la date de la facture** dans l’onglet **Facture** de la page **Paramètres des comptes fournisseurs** (**Comptabilité fournisseur \> Paramétrage \> Paramètres de la comptabilité fournisseur**).

    - Si cette option est définie sur **Oui**, la **date de la facture** est utilisée et le changement de **date de validation** n’affecte pas le taux de change.
    - Si cette option est définie sur **Non**, la date comptable est utilisée pour calculer le taux de change. Lorsque la date comptable est mise à jour, les montants comptables et de reporting sont recalculés. Par conséquent, la validation de l’appariement doit être refaite.

## <a name="validation"></a>Validation

Deux autres champs sur l’onglet **Facture d’achat** de la page **Paramètres des comptes fournisseurs** (**Compte à payer \> Paramétrage \> Paramètres du compte à payer**) affectent le traitement des factures :

- Si le champ **Vérifier le numéro de facture utilisé** est défini sur **Rejeter les doublons au cours de l’exercice**, la date de validation est utilisée pour vérifier les factures en double lors de la comptabilisation des factures.
- Si le champ **Exiger la date du document sur la facture du fournisseur** est défini sur **Option d’erreur**, le champ **Date de la facture sur l’en-tête de la facture en attente** requis. Si la date de la facture est postérieure à la date de validation, un message d’erreur s’affiche.
