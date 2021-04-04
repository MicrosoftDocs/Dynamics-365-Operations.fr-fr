---
title: Paramétrer et utiliser les alertes pour fraude dans le centre d'appels
description: Cette rubrique décrit le paramétrage des règles pour alerter les représentants du service client en cas d'informations potentiellement frauduleuses lorsque des commandes sont traitées. Vous pouvez définir des codes spécifiques qui sont utilisés pour mettre en attente automatiquement ou manuellement des commandes suspectes.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 65e6e065317311395a5a5ca2b049d1c277aa5003
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264526"
---
# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Paramétrer et utiliser les alertes pour fraude dans le centre d'appels

[!include [banner](includes/banner.md)]

Cette rubrique explique comment paramétrer des critères et des règles afin de mettre d'éventuelles commandes client frauduleuses en attente pour une révision ultérieure. La fonction de contrôle de fraude est utilisée pour déterminer la validité des informations dans une commande client. Si les informations d'une commande client semblent douteuses, selon les critères et les règles de fraude d'une organisation, la commande peut être mise en attente pour une révision ultérieure. Dans ce cas, la commande ne peut pas être lancée dans l'entrepôt pour traitement jusqu'à ce que la mise en attente ait été supprimée.

> [!NOTE]
> Cette fonctionnalité ne peut être utilisée que pour le traitement des commandes client du canal du centre d'appels Commerce.

## <a name="turning-on-the-fraud-check-feature"></a>Activation de la fonction de contrôle de fraude

Pour utiliser la fonction de contrôle de fraude, vous devez définir l'option **Activer l'achèvement de la commande** du canal sur **Oui** lorsque le canal du centre d'appels est [défini](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-order-processing-options). Lorsque l'achèvement de la commande est activé, les utilisateurs du centre d'appels doivent sélectionner **Terminer** dans la page de la commande client pour toutes les commandes client créées. L'action Terminer entraîne l'ouverture de la page **Résumé de la commande client**. Une fois que les utilisateurs saisissent les données de paiement requises dans la page **Résumé de la commande client**, ils sélectionnent **Envoyer** pour finaliser la commande. Lorsque la commande est envoyée, la fonction de contrôle de fraude est déclenchée, et les règles actives dans le système sont automatiquement validées.

Les utilisateurs du centre d'appels peuvent également mettre en attente manuellement les commandes client pour révision avant de sélectionner **Envoyer**. Pour mettre en attente manuellement une commande client, dans la page **Résumé de la commande client**, sélectionnez **Blocage** \> **Blocage manuel pour fraude**. Vous êtes invité à entrer un commentaire pour expliquer le motif de la mise en attente de la commande. Ce commentaire s'affiche dans la fenêtre [Blocages de commande](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) pour fournir un contexte à l'utilisateur qui examine les commandes en attente pour déterminer si la commande doit être lancée.

Outre la configuration de l'option **Activer l'achèvement de la commande** dans le canal, vous devez configurer la fonction de contrôle de fraude dans les paramètres du centre d'appels. Accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Paramétrage du centre d'appels** \> **Paramètres du centre d'appels**. Dans la page **Paramètres du centre d'appels**, sous l'onglet **Blocage**, définissez l'option **Contrôle de fraude** sur **Oui**.

Sous l'onglet **Blocage**, vous devez également définir les [codes de blocage](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) à appliquer à une commande qui est manuellement ou automatiquement mise en attente pour révision. Définissez les codes de blocage dans les champs **Code de blocage manuel pour fraude** et **Code de blocage pour fraude**. Il peut être utile de créer deux codes de blocage uniques, afin que les utilisateurs qui utilisent la fonction de blocage puissent facilement filtrer et distinguer les blocages automatiques des blocages manuels.

Pour une utilisation efficace de la fonction de contrôle de fraude, vous devez également définir le champ **Score minimal**. Chaque critère et règle de fraude définie dans le système a un score. Lorsqu'une commande est vérifiée pour les correspondances de fraude, si une ou plusieurs correspondances sont trouvées, les scores sont additionnés pour attribuer un score de fraude total à la commande. Si le score de fraude total pour une commande dépasse la valeur du champ **Score minimal**, la commande est automatiquement mise en attente. Vous pouvez éventuellement utiliser les autres champs de score sous l'onglet **Blocage** pour définir le score d'adresse e-mail, le score de téléphone, le score de code postal et le score de code postal étendu. Si vous ne spécifiez pas de score pour l'un de ces critères de fraude statiques lorsque vous les définissez sur la page **Données frauduleuses statiques**, le système leur affecte un score à l'aide des scores par défaut que vous spécifiez sous l'onglet **Blocage** de la page **Paramètres du centre d'appels**.

Enfin, utilisez le champ **Type de commentaire sur la fraude** pour spécifier le type de document à utiliser lorsque les utilisateurs entrent des commentaires lors de la mise en attente manuelle d'une commande pour révision. Le plus souvent, ce champ est défini sur **Note**.

## <a name="defining-fraud-criteria-and-rules"></a>Définition des critères et règles de fraude

Le système référence deux types de critères de fraude pour déterminer si une commande doit être mise en attente pour révision :

- **Données frauduleuses statiques** utilise une valeur spécifique, comme un numéro de téléphone mis sur une liste de numéros bloqués ou une adresse e-mail signalée car elle est reconnue pour avoir été utilisée pour des transactions frauduleuses précédentes. Pour configurer les données frauduleuses statiques, accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Paramétrage du centre d'appels** \> **Fraude** \> **Données frauduleuses statiques**. Dans la page **Données frauduleuses statiques**, vous pouvez ajouter des critères de fraude manuellement ou via l'importation de données. Les scores sont associés aux informations frauduleuses. Si la fonction de contrôle de fraude est activée, chaque commande client entrée est comparée aux données statiques. Si les données se trouvent dans l'adresse de facturation du client ou l'adresse de livraison associée à l'en-tête de commande, ou si les données se trouvent dans les adresses de livraison associées aux lignes de cette commande client, les scores de toutes les correspondances uniques sont additionnés et comparés à la valeur **Score minimal** pour déterminer si la commande doit être mise en attente.

- Les **Règles de fraude** comprennent des variables définies par l'utilisateur et des conditions définies pour ces variables. Pour créer des règles, accédez à **Retail et Commerce** \> **Paramétrage du canal** \> **Paramétrage du centre d'appels** \> **Fraude** \> **Règles**. Les règles de fraude permettent à une société de configurer un ensemble de règles plus complexes pouvant contenir des instructions **ET** ou **OU** pour évaluer plusieurs conditions. Par exemple, un utilisateur souhaite que toutes les commandes des clients appartenant à un groupe de clients spécifique et ayant commandé un produit spécifique soient mises en attente pour révision. Dans ce cas, les conditions de validation du client et des produits sont définies sur la page **Règles**, et une condition ET est utilisée. Une commande est mise en attente uniquement si les deux conditions sont remplies, et si la valeur du score affectée à cette règle, plus la valeur du score des autres règles correspondant à la commande, entraîne un dépassement de la valeur **Score minimal** du score de fraude total de la commande qui est définie sur la page **Paramètres du centre d'appels**.

> [!NOTE]
> Des règles multiples ou des règles trop complexes affectent les performances système lorsque les commandes client sont envoyées. La fonction de contrôle de fraude n'a pas été optimisée pour gérer un grand nombre de saisies de données statiques de fraude et de nombreuses règles actives. N'oubliez pas que chaque règle est évaluée lorsque les utilisateurs du centre d'appels sélectionnent **Envoyer** lors de la saisie de la commande client. Les règles sont évaluées par rapport à l'en-tête de commande client et toutes les lignes de commande. Plus il y a de règles, plus les instructions sont complexes, et plus le temps de traitement sera long. S'il existe plusieurs articles dans une commande, et plusieurs règles actives et entrées de données statiques, le processus automatique de révision et de validation de toutes les données et de calcul d'un score de fraude peut avoir un impact important sur les performances. Les organisations qui utilisent cette fonction doivent toujours tester et confirmer que la durée du traitement de la soumission de la commande est acceptable avant d'appliquer des modifications aux règles ou aux critères de fraude statiques dans l'environnement de production.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Identification des commandes mises en attente pour révision

Lorsque les utilisateurs du centre d'appels envoient une commande client, si la commande correspond aux critères ou règles de fraude, et si le score dépasse la valeur minimale, les utilisateurs reçoivent un message d'avertissement indiquant que la commande a été mise en attente. Les utilisateurs peuvent fermer ce message, car il est fourni uniquement à titre indicatif. Les utilisateurs peuvent éventuellement communiquer ces informations au client. L'entreprise doit déterminer le protocole que les utilisateurs doivent suivre dans ce cas.

La commande est enregistrée, mais l'indicateur **Ne pas traiter** est défini. Cet indicateur permet de garantir que la commande ne peut pas être lancée dans l'entrepôt. À tout moment, les utilisateurs peuvent afficher la valeur de l'indicateur **Ne pas traiter** pour toute commande client dans la page **Statut détaillé**. Cette page peut être ouverte à partir des pages **Toutes les commandes client** et **Service client**. Le système met également à jour la valeur du champ **Statut détaillé** sur **Blocage pour fraude** pour la commande.

Pour afficher et gérer les commandes mises en attente pour révision, accédez à **Retail et Commerce** \> **Clients** \> **Blocage de commandes**. Dans la page **Blocage de commandes**, sélectionnez une entrée dans la liste, puis cliquez sur **Blocage de commande** pour afficher une vue plus détaillée contenant des informations sur le motif du blocage. Dans l'organisateur **Détails de la fraude**, vous pouvez afficher les critères de fraude systématiques considérés comme une correspondance pour la commande et les scores appliqués. Si la commande est mise en attente manuelle, vous pouvez examiner les commentaires saisis par l'utilisateur qui a mis la commande en attente en consultant la section **Notes relatives à la fraude** dans l'organisateur **Notes**.

Pour plus d'informations sur l'utilisation des commandes en attente, voir [Blocage de commandes](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds).


[!INCLUDE[footer-include](../includes/footer-banner.md)]