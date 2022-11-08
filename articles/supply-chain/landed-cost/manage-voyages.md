---
title: Gérer les trajets
description: Cet article décrit comment utiliser les trajets. Un trajet représente généralement un récipient. Cependant, en fonction de vos pratiques et procédures, il peut représenter un fournisseur, un bon de commande ou un autre élément qui a du sens pour votre organisation.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4499eeb9cdd4efd9c4b630106c6e052378191f2a
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725467"
---
# <a name="manage-voyages"></a>Gérer les trajets

[!include [banner](../../includes/banner.md)]

Un trajet représente généralement un récipient. Cependant, en fonction de vos pratiques et procédures, il peut représenter un fournisseur, un bon de commande ou un autre élément qui a du sens pour votre organisation.

La page **Tous les trajets** fournit des détails sur le trajet, des informations de livraison et de coût, ainsi que des informations sur les articles, les commandes fournisseur et les ordres de transfert. Pour ouvrir la page **Tous les trajets**, allez à **Coût au débarquement \> Trajets \> Tous les trajets**. Cette page affiche une liste de tous les trajets en cours. Vous pouvez utiliser les boutons du volet Actions pour créer, supprimer et utiliser des trajets. Sélectionnez n’importe quel trajet dans la liste pour afficher ses détails.

> [!NOTE]
> Les conteneurs d’expédition et les folios sont liés à un trajet. Les lignes d’achat sont liées à un conteneur d’expédition. En outre, les coûts saisis ici sont répartis sur toutes les lignes d’achat associées.
> Les commandes fournisseur de projet ne sont pas prises en charge dans le Coût au débarquement.

## <a name="action-pane"></a>Volet Actions

Le volet Action de la page **Trajets** fournit des boutons qui vous permettent de travailler avec un trajet sélectionné. Chaque bouton effectue une seule action. Le volet Actions comprend également des onglets, dont chacun fournit à son tour un ensemble de boutons associés. Sauf indication contraire, tous les boutons et onglets sont disponibles à la fois dans la vue de liste de la page **Tous les trajets** et dans la vue détaillée pour un seul trajet sélectionné.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Boutons qui apparaissent directement dans le volet Actions

Le tableau suivant décrit les boutons disponibles directement sur le volet Action.

| Bouton | Description |
|---|---|
| Créer | Créer un trajet. <!-- KFM: Link to scenario --> |
| Retirer | Supprimer le trajet actuel. Seuls les trajets dont le statut de trajet est *Confirmé* peuvent être supprimés. Une fois qu’un trajet quitte le port et traite des marchandises en transit, il ne peut plus être supprimé. |
| Éditeur de voyage | Ouvrez la page **Éditeur de trajet**, où vous pouvez ajouter ou supprimer des lignes d’achat pour le trajet, créer des conteneurs et modifier les détails du trajet lui-même. |
| Coûts du voyage | Ouvrez la page **Frais de trajet**, où vous pouvez afficher et ajouter les coûts du trajet à toutes les marchandises du trajet. Lorsque les frais de trajet sont ajoutés manuellement au trajet, ils sont automatiquement ajoutés à la page **Recherche des coûts** et répartie sur chaque bien selon la méthode spécifiée sur la page **Frais de trajet**. |

### <a name="buttons-on-the-voyage-tab"></a>Boutons de l’onglet Trajet

Le tableau suivant décrit les boutons disponibles directement sur l’onglet **trajet** du volet Action. Cet onglet est disponible uniquement lorsque vous travaillez dans la vue de liste de la page **Tous les trajets**.

| Bouton | Description |
|---|---|
| Conteneur d’expédition | Ouvrez une page qui affiche tous les conteneurs d’expédition associés au trajet sélectionné. Il peut y avoir un ou plusieurs conteneurs. |
| Folio | Ouvrez une page qui affiche tous les folios associés au trajet sélectionné. Il peut y avoir un ou plusieurs folios. |

### <a name="buttons-on-the-manage-tab"></a>Boutons de l’onglet Gérer

Le tableau suivant décrit les actions disponibles directement sur l’onglet **Gérer** du volet Action.

| Bouton | Description |
|---|---|
| Documents reçus | Mettez à jour le trajet afin que l’option **Documents reçus** soit définie sur *Oui*. Vous pouvez utiliser ce bouton pour verrouiller l’article et/ou la ligne d’achat afin qu’il ne puisse plus être mis à jour. |
| En transit | Mettez à jour le champ **Statut du trajet** sur le statut en transit qui est établi sur la page **[Paramètres de coût au débarquement](landed-cost-parameters.md)**. Il n’y a plus de logique sur ce processus. Un trajet peut également être automatiquement mis à jour avec le statut en transit, en fonction des paramètres du [Centre de contrôle de suivi](delivery-information-setup.md).
| Prêt pour l’évaluation des coûts | Mettez à jour le champ **Statut du trajet** sur le statut prêt à l’évaluation des coûts qui est établi sur la page **[Paramètres de coût au débarquement](landed-cost-parameters.md)**. Un trajet peut être chiffré lorsque toutes les factures ont été traitées (factures de stock et factures de frais de trajet) et que les marchandises ont été reçues. Si les coûts estimés associés à un trajet n’ont pas été chiffrés, une erreur se produit lorsque vous essayez de traiter le coût d’un trajet. |
| Évaluer les coûts | Nettoyez toutes les irrégularités de coût après qu’une facture existe pour toutes les commandes fournisseur et les frais de trajet. Lorsque vous sélectionnez ce bouton, la boîte de dialogue **Mise à jour du trajet – Coûts évalués** apparaît. Là, vous pouvez choisir de publier à la date financière standard ou de spécifier une date comptable, puis d’exécuter l’action. Vous pouvez ré-exécuter l’action autant de fois que vous le souhaitez. Vous pouvez également utiliser la boîte de dialogue **Mise à jour du trajet – Coûts évalués** pour établir une planification pour exécuter l’action en tant que tâche périodique (trajet par lots). Nous vous recommandons d’exécuter régulièrement l’action en la configurant en tant que travail par lots. |
| Valider la préparation de réception | Validez une liste de reçus pour toutes les lignes de commande fournisseur du trajet.  |
| Valider l’accusé de réception de produits | Validez un reçu produit pour toutes les lignes de commande fournisseur du trajet. Le processus de réception des produits pour les lignes de commandes fournisseur associées à un trajet ne sera utilisé que si les marchandises ne passent **pas** par le traitement des marchandises en transit. Si les marchandises passent par le traitement des marchandises en transit, vous recevez une erreur lorsque vous essayez de valider l’accusé de réception du produit pour une ligne de commande fournisseur.  |
| Valider la facture | Validez une facture pour toutes les lignes de commande fournisseur du trajet. Si les marchandises en cours de trajet passent par le traitement des marchandises en transit, les lignes de commande fournisseur seront facturées avant la fin du processus de réception. Lorsque la commande fournisseur d’origine est facturée, les commandes de marchandises en transit associées aux lignes de commande d’achat d’origine sont créées. Ces commandes peuvent ensuite être reçues par l’entrepôt.  |
| Expédier l’ordre de transfert | Validez un trajet de transfert de commande pour toutes les lignes de commande de transfert du trajet. Lorsque ce bouton est sélectionné, seuls les ordres de transfert seront disponibles pour mise à jour. |
| Recevoir un ordre de transfert | Validez un reçu de transfert de commande pour toutes les lignes de commande de transfert du trajet. |
| Recevoir des marchandises en transit | Recevez toutes les lignes de commande en transit pendant le trajet. Ce bouton est l’une des trois options disponibles pour recevoir des marchandises en transit lors d’un trajet. (Les deux autres options sont le bouton **Créer un journal des arrivées** décrit plus loin dans ce tableau, et l’application mobile Gestion des entrepôts.) Cette option est l’option la plus simple et traitera les marchandises en transit hors de l’entrepôt de marchandises en transit vers l’entrepôt de destination finale. Si vous souhaitez plus de contrôle sur le processus, utilisez le journal des arrivées ou un appareil mobile pour traiter la réception des marchandises. |
| Rechercher des coûts auto | Rechercher tous les coûts de trajet pertinents. Si ces coûts ont déjà été trouvés ou mis à jour, le message suivant s’affiche : « Il existe des lignes de coût non facturées. Voulez-vous les écraser ? » Tous les coûts qui n’étaient pas associés au trajet au moment de la création seront trouvés. Les frais de trajet liés à un voyage et facturés ne seront pas écrasés. |
| Créer un journal des arrivées | <p>Ouvrez la boîte de dialogue **Créer un journal des arrivées**, dans laquelle vous pouvez créer un journal des arrivées qui spécifie un emplacement. La boîte de dialogue contient les options suivants :</p><ul><li>**Créer à partir de marchandises en transit** ou **Créer à partir d’un ordre de transfert** – L’étiquette de cette option change selon que vous utilisez ou non le processus de marchandises en transit. Réglez-le sur *Oui* pour ouvrir une page du journal des arrivées qui vous permet de traiter un journal des arrivées standard pour les marchandises en transit associées au trajet. Si l’article a déjà été reçu dans l’entrepôt de destination finale, il ne sera pas ajouté aux lignes du journal d’arrivée.</li><li>**Initialiser la quantité** – Réglez cette option sur *Oui* pour initialiser la quantité qui sera reçue, en fonction de la quantité de marchandises spécifiée sur la ligne de trajet. Si la ligne de trajet a été partiellement réceptionnée, cette quantité sera la quantité restante. Nous vous recommandons de définir cette option sur *Oui*.</li><li>**Créer à partir des lignes de commande** – Réglez cette option sur *Oui* pour prendre la valeur des lignes de commande.</li></ul><p>Ce bouton est l’une des trois options disponibles pour recevoir des marchandises lors d’un trajet. (Les autres options sont le bouton **Recevoir les marchandises en transit** qui a été décrit précédemment dans ce tableau et l’application mobile Gestion des entrepôts.)</p> |
| Accumuler les coûts | Vous pouvez comptabiliser des coûts lorsqu’un type de coût a un compte général spécifié pour le débit. Ce bouton est généralement utilisé lorsque le stock est en transit ou lorsque les marchandises ont été reçues et facturées. |
| Agréger les coûts | Déplacer les coûts du niveau du conteneur d’expédition au niveau du trajet. Vous pouvez utiliser ce bouton dans un scénario de services partagés/d’expédition, où plusieurs entités partagent un conteneur d’expédition ou un espace carton. Par exemple, le trajet a un conteneur d’expédition de 40 pieds et un conteneur d’expédition de 20 pieds, et la répartition se fait en volume. Dans ce cas, les marchandises/entités qui partagent ou utilisent l’espace dans le conteneur d’expédition de 20 pieds pourraient être pénalisées. Pour répartir équitablement les coûts, certaines organisations peuvent souhaiter transférer les coûts au trajet et les répartir selon la méthode de répartition au niveau du trajet. |
| Modifier le modèle de parcours | Permet d’ouvrir une boîte de dialogue dans lequel vous pouvez modifier le modèle de trajet. Après avoir modifié le modèle, les frais de trajet seront supprimés. Par conséquent, vous devrez peut-être sélectionner **Trouvez les coûts automobiles** (voir la description plus haut dans ce tableau) ou ajoutez à nouveau manuellement les coûts. |

### <a name="buttons-on-the-general-tab"></a>Boutons de l’onglet Général

Le tableau suivant décrit les boutons disponibles directement sur l’onglet **Général** du volet Action.

| Bouton | Description |
|---|---|
| Préparation de réception | Ouvrez une liste des reçus produits pour toutes les lignes de commande fournisseur du trajet.  Si aucune liste de reçus de produits n’a été traitée, ce bouton n’est pas disponible. |
| Accusé de réception des produits | Ouvrez l’enregistrement de réception de produit pour les lignes de commande d’achat associées au trajet, si cet enregistrement est utilisé. Si aucun reçu de produit n’a été validé, ce bouton n’est pas disponible. Le processus de réception des produits ne sera pas utilisé si vous utilisez le traitement des marchandises en transit. |
| Arrivée d’articles | Ouvrez le journal d’arrivée des articles, s’il est utilisé. |
| Suivi | Ouvrez la page **Suivi entrant**, où vous pouvez mettre à jour la date d’arrivée prévue des marchandises dans un conteneur d’expédition et un trajet, puis mettre à jour les dates de livraison prévues des lignes de commande. |
| Recherche de coûts | <p>Ouvrez la page **Recherche sur les coûts**, qui montre tous les coûts d’un trajet.</p><p>Sélectionnez **Afficher** sur le volet Action et ajustez la vue. Vous pouvez afficher n’importe lequel des niveaux, ainsi que le code d’article et de type de coût.</p><p>Seuls les codes de type de coût qui sont directement liés aux transactions de stock apparaissent sur la page **Rechercher de coûts**. En supprimant les codes de type de coût, vous pouvez ajuster la page en regroupant les coûts. Cette fonctionnalité peut être utile si vous utilisez des tailles et des couleurs.</p><p>La page **Enquête sur les coûts** affiche uniquement les codes de type de coût où le champ **Débit** est défini sur *Article*.</p> |
| Ordres des marchandises en transit | Ouvrez la page **Commandes de marchandises en transit**, qui affiche les enregistrements de marchandises en transit pour le trajet sélectionné uniquement. |

## <a name="lines-view"></a>Vue lignes

Pour ouvrir la vue **Lignes**, ouvrez un trajet, puis sélectionnez l’onglet **Lignes** en haut à droite de l’en-tête du trajet.

### <a name="information-on-the-voyage-header-fasttab"></a>Informations sur le raccourci d’en-tête de trajet

Le raccourci **En-tête de trajet** dans la vue **Lignes** d’un trajet contient des informations de base décrivant le trajet. De nombreux champs qui apparaissent sur ce raccourci apparaissent également dans la vue **En-tête**, comme décrit plus loin dans cet article.

### <a name="information-on-the-voyage-lines-fasttab"></a>Informations sur le raccourci de lignes de trajet

Le raccourci **Lignes de trajet** dans la vue **Lignes** d’un trajet est liée aux détails du trajet et aux informations sur les coûts qui s’appliquent au niveau du trajet. Ici, vous pouvez consulter les conteneurs d’expédition, les folios et les éléments associés au trajet. Le prix et la quantité des articles du trajet sont également indiqués. Vous pouvez afficher n’importe quel conteneur d’expédition ou folio répertorié en sélectionnant le lien approprié.

### <a name="information-on-the-line-details-fasttab"></a>Informations sur le raccourci de détails de lignes

Le raccourci **Détails de la ligne** dans la vue **Lignes** d’un trajet fournit plus d’informations sur la ligne actuellement sélectionnée sur le raccourci **Lignes de voyage**. Notez que ce raccourci inclut des détails sur la position que chaque ligne occupe dans le conteneur et sa quantité déclarée.

## <a name="header-view"></a>Vue de l’en-tête

Pour ouvrir la vue **en-tête**, ouvrez un trajet, puis sélectionnez l’onglet **en-tête** en haut à droite de l’en-tête du trajet.

### <a name="settings-on-the-general-fasttab"></a>Paramètres de l’organisateur Général

Le tableau suivant décrit les champs disponibles sur le raccourci **Général** dans la vue **En-tête** d’un trajet.

| Champ | Description |
|---|---|
| Voyage | Entrez le numéro de trajet ou de vol. |
| Référence de réservation | Si votre expéditeur ou centre d’expédition fournit un numéro de référence pour identifier le trajet (c’est-à-dire la référence interne de l’expéditeur ou du centre d’expédition), saisissez-le ici. |
| Bateau | Entrez ou sélectionnez le récipient. Si le récipient n’est pas répertorié comme une valeur, vous pouvez saisir l’ID du récipient sous forme de texte libre. Dans ce cas, la table principale n’est pas mise à jour afin que l’ID du récipient puisse être sélectionné ultérieurement dans ce champ. |
| ID voyage externe | Entrez l’ID disponible publiquement pour le trajet (tel que le numéro de vol). |
| Feuille de route aérienne principale/Feuille de chargement | Entrez le numéro de la lettre de transport aérien principale ou du connaissement. Vous pouvez spécifier cette valeur lorsque vous expédiez par voie aérienne. |
| Feuille de route aérienne/Feuille de chargement | Entrez la lettre de transport aérien ou le connaissement pour le conteneur d’expédition. |
| Location | Cochez cette case pour indiquer que le conteneur est un conteneur de location qui doit être retourné. |
| Description | Saisissez une description du trajet pour le reconnaître plus facilement. |
| Statut du voyage | Statut du trajet. Les valeurs incluent *Créé*, *En transit*, *Documents reçus*, et *Coûts évalués*. Ce champ n’est pas calculé selon la logique. Il est mis à jour uniquement via l’action de publication. La valeur *Coûts évalués* indique qu’une facture pour le stock et tous les frais de trajet a été reçue. À moins qu’une facture ne soit reçue, un trajet ne peut pas atteindre le statut *Coûts évalués*. |
| Statut de la commande fournisseur | Le statut le plus élevé atteint parmi tous les commandes fournisseur associés au trajet. |
| Documents reçus | Une valeur qui indique si votre entreprise a reçu tous les documents associés au trajet. Pour modifier la valeur, sélectionnez **Documents reçus** dans le groupe **Mise à jour du trajet** sur l’onglet **Gérer** du volet Actions. |
| Société d’expédition | Sélectionnez la société d’expédition pour ce trajet. Ce champ peut être utilisé pour déterminer les coûts automobiles. |
| Nom | Nom de la société sélectionnée dans le champ **Société d’expédition**. |
| Mesure | Ce champ permet de spécifier une mesure dans un coût automatique. Les mesures sont souvent utilisées par des organisations qui ne connaissent pas le volume ou le poids individuel des marchandises, mais qui nécessitent une répartition plus précise que celle fournie par le montant ou la quantité. Le transitaire fournira le poids ou la mesure cubique, et vous pourrez le mettre au niveau d’un article ou de la commande fournisseur. Il peut être mis à jour automatiquement si le paramètre est sélectionné, ou il peut être saisi manuellement. |
| Unité de mesure | L’unité de mesure qui s’applique au nombre dans le champ **Mesure**. |
| Nombre actuel de palettes | Spécifiez le nombre de palettes sur la ligne de trajet. Ce champ est automatiquement mis à jour si l’option **Mettre à jour automatiquement le nombre de cartons** est définie sur *Oui* sur l’onglet **Général** de la page **Paramètres de coût au débarquement**. |

### <a name="settings-on-the-delivery-fasttab"></a>Paramètres de l’organisateur Livraison

Le tableau suivant décrit les champs disponibles sur le raccourci **Livraison** dans la vue **En-tête** d’un trajet.

| Champ | Description |
|---|---|
| Date et heure de création | Date et heure de création de l’enregistrement du trajet. |
| Date départ usine | Ce champ sélectionne la première date départ usine parmi les commandes fournisseur liées au trajet. La date départ usine est disponible sur l’en-tête de la commande fournisseur et est mise à jour à l’aide de la fonction de contrôle de suivi. |
| Date d’expédition | La date estimée à laquelle l’avion ou le navire quitte le point d’origine. |
| Date de départ | La date de départ est généralement la date à laquelle l’avion ou le navire quitte effectivement le port d’outre-mer. La date du navire et la date de départ ne doivent pas nécessairement correspondre. Le champ **Date de départ** est à titre informatif uniquement. Il n’est pas utilisé pour estimer la date de livraison prévue. La fonctionnalité de contrôle de suivi est utilisée pour estimer la date de livraison prévue, et ce champ peut être configuré pour qu’il soit automatiquement rempli par la fonction de contrôle de suivi. |
| Date d’entrée en magasin | Ce champ sélectionne la première date à laquelle les marchandises des commandes fournisseur liées au trajet seront disponibles à la vente. |
| Date de livraison estimée | La date de livraison estimée est généralement la date à laquelle les marchandises doivent arriver dans l’entrepôt. Ce champ est fourni uniquement à titre indicatif. Il n’est pas utilisé pour la planification générale des marchandises. La date de livraison prévue sur la ligne de commande fournisseur est utilisée pour la planification générale des marchandises en trajet et est mise à jour à l’aide de la fonction de contrôle de suivi. Ce champ peut être configuré pour être rempli par la fonction de contrôle de suivi. |
| Date de livraison réelle | La première date de livraison, en fonction des marchandises liées au trajet. |
| HAE au port d’expédition | Entrez la date à laquelle vous prévoyez que le trajet arrivera au port d’expédition, en fonction des informations fournies par votre agent maritime. |
| Documents originaux reçus | Saisissez la date de réception des documents originaux. |
| Courtier avisé | Entrez la date à laquelle le courtier a été avisé. |
| Le connaissement original envoyé | Entrez la date à laquelle le connaissement original a été envoyé. |
| Mise en circulation des marchandises | Saisissez la date à laquelle les marchandises ont été dédouanées. |
| Rendez-vous client | Saisissez la date du rendez-vous client, qui est la date à laquelle vous prévoyez que le client deviendra propriétaire des marchandises. |
| Livraison à l’entrepôt | Saisissez la date à laquelle les marchandises ont été livrées à l’entrepôt. |
| Date de vérification | Entrez la date de vérification. |
| Instructions de livraison | Saisissez la date de réception des instructions de livraison. |
| Mode de livraison | Ce champ fournit des informations sur la méthode utilisée pour fournir le trajet et la sélection des coûts des coûts automobiles associés à cette méthode de livraison. |
| Port de départ | Le port d’expédition d’où part le trajet. |
| Port d’arrivée | Le port d’expédition où arrive le trajet. Les conteneurs d’expédition peuvent avoir différents ports, car le navire peut s’arrêter dans plusieurs ports. En vérifiant le port de destination au niveau du conteneur d’expédition, vous fournissez des détails précis du port pour chaque conteneur d’expédition au cours d’un trajet. Le coût automatique associé au fret est déterminé en fonction de la combinaison du type de conteneur d’expédition, du port de destination et du port de départ. |
| Transitaire local | Ce champ est fourni uniquement à titre indicatif. Le transitaire local doit pouvoir être sélectionné dans la table des fournisseurs. |
| Date du transport local | La date à laquelle le transport local est réservé. Ce champ peut aider l’entrepôt à faire sa planification. |
| Heure du transport local | Le créneau horaire auquel le transport local est réservé. Ce champ peut aider l’entrepôt à faire sa planification. |
| Modèle de parcours | Le modèle de trajet spécifié pour le trajet. Le modèle de trajet est utilisé pour entrer le port de destination et d’arrivée du conteneur d’expédition et du trajet. Ces valeurs, à leur tour, aident à identifier les coûts automobiles associés au trajet. |

### <a name="settings-on-the-other-fasttab"></a>Paramètres de l’organisateur Autre

Le tableau suivant décrit les champs disponibles sur le raccourci **Autre** dans la vue **En-tête** d’un trajet.

| Champ | Description |
|---|---|
| Remarques | Entrez des informations supplémentaires liées au trajet. |
| Date d’évaluation | Sélectionnez la première date départ usine des commandes fournisseur liées au trajet. |
| Voyage en attente | Vous pouvez l’utiliser pour indiquer si votre envoi ou votre trajet est encore parti. Elles sont fournies uniquement à titre indicatif.  |
| Renommer les conteneurs d’expédition | Pour les trajets qui ont plus d’un conteneur, le nombre de conteneurs qui n’ont pas encore été reçus. |

## <a name="voyage-update-periodic-tasks"></a>Tâches périodiques de mise à jour du trajet

Le module **Prix au débarquement** comprend plusieurs tâches périodiques liées au trajet qui peuvent mettre à jour en masse plusieurs aspects des trajets. Pour exécuter ou planifier ces tâches périodiques, accédez à **Prix au débarquement \> Tâches périodiques \> Mises à jour du trajet**, puis sélectionnez l’un des types de tâches suivants :

- **Documents reçus** – Cette tâche vous permet de définir **Documents reçus** sur *Oui* pour plusieurs trajets en même temps. Utilisez les paramètres **Filtre** pour définir l’ensemble de trajets que vous souhaitez mettre à jour.
- **En transit** – Cette tâche vous permet de définir le champ **Statut du trajet** sur le statut en transit qui est établi sur la page **[Paramètres de coût au débarquement](landed-cost-parameters.md)** pour plusieurs trajets en même temps. Utilisez les paramètres **Filtre** pour définir l’ensemble de trajets que vous souhaitez mettre à jour.
- **Prêt pour l’évaluation des coûts** – Cette tâche vous permet de définir le champ **Statut du trajet** sur le statut prêt à l’évaluation des coûts qui est établi sur la page **[Paramètres de coût au débarquement](landed-cost-parameters.md)** pour plusieurs trajets en même temps. Vous configurerez généralement cette tâche pour qu’elle s’exécute selon un calendrier régulier.
- **Coûts évalués** – Cette tâche vous permet de définir le champ **Statut du trajet** sur le statut de coûts évalués qui est établi sur la page **[Paramètres de coût au débarquement](landed-cost-parameters.md)** pour plusieurs trajets en même temps, à condition qu’ils aient été chiffrés mais pas encore mis à jour sur le trajet. Vous configurerez généralement cette tâche pour qu’elle s’exécute selon un calendrier régulier.
