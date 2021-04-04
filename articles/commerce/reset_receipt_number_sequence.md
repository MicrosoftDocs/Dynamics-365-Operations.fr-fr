---
title: Réinitialiser les numéros de ticket de caisse
description: Cette rubrique décrit comment réinitialiser les numéros de ticket de caisse utilisés pour diverses actions à une date souhaitée (par exemple, l'année fiscale ou l'année civile).
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: 97ec85ebccacd3a827e8a016098939134823dceb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243693"
---
# <a name="reset-receipt-numbers"></a>Réinitialiser les numéros d'accusé de réception 

[!include [banner](includes/banner.md)]

> [!NOTE]
> Nous vous demandons de sélectionner la propriété **Souche indépendante** pour tous les types de reçus dans le profil de fonctionnalité avant d'utiliser cette fonction. En outre, le fuseau horaire du système de l'appareil sur lequel le PDV est utilisé, doit correspondre au fuseau horaire du magasin correspondant. En raison de ces limitations, nous vous recommandons de ne pas utiliser cette fonction en production pendant que nous travaillons à résoudre ces problèmes dans une version ultérieure. 

Les détaillants génèrent des numéros de ticket de caisse pour diverses actions dans le magasin, telles que les transactions au comptant, les transactions de retour, les commandes clients, les devis et les paiements. Bien que les détaillants définissent leurs propres formats de ticket de caisse, certains pays ou régions ont des réglementations qui imposent des restrictions sur ces formats. Par exemple, des réglementations peuvent limiter le nombre de caractères sur le ticket de caisse, exiger des numéros de ticket de caisse qui se suivent, restreindre certains caractères spéciaux ou exiger une réinitialisation des numéros de ticket de caisse au début de l'année. Microsoft Dynamics 365 Commerce rend le processus de gestion des numéros de ticket de caisse très flexible, pour aider les détaillants à répondre aux exigences réglementaires. Cette rubrique explique comment utiliser la fonctionnalité de réinitialisation des numéros de ticket de caisse.

Dans Commerce, les formats de ticket de caisse peuvent être alphanumériques. Vous pouvez y mettre à la fois du contenu statique et dynamique. Le contenu statique comprend des caractères alphabétiques, des chiffres et des caractères spéciaux. Le contenu dynamique comprend un ou plusieurs caractères qui représentent des informations telles que le numéro du magasin, le numéro du terminal, la date, le mois, l'année et les séquences de numéros qui sont automatiquement incrémentées. Les formats sont définis dans la section **Numérotation des tickets de caisse** du profil de fonctionnalité. Le tableau suivant décrit les caractères qui représentent le contenu dynamique.

| Caractères | Description |
|------------|-------------|
| D          | Le caractère **S** est utilisé pour le numéro du magasin. Par exemple, si un magasin est numéroté HOUSTON1, le format **SSS** affiche « ON1 » sur le ticket de caisse. Le format **SSSSS** affiche « STON1 » sur le ticket de caisse. |
| T          | Le caractère **T** est utilisé pour le numéro du terminal. Par exemple, si un terminal est numéroté 0001, le format **TTTT** affiche « 0001 » sur le ticket de caisse. |
| C          | Le caractère **C** est utilisé pour l'ID personnel. Par exemple, si un membre du personnel a un ID 000160, le format **CCCC** indique « 0160 » sur le ticket de caisse. |
| jjj        | Les caractères **jjj** correspondent au jour de l'année, de 1 à 366. Par exemple, le 15 janvier, le format **jjj** affiche « 015 » sur le ticket de caisse. |
| MM         | Les caractères **MM** sont utilisés pour le mois à deux chiffres. Par exemple, en janvier, le format **MM** affiche « 01 » sur le ticket de caisse. |
| JJ         | Les caractères **JJ** sont utilisés pour le jour du mois à deux chiffres. Par exemple, le 15 janvier, le format **JJ** affiche « 15 » sur le ticket de caisse. |
| AA         | Les caractères **AA** sont utilisés pour l'année à deux chiffres. Par exemple, pour un mois de l'année 2020, le format **AA** affiche « 20 » sur le ticket de caisse. |
| \#         | Un signe numérique (**\#**) est utilisé pour la numérotation séquentielle. Par exemple, le format **####** affiche « 0001 », « 0002 », « 0003 », etc. sur le ticket de caisse. |

Vous pouvez réinitialiser la numérotation séquentielle du ticket de caisse sur une date spécifique. Ensuite, pour la première transaction réalisée après 12h00 à la date de réinitialisation sélectionnée, le système réinitialise la séquence de numéros du ticket de caisse sur 1. Vous pouvez également indiquer si la réinitialisation ne se produit qu'une seule fois ou si elle se reproduit chaque année. Si elle se reproduit chaque année, la réinitialisation se produit automatiquement chaque année jusqu'à ce que le détaillant choisisse de l'arrêter. 

Pour activer la réinitialisation, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**.
1. Au niveau de l'organisateur **Numérotation des tickets de caisse**, sélectionnez **Réinitialiser la date de réinitialisation du numéro**.
1. Dans la boîte de dialogue déroulante, au niveau du champ **Réinitialiser la date**, sélectionnez la date future de la réinitialisation.
1. Dans le champ **Réinitialiser le type de ticket de caisse**, sélectionnez **Occasionnel uniquement** ou **Tous les ans**.
1. Cliquez sur **OK**.

![Sélection d'une date de réinitialisation du ticket de caisse](media/Enable_receipt_reset.png "Sélection d'une date de réinitialisation du ticket de caisse")

Dès que la date est sélectionnée, elle apparaît dans la colonne **Date de réinitialisation du numéro de ticket de caisse**. La date de réinitialisation s'applique à tous les types de transaction de réception. Par conséquent, la séquence des numéros de ticket de caisse est réinitialisée pour tous les types de ticket.

Dès que la date de réinitialisation arrive, le numéro du ticket de caisse est réinitialisé pour la première transaction de chaque type. De plus, dans le profil de fonctionnalité, la date de réinitialisation est déplacée de la colonne **Date de réinitialisation du numéro de ticket de caisse suivant** vers la colonne **Date de réinitialisation du numéro de ticket de caisse actuel**. Cette modification indique que si un registre n'est pas utilisé à la date de réinitialisation, le numéro du ticket de caisse est réinitialisé à la prochaine *utilisation* du registre. Par exemple, le 3 décembre 2019, vous sélectionnez le **1 janvier 2020** comme date de réinitialisation. Le 1er janvier, lorsque les registres effectuent leur première transaction, le numéro du ticket de caisse est réinitialisé. Toutefois, un registre n'est pas du tout utilisé en décembre et en janvier, mais commence à être utilisé en février. Dans ce cas, comme une action de réinitialisation a été définie, le numéro du ticket de caisse pour ce registre est réinitialisé lorsque le registre effectue sa première transaction en février.

Utilisez la fonctionnalité **Effacer la date de réinitialisation** pour effacer les futures dates de réinitialisation. Toutefois, si la date de réinitialisation s'est produite dans le passé, elle ne peut pas être annulée. Par conséquent, la réinitialisation continuera de se produire pour tous les registres pour lesquels la réinitialisation n'est pas encore arrivée.

> [!NOTE]
> Selon la date de réinitialisation sélectionnée et le format du ticket de caisse, vous pouvez avoir des numéros de ticket de caisse en double. Même si le système de point de vente (PDV) peut gérer ces situations, il augmente le temps requis pour traiter les retours car les vendeurs doivent sélectionner parmi les tickets de caisse en double. D'autres complications liées au nettoyage des données peuvent survenir si les tickets de caisse en double n'étaient pas prévus. Par conséquent, nous vous recommandons d'utiliser des caractères de date dynamiques (par exemple, **jjj**, **MM**, **JJ** et **AA**) pour éviter la duplication des numéros de ticket de caisse après une réinitialisation.


[!INCLUDE[footer-include](../includes/footer-banner.md)]