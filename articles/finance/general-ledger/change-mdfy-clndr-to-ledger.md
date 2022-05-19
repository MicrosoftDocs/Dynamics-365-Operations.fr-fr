---
title: Modifier ou réaffecter un calendrier comptable
description: Cette rubrique explique comment modifier le calendrier actuellement affecté à une comptabilité et comment affecter un nouveau calendrier.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 25777a5b807921acc13338116627e9356fe62a20
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711629"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Modifier ou réaffecter un calendrier comptable

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment modifier le calendrier actuellement affecté à une comptabilité et comment affecter un nouveau calendrier.

## <a name="issue"></a>Problème

Les entreprises sont parfois amenées à modifier le calendrier affecté à une comptabilité ou à affecter un nouveau calendrier.

## <a name="resolution"></a>Résolution

Il existe deux scénarios pour modifier ou réaffecter un calendrier comptable. Le premier scénario consiste à modifier un calendrier existant déjà affecté à la comptabilité. Le deuxième scénario consiste à créer un nouveau calendrier et à l’affecter à la comptabilité. Les deux modifications peuvent être effectuées à tout moment, même après que les transactions ont été validées dans la comptabilité.

### <a name="change-an-existing-fiscal-calendar"></a>Modifier un calendrier fiscal existant

Pour modifier le calendrier affecté à votre comptabilité, accédez à **Comptabilité \> Configuration de la comptabilité \> Comptabilité**, puis sélectionnez le lien du calendrier fiscal pour ouvrir la page **Calendriers comptables**.

Les modifications que vous pouvez apporter au calendrier sont soumises à certaines conditions. Par exemple, vous pouvez modifier les dates de début et de fin des *périodes* dans une année, mais vous ne pouvez pas modifier les dates de début et de fin d’une *année* dans le calendrier.

Pour modifier les périodes dans une année, sélectionnez le calendrier et l’année appropriés. Tout d’abord, utilisez le bouton **Supprimer la période** pour supprimer tout ou partie des périodes de fonctionnement existantes. Toutes les périodes de fonctionnement sauf la première peuvent être supprimées. Ensuite, utilisez le bouton **Diviser la période** pour diviser la ou les périodes restantes en nouvelles périodes en saisissant une date de début appropriée pour la période suivante.

Après avoir modifié les périodes dans un calendrier, vous devez exécuter le processus **Recalculer les périodes comptables** dans chaque entité juridique (entreprise) à laquelle le calendrier est attribué. Bien qu’aucun message d’avertissement ne vous rappelle d’effectuer cette étape, le recalcul est nécessaire pour mettre à jour la période affectée à chaque transaction validée dans la comptabilité. Pour exécuter le recalcul, sélectionnez **Recalculer les périodes comptables** sur la page **Configuration de la comptabilité** dans chaque entreprise.

Si le recalcul n’est pas exécuté, les soldes de transaction sur une balance comptable ou sur les tableaux d’analyse risquent d’être incorrectement inclus dans les périodes. Dans ce cas, vous pouvez corriger les soldes à tout moment en exécutant le recalcul.

### <a name="assign-a-new-fiscal-calendar"></a>Attribuer un nouveau calendrier fiscal

Pour attribuer un nouveau calendrier fiscal, accédez à **Comptabilité \> Configuration de la comptabilité \> Comptabilité** et sélectionnez **Comptabilité** pour définir la page **comptabilité** en mode Édition. Puis, sélectionnez un nouveau calendrier fiscal dans le champ **Calendrier fiscal**.

Après avoir modifié le calendrier fiscal d’une comptabilité, vous devez **Recalculer les périodes comptables**. Lorsque vous affectez un nouveau calendrier fiscal à une comptabilité, un message vous rappelle d’effectuer cette étape. Le message peut sembler indiquer que le processus de recalcul est facultatif, mais ce n’est pas le cas. Il est nécessaire de mettre à jour la période affectée à chaque transaction validée en Comptabilité. Pour exécuter le processus de recalcul, sélectionnez **Recalculer les périodes comptables** sur la page **Configuration de la comptabilité**.

Si le recalcul n’est pas exécuté, les soldes de transaction sur une balance comptable ou sur les tableaux d’analyse risquent d’être incorrectement inclus dans les périodes. Dans ce cas, vous pouvez corriger les soldes à tout moment en exécutant le recalcul.
