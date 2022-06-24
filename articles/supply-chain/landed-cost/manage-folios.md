---
title: Gérer les folios
description: Cet article décrit comment utiliser les folios. Un folio se compose généralement de marchandises d’un fournisseur pour une entité ou entreprise par expédition. Les marchandises d’un folio peuvent se trouver dans un seul conteneur ou être réparties sur plusieurs conteneurs.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4cc556c47f7027f2f5d5b24c235b11ced63b3e4e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905890"
---
# <a name="manage-folios"></a>Gérer les folios

[!include [banner](../../includes/banner.md)]

Un folio est souvent déterminé par la réglementation douanière. Un folio se compose de marchandises d’un fournisseur pour une entité ou entreprise par expédition. Les marchandises d'un folio sont gérées dans un conteneur.

Pour ouvrir la page **Tous les folios**, allez à **Coût au débarquement \> folios \> Tous les folios**. Cette page affiche une liste de tous les folios en cours. Vous pouvez utiliser les boutons du volet Actions pour créer, supprimer et utiliser des folios. Sélectionnez n’importe quel folio dans la liste pour afficher ses détails sur la page **folios**.

## <a name="action-pane"></a>Volet Actions

Le volet Action de la page **Tous les folios** et la page **folios** fournit des boutons qui vous permettent de travailler avec un folio sélectionné. Chaque bouton effectue une seule action. Le volet Actions comprend également des onglets, dont chacun fournit à son tour un ensemble de boutons associés. Sauf indication contraire, tous les boutons et onglets décrits dans les sous-sections suivantes sont disponibles à la fois dans la vue de liste (c’est-à-dire sur la page **Tous les folios**) et dans la vue détaillée (c’est-à-dire sur la page **folios**).

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Boutons qui apparaissent directement dans le volet Actions

Le tableau suivant décrit les boutons disponibles directement sur le volet Action.

| Bouton | Description |
|---|---|
| Créer | Création d’un folio. |
| Retirer | Supprimez le folio ouvert ou sélectionné. |
| Coûts du voyage | Ouvrez la page **Frais de trajet**, où vous pouvez afficher et ajouter les coûts au niveau de folio à toutes les marchandises du trajet. Lorsque les frais de folios sont ajoutés manuellement au trajet, ils sont automatiquement ajoutés à la page Recherche des coûts et répartie sur chaque bien selon la méthode spécifiée sur la page **Frais de trajet**. |

### <a name="buttons-on-the-manage-tab"></a>Boutons de l’onglet Gérer

Le tableau suivant décrit les boutons disponibles directement sur l’onglet **Gérer** du volet Action.

| Bouton | Description |
|---|---|
| Valider la préparation de réception | Validez une liste de reçus pour toutes les lignes de commande fournisseur du folio. Si des expéditions multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de liste de réception s’ouvre pour chaque entreprise. |
| Valider l’accusé de réception de produits | Validez un reçu produit pour toutes les lignes de commande fournisseur du folio. Si des trajets multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de réception de produit s’ouvre pour chaque entreprise. |
| Valider la facture | Validez une facture pour toutes les lignes de commande fournisseur du folio. Si des trajets multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de facture s’ouvre pour chaque entreprise. |
| Expédier l’ordre de transfert | Enregistrez un ordre de transfert pour toutes les lignes d’ordre de transfert liées au folio actuel dans l’envoi associé. |
| Recevoir un ordre de transfert | Enregistrez un reçu d’ordre de transfert pour toutes les lignes d’ordre de transfert liées au folio actuel dans l’envoi associé. |
| Recevoir des marchandises en transit | Recevez toutes les lignes de commande en transit dans le folio. |
| Documents reçus | Mettez à jour le paramètre de l’option **Documents reçus** sur *Oui*. Vous pouvez utiliser ce bouton pour verrouiller l’article et/ou la ligne d’achat afin qu’il ne puisse plus être mis à jour. |
| Rechercher des coûts auto | Rechercher des coûts de trajet pertinents. Si ces coûts ont déjà été trouvés ou mis à jour, le message suivant s’affiche : « Il existe des lignes de coût non facturées. Voulez-vous les écraser ? » Notez que les frais de trajet liés au folio et facturés ne seront pas écrasés. |
| Créer un journal des arrivées | Générer un journal des arrivées pour les organisations à l’aide des fonctionnalités avancées de l’entrepôt. Sélectionnez **Initialiser la quantité** (recommandé), et **Créer à partir de marchandises en transit** et/ou **Créer à partir des commande fournisseur**. La dernière option dépend de l’utilisation ou non du traitement des marchandises en transit. |
| Accumuler les coûts | Régularisez des coûts lorsqu’un type de coût a un compte général spécifié pour le débit. Ce bouton est généralement utilisé lorsque le stock est en transit ou lorsque les marchandises ont été reçues et facturées. |

### <a name="buttons-on-the-general-tab"></a>Boutons de l’onglet Général

Le tableau suivant décrit les boutons disponibles directement sur l’onglet **Général** du volet Action.

| Bouton | Description |
|---|---|
| Préparation de réception | Validez une liste de reçus pour toutes les lignes de commande fournisseur du folio. Si des trajets multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de liste de produit s’ouvre pour chaque entreprise. |
| Accusé de réception des produits | Consultez l’enregistrement de réception du produit, s’il est utilisé. |
| Arrivée d’articles | Affichez le journal d’arrivée des articles, s’il est utilisé. |
| Recherche de coûts | Ouvrez la page de demande de prix pour afficher tous les coûts d’un voyage, y compris le conteneur d’expédition, le folio et la commande fournisseur. Vous pouvez ajuster la vue exacte de la page à l’aide de l’action Afficher. Sur la page de demande de coût, vous pouvez afficher l’un des domaines, ainsi que l’article et le code du type de coût. En supprimant ces articles, vous pouvez ajuster la page en regroupant les coûts. Cette fonctionnalité peut être utile si vous utilisez des tailles et des couleurs. Vous pouvez modifier les dimensions affichées sur la page. La page **Coûts** affiche uniquement les codes de type de coût où l’entrée **Dr** sur l’onglet **Validation** est défini sur *Article*. |

## <a name="header-view"></a>Vue de l’en-tête

Pour ouvrir la vue **en-tête**, ouvrez un folio, puis sélectionnez l’onglet **en-tête** en haut à droite de l’en-tête du folio.

### <a name="settings-on-the-general-fasttab"></a>Paramètres de l’organisateur Général

Le tableau suivant décrit les champs disponibles sur le raccourci **Général** dans la vue **En-tête** d’un folio.

| Champ | Description |
|---|---|
| Folio | Nom du folio. Ce nom est généré automatiquement lors de la création du folio.|
| Voyage | Le voyage associé au folio. |
| Courtier en douane | Sélectionnez le courtier en douane du folio. Les courtiers en douane sont définis sur le fournisseur. Ils permettent de déterminer automatiquement les coûts créés. |
| Feuille de route aérienne/Feuille de chargement | Spécifiez la lettre de transport aérien ou le connaissement qui s’applique au folio. |
| Société | Entité juridique associé au folio. |
| Numéro de contrôle de la cargaison | Ce champ est utilisé par les services des douanes de certains pays ou régions. |
| Mesure | Ce champ permet de spécifier une mesure dans le module **Prix au débarquement**. Les mesures sont souvent utilisées par des organisations qui ne connaissent pas le volume ou le poids individuel des marchandises, mais qui nécessitent une répartition plus précise que celle fournie par le montant ou la quantité. Le transitaire fournira le poids ou la mesure cubique, et vous pourrez le mettre au niveau d’un article ou de la commande fournisseur. Il peut être mis à jour automatiquement si le paramètre est sélectionné ou manuellement. |
| Unité de mesure | L’unité qui s’applique à la mesure spécifiée. |
| Nombre de cartons | Le nombre de cartons dans le folio. Ce champ peut être mis à jour automatiquement, en fonction de la sélection des paramètres. |
| Compte fournisseur | Permet de sélectionner le fournisseur associé au folio. Ce champ est fourni uniquement à titre indicatif. Cela n’affecte aucune fonctionnalité. |
| Nom | Nom du compte de fournisseur sélectionné. |
| Remarques | Permet d’entrer des informations supplémentaires liées au folio. |
| Description des marchandises | Sélectionnez une description de marchandises pour vous aider à identifier le folio. Pour plus d’informations, voir [Description des marchandises](shipping-information-setup.md#description-of-goods). |
| Date d’évaluation | Ce champ est lié à la page de saisie des droits. Le module **Prix au débarquement** utilisera le taux de change douanier pour la date que vous définissez ici. La valeur par défaut est la date sur la page de saisie des droits. |
| ID douanes | Saisissez l’ID douanes. Les services des douanes des pays ou régions fournissent cet identifiant. |
| Code Tarif | Saisissez un code tarifaire à associer au folio. Ce code est généralement requis (et défini) selon la destination. |

### <a name="settings-on-the-delivery-fasttab"></a>Paramètres de l’organisateur Livraison

Le tableau suivant décrit les paramètres disponibles sur le raccourci **livraison** dans la vue **En-tête** d’un folio.

| Champ | Description |
|---|---|
| Date du folio | Sélectionnez une date à associer au folio. La valeur par défaut est la date de création du voyage. |
| HAE au port d’expédition | L’heure estimée à la date d’arrivée au port de destination (port "à"). |
| Date de livraison estimée | Habituellement, la date à laquelle les marchandises doivent arriver dans l’entrepôt. Ce champ n’est pas utilisé lors du calcul de la date de livraison estimée. (La date de livraison estimée du contrôle de suivi est utilisée à la place.) Pour définir ce champ afin que la valeur corresponde à la date de livraison estimée du contrôle de suivi, utilisez le [Centre de contrôle de suivi](delivery-information-setup.md#tracking-control-center). |
| Documents originaux reçus | Date de réception des documents originaux. |
| Courtier avisé | Date à laquelle le courtier a été avisé. |
| Feuille de chargement initiale envoyée | Date à laquelle le connaissement original a été envoyé. |
| Mise en circulation des marchandises | Date à laquelle les marchandises ont été dédouanées. |
| Rendez-vous client | La date du rendez-vous client. |
| Livraison à l’entrepôt | La date à laquelle les marchandises ont été livrées à l’entrepôt. |
| Date de vérification | La date de vérification. |
| Instructions de livraison | La date de réception des instructions de livraison. |
| Port de départ | Le port d’où part le trajet. |
| Port d’arrivée | Le port où arrive le trajet. Le conteneur d’expédition peut avoir un différent port, car le navire peut s’arrêter dans plusieurs ports. |

### <a name="settings-on-the-export-fasttab"></a>Paramètres de l’organisateur Exportation

Le tableau suivant décrit les paramètres disponibles sur le raccourci **Exportation** dans la vue **En-tête** d’un folio.

| Champ | Description |
|---|---|
| Exportateur | L’exportateur peut être stocké sur le folio. Dans le commerce international, vous pouvez envoyer une commande fournisseur à une entreprise mais recevoir les marchandises d’une autre entreprise. Le suivi et la documentation sont exigés par les douanes. Le nom et l’adresse de l’exportateur peuvent être enregistrés ici. |
| Nom | Nom de l’exportateur sélectionné. |

## <a name="lines-view"></a>Vue lignes

Pour ouvrir la vue **Lignes**, ouvrez un folio, puis sélectionnez l’onglet **Lignes** en haut à droite de l’en-tête du folio.

### <a name="information-on-the-folio-fasttab"></a>Organisateur Informations sur le folio

Le raccourci **folio** dans la vue **Lignes** affiche des informations sur le folio. La plupart de ces informations figurent également dans la vue **En-tête**, comme décrit précédemment dans cet article.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informations et boutons du raccourci Lignes

Le raccourci **Lignes** de la vue **Lignes** affiche des détails sur chaque ligne de commande fournisseur complète ou partielle incluse dans le folio actuel.

Le tableau suivant décrit les boutons disponibles directement sur la barre d’outils du raccourci **Lignes** de la vue **Lignes**.

| Bouton | Description |
|---|---|
| Exécute la suppression | Supprimez la ligne de commande fournisseur sélectionnée du voyage. |
| Stock \> transactions | Afficher les transactions de stock de la ligne de commande fournisseur. Notez que si vous utilisez des marchandises en transit, la commande d’origine et les commandes de marchandises en transit sont également affichées. |
| Stock \> Afficher les dimensions | Ouvrez une boîte de dialogue dans laquelle vous pouvez sélectionner les dimensions de stock affichées pour les transactions que vous affichez. |
| Actualiser | Mettez à jour les informations liées au montant, au poids ou au volume de la ligne de commande fournisseur sélectionnée. |

### <a name="information-on-the-lines-details-fasttab"></a>Informations sur le raccourci Détails de lignes

Le raccourci **Détails de lignes** dans la vue **Lignes** affiche des informations sur la ligne de commande fournisseur actuellement sélectionnée sur le raccourci **Lignes**.
