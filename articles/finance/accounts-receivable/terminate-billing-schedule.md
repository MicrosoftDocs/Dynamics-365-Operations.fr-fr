---
title: Résilier des calendriers de facturation
description: Cette rubrique explique comment résilier les calendriers de facturation et les lignes de calendrier de facturation dans la facturation d’abonnement.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: df81cc888e893c6a4a127e1a43426a0a0b56f0d1
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8470453"
---
# <a name="terminate-billing-schedules"></a>Résilier des calendriers de facturation

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment résilier les calendriers de facturation et les lignes de calendrier de facturation dans la facturation d’abonnement. Lorsque vous résiliez un calendrier de facturation, celui-ci doit avoir le statut **Actif**. Il ne peut pas avoir un statut **En attente**. De même, lorsque vous résiliez une ligne calendrier de facturation, elle doit avoir le statut **Actif**. La section d’en-tête de l’échéancier de facturation n’est pas affectée lorsque vous résiliez une ligne d’échéancier de facturation.

Pour résilier un échéancier de facturation ou une ligne d’échéancier de facturation, accédez à l’un des emplacements suivants :

- La page de liste **Tous/Calendriers de facturation actifs**
- Un calendrier de facturation spécifique sur la page **Tous les calendriers de facturation**
- Une ligne de calendrier de facturation spécifique sur la page **Tous les calendriers de facturation**

> [!NOTE]
> Si vous souhaitez résilier plusieurs calendriers de facturation en même temps, utilisez la page **Traitement des résiliations en masse**.

## <a name="terminate-a-billing-schedule-or-line"></a>Résilier un calendrier de facturation ou une ligne

Pour résilier un échéancier de facturation ou une ligne d’échéancier de facturation, procédez comme suit.

1. Sélectionnez un calendrier de facturation ou une ligne de calendrier de facturation, puis sélectionnez **Résilier**. 
2. Définissez les champs **Date de résiliation**, **Type de résiliation** et **Code motif**.
3. Définissez le champ **Option d’avoir** sur **Émettre un avoir**.
4. Sélectionnez **Résilier**.

Le statut du calendrier de facturation change en fonction du type de résiliation que vous avez sélectionné. Si vous avez sélectionné **Facture restante** comme type de résiliation, le statut de toutes les lignes du calendrier de facturation est **Dernière facturation**. Le statut du calendrier de facturation reste **Actif** jusqu’au traitement de la dernière facture. Une fois la dernière facture traitée, le statut est mis à jour en **Résilié**. Si vous avez sélectionné **Ajuster le calendrier** comme type de résiliation, le statut du calendrier de facturation est immédiatement mis à jour en **Résilié**.

## <a name="terminate-a-billing-schedule-or-line-and-apply-a-refund"></a>Résilier un calendrier de facturation ou une ligne et appliquer un remboursement

Pour résilier un échéancier de facturation ou une ligne d’échéancier de facturation et appliquer un remboursement, procédez comme suit.

1. Sélectionnez un calendrier de facturation ou une ligne de calendrier de facturation, puis sélectionnez **Résilier**.
2. Définissez les champs **Date de résiliation**, **Type de résiliation**, **Code motif** et **Option d’avoir**.
3. Sélectionnez **Résilier avec remboursement**. La page **Traitement des résiliations en masse** apparaît et est filtrée afin d’afficher le calendrier de facturation.
4. Sélectionnez **Voir l’aperçu** pour afficher les lignes des échéanciers de facturation, puis sélectionnez **Traiter**.

Une fois l’avoir traité, ouvrez la page **Afficher les détails de facturation** pour vérifier l’avoir qui a été appliqué au calendrier de facturation. Si le montant de l’avoir est supérieur à 0 (zéro), toutes les futures lignes non facturées sont supprimées et remplacées par des lignes de détail de facturation qui affichent les montants négatifs de l’avoir appliqué au calendrier de facturation.

### <a name="view-example"></a>Afficher un exemple

Un calendrier de facturation comporte les informations suivantes :

- La date de début est le 1er janvier 2020.
- La date de fin est le 31 décembre 2020.
- Le montant de la période de facturation est de 100,00 par mois.
- Les factures ont été créées pour les périodes de facturation de janvier à juillet.
- La date de fin de contrat est le 15 juin 2020.

Lorsque l’ajustement du crédit est traité, toutes les périodes de facturation futures (d’août à décembre) sont supprimées de la page **Afficher les détails de facturation**. Une ligne d’ajustement de crédit est ajoutée après la période de facturation de juillet :

- Du 16 juin au 31 juillet, avec un montant de crédit de 150,00

Si la fonction de revenus non facturés est utilisée, la page **Audit des écritures au journal des revenus non facturés** est mise à jour avec l’entrée de résiliation.

## <a name="terminate-a-billing-schedule-or-line-without-applying-a-credit"></a>Résilier un calendrier de facturation ou une ligne et sans appliquer de crédit

Pour résilier un échéancier de facturation ou une ligne d’échéancier de facturation sans appliquer de crédit, procédez comme suit.

1. Sélectionnez un calendrier de facturation ou une ligne de calendrier de facturation, puis sélectionnez **Résilier**.
2. Définissez le champ **Date de résiliation**.
3. Définissez le champ **Type de résiliation** sur **Aucun ajustement**. Le champ **Option d’avoir** est automatiquement défini sur **Aucun crédit**.
3. Définissez le champ **Code motif**.
4. Dans le champ **Notes sur la résiliation**, entrez des notes supplémentaires requises.
5. Sélectionnez **Résilier**. 

Lorsque la résiliation est traitée, toutes les lignes de détails de facturation après la date de résiliation sont supprimées. (Ces lignes incluent la ligne qui contient la date de résiliation.) Les factures ne peuvent pas être créées pour les lignes résiliées. Si la résiliation est supprimée, toutes les lignes terminées sont rajoutées à la page **Afficher les détails de facturation** et deviennent disponibles pour la facturation.

## <a name="fields"></a>Champs

La page **Afficher les détails de facturation** contient les champs suivants.

| Champ | Description |
|-------|-------------| 
| Date de fin de contrat | Sélectionnez la date à laquelle vous souhaitez résilier un calendrier de facturation ou une ligne de calendrier de facturation. |
| Type de résiliation | <p>Sélectionnez le type de résiliation :</p><ul><li>**Ajuster le calendrier** : tronque les périodes de facturation de la ligne à la date de résiliation et change le statut de la ligne en **Dernière facturation**. Si un échéancier de report existe pour l’article de la ligne, il est ajusté en annulant le montant qui ne doit plus être reconnu. Si la date de début de facturation est postérieure à la date de fin, les périodes de facturation restantes sont supprimées.</li><li>**Facture restante** – Ajoute tout montant restant pour la période de facturation à la période de résiliation et change le statut de la ligne en **Dernière facturation**. Si un échéancier de report existe pour l’article de la ligne, la date de fin du report est mise à jour. Si la date de début de facturation est postérieure à la date de fin, le montant total de toutes les périodes de facturation restantes est ajouté à la période de facturation et les périodes de facturation restantes sont supprimées.</li><li>**Aucun ajustement** – Résilie les périodes de facturation de la ligne à la date de résiliation spécifiée. Aucun ajustement n’est effectué. Lorsque ce type de terminaison est sélectionné, le champ **Option d’avoir** est défini sur **Aucun avoir**, et le champ **Prorata quotidien** est défini sur **Non**. Ces deux champs deviennent alors en lecture seule et ne peuvent pas être modifiés.</li></ul> |
| Option de crédit | <p>Sélectionnez la façon dont le crédit est appliqué lorsque vous résiliez une ligne d’échéancier de facturation :</p><ul><li>**Ajustement de crédit** – Crée un ajustement de crédit pour un calendrier de facturation lorsqu’une ligne est résiliée. L’ajustement de crédit apparaît dans une période de facturation future pour le calendrier de facturation. L’ajustement ajuste également automatiquement le montant de la facture pour la période de facturation suivante jusqu’à ce que le crédit ait fini d’être appliqué au calendrier de facturation.</li><li>**Émettre un avoir** – Crée un avoir quand un calendrier de facturation ou une ligne de calendrier de facturation est résiliée.</li><li>**Aucun avoir** – Ne crée pas un ajustement de crédit ni un avoir quand un calendrier de facturation ou une ligne de calendrier de facturation est résiliée. Cette option est disponible uniquement lorsque vous utilisez une résiliation du type **Aucun ajustement** pour résilier un calendrier de facturation.</li></ul><p>L’option par défaut provient de la page **Paramètres de facturation des contrats récurrents**.</p> |
| Code motif | Sélectionnez le code motif de la résiliation. |
| Description du motif | Description du code motif. |
| Notes sur la résiliation | Permet d’entrer des notes sur la résiliation. |

<!--## Additional information-->
