---
title: Gérer les conteneurs d’expédition
description: Cette rubrique décrit comment utiliser les conteneurs d’expédition. Les conteneurs d’expédition sont utilisés pour regrouper les marchandises qui sont physiquement regroupées. Ils sont également utilisés dans les cas où les coûts doivent être partagés uniquement entre ces produits, généralement parce qu’ils sont physiquement ensemble.
author: sherry-zheng
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: d3a47aa2ae36cd36a7e92aa2503252021e03f739
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573775"
---
# <a name="manage-shipping-containers"></a>Gérer les conteneurs d’expédition

[!include [banner](../../includes/banner.md)]

Les conteneurs d’expédition sont utilisés pour regrouper les marchandises qui sont physiquement regroupées. Ils sont également utilisés dans les cas où les coûts doivent être partagés uniquement entre ces produits, généralement parce qu’ils sont physiquement ensemble.

Pour afficher et traiter les marchandises via la page du conteneur d’expédition, accédez à **Prix au débarquement \> Conteneurs d’expédition \> Tous les conteneurs d’expédition**. La page **Tous les conteneurs d’expédition** affiche une liste de tous les conteneurs d’expédition disponibles. Vous pouvez utiliser les boutons du volet Actions pour créer, supprimer et utiliser des conteneurs d’expédition. Sélectionnez n’importe quel conteneur d’expédition dans la liste pour afficher ses détails sur la page **Conteneurs d’expédition**.

La partie supérieure de la page des détails du conteneur d’expédition affiche les informations sur le conteneur d’expédition et les coûts. La section **Lignes** affiche les folios, articles et commande fournisseur ou ordres de transfert qui sont attachés au conteneur.

## <a name="action-pane"></a>Volet Actions

Le volet Actions sur les pages **Tous les conteneurs d’expédition** et **Conteneurs d’expédition** fournit des boutons qui vous permettent de travailler avec un conteneur d’expédition sélectionné. Chaque bouton effectue une seule action. Le volet Actions comprend également des onglets, dont chacun fournit à son tour un ensemble de boutons associés. Sauf indication contraire, tous les boutons et onglets décrits dans les sous-sections suivantes sont disponibles à la fois dans la vue de liste (c’est-à-dire sur la page **Tous les conteneurs d’expédition**) et dans la vue détaillée (c’est-à-dire sur la page **Conteneurs d’expédition** ).

### <a name="buttons-on-the-manage-tab"></a>Boutons de l’onglet Gérer

Le tableau suivant décrit les boutons disponibles directement sur l’onglet **Gérer** du volet Action.

| Bouton | Descriptions |
|---|---|
| Valider la préparation de réception | Publiez une liste de reçus ou affichez les listes de reçus de produits pour toutes les lignes de commande fournisseur dans le conteneur d’expédition. Si des expéditions multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de liste de réception s’ouvre pour chaque entreprise. |
| Valider l’accusé de réception de produits | Validez un reçu produit pour toutes les lignes de commande fournisseur du conteneurs d’expédition. |
| Valider la facture | Validez une facture pour toutes les lignes de commande fournisseur du conteneurs d’expédition. Si des expéditions multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de facture s’ouvre pour chaque entreprise. |
| Expédier l’ordre de transfert | Validez une expédition de transfert de commande pour toutes les lignes de commande de transfert du conteneurs d’expédition. Seules les lignes du conteneur d’expédition qui sont un type d’ordre de transfert apparaissent dans la boîte de dialogue. |
| Recevoir un ordre de transfert | Validez un reçu de transfert de commande pour toutes les lignes de commande de transfert du conteneurs d’expédition. La boîte de dialogue de réception est le moyen le plus simple de recevoir des marchandises dans un conteneur d’expédition ou un voyage et constitue l’une des trois options disponibles. Vous pouvez également recevoir via les journaux d’arrivée ou le traitement des appareils mobiles. |
| Créer un journal des arrivées | Vous pouvez générer un journal des arrivées pour les organisations à l’aide des fonctionnalités avancées de l’entrepôt. Les options sont _Initialiser la quantité_ (recommandé), et _Créer à partir de marchandises en transit_ ou _Créer à partir des commande fournisseur_. Les deux dernières options dépendent de l’utilisation ou non du traitement des marchandises en transit. |
| Renommer | Ouvrez une boîte de dialogue dans laquelle vous pouvez renommer un conteneur d’expédition sélectionné. |
| Modifier le modèle de parcours | Modifier le modèle de trajet. Après avoir modifié le modèle de parcours, vous devrez peut-être sélectionner **Trouvez les coûts automatiques** ou ajoutez à nouveau manuellement les coûts, car les frais d’expédition seront supprimés. |
| Convertir en location | Convertissez un conteneur d’expédition sélectionné en conteneur d’expédition de location. |

### <a name="buttons-on-the-general-tab"></a>Boutons de l’onglet Général

Le tableau suivant décrit les boutons disponibles directement sur l’onglet **Général** du volet Action.

| Bouton | Descriptions |
|---|---|
| Préparation de réception | Validez un liste de reçus pour toutes les lignes de commande fournisseur du conteneurs d’expédition. Si des trajets multi-entreprises sont utilisés, une nouvelle boîte de dialogue d’enregistrement de liste de produit s’ouvre pour chaque entreprise. |
| Accusé de réception de marchandises | Consultez l’enregistrement de réception du produit, s’il est utilisé. Le processus de réception des produits ne sera utilisé que si les marchandises n’utilisent pas la fonctionnalité de marchandises en transit. |
| Arrivée d’articles | Consultez le journal des arrivées d’articles pour le conteneur d’expédition, si ce journal est utilisé. |
| Étapes | Les étapes sont utilisées pour identifier des parties distinctes d’un voyage. Des délais peuvent être associés à chaque étape pour faciliter le suivi des expéditions. Pour plus d’informations, consultez [Configuration de voyage multi-étapes](multi-leg-journey-setup.md). |
| Suivi | Afficher ou mettre à jour le suivi des envois. |
| Ordres des marchandises en transit | Vous pouvez ouvrir la page **Marchandises en transit** directement à partir du conteneur. Cette page affiche les enregistrements de marchandises en transit pour le conteneur d’expédition sélectionné uniquement. |

## <a name="header-view"></a>Vue de l’en-tête

Pour ouvrir la vue **en-tête**, ouvrez un conteneurs d’expédition, puis sélectionnez l’onglet **en-tête** en haut à droite de l’en-tête du conteneurs d’expédition.

### <a name="settings-on-the-general-fasttab"></a>Paramètres de l’organisateur Général

Le tableau suivant décrit les paramètres disponibles sur le raccourci **Général** dans la vue **En-tête** d’un conteneurs d’expédition.

| Champ | Description |
|---|---|
| Conteneur d’expédition | Le nom du conteneur d’expédition. |
| Voyage | Le voyage associé au conteneur d’expédition. |
| Type de conteneur d’expédition | Saisissez le type de conteneur d’expédition. Ce champ doit être défini. Vous pouvez l’utiliser pour déterminer le coût du fret, par exemple en sélectionnant le coût automatique associé au type de conteneur d’expédition. |
| Bateau | Entrez ou sélectionnez le récipient. Si le récipient n’est pas répertorié comme une valeur, vous pouvez saisir l’ID du récipient sous forme de texte libre. Dans ce cas, la table principale n’est pas mise à jour afin que l’ID du récipient puisse être sélectionné ultérieurement dans ce champ. Pour plus d’informations, consultez [Navire](shipping-information-setup.md#vessels). |
| Type d’unité | Les types d’unités sont utilisés comme moyen supplémentaire de regrouper et d’identifier les conteneurs d’expédition. Ils sont affichés et sélectionnés sur la page du conteneur d’expédition. Pour plus d’informations, voir [Paramétrer des types d’unités](shipping-container-setup.md#unit-types). |
| Type de réfrigération | Les types de réfrigération sont utilisés comme moyen supplémentaire de regrouper et d’identifier les conteneurs d’expédition, en général des conteneurs réfrigérés. Ils sont affichés et sélectionnés sur la page du conteneur d’expédition. Pour plus d’informations, voir [Paramétrer des types de réfrigération](shipping-container-setup.md#refrigeration-types). |
| Mesure | Ce champ permet de spécifier une mesure dans le module **Prix au débarquement**. Les mesures sont souvent utilisées par des organisations qui ne connaissent pas le volume ou le poids individuel des marchandises, mais qui nécessitent une répartition plus précise que celle fournie par le montant ou la quantité. Le transitaire fournira le poids en kilos ou la mesure cubique, et vous pourrez le mettre au niveau d’un article ou de la commande fournisseur. Il peut être mis à jour automatiquement si le paramètre est sélectionné, ou il peut être saisi manuellement. |
| Unité de mesure | L’unité de mesure qui s’applique au nombre dans le champ **Mesure**. |
| Poids réel | Vous pouvez enregistrer le poids réel du carton ou du contenant. Cette valeur peut être utilisée pour la vérification par rapport au poids maximum autorisé dans la configuration d’un conteneur d’expédition. |
| Nombre de cartons | Le nombre de cartons est automatiquement mis à jour si le paramètre est sélectionné. |
| Description des marchandises | Une description des marchandises peut être sélectionnée sur le conteneur d’expédition ou l’en-tête du folio. Il est utilisé pour aider à identifier un voyage, un conteneur d’expédition ou un folio de marchandises. Pour plus d’informations, voir [Description des marchandises](shipping-information-setup.md#description-of-goods). |
| Feuille de route aérienne/Feuille de chargement | Vous pouvez spécifier la lettre de transport aérien ou le connaissement pour le conteneur d’expédition. |
| Remarques | Informations supplémentaires liées au conteneurs d’expédition. |
| Pouvant faire l’objet d’un retour | Une valeur qui indique si le conteneur d’expédition peut être retourné après le voyage. |
| Statut du voyage | Statut du trajet associé au conteneurs d’expédition. |
| Statut de la commande fournisseur | Statut de la commande fournisseur associée au conteneurs d’expédition. |

### <a name="settings-on-the-delivery-fasttab"></a>Paramètres de l’organisateur Livraison

Le tableau suivant décrit les paramètres disponibles sur le raccourci **livraison** dans la vue **En-tête** d’un conteneurs d’expédition.

| Champ | Description |
|---|---|
| Date et heure de création | Date et heure de création du conteneur. |
| Date départ usine | Cette date est généralement fournie à l’usine/au fournisseur pour indiquer quand vous prévoyez que les marchandises quittent ses locaux. Lorsque vous travaillez avec une usine en Asie, cette date est souvent requise au lieu de la date à laquelle vous attendez les marchandises. (En revanche, pour une livraison locale, la date à laquelle vous attendez les marchandises est obligatoire.) Ce champ peut être rempli à partir des lignes de commande fournisseur dans la liste des conteneurs d’expédition. Vous pouvez les saisir ici manuellement. |
| Date d’expédition | Cette date peut être imprimée sur le document de commande fournisseur. Il informe généralement l’usine/le fournisseur de la date à laquelle les marchandises doivent être livrées au port au plus tard. Ce champ est fourni uniquement à titre indicatif. Il n’est pas utilisé pour estimer la date de livraison prévue des marchandises dans le conteneur d’expédition. Ce champ peut être défini pour qu’il soit automatiquement mis à jour lorsque la page de contrôle de suivi est mise à jour. |
| Date d’entrée en magasin | La première date à laquelle les marchandises des commandes fournisseur liées au trajet seront disponibles à la vente.|
| Date de livraison estimée | Habituellement, la date à laquelle les marchandises doivent arriver dans l’entrepôt. Ce champ est fourni uniquement à titre indicatif. Il n’est pas utilisé pour calculer la planification générale sur les lignes de commande fournisseur dans le conteneur d’expédition. La date de livraison prévue sur les lignes de commande fournisseur est mise à jour via le contrôle de suivi. Ce champ peut être configuré pour qu’il soit mis à jour lorsque la page de contrôle de suivi est mise à jour. |
| Date de départ | Généralement, la date de départ est la date à laquelle l’avion ou le navire quitte effectivement le port d’outre-mer. |
| HAE au port d’expédition | La date d’arrivée estimée au port de destination (port "à"). |
| Documents originaux reçus | Facultatif : Mettez à jour la date de réception des documents originaux. |
| Courtier avisé | Facultatif : Mettez à jour la date à laquelle le courtier a été avisé. |
| Le connaissement original envoyé | Facultatif : Mettez à jour la date à laquelle le connaissement original a été envoyé. |
| Mise en circulation des marchandises | Facultatif : Mettez à jour la date de lancement des marchandises. |
| Rendez-vous client | Facultatif : mettez à jour la date du rendez-vous client. |
| Livraison à l’entrepôt | Facultatif : Mettez à jour la date à laquelle les marchandises ont été livrées à l’entrepôt. |
| Date de vérification | Facultatif : mettez à jour la date de vérification. |
| Instructions de livraison | Facultatif : mettez à jour la date des instructions de livraison. |
| Port de départ | Le port à partir duquel les articles seront expédiés. |
| Port d’arrivée | Le port vers lequel les articles seront expédiés. |
| Transitaire local | Ce champ est fourni uniquement à titre indicatif. Le transitaire local doit pouvoir être sélectionné dans la table des fournisseurs. |
| Date du transport local | Entrez la date à laquelle le transport local est réservé. Ce champ peut aider l’entrepôt à faire sa planification. |
| Heure du transport local | Entrez le créneau horaire. Ce champ peut aider l’entrepôt à faire sa planification. |
| Modèle de parcours | Le modèle de trajet spécifié pour le trajet. Le modèle de voyage fournit les détails des ports "a" et "de", ainsi que les délais associés au contrôle de suivi du conteneur d’expédition. |

### <a name="settings-on-the-other-fasttab"></a>Paramètres de l’organisateur Autre

Le tableau suivant décrit les paramètres disponibles sur le raccourci **Autres** dans la vue **En-tête** d’un conteneurs d’expédition.

| Champ | Description |
|---|---|
| Location | Valeur qui indique si le conteneur d’expédition est un conteneur d’expédition de location. Les coûts de location peuvent être associés aux conteneurs de location. |
| Converti en location | Valeur qui indique si le conteneur d’expédition a été converti en un conteneur d’expédition de location. Les coûts de location peuvent être associés aux conteneurs de location. |
| Voyage d’origine | Si le conteneur d’expédition a été déplacé vers un nouveau voyage, le voyage d’origine. |
| Utilisé(e) | Utilisez cette option pour enregistrer si un conteneur d’expédition de location a été utilisé. Elles sont fournies uniquement à titre indicatif. |
| Date de chargement prévue | La date à laquelle le conteneur d’expédition devrait être chargé de marchandises. |
| Notre numéro de série | Saisissez le numéro de série que votre entreprise utilise en interne pour le conteneur d’expédition. |
| Numéro de série de la compagnie maritime | Saisissez le numéro de série que la compagnie maritime ou l’agent a fourni pour le conteneur d’expédition. |
| Date d’application du certificat d’examen | La date à laquelle un examen a été demandé pour le conteneur d’expédition. |
| Date de réception du certificat d’examen | Date de réception du certificat d’examen. |
| Date d’expiration du certificat d’examen | Date d’expiration du certificat d’examen. |
| Numéro du certificat d’examen | Le numéro de certificat du certificat qui a été délivré après un examen. |

## <a name="lines-view"></a>Vue lignes

Pour ouvrir la vue **Lignes**, ouvrez un conteneurs d’expédition, puis sélectionnez l’onglet **Lignes** en haut à droite de l’en-tête du conteneurs d’expédition.

### <a name="information-on-the-shipping-container-fasttab"></a>Informations sur le raccourci Conteneur d’expédition

Le raccourci **Conteneurs d’expédition** dans la vue **Lignes** affiche des informations sur le folio. La plupart de ces informations figurent également dans la vue **En-tête**, comme décrit précédemment dans cette rubrique.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informations et boutons du raccourci Lignes

Le raccourci **Lignes** de la vue **Lignes** affiche des détails sur chaque ligne de commande fournisseur complète ou partielle incluse dans le conteneur d’expédition actuel.

Le tableau suivant décrit les boutons disponibles directement sur la barre d’outils du raccourci **Lignes** de la vue **Lignes**.

| Bouton | Description |
|---|---|
| Exécute la suppression | Supprimez la ligne de commande fournisseur sélectionnée du voyage. |
| Stock \> transactions | Afficher les transactions de stock de la ligne de commande fournisseur. Notez que si vous utilisez des marchandises en transit, la commande d’origine et les commandes de marchandises en transit sont également affichées. |
| Stock \> Afficher les dimensions | Ouvrez une boîte de dialogue dans laquelle vous pouvez sélectionner les dimensions de stock affichées pour les transactions que vous affichez. |
| Actualiser | Mettez à jour les informations liées au montant, au poids ou au volume de la ligne de commande fournisseur sélectionnée. |

### <a name="information-on-the-lines-details-fasttab"></a>Informations sur le raccourci Détails de lignes

Le raccourci **Détails de lignes** dans la vue **Lignes** affiche des informations sur la ligne de commande fournisseur actuellement sélectionnée sur le raccourci **Lignes**.
