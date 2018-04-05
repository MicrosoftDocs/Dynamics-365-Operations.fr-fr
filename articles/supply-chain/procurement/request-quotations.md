---
title: Appels d'offre
description: "Cette rubrique fournit une vue d'ensemble des appels d'offre. Les organisations émettent des appels d'offre lorsqu'elles souhaitent comparer les offres de plusieurs fournisseurs pour les articles ou les services qu'elles doivent acheter."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: b86363004b8702d1a654f2a1da49bba82fc8ff2a
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="requests-for-quotation-rfqs"></a>Appels d'offre

[!include[banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des appels d'offre. Les organisations émettent des appels d'offre lorsqu'elles souhaitent comparer les offres de plusieurs fournisseurs pour les articles ou les services qu'elles doivent acheter. Dans une demande de devis, vous demandez aux fournisseurs d'indiquer les prix et les délais de livraison pour des quantités de produits que vous spécifiez. Vous pouvez également demander aux fournisseurs de spécifier s'il y a des frais accessoires, comme des frais de transport, ou si le fournisseur offre des remises pour les commandes importantes ou le paiement anticipé de la facture fournisseur.

Le processus d'appel d'offre comprend les tâches suivantes :

1. Créer et envoyer un appel d'offre à un ou plusieurs fournisseurs.
2. Recevoir et enregistrer les réponses à l'appel d'offre (offres).
3. Transférer les offres que vous acceptez pour une commande fournisseur, un contrat d'achat ou une demande d'achat.

L'illustration suivante présente une vue d'ensemble du processus d'appel d'offre.

[![Processus RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Vous pouvez créer un appel d'offre à partir des commandes planifiées, d'une demande d'achat ou par saisie manuelle. L'appel d'offre que vous créez s'appelle un dossier d'appel d'offre. Il s'agit du document de base que vous utilisez pour délivrer un appel d'offre à chaque fournisseur.

Après avoir préparé le dossier d'appel d'offre et ajouté des fournisseurs, sélectionnez **Envoyer** dans le dossier d'appel d'offre. Un journal d'appel d'offre est généré pour chaque fournisseur auquel vous envoyez l'appel d'offre. Vous pouvez configurer les paramètres de gestion de l'impression pour l'action Envoyer afin d'imprimer un état pour chaque fournisseur dans une archive ou pour envoyer un état à l'adresse électronique de chaque fournisseur. En outre, vous pouvez utiliser le journal d'appel d'offre de chaque fournisseur pour générer un état que vous pouvez envoyer ou renvoyer au fournisseur ultérieurement. Vous pouvez également configurer l'action Envoyer afin de générer une feuille de réponse que le fournisseur peut compléter.

Cette rubrique décrit le processus de gestion des appels d'offre lorsque la collaboration fournisseur n'est pas utilisée. Si votre système est paramétré pour la collaboration fournisseur, les fournisseurs peuvent entrer des offres directement dans Microsoft Dynamics 365 for Finance and Operations. Pour plus d'informations, voir [Collaboration fournisseur avec les clients](vendor-collaboration-work-customers-dynamics-365-operations.md).
 
Si vous devez modifier un appel d'offre après son envoi, vous pouvez le renvoyer aux fournisseurs lorsque vous avez terminé à l'aide des deux actions de modification : Créer et Finaliser.

Lorsque vous recevez des offres par courrier électronique, vous devez les saisir sur la page **Réponses aux appels d'offre**. Si vous sélectionnez l'option **Copier des données dans la réponse**, les données telles que la quantité et les dates du dossier d'appel d'offre sont copiées dans la réponse. Vous pouvez modifier ces données pour refléter l'offre du fournisseur.

Si une deuxième itération d'une réponse est requise pour un fournisseur, sélectionnez **Retour** sur la page **Réponse à l'appel d'offre**. L'action Retour génère un nouveau journal et un état qui seront imprimés, archivés et envoyés conformément à vos paramètres de gestion de l'impression.

Si vous avez ajouté des critères de score à votre dossier d'appel d'offre, la réponse à la demande de devis dispose d'un volet de score où vous pouvez saisir les scores. Tous les scores s'affichent lorsque vous comparez les réponses sur la page **Comparer les réponses**. Sur cette page, vous pouvez également comparer les autres données de réponse, telles que le prix de la ligne, la date de livraison et le prix total.

Après avoir choisi une offre ou des offres partielles, vous pouvez les accepter et rejeter le reste. Les journaux d'acceptation, les journaux de rejet et les états correspondants sont générés et imprimés, archivés et envoyés conformément à vos paramètres de gestion de l'impression. Lorsque vous acceptez une offre ou des lignes spécifiques d'une offre, un contrat d'achat ou une commande fournisseur est générée, ou une demande d'achat est mise à jour, selon le type d'achat de l'appel d'offre. Vous pouvez créer un contrat commercial que vous pouvez utiliser ultérieurement pour toute réponse, peu importe si vous les avez acceptées ou rejetées.

Le statut d'un appel d'offre apparaît sur l'en-tête de l'appel d'offre et dépend du statut des lignes de l'appel d'offre. Le statut indique le niveau de traitement de l'appel d'offre. Chaque appel d'offre a deux valeurs de statut : le statut le moins élevé et le statut le plus élevé. Le statut le moins élevé correspond au stade le moins avancé de toute ligne de la demande de devis, et le statut le plus élevé au stade le plus avancé. Par exemple, si le stade le moins avancé dans un appel d'offre concerne une ligne créée, le statut le moins élevé pour l'appel d'offre est **Créé**. Si le stade le plus avancé dans l'appel d'offre concerne une ligne envoyée aux fournisseurs, le statut le plus élevé pour l'appel d'offre est **Envoyé**. Les statuts sont automatiquement mis à jour à mesure que vous traitez une demande de devis.

Vous pouvez consulter les statuts le moins élevé et le plus élevé d'un en-tête de demande de devis sur la page de liste **Toutes les demandes de devis**. Vous pouvez consulter les statuts le moins élevé et le plus élevé d'une ligne de demande de devis sur l'onglet **Lignes** sur la page **Demande de devis**.

Voici la séquence des statuts pour le traitement d'un appel d'offre :

1. **Créé**
2. **Envoyé**
3. **Reçue**
4. **Accepté**, **Annulé** ou **Rejeté**

Ces statuts sont décrits en détail plus loin dans cette rubrique.

## <a name="setting-up-rfq-functionality"></a>Paramétrage de la fonctionnalité de demande de devis

Avant de pouvoir créer un dossier de demande de devis, vous devez paramétrer les informations de demande de devis sur la page **Paramètres d'approvisionnement**. Lorsque vous créez une demande de devis, vous pouvez spécifier les valeurs par défaut qui sont copiées dans la demande de devis. Vous pouvez spécifier les valeurs par défaut suivantes :

- Le type d'achat de nouvelles demandes de devis : **Commande fournisseur** ou **Contrat d'achat**
- Date et heure d'expiration
- Informations de livraison et conditions de paiement
- Champs devant être inclus dans la réponse de demande de devis

Vous pouvez remplacer ces valeurs pour un dossier de demande de devis spécifique.

Vous devez également configurer le processus d'avenant. Dans le cadre de cette configuration, vous pouvez activer le verrouillage du champ. Lorsqu'un verrouillage de champ est activé, un professionnel de l'approvisionnement qui souhaite modifier un appel d'offre doit d'abord sélectionner **Créer** dans la section **Avenant** de l'onglet **Devis**. Ensuite, une fois que l'appel d'offre a été mis à jour avec l'avenant, le professionnel de l'approvisionnement doit terminer le processus en sélectionnant **Finaliser**. L'action Finaliser génère un message e-mail qui informe les fournisseurs de l'appel d'offre modifié.

Sur la page **Paramètres de l'approvisionnement**, sélectionnez le modèle à utiliser pour la notification par e-mail qui est envoyée aux fournisseurs. Lorsqu'un modèle est créé, il peut contenir les jetons de remplacement suivants :

- %Dossier d'appel d'offre%
- %Motif de retour de l'offre%
- %Motif de l'avenant%
- %Avenant préparé par%
- %Société%
- %Nom du dossier d'appel d'offre%
- %ExpiryDateTime%
- %Date%

Les jetons %Motif de retour de l'offre% et %Motif de l'avenant% sont remplacés par du texte que le professionnel de l'approvisionnement peut saisir lorsqu'il remplit l'avenant dans l'assistant **Avenant**. Les valeurs des jetons %Avenant préparé par% et %Société% sont automatiquement extraites de la demande de devis. Le jeton %Date% est remplacé par la date actuelle.

Un modèle d'e-mail est également nécessaire si vous annulez un appel d'offre après son envoi. Ce modèle d'e-mail permet d'envoyer la notification d'annulation aux personnes à contacter chez le fournisseur. Le modèle doit être sélectionné sur la page **Paramètres d'approvisionnement**. Lorsque le modèle est créé, il peut contenir les jetons de remplacement suivants :

- %Motif d'annulation%
- %Dossier d'appel d'offre% 
- %Appel d'offre annulé par%
- %Société%
- %Nom du dossier d'appel d'offre%
- %Date%

Le jeton %Motif d'annulation% est remplacé par le texte que le professionnel de l'approvisionnement peut saisir dans l'assistant **Annulation**. Le jeton %Date% est remplacé par la date actuelle.

Si vous souhaitez utiliser des codes motif d'une demande de devis pour indiquer la raison pour laquelle une offre a été rejetée ou acceptée, vous devez paramétrer des codes motif sur la page **Motifs de fournisseur**.

Sur la page **Paramétrage d'écran** du module Approvisionnements, vous pouvez configurer l'apparence de vos documents d'appel d'offre imprimés ou stockés.

> [!NOTE]
> Pour une configuration du secteur public, vous devez utiliser le processus d'avenant pour modifier un appel d'offre qui a déjà été envoyé. Lorsqu'un appel d'offre est envoyé, les champs sont verrouillés. Par conséquent, pour apporter des modifications à l'appel d'offre, vous devez sélectionner **Créer** pour démarrer le processus d'avenant, comme décrit précédemment. Le comportement de verrouillage est contrôlé par l'option **Verrouiller les appels d'offre lorsqu'ils sont envoyés** dans la page **Paramètres d'approvisionnement**. Par défaut, ce paramètre est défini sur **Oui** et pour une configuration du secteur public, le paramètre par défaut ne peut pas être modifié. Par conséquent, bien que le processus d'avenant puisse être géré manuellement dans une configuration hors secteur public, il doit être utilisé pour une configuration du secteur public.

Lorsque vous créez une demande de devis pour une commande fournisseur et ajoutez un article en stock à la demande de devis, un mouvement de stock ayant le statut de réception **Réception de devis** est également créé. Seules les lignes de demande de devis avec ce statut sont prises en compte lorsque vous utilisez un plan général pour calculer les approvisionnements. Si vous souhaitez que le plan général inclut les lignes de demande de devis comme une réception prévue, vous devez configurer ce comportement dans le paramétrage de la planification principale.

Un gestionnaire ou agent des achats peut créer et tenir à jour des types de sollicitation, afin qu'ils correspondent aux exigences d'approvisionnement de l'organisation. Chaque type de sollicitation peut être associé à une méthode d'attribution de score. Ces dernières consistent en un ensemble de critères pouvant être utilisés lorsque vous attribuez un score aux offres. Vous devez paramétrer des types de sollicitation, les méthodes d'attribution de score et les critères d'attribution de score sur les pages **Type de sollicitation** et **Méthode d'attribution de score**.

## <a name="creating-and-sending-an-rfq"></a>Création et envoi d'un appel d'offre

Vous créez une demande de devis, sélectionnez les fournisseurs pour lesquels vous souhaitez soumettre une offre de devis, puis vous envoyez le devis aux fournisseurs. Vous pouvez utiliser la gestion de l'impression afin d'acheminer l'état des appels d'offre et les états de fiche de réponse à votre destination préférée.

Vous pouvez créer un appel d'offre pour le type d'achat **Commande fournisseur** ou **Contrat d'achat**.

Si l'appel d'offre est de type **Commande fournisseur**, le comportement suivant se produit :

- Lorsque les lignes de demande de devis sont créées, les transactions du stock sont générées avec un statut de réception de **Réception de devis**.
- Lorsque vous acceptez une offre, une commande fournisseur est générée.

Si l'appel d'offre est de type **Contrat d'achat**, le comportement suivant se produit :

- La demande de devis est utilisée pour un accord sur l'achat d'une quantité ou d'une valeur spécifique d'un produit au fil du temps. Vous devez sélectionner l'intervalle de dates qui s'applique au contrat d'achat et le nom de la personne qui gère le contrat d'achat.
- Lorsque vous acceptez une offre, un contrat d'achat est généré.

Si la demande de devis est générée à partir d'une demande d'achat, le type **Demande d'achat** est automatiquement attribué. Vous ne pouvez pas créer manuellement de demande de devis de type **Demande d'achat**.

Vous pouvez créer un appel d'offre à partir d'une demande d'achat uniquement si le statut de la demande d'achat est **En cours de révision** et si vous êtes affecté pour effectuer la tâche de workflow suivante. Les lignes de la demande d'achat sont mises à jour automatiquement lorsque vous acceptez les lignes à partir des réponses d'appel d'offre (offres) que vous avez reçues des fournisseurs. Tant que la demande de devis est en cours, vous ne pouvez effectuer aucune action (terminer, rejeter ou approuver) sur la demande d'achat.

Lorsque vous créez un appel d'offre, vous pouvez sélectionner un type de sollicitation. Le type de sollicitation détermine l'ensemble de critères d'attribution de score utilisés pour attribuer un score aux réponses à la demande de devis.

Vous pouvez ajouter un questionnaire à un dossier de demande de devis. Ce questionnaire s'affiche ensuite sur toutes les réponses une fois que vous envoyez la demande de devis.

Il existe trois méthodes pour sélectionner les fournisseurs à ajouter à un dossier de demande de devis :

- Ajout de fournisseurs l'un après l'autre.
- Recherchez tous les fournisseurs qui répondent à des critères spécifiques.
- Ajoutez automatiquement tous les fournisseurs qui sont validés pour les catégories d'approvisionnement utilisées sur les lignes de demande de devis.

Lorsque l'appel d'offre est prêt, sélectionnez **Envoyer**. L'action Envoyer génère des journaux et des états qui seront imprimés, archivés et envoyés conformément à vos paramètres de gestion de l'impression.

Si vous définissez **Utiliser le fournisseur pour recalculer les prix** et **Utiliser les informations relatives à l'article spécifiques au fournisseur** sur **Oui** sur la page **Envoi de l'appel d'offre** lorsque vous avez soumis l'appel d'offre aux fournisseurs, certaines informations spécifiques au fournisseur sont entrées automatiquement. Vous pouvez modifier ces informations sur la page **Réponse de demande de devis**.

Le tableau suivant indique les changements de statut de demande de devis lorsque vous créez une demande de devis et l'envoyez aux fournisseurs.

| Action                             | Statut d'en-tête d'appel d'offre le moins élevé | Statut d'en-tête d'appel d'offre le plus élevé                        | Statut de ligne d'appel d'offre le moins élevé | Statut de ligne d'appel d'offre le plus élevé |
|------------------------------------|--------------------------|--------------------------------------------------|------------------------|-------------------------|
| Créez l'en-tête et les lignes de l'appel d'offres.    | Créé                  | Créé                                          | Créé                | Créé |
| Envoyez l'appel d'offre à un fournisseur spécifique. | Envoyé                     | Envoyé                                             | Envoyé                   | Envoyé |
| Ajoutez un autre fournisseur.                | Créé                  | Envoyé (L'appel d'offre a été envoyé à un seul fournisseur.) | Créé                | Envoyé |
| Envoyez la demande de devis au deuxième fournisseur. | Envoyé                     | Envoyé                                             | Envoyé                   | Envoyé |

> [!NOTE]
> Vous pouvez ajouter des fournisseurs à un appel d'offre à tout moment. Les statuts le plus élevé et le mois élevé sont mis à jour en fonction des nouveaux fournisseurs. Par exemple, si vous avez reçu des offres de tous les fournisseurs et accepté au moins une ligne d'une offre, le statut le moins élevé de l'en-tête de la demande de devis est **Rejeté** et le statut le plus élevé est **Accepté**. Si vous ajoutez un nouveau fournisseur, le statut le moins élevé de toute ligne est désormais **Créé**. Le statut le moins élevé de l'en-tête de l'appel d'offre est mis à jour sur **Créé**, mais le statut le plus élevé reste **Accepté**.

## <a name="amending-an-rfq"></a>Modification d'une demande de devis

Parfois, vous devez modifier une demande de devis après son envoi. Vous devrez peut-être modifier un appel d'offre si, par exemple, les dates de livraison ont changé ou vous souhaitez des produits supplémentaires ou différentes quantités de produits. Vous pouvez configurer le processus d'avenant de manière à ce qu'il soit plus ou moins restrictif.

Si vous configurez le processus d'avenant de manière à ce qu'il soit plus restrictif, avant de modifier les champs d'un dossier d'appel d'offre qui a déjà été soumis, vous devez sélectionner **Créer** dans le dossier d'appel d'offre pour démarrer un avenant. Après avoir terminé vos modifications, vous devez sélectionner **Finaliser**. Vous êtes ensuite guidé dans le processus d'ajout d'informations pour le message électronique envoyé pour notifier les fournisseurs de l'avenant. L'état mis à jour de l'appel d'offre, qui inclut une note d'avenant, est automatiquement joint au message électronique.

Si vous configurez le processus d'avenant de manière à ce qu'il soit moins restrictif, il n'est pas nécessaire de sélectionner **Créer** pour pouvoir modifier les champs d'un dossier d'appel d'offre qui a déjà été envoyé. Toutefois, vous devez ajouter manuellement une note d'avenant dans l'appel d'offre et renvoyer le dossier. Notez que cette approche ne peut être utilisée que si aucune des réponses (offres) n'a été modifiée. Si vous avez entré une réponse et que son état est **Reçu**, le bouton **Envoyer** n'est pas disponible. Dans ce cas, vous devez sélectionner **Créer** puis **Finaliser**, comme vous devez le faire dans le processus plus restrictif. La réponse est ensuite réinitialisée pour refléter les modifications du dossier d'appel d'offre. 

Si les fournisseurs utilisent l'interface de collaboration fournisseur pour saisir des offres, vous devez toujours utiliser le processus d'avenant pour informer les fournisseurs des modifications du dossier d'appel d'offre. Cela permet d'éviter la situation où les fournisseurs font une offre sur un dossier d'appel d'offre obsolète alors que leur offre est en cours. Pour plus d'informations sur la collaboration fournisseur, voir [Collaboration fournisseur avec des fournisseurs externes](vendor-collaboration-work-external-vendors.md). 

Si vous voulez inviter d'autres fournisseurs à faire une offre et qu'aucune modification n'a été apportée au dossier d'appel d'offre, vous pouvez utiliser le bouton **Envoyer**. Les fournisseurs que vous avez ajoutés s'affichent sur la page **Envoyer** et reçoivent l'invitation par courrier électronique.

## <a name="receiving-and-registering-rfq-replies"></a>Réception et enregistrement des réponses à la demande de devis

Lorsque vous envoyez une demande de devis, une feuille de réponse est automatiquement générée. Lorsque vous recevez des réponses (enchères) à une demande de devis, vous devez saisir les éléments de réponse envoyés par chaque fournisseur dans une réponse globale spécifique à chaque fournisseur. Si vous avez ajouté des critères d'attribution de score, vous pouvez attribuer un score aux réponses. De même, vous pouvez comparer les offres des fournisseurs en les classant selon vos critères d'évaluation, notamment le meilleur prix total ou le meilleur délai de livraison proposé.

Si un questionnaire est joint au dossier d'appel d'offre, vous devez saisir manuellement les réponses aux questions sur la feuille de réponse.

Vous pouvez également entrer d'autres lignes, si le dossier d'appel d'offre autorise d'autres lignes. Dans l'organisateur **Lignes de devis d'achat**, sélectionnez **Ajouter une ligne**. Puis entrez les informations relatives au produit, telles que le numéro d'article ou la catégorie d'approvisionnement, la quantité, le prix et la remise.

Si vous avez entré une réponse, mais si vous avez besoin d'une nouvelle offre du fournisseur, vous pouvez renvoyer la demande de devis. Un nouveau journal et un état sont générés et vous pouvez les utiliser pour demander des modifications de la part du fournisseur.

Vous pouvez afficher une vue d'ensemble de toutes les demandes de devis et leurs statuts de réponse sur la page **Suivi de la demande de devis**.

Le tableau suivant indique les changements de statut d'appel d'offre à mesure que vous recevez des offres et enregistrez les informations sur la feuille de réponse de l'appel d'offre.

| Action                                         | Statut d'offre le moins élevé | Statut d'offre le plus élevé | Statut d'en-tête d'appel d'offre le moins élevé | Statut d'en-tête d'appel d'offre le plus élevé | Statut de ligne d'appel d'offre le moins élevé | Statut de ligne d'appel d'offre le plus élevé |
|------------------------------------------------|-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Enregistrez l'offre d'un fournisseur, et sauvegardez-la.        | Envoyé              | Reçu(e)           | Envoyé                     | Reçu(e)                  | Envoyé                   | Reçu(e) |
| Enregistrez l'offre du deuxième fournisseur, et sauvegardez-la. | Reçu(e)          | Reçu(e)           | Reçu(e)                 | Reçu(e)                  | Reçu(e)               | Reçu(e) |

> [!NOTE]
> Si vous renvoyez une offre à un fournisseur pour une négociation supplémentaire, les statuts le moins élevé et le plus élevé restent tous les deux **Reçue**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Acceptation et rejet des offres, et transfert des offres reçues vers les documents en aval

Après avoir identifié l'offre la plus intéressante, par exemple celle offrant le meilleur prix total, vous pouvez accepter l'offre. Vous pouvez recevoir certaines lignes d'une offre et rejeter d'autres. Vous pouvez également recevoir des lignes de différents fournisseurs. Sachez que si vous acceptez certaines lignes, vous devez rejeter toutes les autres. Par conséquent, si vous souhaitez accepter d'autres lignes, vous devez sélectionner **Annuler** à l'invite. Le statut de la réponse à l'appel d'offre pour chaque fournisseur dont vous acceptez des offres ou des lignes est mis jour sur **Accepté**. 

Lorsque vous acceptez une offre ou des lignes spécifiques d'une offre, une commande fournisseur ou un contrat d'achat est automatiquement généré. Vous pouvez ensuite rejeter les offres de tous les autres fournisseurs.

Dans la réponse, vous pouvez ajouter un code motif pour expliquer la raison pour laquelle vous avez accepté ou rejeté une offre.

Lorsque vous acceptez une réponse de demande de devis de type **Demande d'achat**, les lignes de la réponse de demande de devis mettent à jour les lignes de la demande d'achat avec les informations suivantes :

- Prix unitaire
- Pourcentage de remise
- Montant de remise
- Frais sur achat
- Frais de ligne
- Fournisseur
- Numéro externe
- Description externe

Le tableau suivant indique les changements de statut de la demande de devis à mesure que vous acceptez et refusez les offres des fournisseurs.

| Action                      | Statut d'offre le moins élevé | Statut d'offre le plus élevé | Statut d'en-tête de demande de devis le moins élevé | Statut d'en-tête d'appel d'offre le plus élevé | Statut de ligne d'appel d'offre le moins élevé | Statut de ligne d'appel d'offre le plus élevé |
|-------------------------    |-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Acceptez l'une des offres.     | Reçu(e)          | Acceptée           | Reçu(e)                 | Acceptée                  | Reçu(e)               | Acceptée |
| Rejetez toutes les autres offres.  | Rejeté          | Acceptée           | Rejeté                 | Acceptée                  | Rejeté               | Accepté(e) |

