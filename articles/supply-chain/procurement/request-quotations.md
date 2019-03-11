---
title: Appels d'offre
description: Cette rubrique fournit une vue d'ensemble des appels d'offre. Les organisations émettent des appels d'offre lorsqu'elles souhaitent comparer les offres de plusieurs fournisseurs pour les articles ou les services qu'elles doivent acheter.
author: mkirknel
manager: AnnBe
ms.date: 06/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 714715ccfbdd57e4450c301f5302e008c0c136b1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "351284"
---
# <a name="requests-for-quotation-rfqs"></a>Appels d'offre

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des appels d'offre. Les organisations émettent des appels d'offre lorsqu'elles souhaitent comparer les offres de plusieurs fournisseurs pour les articles ou les services qu'elles doivent acheter. Dans une demande de devis, vous demandez aux fournisseurs d'indiquer les prix et les délais de livraison pour des quantités de produits que vous spécifiez.
Vous pouvez également demander aux fournisseurs de spécifier s'il y a des frais accessoires, comme des frais de transport, ou si le fournisseur offre des remises pour les commandes importantes ou le paiement anticipé de la facture fournisseur.

Le processus d'appel d'offre comprend les tâches suivantes :

1.  Créer et envoyer un appel d'offre à un ou plusieurs fournisseurs.

2.  Recevoir et enregistrer les offres (réponses à l'appel d'offre).

3.  Transférer les offres que vous acceptez pour une commande fournisseur, un contrat d'achat ou une demande d'achat.

L'illustration suivante présente une vue d'ensemble du processus d'appel d'offre.

[![Processus RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Vous pouvez créer une demande de devis à partir des commandes planifiées, d'une demande d'achat ou par saisie manuelle. Il s'agit du document de base que vous utilisez pour délivrer un appel d'offre à chaque fournisseur.+

Après avoir préparé la demande de devis et ajouté des fournisseurs, sélectionnez **Envoyer** (**Envoyer et publier** pour le secteur public) sur la demande de devis. Un journal d'appel d'offre est généré pour chaque fournisseur auquel vous envoyez l'appel d'offre. Vous pouvez configurer les options d'impression pour l'action Envoyer afin d'imprimer un état pour chaque fournisseur dans une archive ou pour envoyer un état à l'adresse électronique de chaque fournisseur. En outre, vous pouvez utiliser le journal d'appel d'offre de chaque fournisseur pour générer un état que vous pouvez envoyer ou renvoyer au fournisseur ultérieurement. Vous pouvez également configurer l'action Envoyer afin de générer une feuille de réponse que le fournisseur peut compléter.

Cette rubrique décrit le processus de gestion des appels d'offre lorsque la collaboration fournisseur n'est pas utilisée. Si votre système est paramétré pour la collaboration de fournisseur, les fournisseurs peuvent saisir directement les offres dans Microsoft Dynamics 365 for Finance and Operations. Pour plus d'informations voir [Collaboration fournisseur avec des clients](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) et [Collaboration fournisseur avec des fournisseurs externes](vendor-collaboration-work-external-vendors.md).

Si vous devez modifier un appel d'offre après son envoi, vous pouvez le renvoyer aux fournisseurs lorsque vous avez terminé à l'aide des deux actions de modification : Créer et Finaliser.+

Lorsque vous recevez des offres par courrier électronique, vous pouvez gérer ces offres sur la page **Appels d'offre**.

Si une deuxième itération d'une réponse d'un fournisseur est requise, sélectionnez **Retour** sur la page **Appel d'offre**. L'action Retour génère un nouveau journal et un état qui seront imprimés, archivés et envoyés conformément à vos paramètres d'impression.

> [!NOTE]
> Le nom de la page **Appel d'offre** a été modifiée. Dans les versions précédentes de Dynamics 365 for Finance and Operations, cette page est appelée **Réponse aux appels d'offre**.

Si vous avez ajouté des critères de score à votre dossier d'appel d'offre, la demande de devis dispose d'un volet de score où vous pouvez saisir les scores. Tous les scores s'affichent sur l'appel d'offre lorsque vous comparez les réponses sur la page **Comparer les réponses**. Sur la page **Comparer les réponses**, vous pouvez également comparer les autres données de réponse, telles que le prix de la ligne, la date de livraison et le prix total.

Lorsque vous sélectionnez une offre ou plusieurs lignes d'une offre, vous pouvez accepter toutes ou certaines lignes et rejeter le reste. Les journaux d'acceptation, les journaux de rejet et les états correspondants sont générés et imprimés, archivés et envoyés conformément à vos paramètres d'impression. Lorsque vous acceptez une offre ou des lignes spécifiques d'une offre, un contrat d'achat ou une commande fournisseur est générée, ou une demande d'achat est mise à jour, selon le type d'achat de l'appel d'offre. Vous pouvez créer un contrat commercial que vous pouvez utiliser ultérieurement pour toute réponse, peu importe si vous les avez acceptées ou rejetées.

Une demande de devis a deux statuts : le plus élevé et le plus bas, vous pouvez consulter le statut sur la page de liste de **Toutes les demandes de devis**. Le statut le moins élevé correspond au stade le moins avancé de toute ligne de la demande de devis, et le statut le plus élevé au stade le plus avancé. Par exemple, si une demande de devis avec trois lignes est envoyée à deux fournisseurs, il existe deux demandes de devis avec chacune trois lignes. Toutes les lignes sont **Envoyées**. Ensuite, une offre est entrée par l'un des fournisseurs et les lignes de l'appel d'offre reçoivent le statut **Reçues**. Cela signifie que sur les trois lignes de la demande de devis, toutes sont **Envoyées** pour une demande de devis et **Reçues** pour une autre demande de devis. Le statut le moins élevé est alors **Envoyé,** et le statut le plus élevé est **Reçu.**

Ces statuts sont décrits en détail plus loin dans cette rubrique.

## <a name="setting-up-rfq-functionality"></a>Paramétrage de la fonctionnalité de demande de devis

Avant de pouvoir créer un dossier de demande de devis, vous devez paramétrer les informations de demande de devis sur la page **Paramètres d'approvisionnement**. Lorsque vous créez une demande de devis, vous pouvez spécifier les valeurs par défaut qui sont copiées dans la demande de devis. Vous pouvez spécifier les valeurs par défaut suivantes :

-   Le type d'achat de nouvelles demandes de devis : **Commande fournisseur** ou **Contrat d'achat**

-   Décalage entre la date et l'heure d'expiration et le jour où la demande de devis a été créée

-   Type de sollicitation, qui peut transférer une méthode de notation spécifique à la demande de devis par défaut

-   Informations de livraison et conditions de paiement

-   Champs devant être inclus dans l'offre

Vous pouvez remplacer ces valeurs pour un dossier de demande de devis spécifique.

Vous devez également configurer le processus d'avenant. Dans le cadre de cette configuration, vous pouvez activer le verrouillage du champ. Lorsque le verrouillage du champ est activé, un professionnel de l'approvisionnement qui souhaite modifier une demande de devis doit tout d'abord sélectionner **Créer** dans la section **Avenant** de l'onglet **Devis** de la demande de devis. Ensuite, une fois la demande de devis mise à jour avec les modifications, le professionnel d'approvisionnement doit effectuer le processus en sélectionnant **Finaliser**. L'action Finaliser génère un message e-mail qui informe les fournisseurs de l'appel d'offre modifié.

Sur la page **Paramètres de l'approvisionnement**, sélectionnez le modèle à utiliser pour la notification par e-mail qui est envoyée aux fournisseurs. Lorsqu'un modèle est créé dans **Modèles d'e-mail**, il peut contenir les jetons de remplacement suivants :

-   %Dossier d'appel d'offre%

-   %Motif de retour de l'offre%

-   %Motif de l'avenant%

-   %Avenant préparé par%

-   %Société%

-   %Nom du dossier d'appel d'offre%

-   %Date et heure d'expiration%

-   %Date%

Les jetons %Motif de retour de l'offre% et %Motif de l'avenant% sont remplacés par du texte que le professionnel de l'approvisionnement peut saisir lorsqu'il remplit l'avenant dans l'assistant **Avenant**. Les valeurs des jetons %Avenant préparé par% et %Société% sont automatiquement extraites de la demande de devis. Le jeton %Date% est remplacé par la date actuelle.

Si vous souhaitez annuler un appel d'offre envoyé, vous pouvez effectuer cela depuis la demande de devis. Pour l'annulation, un modèle d'e-mail est requis pour envoyer la notification d'annulation aux personnes à contacter chez le fournisseur. Le modèle doit être sélectionné sur la page **Paramètres d'approvisionnement**. Lorsque le modèle est créé, il peut contenir les jetons de remplacement suivants :

-   %Motif d'annulation%

-   %Dossier d'appel d'offre%

-   %Appel d'offre annulé par%

-   %Société%

-   %Nom du dossier d'appel d'offre%

-   %Date%

Le jeton %Motif d'annulation% est remplacé par le texte que le professionnel de l'approvisionnement peut saisir dans l'assistant **Annulation**. Le jeton %Date% est remplacé par la date actuelle.

Si vous souhaitez utiliser des codes motif d'une offre pour indiquer la raison pour laquelle elle a été rejetée ou acceptée, vous devez paramétrer des codes motif sur la page **Motifs de fournisseur**.

Sur la page **Paramétrage d'écran** du module Approvisionnements, vous pouvez configurer l'apparence de vos documents d'appel d'offre imprimés ou stockés.

> [!NOTE]
> Pour une configuration du secteur public, vous devez utiliser le processus d'avenant pour modifier un appel d'offre qui a déjà été envoyé. Lorsqu'un appel d'offre est envoyé, les champs sont verrouillés.
Par conséquent, pour apporter des modifications à l'appel d'offre, vous devez sélectionner **Créer** pour démarrer le processus d'avenant, comme décrit précédemment. Le comportement de verrouillage est contrôlé par l'option **Verrouiller les appels d'offre lorsqu'ils sont envoyés** dans la page **Paramètres d'approvisionnement**. Par défaut, ce paramètre est défini sur **Oui** et pour une configuration du secteur public, le paramètre par défaut ne peut pas être modifié. Par conséquent, bien que le processus d'avenant puisse être géré manuellement dans une configuration hors secteur public, il doit être utilisé pour une configuration du secteur public.

Lorsque vous créez une demande de devis de type Commande fournisseur et ajoutez un article en stock à la demande de devis, un mouvement de stock ayant le statut de réception **Réception de devis** est également créé. Seules les lignes de demande de devis avec ce statut sont prises en compte lorsque vous utilisez un plan général pour calculer les approvisionnements. Si vous souhaitez que le plan général inclut les lignes de demande de devis comme une réception prévue, vous devez configurer ce comportement dans le paramétrage de la planification principale.

Un gestionnaire ou agent des achats peut créer et tenir à jour des types de sollicitation, afin qu'ils correspondent aux exigences d'approvisionnement de l'organisation. Chaque type de sollicitation peut être associé à une méthode d'attribution de score. Ces dernières consistent en un ensemble de critères pouvant être utilisés lorsque vous attribuez un score aux offres. Vous devez paramétrer des types de sollicitation, les méthodes d'attribution de score et les critères d'attribution de score sur les pages **Type de sollicitation** et **Méthode d'attribution de score**.

## <a name="creating-and-sending-an-rfq"></a>Création et envoi d'un appel d'offre

Vous créez une demande de devis, sélectionnez les fournisseurs pour lesquels vous souhaitez soumettre une offre sur la demande de devis, puis vous envoyez le devis aux fournisseurs. Vous pouvez utiliser les paramètres d'impression afin d'acheminer l'état des appels d'offre et les états de fiche de réponse à votre destination préférée.

Vous pouvez créer manuellement une demande de devis pour le type d'achat **Commande fournisseur** ou **Contrat d'achat**.

Si la demande de devis est de type **Commande fournisseur**, le comportement suivant se produit déviant d'autres types de demande de devis :

-   Lorsque les lignes de demande de devis sont créées, les transactions du stock sont générées avec un statut de réception de **Réception de devis**.

-   Lorsque vous acceptez une offre, une commande fournisseur est générée.

Si l'appel d'offre est de type **contrat d'achat**, le comportement suivant se produit déviant d'autres demandes de devis :

-   La demande de devis est utilisée pour un accord sur l'achat d'une quantité ou d'une valeur spécifique d'un produit au fil du temps. Vous devez sélectionner l'intervalle de dates qui s'applique au contrat d'achat et le nom de la personne qui gère le contrat d'achat.

-   Lorsque vous acceptez une offre, un contrat d'achat est généré.

Si la demande de devis est générée à partir d'une demande d'achat, le type **Demande d'achat** est automatiquement attribué. Vous ne pouvez pas créer manuellement de demande de devis de type **Demande d'achat**.

Vous pouvez créer une demande de devis à partir d'une demande d'achat uniquement si le statut de la demande d'achat est **En cours de révision** et si vous êtes affecté pour effectuer la tâche de workflow suivante. Les lignes de la demande d'achat sont mises à jour automatiquement lorsque vous acceptez les lignes à partir des offres (réponses à l'appel d'offre) que vous avez reçues des fournisseurs. Vous ne pouvez pas effectuer, rejeter, approuver, ou exécuter d'autres action sur la demande d'achat tant que la ligne de demande n'est pas mise à jour avec une ligne d'appel d'offre acceptée ou que la demande de devis n'est pas annulée.

Lorsque vous créez une demande de devis, vous pouvez sélectionner un type de sollicitation. Le type de sollicitation détermine l'ensemble de critères d'attribution de score utilisés pour attribuer un score aux réponses d'appel d'offre à la demande de devis.

Vous pouvez ajouter un questionnaire à un dossier de demande de devis. Ce questionnaire s'affiche ensuite sur toutes les réponses d'appel d'offre une fois que vous envoyez la demande de devis. Le remplissage du questionnaire est une tâche obligatoire avant que l'offre puisse être soumise.


Il existe trois méthodes pour sélectionner les fournisseurs à ajouter à un dossier de demande de devis :

- Ajout de fournisseurs l'un après l'autre.
- Recherchez tous les fournisseurs qui répondent à des critères spécifiques.
- Ajoutez automatiquement tous les fournisseurs qui sont validés pour les catégories d'approvisionnement utilisées sur les lignes de demande de devis.

Lorsque l'appel d'offre est prêt, sélectionnez **Envoyer**. L'action Envoyer génère des journaux et des états qui seront imprimés, archivés et envoyés conformément à vos paramètres d'impression.

Si vous définissez **Utiliser le fournisseur pour recalculer les prix** et **Utiliser les informations relatives à l'article spécifiques au fournisseur** sur **Oui** sur la page **Envoi de l'appel d'offre** lorsque vous avez soumis l'appel d'offre à un fournisseur, certaines informations spécifiques au fournisseur sont entrées automatiquement dans l'appel d'offre pour ce fournisseur.


## <a name="amending-an-rfq-case"></a>Modification d'une demande de devis

Parfois, vous devez modifier une demande de devis après son envoi. Vous devrez peut-être modifier une demande de devis si, par exemple, les dates de livraison ont changé ou vous souhaitez des produits supplémentaires ou différentes quantités de produits. Vous pouvez configurer le processus d'avenant de manière à ce qu'il soit plus ou moins restrictif.

Si vous configurez le processus d'avenant de manière à ce qu'il soit plus restrictif, avant de modifier les champs d'un dossier d'appel d'offre qui a déjà été soumis, vous devez sélectionner **Créer** dans le dossier d'appel d'offre pour démarrer un avenant. Après avoir terminé vos modifications, vous devez sélectionner **Finaliser**. Vous êtes ensuite guidé dans le processus d'ajout d'informations pour le message électronique envoyé pour notifier les fournisseurs de l'avenant. L'état mis à jour de l'appel d'offre, qui inclut une note d'avenant, est automatiquement joint au message électronique.

Si vous configurez le processus d'avenant de manière à ce qu'il soit moins restrictif, il n'est pas nécessaire de sélectionner **Créer** pour pouvoir modifier les champs d'un dossier d'appel d'offre qui a déjà été envoyé. Toutefois, vous devez ajouter manuellement une note d'avenant dans l'appel d'offre et renvoyer le dossier. Notez que cette approche ne peut être utilisée que si aucune des réponses (offres) n'a été modifiée. Si vous avez entré une réponse et que son état est **Reçu**, le bouton **Envoyer** n'est pas disponible. Dans ce cas, vous devez sélectionner **Créer** puis **Finaliser**, comme vous devez le faire dans le processus plus restrictif. La réponse est ensuite réinitialisée pour refléter les modifications du dossier d'appel d'offre.

Si les fournisseurs utilisent l'interface de collaboration fournisseur pour saisir des offres, vous devez toujours utiliser le processus d'avenant pour informer les fournisseurs des modifications du dossier d'appel d'offre. Ce processus permet d'éviter la situation où les fournisseurs font une offre sur un dossier d'appel d'offre obsolète alors que leur offre est en cours. Pour plus d'informations sur la collaboration fournisseur, voir [Collaboration fournisseur avec des fournisseurs externes](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Si vous voulez inviter d'autres fournisseurs à faire une offre et qu'aucune modification n'a été apportée au dossier d'appel d'offre, vous pouvez utiliser le bouton **Envoyer**. Les fournisseurs que vous avez ajoutés s'affichent sur la page **Envoyer** et reçoivent l'invitation par courrier électronique.


## <a name="receiving-and-registering-rfq-replies"></a>Réception et enregistrement des réponses à la demande de devis

Lorsque vous envoyez une demande de devis, une feuille de réponse est automatiquement générée. Lorsque vous recevez des offres à un appel d'offre, vous devez les entrer à partir de la page **Appel d'offre** en cliquant sur l'action **Modifier la réponse à l'appel d'offre.** Cela vous permet d'entrer des informations d'offre sur un écran d'offre dédié. Initialement, **Progression de réponse** est **Non commencé**. Lorsque vous cliquez sur **Modifier la réponse d'appel d'offre,** le statut de progression est **L'acheteur effectue une mise à jour** jusqu'à ce que l'offre soit envoyée. Cliquez sur **Envoyer** lorsque vous avez entré les informations d'offre. Le statut de progression de l'offre passe à **Soumis par l'acheteur.** De même, avec la collaboration de fournisseur activée, **Progression de réponse** est mis à jour à mesure que le fournisseur interagit avec l'offre. Le statut passe ensuite **L'acheteur effectue une mise à jour** à **Soumis par le fournisseur**. Lorsque l'offre est envoyée, un journal est créé comme **Reçu**. La réponse (offre) doit être envoyée pour être enregistrée comme reçue, et c'est ensuite seulement qu'elle peut être encore été traitée comme acceptée ou de refusée.

Si vous devez mettre l'offre à jour, vous devez passer par le même processus comme ci-dessus et la soumettre de nouveau.

Notez que la modification du formulaire **Appel d'offre** est autorisée uniquement pour les informations liées au traitement de l'offre, pas pour entrer l'offre. Pour entrer ou modifier l'offre, cliquez sur **Modifier la réponse à l'appel d'offre.**

Lorsque vous entrez les informations d'offre, si la demande de devis autorise des lignes alternatives, vous pouvez ajouter des lignes alternatives ayant uniquement une catégorie d'approvisionnement et aucun article de catalogue spécifiés. Cliquez sur **Ajouter une alternative** pour ajouter des lignes alternatives.

Si vous avez entré une réponse, mais si vous avez besoin d'une nouvelle offre du fournisseur, vous pouvez retourner l'appel d'offre. Un nouveau journal et un nouveau rapport sont générés, qui peuvent être envoyés au fournisseur.

Vous pouvez afficher une vue d'ensemble de toutes les demandes de devis et leurs statuts : **Créée, Envoyée, Reçue, Rejetée, Acceptée, Refusée, Annulée** sur la page **Suivi de la demande de devis**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Acceptation et rejet des offres, et transfert des offres reçues vers les documents en aval

Après avoir identifié l'offre la plus intéressante, par exemple celle offrant le meilleur prix total, vous pouvez accepter l'offre. Vous pouvez recevoir certaines lignes d'une offre et rejeter d'autres.
Vous pouvez également recevoir des lignes de différents fournisseurs. Sachez que si vous acceptez certaines lignes, vous devez rejeter toutes les autres. Par conséquent, si vous souhaitez accepter d'autres lignes, vous devez sélectionner **Annuler** à l'invite. Le statut de la réponse à l'appel d'offre pour chaque fournisseur dont vous acceptez des offres ou des lignes est mis jour sur **Accepté**.

Si vous, tandis que vous préparez la commande fournisseur ou le contrat d'achat, avez besoin d'ajouter une ligne supplémentaire à l'appel d'offre, vous pouvez le faire en cliquant sur **Ajouter une ligne** sur la grille de ligne de la page **Appel d'offre**. Vous pouvez uniquement afficher et modifier cette ligne sur la page **Appel d'offre**. Elle sera visible sur la page d'offre lorsqu'elle sera acceptée.

Lorsque vous acceptez une offre ou une ou plusieurs lignes d'une offre, une commande fournisseur ou un contrat d'achat est automatiquement généré. Vous pouvez ensuite rejeter les offres de tous les autres fournisseurs.

Dans la réponse, vous pouvez ajouter un code motif pour expliquer la raison pour laquelle vous avez accepté ou rejeté une offre.

Lorsque vous acceptez une offre de type **Demande d'achat**, les lignes de la demande d'achat sont mises à jour avec les informations suivantes qui reflètent les informations de l'offre acceptée :

-   Prix unitaire

-   Pourcentage de remise

-   Montant de remise

-   Frais sur achat

-   Frais de ligne

-   Fournisseur

-  Numéro externe

-   Description externe


Le tableau suivant indique les changements de statut de la demande de devis à mesure que vous acceptez et refusez les offres des fournisseurs.

<a name="statuses--highest-and-lowest"></a>Status – le moins élevé et le plus élevé.
-----------------------------

Sous l'onglet Fournisseur de la demande de devis, vous pouvez afficher les lignes ayant le statut le plus élevé et le moins élevé d'un fournisseur spécifique. Lorsque le fournisseur est ajouté, et qu'aucune ligne n'a encore été soumise, les statut le moins élevé et le plus élevé sont <strong>Créés.</strong>Lorsque l'appel d'offre est envoyé au fournisseur avec toutes les lignes, le statut des deux lignes est <strong>Envoyées</strong>. Si certaines lignes d'une offre d'un fournisseur sont acceptées et d'autres rejetées, les lignes rejetées obtiennent le statut le moins élevé qui est <strong>Rejetée</strong>, et les lignes acceptées obtiennent le statut le plus élevé qui est <strong>Acceptée</strong>.

Sur les lignes de demande de devis, vous pouvez afficher le statut le plus élevé et le moins élevé par ligne dans tous les fournisseurs. Si vous avez soumis une ligne à tous les fournisseurs de la demande de devis et que personne n'ont répondu, le statut le moins élevé et le plus élevé sont **Envoyée.** Lorsqu'au moins un fournisseur répond, le statut le plus élevé devient **Reçue**. Si vous ajoutez un nouveau fournisseur à la demande, le statut le moins élevé passe à **Créé**

Les statuts le plus élevé et le moins élevé de la demande de devis sont une agrégation du statut sous l'onglet \<Fournisseur et l'onglet Lignes.

Les statuts sont classés de la façon suivante du moins élevé au plus élevé : Créé, Envoyé, Reçu, Rejeté, Accepté, Refusé, Annulé.

Le tableau suivant indique les changements de statut de demande de devis lorsque vous créez une demande de devis avec des lignes et l'envoyez aux fournisseurs.

| **Action**                                | **Statut de demande de devis le moins élevé** | **Statut de demande de devis le plus élevé** | **Statut de ligne de demande de devis le moins élevé** | **Statut de ligne de demande de devis le plus élevé** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Créez l'en-tête et les lignes de la demande de devis.      | Créé(e)                    | Créé(e)                     | Créé(e)                         | Créé(e)                          |
| Envoyez les appels d'offre à tous les fournisseurs de la demande de devis. | Envoyé                       | Envoyé                        | Envoyé                            | Envoyé                             |
| Ajoutez un autre fournisseur.                       | Créé(e)                    | Envoyé                        | Créé(e)                         | Envoyé                             |
| Envoyez la demande de devis au deuxième fournisseur.        | Envoyé                       | Envoyé                        | Envoyé                            | Envoyé                             |

Toutes les lignes de l'appel d'offre associées à la demande de devis seront dans l'état **Envoyées**.

Le tableau suivant indique les changements de statut d'appel d'offre à mesure que vous recevez des offres et enregistrez les informations sur la feuille de réponse de l'appel d'offre.

| **Action**                                               | **Statut le moins élevé parmi toutes les lignes de tous les appels d'offre** | **Statut le plus élevé parmi toutes les lignes de tous les appels d'offre** | **Statut d'en-tête de demande de devis le moins élevé** | **Statut d'en-tête de demande de devis le plus élevé** | **Statut de ligne de demande de devis le moins élevé** | **Statut de ligne de demande de devis le plus élevé** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Enregistrez l'offre d'un fournisseur à un appel d'offre, et sauvegardez-la.        | Envoyé                                           | Reçu(e)                                        | Envoyé                              | Reçu(e)                           | Envoyé                            | Reçu(e)                         |
| Enregistrez l'offre du deuxième fournisseur à un appel d'offre, et sauvegardez-la. | Reçu(e)                                       | Reçu(e)                                        | Reçu(e)                          | Reçu(e)                           | Reçu(e)                        | Reçu(e)                         |


L'exemple ci-dessous présente les statuts le plus élevé et le moins élevé de la demande de devis pour laquelle est une offre a été reçue et l'autre offre a été acceptée. Lorsqu'une offre reçue est rejetée, le statut le moins élevé passe de reçu à rejeté dans l'en-tête et la ligne de la demande de devis.


|            <strong>Action</strong>             | <strong>Statut le moins élevé parmi toutes les lignes de tous les appels d'offre</strong> | <strong>Statut le plus élevé parmi toutes les lignes de tous les appels d'offre</strong> | <strong>Statut d'en-tête de demande de devis le moins élevé</strong> | <strong>Statut d'en-tête de demande de devis le plus élevé</strong> | <strong>Statut de ligne de demande de devis le moins élevé</strong> | <strong>Statut de ligne de demande de devis le plus élevé</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Acceptez l'une des offres. (ou au moins une ligne) |                          Reçu(e)                           |                           Acceptée                           |                    Reçu(e)                    |                    Acceptée                     |                   Reçu(e)                   |                   Acceptée                    |
|           Rejetez toutes les autres offres.           |                          Rejeté                           |                           Acceptée                           |                    Rejeté                    |                    Acceptée                     |                   Rejeté                   |                   Accepté(e)                    |

