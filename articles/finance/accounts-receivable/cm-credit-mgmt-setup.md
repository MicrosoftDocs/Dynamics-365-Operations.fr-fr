---
title: Paramétrage de la gestion du crédit
description: Cet article décrit les options que vous pouvez utiliser pour configurer la gestion des crédits pour répondre aux besoins de votre entreprise.
author: JodiChristiansen
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8955518e7b5c0200d3827c1c22b7d150a09be244
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799543"
---
# <a name="credit-management-parameters-setup"></a>Paramétrage de la gestion du crédit

[!include [banner](../includes/banner.md)]

Cet article décrit les options que vous pouvez utiliser pour configurer la gestion des crédits pour répondre aux besoins de votre entreprise. Pour utiliser les fonctions de gestion des crédits, configurez les paramètres sur la page **Paramètres de crédits et recouvrements** (**Crédits et recouvrements \> Paramétrer \> Paramètres de crédits et recouvrements**).

## <a name="credit-parameters"></a>Paramètres de crédit

Dans la section **Crédit**, quatre raccourcis vous permettent de modifier les paramètres qui contrôlent la gestion des crédits : **Suspensions de crédit**, **Point de contrôle de gestion de crédit**, **Statistiques de gestion de crédit** et **Limites de crédit**. Les sections suivantes décrivent les paramètres disponibles sur chaque raccourci.

### <a name="credit-holds"></a>Suspensions de crédit

- Paramétrez l’option **Autoriser la modification de la valeur des commandes client une fois le blocage de la commande levé** sur **Non** pour exiger que les règles de validation soient à nouveau vérifiées si la valeur de la commande client (prix étendu) a été augmentée depuis que la commande client a été libérée de la liste d’attente.
- Dans le champ **Motifs des commandes annulées**, sélectionnez le motif de libération qui sera utilisé par défaut lorsqu’une commande client qui était en attente de gestion des crédits est annulée.
- Paramétrez l’option **Vérifier la limite de crédit des groupes de crédits client** sur **Oui** pour vérifier la limite de crédit d’un groupe de crédits client lorsque le client d’une commande client appartient à un groupe de crédits client. La limite de crédit pour le groupe sera vérifiée, puis, si elle est suffisante, la limite de crédit pour le client sera vérifiée.
- Paramétrez l’option **Vérifier la limite de crédit lorsque les conditions de paiement sont augmentées** sur **Oui** pour vérifier le classement des modalités de paiement afin de déterminer si les modalités de paiement de la commande client diffèrent des modalités de paiement par défaut du client. Si les nouvelles modalités de paiement ont un rang supérieur aux modalités de paiement d’origine, la commande est mise en attente pour la gestion du crédit.
- Paramétrez l’option **Vérifier la limite de crédit lorsqu’une remise sur le règlement est augmentée** sur **Oui** pour vérifier le classement de la remise sur le règlement afin de déterminer si l’escompte de règlement de la commande client diffère de l’escompte de paiement par défaut du client. Si le nouvel escompte de règlement a un rang supérieur à celui d’origine, la commande est mise en attente pour la gestion du crédit.
- Dans le champ **Motif de la libération des commandes modifiées**, sélectionnez le motif de libération qui sera utilisé par défaut lorsque les commandes modifiées sont automatiquement libérées de la gestion des crédits.
- Paramétrez l’option **Ignorer la règle de blocage de limite de crédit expirée lorsque la date d’expiration est vide** sur **Oui** pour contrôler le comportement de la règle **Limite de crédit expirée**. Paramétrez l’option sur **Non** pour bloquer une commande lorsque la date d’expiration est vide.
- Dans la gestion d’entrepôt, les charges peuvent être créées au moment de la saisie de la commande client. Paramétrez l’option **Supprimer les lignes de charge bloquées** sur **Non** pour laisser les lignes de commande client sur la charge lorsqu’une commande client est en attente de crédit. La charge ne peut pas être traitée lorsque la commande client est en attente. Paramétrez l’option sur **Oui** pour supprimer les lignes de commande client de la charge lorsqu’une commande client est en attente de crédit. La charge peut alors être traitée.
- Les commandes client peuvent être automatiquement libérées de l’examen de la gestion du crédit. Dans le champ **Motif de la libération automatique**, sélectionnez le motif de libération qui sera utilisé par défaut lorsque les commandes client sont automatiquement libérées.
- Les commandes client peuvent être automatiquement libérées de l’examen de la gestion du crédit. Dans le champ **Libérer automatiquement**, sélectionnez **Sans validation** pour débloquer la mise en attente d’une commande. Vous devez exécuter manuellement le processus qui a mis la commande en attente. Sélectionnez **Avec validation** pour valider la commande en utilisant le même processus de validation que celui exécuté lors de la mise en attente de la commande client.

### <a name="credit-management-checkpoint"></a>Point de contrôle de la gestion du crédit

Vous pouvez définir le calendrier utilisé pour vérifier les commandes client pour les problèmes de crédit. Le raccourci **Point de contrôle de gestion de crédit** identifie les processus de validation de documents qui incluent le traitement des règles de gestion du crédit. Vous pouvez également vérifier les règles de crédit pendant que vous effectuez une validation pro forma ou une validation complète de la commande client. Cochez les cases pour définir les processus de validation qui doivent mettre une commande en attente si un problème est détecté après le traitement des règles de blocage de la gestion des crédits.

Vous pouvez également définir le nombre de jours de grâce avant de vérifier à nouveau les règles de crédit. Bien que vous puissiez spécifier que les règles de gestion des crédits sont vérifiées lors de la validation, les règles ne seront pas vérifiées pendant le nombre de jours de grâce spécifié. Par exemple, vous confirmez une commande client le jour 1 et vous spécifiez deux jours de grâce pour l’étape de confirmation. Dans ce cas, les règles de crédit ne seront pas vérifiées à la prochaine étape de validation (par exemple, création d’un bon de livraison ou facturation de la commande) jusqu’au jour 4. Le jour 4 ou après, les règles seront à nouveau vérifiées lors de la validation , et le nombre de jours de grâce sera modifié en la valeur spécifiée pour le prochain point de contrôle de validation.

Si vous ne spécifiez pas le nombre de jours de grâce, les règles de crédit seront vérifiées à chaque étape de validation configurée pour exécuter les règles de gestion des crédits. Si vous validez la commande client sans validation, puis exécutez à nouveau la même étape de traitement des commandes, les règles de crédit seront à nouveau vérifiées. Par exemple, une commande est mise en attente après une confirmation et vous la validez avec ou sans validation. Dans ce cas, la commande sera à nouveau suspendue si vous la confirmez à nouveau. Utilisez les jours de grâce si la commande doit passer à l’étape de traitement suivante sans être à nouveau suspendue.

> [!Note]
> Si un point de contrôle de publication a un jour de grâce entré, tous les points de contrôle qui sont marqués pour publication doivent avoir des jours de grâce.

- Cochez la case **Validation** pour exécuter les règles de gestion du crédit lorsque le point de contrôle de validation affiché sur la ligne est exécuté. Si vous ne cochez pas la case, les règles ne seront vérifiées qu’une seule fois pendant tout le processus de validation.
- Si vous cochez la case **Validation**, spécifiez le nombre de jours de grâce qui doivent s’écouler avant que les règles de blocage soient à nouveau vérifiées. Vous ne pouvez pas ajouter de jours de grâce si la case **Validation** n’est pas cochée.
- Cochez la case **Pro forma** pour exécuter les règles de gestion du crédit lorsque le point de contrôle de validation Pro forma affiché sur la ligne est exécuté. Dans la plupart des cas, le champ **Validation** est paramétré sur **Non** dans la boîte de dialogue qui s’affiche lorsqu’une commande client est validée.
- Si vous cochez la case **Validation**, spécifiez le nombre de jours de grâce qui doivent s’écouler avant que les règles de blocage soient à nouveau vérifiées. Vous ne pouvez pas ajouter de jours de grâce si la case **Validation** n’est pas cochée.

### <a name="credit-management-statistics"></a>Statistiques de gestion du crédit

Plusieurs statistiques de gestion du crédit sont incluses dans le récapitulatif **Statistiques de gestion du crédit client** sur la page **Client**. Vous devez spécifier plusieurs valeurs requises pour calculer ces statistiques. Entrez le nombre de mois utilisé pour calculer les valeurs suivantes dans le récapitulatif **Statistiques de gestion du crédit client** :

1. Ventes quotidiennes restantes 1
2. Ventes quotidiennes restantes 2
3. Solde moyen 1
4. Solde moyen 2
5. Limite de crédit moyenne %
6. Exposition moyenne %

### <a name="credit-limits"></a>Limites de crédit

- Dans la gestion des crédits, la limite de crédit client est affichée dans la devise du client. Vous devez définir le type de taux de change pour la limite de crédit dans la devise du client. Dans le champ **Type de taux de change limite de crédit**, sélectionnez le type de taux de change à utiliser pour convertir la limite de crédit principale en limite de crédit du client.
- Paramétrez l’option **Autoriser la modification manuelle des limites de crédit** sur **Non** pour empêcher les utilisateurs de modifier les limites de crédit sur la page **Client**. Si cette option est définie sur **Non**, les modifications de la limite de crédit d’un client ne peuvent être effectuées qu’en enregistrant des transactions d’ajustement de limite de crédit.
- Met l’option **Contourner les réservations de stock** sur **Oui** pour ignorer les réservations de stock à la vérification des règles de blocage de la gestion des crédits. Dans ce cas, les quantités sont vérifiées et les périodes de grâce des points de contrôle sont activées, quelle que soit la quantité de réservation de stock.
- Lorsque la gestion des crédits est activée, le réglage du champ **Message en cas de dépassement de limite de crédit** est utilisé pour traiter uniquement les factures financières. Bien que des messages soient toujours ajoutés aux commandes client lorsque les clients ont dépassé leur limite de crédit, la présence de ces messages ne bloquera pas la confirmation, l’impression des listes de prélèvement et des bons de livraison, ou l’affichage des factures.

    La gestion des crédits est activée par défaut, mais vous pouvez la désactiver. S’il est activé, vous utilisez les règles de blocage de la gestion du crédit et les points de contrôle pour identifier quand les clients ont dépassé leur limite de crédit. S’il est désactivé, les messages ajoutés aux commandes client en fonction du paramétrage du champ **Message en cas de dépassement de limite de crédit** peut vous aider à identifier quand les clients ont dépassé leur limite de crédit.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Paramètres de séquence de nombres partagés et séquences de nombres

Un ID de journal est nécessaire pour traiter les ajustements de limite de crédit. Vous devez ajouter le numéro d’ajustement de limite de crédit qui doit être utilisé pour générer l’ID de journal.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
