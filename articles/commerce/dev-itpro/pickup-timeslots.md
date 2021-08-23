---
title: Créer et mettre à jour des plages horaires pour le ramassage des clients
description: Cette rubrique décrit comment créer, configurer et mettre à jour les plages horaires pour le ramassage des clients dans le siège Commerce.
author: anupamar-ms
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.15 update
ms.openlocfilehash: a9ee1356bfcaeee881c28cf0361b34b2c65acbc7a3b57347fa2581a8a935da42
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713419"
---
# <a name="create-and-update-time-slots-for-customer-pickup"></a>Créer et mettre à jour des plages horaires pour le ramassage des clients

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment créer, configurer et mettre à jour les plages horaires pour le ramassage des clients dans le siège Commerce.

La fonction de créneau horaire permet aux détaillants de définir un créneau horaire pour les articles pour lesquels le mode de livraison de ramassage client est activé. Les plages horaires permettent aux détaillants de définir les jours et les heures où les commandes peuvent être récupérées dans un magasin. Les détaillants peuvent également définir le nombre de commandes pouvant être retirées pendant une période donnée. De cette manière, les commerçants peuvent limiter le nombre de commandes pouvant être récupérées un jour et à une heure donnés. Le résultat est une expérience de meilleure qualité pour leurs clients.

> [!NOTE]
> La fonctionnalité de créneau horaire est disponible dans Microsoft Dynamics 365 Commerce version 10.0.15 et ultérieure.

L’illustration suivante montre un exemple de sélection de créneau horaire lors du paiement en ligne.

![Exemple de sélection de créneau horaire lors du paiement en ligne de la commande.](../dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="time-slot-properties"></a>Propriétés du créneau horaire

Un créneau horaire est un intervalle spécifique pendant lequel un client peut choisir de récupérer une commande dans un magasin ou à un emplacement spécifique. La fonction de gestion des créneaux horaires est disponible uniquement lorsque le mode de livraison de retrait client est configuré dans Dynamics 365 Commerce.

Un créneau horaire est défini à l’aide des propriétés suivantes :

- **Mode de livraison** – Précisez le mode de ramassage de livraison auquel s’applique le créneau horaire.
- **Nombre de jours minimum** et **Nombre de jours maximum** – Indiquez les dates les plus anciennes et les plus récentes pouvant être sélectionnées pour le retrait par rapport à la date à laquelle la commande est passée. 

    La propriété **Nombre de jours minimum** garantit que le détaillant dispose de suffisamment de temps pour traiter la commande avant qu’elle ne soit prête pour le retrait. La propriété **Nombre de jours maximum** garantit que l’utilisateur ne peut pas sélectionner une date trop éloignée dans le futur. Par exemple, si la valeur minimale est définie sur **1**, et qu’une commande est passée le 20 septembre, le premier jour où la commande sera disponible pour le retrait est le prochain jour éligible (21 septembre). De la même manière, en définissant une valeur maximum, vous pouvez définir le nombre maximum de jours pendant lesquels une commande peut être récupérée. Lorsque les valeurs minimales et maximales sont définies, les utilisateurs du site peuvent voir et sélectionner uniquement un ensemble spécifique de jours pendant leur expérience de paiement.

    Vous pouvez définir la valeur minimale sur une valeur décimale inférieure à 1. Par exemple, si le retrait est disponible quatre heures après la commande, définissez la valeur minimale sur **0,17** (= 4 ÷ 24, arrondi à deux décimales supérieures). Cependant, si vous définissez la valeur minimale sur une valeur décimale supérieure à 1, elle est toujours arrondie au nombre entier le plus proche. Par exemple, une valeur de **1,2** sera arrondie à **2**. De même, si vous définissez la valeur maximale sur une valeur décimale, elle est toujours arrondie au nombre entier le plus proche. 

- **Date de début** et **Date de fin** – Spécifiez les dates de début et de fin du créneau horaire. Chaque entrée de créneau horaire a une date de début et une date de fin. Par conséquent, vous avez la possibilité d’ajouter différents créneaux horaires tout au long de l’année (par exemple, des retraits pendant les heures de vacances). Si le début et les dates d’un créneau horaire sont modifiés après qu’une commande est passée, les modifications ne s’appliqueront pas à cette commande. Lorsque vous définissez des dates de début et de fin, vous devez tenir compte des dates de fermeture du magasin (par exemple, le jour de Noël) et vous assurer que les plages horaires ne sont pas définies pour ces jours.
- **Heures de retrait actives** – Spécifiez la période pendant laquelle le retrait est autorisé. Par exemple, les heures de retrait peuvent être comprises entre 14 h 00 et 17 h 00 tous les jours. Cette propriété permet aux heures de retrait d’être indépendantes des heures d’ouverture du magasin. Par conséquent, le détaillant peut configurer des heures de retrait qui correspondent à ses exigences commerciales spécifiques. Lorsque vous définissez les heures de retrait actives, vous devez tenir compte des heures d’ouverture du magasin et vous assurer que les heures de retrait ne sont pas définies pour les heures de fermeture du magasin.

    > [!NOTE]
    > Les heures de retrait en magasin doivent être définies dans le fuseau horaire du magasin approprié.

- **Intervalle de créneau horaire** – Spécifiez la durée qui peut être allouée à chaque plage horaire. Par exemple, la durée de chaque créneau horaire peut être par incréments de 15 minutes, 30 minutes ou une heure. Si la valeur de l’intervalle de temps est 0, l’intervalle de temps est disponible pendant toute la durée entre l’heure de début et l’heure de fin.
- **Créneaux par intervalle** – Spécifiez le nombre de clients ou de commandes pouvant être servis pour le retrait pendant chaque intervalle de temps. Par exemple, entrez **1**, **2**, **3**, ou tout autre nombre entier.
- **Jours actifs** – Spécifiez les jours de la semaine où les plages horaires de retrait sont actives. Cette propriété permet au détaillant de définir les jours où il souhaite prendre en charge les ordres de retrait.
- **Canaux de vente au détail** – Spécifiez les canaux de vente au détail. Chaque tranche horaire peut être associée à un ou plusieurs magasins de détail. En fonction des heures d’ouverture de chaque magasin, une ou plusieurs entrées de créneau horaire peuvent être créées et associées à un canal. 

<!-- ![HQ Timeslot overview.](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

Un seul modèle de créneau horaire peut être configuré par canal. Ces canaux incluent des magasins physiques, des centres d’appel, des appareils mobiles et des sites de commerce en ligne.

## <a name="configure-the-time-slot-feature-in-commerce-headquarters"></a>Configurer la fonctionnalité de créneau horaire au siège de Commerce

Des plages horaires doivent être définies pour chaque mode de retrait de livraison au siège de Commerce, afin que les points de vente (PDV) et les canaux d’e-commerce puissent les référencer.

- Seul un modèle de créneau horaire peut être associé à chaque magasin ou canal.
- Chaque créneau horaire créé doit être unique pour chaque mode de livraison de chaque modèle.
- Une fois la fonction de plage horaire configurée, le calendrier des plages horaires sera disponible pour les magasins ou groupes de magasins sélectionnés. Elle sera également visible au PDV, pour référence.

Pour configurer la fonctionnalité de créneau horaire au siège de Commerce, procédez comme suit.

1. Aller à **Commerce** \> **Configuration des canaux** \> **Créneau horaire de retrait en magasin**.
1. Sélectionnez **Nouveau** pour créer un modèle de créneau horaire. Pour utiliser un modèle existant, sélectionnez le modèle dans le volet de gauche.
1. Entrez des valeurs dans les champs **ID de créneau horaire** et **Description**.
1. Sur le raccourci **Retrait des commandes – Paramètres de l’heure**, sélectionnez **Ajouter**.
1. Dans la boîte de dialogue **Retrait des commandes – Paramètres de l’heure**, définissez la plage de dates, le mode de livraison, les heures de livraison actives, les jours actifs, l’intervalle de créneau horaire, les créneaux par intervalle et d’autres paramètres.

    Si les créneaux horaires seront statiques dans un avenir prévisible, définissez le champ **Date de fin** sur **Jamais**.

    > [!NOTE]
    > Vous pouvez créer plusieurs modèles, mais un seul modèle peut être associé à un seul canal ou magasin.

    ![Boîte de dialogue Retrait des commandes – Paramètres de l’heure.](../dev-itpro/media/Curbside_timeslot_Settings_Page.PNG)

1. Lorsque vous avez terminé, sélectionnez **OK**.
1. Si les plages horaires d’une journée varient, créez des entrées supplémentaires sur le raccourci **Retrait des commandes – Paramètres de l’heure** pour vous assurer que les dates et heures ne se chevauchent pas.
1. Sur le raccourci **Canaux de vente au détail**, sélectionnez **Ajouter** pour associer le modèle de créneau horaire aux magasins ou chaînes où il sera utilisé.
1. Dans la boîte de dialogue **Choisir des nœuds d’organisation**, utilisez les boutons de flèches pour sélectionner (ou désélectionner) les magasins, les régions et les organisations auxquels le modèle doit être associé.

    <!-- ![HQ Timeslot overview.](../dev-itpro/media/Curbside_timeslot_Settings_overview.PNG) -->

1. Lorsque vous avez terminé, sélectionnez **OK**.
1. Sur la page **Programme de distribution**, exécutez les tâches **1070** et **1135** pour synchroniser les données avec les canaux.

## <a name="time-slot-selection-for-pos-orders"></a>Sélection des plages horaires pour les commandes en PDV

Au PDV, lorsqu’une commande ou une ligne de commande est identifiée pour le retrait, le caissier peut sélectionner le magasin ou le lieu de retrait, ainsi qu’une date et un créneau horaire. Si un client a un ordre de prélèvement pour un autre magasin, l’agent de caisse peut sélectionner les dates lorsque le prélèvement sera disponible dans ce magasin. La recherche du magasin génère une référence aux dates et heures d’ouverture de magasin.

L’illustration suivante montre un exemple de sélection de créneau horaire pour une commande au PDV.

![Un exemple de sélection de créneau horaire pour une commande au PDV.](../dev-itpro/media/Curbside_timeslot_POS.png)

## <a name="time-slot-selection-for-e-commerce-orders"></a>Sélection des plages horaires pour les commandes d’e-commerce

Pour plus d’informations sur la façon de rendre la sélection de créneau horaire disponible pour les commandes d’e-commerce, voir [Module d’information sur le retrait](../pickup-info-module.md).

> [!NOTE]
> Les utilisateurs peuvent afficher ou modifier les créneaux horaires de retrait sur la page de paiement d’un site de commerce uniquement si le module d’informations de retrait a été ajouté à cette page. Si la page de paiement n’inclut pas le module d’informations de retrait, les commandes seront passées sans permettre aux utilisateurs de spécifier ou d’afficher les informations sur les plages horaires.

L’illustration suivante montre un exemple de commande e-commerce où un créneau horaire de retrait a été sélectionné.

![Exemple de commande e-commerce où un créneau horaire de retrait a été sélectionné.](../dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="time-slot-selection-for-call-center-orders"></a>Sélection des plages horaires pour les commandes de centre d’appels

Dans l’application du centre d’appels, les agents peuvent sélectionner le magasin ou le lieu de retrait, ainsi qu’une date et un créneau horaire, comme indiqué dans l’illustration suivante.

![Exemple de commande de centre d’appels où un créneau horaire de retrait a été sélectionné.](../dev-itpro/media/Curbside_timeslot_callcenter.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Module Information sur les prélèvements](../pickup-info-module.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]