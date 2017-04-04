---
title: Le demande de devis (RFQs)
description: "Cet article fournit une vue d&quot;ensemble des demandes de devis émises par les organisations lorsqu&quot;elles doivent acheter des articles ou des services et souhaitent recevoir des offres de plusieurs fournisseurs. Dans une demande de devis, vous demandez aux fournisseurs d&quot;indiquer les prix et les délais de livraison pour des quantités de produits que vous spécifiez. Vous pouvez également demander aux fournisseurs de spécifier s&quot;il y a des frais accessoires, comme des frais de transport, ou si le fournisseur offre des remises pour les commandes importantes ou le paiement anticipé de la facture fournisseur."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: d70b4ae0a6b177508021ee72481333cf6f265069
ms.lasthandoff: 03/31/2017


---

# <a name="request-for-quotations-rfqs"></a>Le demande de devis (RFQs)

Cet article fournit une vue d'ensemble des demandes de devis émises par les organisations lorsqu'elles doivent acheter des articles ou des services et souhaitent recevoir des offres de plusieurs fournisseurs. Dans une demande de devis, vous demandez aux fournisseurs d'indiquer les prix et les délais de livraison pour des quantités de produits que vous spécifiez. Vous pouvez également demander aux fournisseurs de spécifier s'il y a des frais accessoires, comme des frais de transport, ou si le fournisseur offre des remises pour les commandes importantes ou le paiement anticipé de la facture fournisseur.

Le processus de demande de devis couvre les actions suivantes :

-   création et envoi d'une demande de devis à un ou plusieurs fournisseurs ;
-   réception et enregistrement des réponses à la demande de devis (offres) ;
-   transfert des réponses acceptées pour une commande fournisseur, un contrat d'achat ou une demande d'achat.

L'illustration suivante présente une vue d'ensemble du processus de demande de devis.  

[processus de demande![à partir![(]. /media/rfq-process-458x1024.jpg)](. /media/rfq-process.jpg)  

Vous pouvez créer une demande de devis à partir des commandes planifiées, une demande d'achat ou une entrée manuelle. L'appel d'offre que vous créez s'appelle un dossier d'appel d'offre et il s'agit là du document de base que vous utilisez pour délivrer un appel d'offre à chaque fournisseur. Après avoir préparer la demande de devis et ajouter des fournisseurs, cliquez sur ** l'envoi ** sur la demande de devis, puis un journal des demandes de devis est généré pour chaque fournisseur que vous avez soumis la demande de devis. Vous pouvez configurer les paramètres de gestion de l'impression pour l'action à envoyer à imprimer un état pour chaque fournisseur dans une archive ou soumettre un état à l'adresse électronique de chaque fournisseur. En outre, le journal d'appel d'offre de chaque fournisseur peut être utilisé pour générer un rapport que vous pouvez envoyer ou renvoyer à un fournisseur ultérieurement. Vous pouvez également configurer l'action Envoyer afin de générer une feuille de réponse que le fournisseur peut compléter.  

Si vous devez modifier un appel d'offre après son envoi, vous pouvez l'envoyer à nouveau aux fournisseurs lorsque vous avez terminé.  

Lorsque vous recevez des offres, vous devez les saisir sur la page **Réponses aux demandes de devis**. Si vous sélectionnez l'option **Copier des données dans la réponse**, les données telles que la quantité et les dates du dossier d'appel d'offre sont copiées dans la réponse. Vous pouvez modifier ces données pour refléter l'offre du fournisseur.  

Si une deuxième itération d'une réponse est requise pour un fournisseur spécifique, cliquez sur **Retour **sur la page** Réponse de demande de devis**. L'action Retour génère un nouveau journal et un rapport qui sera imprimé, archivé et envoyé conformément à vos paramètres de gestion des impressions.  

Si vous avez ajouté des critères de score à votre dossier d'appel d'offre, la réponse à la demande de devis dispose d'un volet de score où vous pouvez saisir les scores. Tous les scores s'affichent lorsque vous comparez les réponses sur la page **Comparer les réponses **, sur laquelle vous pouvez également comparer les autres données de réponse, telles que le prix de ligne, la date de livraison et le prix total.  

Après avoir opté pour une offre ou des offres partielles, vous pouvez les accepter et rejeter le reste. Les journaux d'acceptation, les journaux de rejet et les rapports correspondants sont générés. Celles-ci seront imprimés, archivés, et envoyés en fonction de les paramètres de gestion de l'impression. Lorsque vous acceptez une offre ou des lignes spécifiques dans une offre, un contrat d'achat ou fournisseur est généré, ou une demande d'achat est mise à jour, selon le type d'achat de demande de devis. Vous pouvez créer un contrat commercial que vous pouvez utiliser ultérieurement pour toute réponse, peu importe si vous les avez acceptées ou rejetées.  

Le statut d'un appel d'offre apparaît dans l'en-tête de l'appel d'offre et dépend du statut des lignes de l'appel d'offre. Le statut indique où en est l'appel d'offre dans le cadre de son traitement. Chaque appel d'offre a deux valeurs pour le statut : le moins élevé et le plus élevé. Le statut le moins élevé correspond au stade le moins avancé de toute ligne de la demande de devis, et le statut le plus élevé au stade le plus avancé. Par exemple, si le stade le moins avancé dans un appel d'offre concerne une ligne créée, le statut le moins élevé pour l'appel d'offre est **Créé**. Si le stade le plus avancé dans l'appel d'offre concerne une ligne envoyée aux fournisseurs, le statut le plus élevé pour l'appel d'offre est **Envoyé**. Les statuts sont automatiquement mis à jour à mesure que vous traitez une demande de devis.  

Vous pouvez consulter les statuts le moins élevé et le plus élevé d'un en-tête de demande de devis sur la page de liste **Toutes les demandes de devis**. Vous pouvez consulter les statuts le moins élevé et le plus élevé d'une ligne de demande de devis sur l'onglet **Lignes** sur la page **Demande de devis**.  

Voici la séquence des statuts pour traiter les demandes de devis :

1.  **Créé**
2.  **Sent**
3.  **Received**
4.  ** Accepté **/** annulé **/** rejeté **

Les statuts sont décrits plus en détail dans les sections ultérieures de cet article.

## <a name="setting-up-rfq-functionality"></a>Paramétrage de la fonctionnalité de demande de devis
Avant de pouvoir créer un dossier de demande de devis, vous devez paramétrer les informations de demande de devis sur la page **Paramètres d'approvisionnement**. Lorsque vous créez une demande de devis, vous pouvez spécifier les valeurs par défaut qui sont copiées dans la demande de devis. Vous pouvez spécifier les valeurs par défaut suivantes :

-   Le type d'achat de nouvelles demandes de devis : **Commande fournisseur** ou **Contrat d'achat**
-   Paramètres pour la date et l'heure d'expiration
-   Informations de livraison et conditions de paiement.
-   Champs devant être inclus dans la réponse de demande de devis

Vous pouvez remplacer ces valeurs pour un dossier de demande de devis spécifique. Vous devez également configurer le processus d'avenant. Dans le cadre de cette configuration, vous pouvez activer le verrouillage du champ. Lorsque le verrouillage du champ est activé, un professionnel de l'approvisionnement qui souhaite modifier une demande de devis doit tout d'abord cliquer sur **Créer** dans la section **Avenant** de l'onglet **Devis**. Une fois la demande de devis a été mis à jour avec les modifications, le professionnel d'approvisionnement doit effectuer le processus en cliquant sur ** finaliser à mettre fin **. ** ** Action de finalisation génère un message e-mail qui signale les fournisseurs sur la demande de devis modifié. Vous sélectionnez le modèle de la notification par e-mail qui est envoyée aux fournisseurs sur la page **Paramètres de l'approvisionnement**. Lorsqu'un modèle est créé, il peut contenir les jetons de remplacement suivants :

-   %Motif de retour de l'offre%
-   %Motif de l'avenant%
-   %Avenant préparé par%
-   %Société%

Les jetons %Motif de retour de l'offre% et %Motif de l'avenant% sont remplacés par du texte que le professionnel de l'approvisionnement peut saisir lorsqu'il remplit l'avenant dans l'assistant **Avenant**. Les valeurs des jetons %Avenant préparé par% et %Société% sont automatiquement extraites de la demande de devis.  

Si vous souhaitez utiliser des codes motif d'une demande de devis pour indiquer la raison pour laquelle une offre a été rejetée ou acceptée, vous devez paramétrer des codes motif sur la page **Motifs de fournisseur**.  

Vous pouvez configurer l'apparence de vos documents de demande de devis imprimés ou stockés sur la page **Paramétrage d'écran** dans Approvisionnements.  

Lorsque vous créez une demande de devis pour une commande fournisseur et ajoutez un article en stock à la demande de devis, un mouvement de stock ayant le statut de réception **Réception de devis** est également créé. Seules les lignes de demande de devis avec ce statut sont prises en compte lorsque vous utilisez un plan général pour calculer les approvisionnements. Si vous souhaitez que le plan général inclut les lignes de demande de devis comme une réception prévue, vous devez configurer ce comportement dans le paramétrage de la planification principale.  

En tant que gestionnaire des achats ou agent, vous pouvez créer et tenir à jour des types de sollicitation, afin qu'ils correspondent aux exigences de l'approvisionnement de votre organisation. Chaque type de sollicitation peut entraîner des méthodes d'attribution de score. Ces dernières consistent en un ensemble de critères pouvant être utilisés lorsque vous attribuez un score aux offres. Vous devez paramétrer des types de sollicitation, les méthodes d'attribution de score et les critères d'attribution de score sur les pages **Type de sollicitation** et **Méthode d'attribution de score**.

## <a name="creating-and-sending-an-rfq"></a>Création et envoi d'un appel d'offre
Vous créez une demande de devis, sélectionnez les fournisseurs pour lesquels vous souhaitez soumettre une offre de devis, puis vous envoyez le devis aux fournisseurs. Vous pouvez utiliser la gestion des impressions afin d'acheminer le rapport des demandes de devis et les rapports de fiche de réponse à votre destination préférée.  

Vous pouvez créer une demande de devis pour le type d'achat **Commande fournisseur** ou **Contrat d'achat**.  

Si la demande de devis est générée à partir d'une demande d'achat, le type **Demande d'achat** est automatiquement attribué. Vous ne pouvez pas créer manuellement de demande de devis de type **Demande d'achat**. Si la demande de devis est de type **Commande fournisseur** :

-   Lorsque les lignes de demande de devis sont créées, les transactions du stock sont générées avec un statut de réception de **Réception de devis**.
-   Lorsque vous acceptez une offre, une commande fournisseur est générée.

Si la demande de devis est de type **Contrat d'achat** :

-   La demande de devis est utilisée pour un accord sur l'achat d'une quantité ou d'une valeur spécifique d'un produit au fil du temps. Vous devez sélectionner l'intervalle de dates qui s'applique au contrat d'achat et le nom de la personne qui gère le contrat d'achat.
-   Lorsque vous acceptez une offre, un contrat d'achat est généré.

Vous pouvez créer une demande de devis à partir d'une demande d'achat uniquement si le statut de la demande d'achat est **En cours de révision **et si vous êtes affecté pour effectuer la tâche de workflow suivante. Les lignes de la demande d'achat sont mises à jour automatiquement comme vous acceptez les lignes à partir des réponses de demande de devis (offres) que vous avez reçues des fournisseurs. Tant que la demande de devis est en cours, vous ne pouvez effectuer aucune action (terminer, rejeter ou approuver) sur la demande d'achat.  

Lorsque vous créez une demande de devis, vous pouvez sélectionner un type de sollicitation spécifique. Le type de sollicitation détermine l'ensemble de critères d'attribution de score utilisés pour attribuer un score aux réponses à la demande de devis.  

Vous pouvez ajouter un questionnaire à un dossier de demande de devis. Ce questionnaire s'affiche ensuite sur toutes les réponses une fois que vous envoyez la demande de devis.  

Il existe trois méthodes pour sélectionner les fournisseurs à ajouter à un dossier de demande de devis :

-   Ajout de fournisseurs l'un après l'autre.
-   Recherchez tous les fournisseurs qui répondent à des critères spécifiques.
-   Ajoutez automatiquement tous les fournisseurs qui sont validés pour les catégories d'approvisionnement utilisées sur les lignes de demande de devis.

Lorsque la demande de devis est prête, cliquez sur **Envoyer**. L'action Envoyer génère des journaux et des rapports qui seront imprimés, archivés et envoyés conformément à vos paramètres de gestion des impressions.  

Si vous avez coché les cases **Utiliser le fournisseur pour recalculer les prix** et **Utiliser les informations relatives à l'article spécifiques au fournisseur** sur la page **Envoi de la demande de devis** lorsque vous avez soumis la demande aux fournisseurs, certaines informations spécifiques au fournisseur sont entrées automatiquement. Vous pouvez modifier ces informations sur la page **Réponse de demande de devis**.  

Le tableau suivant indique les changements de statut de demande de devis lorsque vous créez une demande de devis et l'envoyez aux fournisseurs.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Action**                         | **Lowest RFQ header status** | **Highest RFQ header status**                   | **Lowest RFQ line status** | **Highest RFQ line status** |
| Créez l'en-tête et les lignes de l'appel d'offres.    | Créé                      | Créé                                         | Créé                    | Créé                     |
| Envoyez l'appel d'offre à un fournisseur spécifique. | Envoyé                         | Envoyé                                            | Envoyé                       | Envoyé                        |
| Ajoutez un autre fournisseur.                | Créé                      | Envoyé (La demande de devis a été envoyée à un seul fournisseur.) | Créé                    | Envoyé                        |
| Envoyez la demande de devis au deuxième fournisseur. | Envoyé                         | Envoyé                                            | Envoyé                       | Envoyé                        |

**Remarque :** Vous pouvez ajouter des fournisseurs à une demande de devis à tout moment. Les statuts le plus élevé et le mois élevé changent en fonction des fournisseurs ajoutés. Par exemple, si vous avez reçu des offres de tous les fournisseurs et accepté au moins une ligne d'une offre, le statut le moins élevé de l'en-tête de la demande de devis est **Rejeté** et le statut le plus élevé est **Accepté**. Si vous ajoutez un nouveau fournisseur, le statut le moins élevé de toute ligne est désormais **Créé**. Le statut le moins élevé de l'en-tête de la demande de devis devient donc **Créé**, et le statut le plus élevé reste **Accepté**.

## <a name="amending-an-rfq"></a>Modification d'une demande de devis
Parfois, vous devez modifier une demande de devis après son envoi. Cela peut se produire, parce que, par exemple, les dates de livraison ont changé ou parce que vous souhaitez des produits supplémentaires ou différentes quantités de produits. Vous pouvez configurer le processus d'avenant afin qu'il soit plus ou moins restrictif.  

Si vous utilisez le processus d'avenant plus restrictif, vous devez cliquer sur **Créer** sur le dossier de demande de devis pour démarrer un avenant avant de pouvoir modifier les champs sur le dossier de demande de devis. Après avoir terminé d'apporter vos modifications, vous devez cliquer sur **Finaliser**. Vous êtes ensuite guidé via le processus d'ajout d'informations pour le message électronique envoyé pour notifier les fournisseurs de l'avenant. L'état mis à jour de la demande de devis, qui inclut une note d'avenant, est automatiquement joint au message.  

Si vous utilisez le processus d'avenant moins restrictif, vous n'avez pas à créer d'avenant avant de pouvoir modifier les champs sur un dossier de demande de devis qui a déjà été envoyé. Toutefois, vous devez ajouter manuellement une note d'avenant sur la demande de devis.

## <a name="receiving-and-registering-rfq-replies"></a>Réception et enregistrement des réponses à la demande de devis
Lorsque vous envoyez une demande de devis, une feuille de réponse est automatiquement générée. Lorsque vous recevez des réponses (enchères) à une demande de devis, vous devez saisir les éléments de réponse envoyés par chaque fournisseur dans une réponse globale spécifique à chaque fournisseur. Si vous avez ajouté des critères d'attribution de score, vous pouvez attribuer un score aux réponses. De même, vous pouvez comparer les offres des fournisseurs en les classant selon vos critères d'évaluation, notamment le meilleur prix total ou le meilleur délai de livraison proposé.  

Si un questionnaire est joint au dossier de demande de devis, vous devez saisir manuellement les réponses aux questions dans la feuille de réponse.  

Si vous devez entrer les autres lignes, et si le dossier de demande de devis permet de faire, sur l'organisateur **Lignes de devis d'achat**, cliquez sur **Ajouter une ligne**. Puis entrez les informations relatives au produit, telles que le numéro d'article ou la catégorie d'approvisionnement, la quantité, le prix et la remise.  

Si vous avez entré une réponse mais souhaitez une nouvelle devis du fournisseur, vous pouvez renvoyer la demande de devis. Un nouveau journal et signalera que vous pouvez utiliser pour demander des modifications du fournisseur.  

Vous pouvez afficher une vue d'ensemble de toutes les demandes de devis et leurs statuts de réponse sur la page **Suivi de la demande de devis**.  

Le tableau suivant indique les changements de statut de la demande de devis à mesure que vous recevez des offres et enregistrez les informations dans la feuille de réponse de la demande de devis.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Action**                                     | **Lowest bid status** | **Highest bid status** | **Lowest RFQ header status** | **Highest RFQ header status** | **Lowest RFQ line status** | **Highest RFQ line status** |
| Enregistrez l'offre d'un fournisseur, et sauvegardez-la.        | Envoyé                  | Reçu(e)               | Envoyé                         | Reçu(e)                      | Envoyé                       | Reçu(e)                    |
| Enregistrez l'offre du deuxième fournisseur, et sauvegardez-la. | Reçue              | Reçue               | Reçue                     | Reçue                      | Reçue                   | Reçue                    |

**Remarque :** Si vous envoyez une offre à un fournisseur pour une négociation supplémentaire, les statuts le moins élevé et le plus élevé restent tous les deux **Reçue**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Acceptation et rejet des offres, et transfert des offres reçues vers les documents en aval

Après avoir identifié l'offre la plus intéressante, par exemple celle offrant le meilleur prix total, vous pouvez accepter l'offre. Le statut de la réponse de demande de devis pour ce fournisseur est mis à jour avec le statut **Accepté**. Lorsque vous recevez une offre ou des lignes spécifiques d'une offre, une commande fournisseur ou un contrat d'achat est généré automatiquement, et vous pouvez rejeter les offres des autres fournisseurs.  

Lorsque vous acceptez une réponse de demande de devis de type **Demande d'achat**, les lignes de la réponse de demande de devis mettent à jour les lignes de la demande d'achat avec les informations suivantes :

-   Prix unitaire
-   Pourcentage de remise
-   Montant de remise
-   Frais sur achat
-   Frais de ligne
-   Fournisseur
-   Numéro externe
-   Description externe

Dans la réponse, vous pouvez ajouter un code motif pour expliquer la raison pour laquelle vous avez accepté ou rejeté une offre.  

Vous pouvez recevoir certaines lignes d'une offre et rejeter d'autres. Vous pouvez également recevoir des lignes de différents fournisseurs. Il suffit simplement de savoir que si vous acceptez certaines lignes, vous devrez rejeter toutes les autres. Par conséquent, si vous souhaitez accepter d'autres lignes, vous devez cliquer sur **Annuler** à l'invite.  

Le tableau suivant indique les changements de statut de la demande de devis à mesure que vous acceptez et refusez les offres des fournisseurs.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Action**              | **Lowest bid status** | **Highest bid status** | **Lowest RFQ header status** | **Highest RFQ header status** | **Lowest RFQ line status** | **Highest RFQ line status** |
| Acceptez l'une des offres. | Reçu(e)              | Accepté(e)               | Reçue                     | Accepté(e)                      | Reçue                   | Accepté(e)                    |
| Rejetez les autres offres.  | Rejeté(e)              | Accepté(e)               | Rejeté(e)                     | Accepté(e)                      | Rejeté(e)                   | Accepté(e)                    |




