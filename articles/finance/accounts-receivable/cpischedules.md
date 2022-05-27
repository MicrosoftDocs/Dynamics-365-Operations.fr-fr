---
title: Programmes d’indice des prix à la consommation
description: Cette rubrique explique comment créer la liste des barèmes de l'indice des prix à la consommation (IPC) que vous obtenez sur Internet pour vous aider à déterminer les frais d'escalade dans la facturation des abonnements.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 54114fae25565ed1aae7056ef9be5a4a159291e9
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686517"
---
# <a name="consumer-price-index-schedule"></a>Programmes d’indice des prix à la consommation

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer, supprimer, réviser et traiter les barèmes de l'indice des prix à la consommation (IPC). Un barème IPC peut être utilisé pour déterminer les prix des biens et services de consommation que vous ajoutez en tant que lignes d'échéancier de facturation. Le barème IPC peut ensuite être utilisé avec une tarification progressive et avec remise sur un échéancier de facturation, ou il peut être traité manuellement pour mettre à jour les montants de facturation sur les échéanciers de facturation. Vous pouvez saisir manuellement des barèmes IPC ou vous pouvez les importer à l'aide de l'entité composite de barème IPC.

Pour ajouter un barème IPC, procédez comme suit.

1. Dans la page **Barème de l'indice des prix à la consommation**, sélectionnez **Nouveau**.
2. Dans le champ **Barème de l'indice des prix à la consommation**, entrez un nom unique.
3. Entrez une description dans le champ **Description**.
4. Dans l'onglet **Barème de l'indice des prix à la consommation**, sélectionnez **Ajouter**.
5. Dans le champ **Date de l'indice des prix à la consommation**, spécifiez la date à laquelle le nouveau barème IPC devient actif.
6. Dans le champ **Barème de l'indice des prix à la consommation**, entrez le nom que vous avez entré à l'étape 2.
7. Cliquez sur **Enregistrer**.

Pour supprimer une date de barème IPC, procédez comme suit.

1. Sur la page **Barème de l'indice des prix à la consommation**, sélectionnez une ou plusieurs lignes que vous souhaitez supprimer, puis sélectionnez **Retirer**.
2. Pour supprimer l'ensemble du barème IPC, dans le volet Actions, sélectionnez **Supprimer**. Vous ne pouvez pas supprimer le barème IPC sélectionné s'il est associé à un calendrier de facturation.
3. Dans le volet Actions, sélectionnez **Traiter** pour mettre à jour les échéanciers de facturation qui utilisent le barème IPC sélectionné. Les dernières dates de l'IPC et les montants de l'échéancier seront utilisés pour mettre à jour les prix de l'échéancier de facturation.
4. Dans l'organisateur **Traitement de l'indice des prix à la consommation**, passez en revue les champs **Numéro de l'échéancier de facturation**, **Numéro d'article**, **Date de début de facturation**, **Date de fin de facturation**, **Date d'escalade** et **Fréquence d'escalade** mis à jour.

Une fois les barèmes IPC configurés, ils peuvent être utilisés pour les modifications d'escalade de prix et de remise dans les échéanciers de facturation.

## <a name="cpi-calculation"></a>Calcul de l'IPC

Pour ces exemples, la période va du 1er janvier 2020 au 31 décembre 2022. Le taux de base de l'IPC (la valeur de l'IPC au début du contrat) est de 105,65. Au 1er janvier 2021, l'IPC actuel est de 110,5. Au 1er janvier 2022, l'IPC actuel est de 114,25. Le montant initial est de 1000 USD.

**Exemple 1 :**

Sur la page **Paramètres de facturation des contrats récurrents**, vous définissez le champ **Calcul de l'indice des prix à la consommation** sur **Indice des prix à la consommation de base**.

Pour la période du 1er janvier 2021, le premier montant d'escalade est calculé de la manière suivante, sur la base du montant initial :

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

Pour la période du 1er janvier 2022, le montant d'escalade est calculé de la manière suivante :

1 000 + (114,25 – 105,65) &divide; 105,65 &times; 1 000 = 1 081,40

**Exemple 2 :**

Sur la page **Paramètres de facturation des contrats récurrents**, vous définissez le champ **Calcul de l'indice des prix à la consommation** sur **Indice des prix à la consommation antérieur**.

Pour la période du 1er janvier 2021, le premier montant d'escalade est calculé de la manière suivante, sur la base du montant initial :

1 000 + (110,5 – 105,65) &divide; 105,65 &times; 1 000 = 1 045,91

Pour la période du 1er janvier 2022, le montant d'escalade est calculé de la manière suivante, sur la base du premier montant d'escalade :

1 045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1 045,91 = 1 081,40

> [!NOTE]
> Le processus d'escalade utilise toujours la dernière valeur de l'IPC, quelle que soit la date de l'indice. Par exemple, si l'escalade est en septembre, mais que la dernière valeur de l'IPC est pour juillet, l'indice de juillet est utilisé. Aucun ajustement n'est effectué après la saisie de l'indice de septembre.

## <a name="prorated-escalation"></a>Escalade au prorata

Si l'escalade se produit au milieu d'une période de facturation, le montant est calculé au prorata. Par exemple, la période de facturation va du 1er août 2020 au 31 juillet 2021. À la date de l'IPC du 1er septembre 2019, la valeur de l'IPC est de 244. À la date de l'IPC du 1er septembre 2020, la valeur de l'IPC est de 250. Si le taux précédent est de 1 000, les formules suivantes sont utilisées pour calculer le montant de la facturation pour la période :

* *Modifications IPC* = (250 – 244) &divide; 244 = 2,459 %
* *Taux actuel* = 1 000 &times; 2,459 % = 1 024,59
* *Nombre de jours au tarif en vigueur* = 31 juillet 2021 – 1er septembre 2020 = 334
* *Taux précédent* = 1 000
* *Nombre de jours au taux précédent* = 31 août 2020 – 1er août 2020 = 31
* *Nombre total de jours de la période de facturation* = 31 juillet 2021 – 1 août 2020 + 1 = 365
* *Montant facturé pour cette période* = (1 000 &times; 31 &divide; 365) + (1 024,59 &times; 334 &divide; 365) = 1 022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Escalade qui utilise l'IPC et le pourcentage

Les escalades peuvent être effectuées à l'aide de l'IPC. L'IPC plus une augmentation de 3 % commence le 1er janvier 2020 et a une fréquence annuelle.

- Le montant facturé du 1er janvier 2019 au 31 décembre 2020 est de 4 000.
- La période de facturation qui sera augmentée va du 1er janvier 2020 au 31 décembre 2020.
- À la date de l'IPC du 1er décembre 2018, la valeur de l'IPC est de 205,3. À la date de l'IPC du 1er décembre 2019, la valeur de l'IPC est de 219,6.

Si le taux précédent est de 4 000, le montant de la facturation pour cette période est calculé de la manière suivante :

- *Modifications IPC* = (219.6 – 205.3) &divide; 205.3 = 6,965 %
- *Taux actuel* = (4 000 &times; 6,965 %) – 4 000 = 278,60
- *Modification du pourcentage* = (4 000 &times; 1,03) – 4 000 = 120
- *Montant facturé* = 4 000 + 278,6 + 120 = 4 398,6
