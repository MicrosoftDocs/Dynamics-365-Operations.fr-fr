---
title: Coût au débarquement et gestion du transport
description: Microsoft Dynamics 365 Supply Chain Management fournit deux modules différents pour travailler avec le transport, la gestion du transport (TMS) et le coût au débarquement. Cette rubrique résume les fonctionnalités que les deux modules ont en commun et met en évidence les différences entre eux.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c7bc17cad246f4bdb9c2bc63cbc47d05731ad2ac
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021222"
---
# <a name="landed-cost-vs-transportation-management"></a>Coût au débarquement et gestion du transport

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management fournit deux modules différents pour travailler avec le transport : **la gestion du transport (TMS)** et **le coût au débarquement**. Cette rubrique résume les fonctionnalités que les deux modules ont en commun et met en évidence les différences entre eux. Vous pouvez utiliser ces informations pour décider quel module correspond le mieux à vos pratiques commerciales. Vous constaterez peut-être que certaines pratiques commerciales fonctionnent mieux avec TMS, tandis que d’autres fonctionnent mieux avec le Coût au débarquement. Ensuite, en fonction des besoins de votre entreprise, vous pouvez choisir d’utiliser un module exclusivement, ou vous pouvez combiner les deux modules.

Cette rubrique n’est pas une revue complète de toutes les fonctionnalités de l’un ou l’autre module. Au lieu de cela, il met en évidence la fonctionnalité disponible en ce qui concerne le transport des marchandises d’un fournisseur à l’entrepôt de votre entreprise, où elles peuvent être consommées.

## <a name="terminology-reference-data-and-reporting-differences"></a>Terminologie, données de référence et rapports sur les différences

### <a name="terminology-comparison"></a>Comparaison terminologique

TMS et Coût au débarquement utilisent des termes différents pour des concepts similaires. Le tableau suivant résume ces termes et leur utilisation dans les deux modules.

| Terme TMS | Terme de coût au débarquement | Notes |
|----------|------------------|-------|
| **Charge**<p>Une *charge* est un ensemble d’envois qui sont transportés simultanément sur la même unité de transport (comme un camion ou un bateau). Les charges peuvent être entrantes ou sortantes.</p> | **Voyage**<p>En règle générale, un *voyage* est un seul navire qui se déplace le long d’un seul *voyage*. Un voyage peut contenir plusieurs *conteneurs d’expédition*, et il peut également inclure des commandes entrantes provenant de différentes entités juridiques de votre organisation. Les voyages peuvent uniquement être entrants.</p> | TMS utilise également le terme *numéro de voyage*, qui fait référence à un champ d’information dans lequel vous pouvez saisir un identifiant. Cependant, aucune fonctionnalité n’est associée au champ TMS, et elle n’est pas liée au concept de *voyage* en coût au débarquement. |
| **Route**<p>Une *route* est le chemin physique d’un transport de l’origine à la destination.</p> | **Parcours**<p>Une *parcours* est le chemin physique d’un transport de l’origine à la destination. Chaque voyage doit être affecté à un parcours.</p> | |
| **Segments d’itinéraire**<p>Un itinéraire peut avoir plusieurs *segments de route*, dont chacun représente une étape du voyage. Un itinéraire peut inclure plusieurs transporteurs ou services, dont chacun est considéré comme un segment d’itinéraire.</p> | **Étapes**<p>Chaque itinéraire peut avoir plusieurs *segments*, dont chacun représente une étape du voyage. Une étape peut faire partie du transport, de la gestion des tâches ou d’une autre activité.</p> | |
| **Conteneurs**<p>Un *conteneur* peut être tout type d’emballage ou d’emballage utilisé par TMS.</p> | **Conteneurs d’expédition**<p>Un *conteneur de livraison* est un conteneur d’expédition littéral et physique, tel que connu des porte-conteneurs.</p> | |
| **Codes marchandise**<p>Dans TMS (et ailleurs dans Supply Chain Management), les *codes marchandises* identifier les types de produits. Ils peuvent affecter les tarifs, la manutention des matières dangereuses, etc.</p> | **Codes marchandise**<p>En coût au débarquement, les *codes marchandises* sont établis au niveau de la personne morale. Elles sont principalement utilisées pour la génération d’états.</p> | Le coût au débarquement peut également utiliser les codes de marchandise utilisés pour TMS et à d’autres endroits dans Supply Chain Management. Cependant, les codes de produit de coût au débarquement ne sont utilisés que par coût au débarquement. |

### <a name="some-reference-data-isnt-shared"></a>Certaines données de référence ne sont pas partagées

TMS et Coût au débarquement ne partagent pas les données de référence pour des entités telles que la configuration des coûts, les trajets et les segments. Si vous utilisez les deux modules, vous devez recréer les données de référence non partagées.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>Les rapports intersociétés ne fonctionnent pas avec les marchandises en transit

Les rapports suivants ne fonctionnent pas avec la fonction Marchandises en transit fournie par le coût au débarquement :

- [Rapport Totaux des marchandises en transit intersociétés](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Rapport Totaux des marchandises en transit intersociétés](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Ces rapports supposent que les marchandises sont mises en transit dès que vous émettez un bon de livraison et qu’elles sont prises en stock dès le transit dès leur réception. Cependant, les marchandises en transit ne sont pas traitées de cette manière. Par conséquent, si vous utilisez ensemble les marchandises en transit et les fonctions intersociétés, les résultats de ces deux rapports seront incorrects.

## <a name="using-the-two-modules-together"></a>Utiliser les deux modules ensemble

Vous pouvez utiliser TMS pour les opérations entrantes et sortantes. Bien que le coût au débarquement fournisse la plupart des mêmes fonctionnalités de base que TMS pour les opérations entrantes, il ajoute également certaines fonctionnalités. Par conséquent, vous pouvez envisager d’utiliser TMS pour les opérations sortantes et le coût au débarquement pour les opérations entrantes.

En général, nous vous déconseillons d’utiliser les deux modules ensemble pour les opérations entrantes. Vous devez utiliser le module qui répond le mieux à vos besoins. Si vous utilisez les deux modules ensemble, vous ne devez pas partager de documents source entre eux. Par exemple, n’utilisez pas le même bon de commande pour un chargement dans TMS et un voyage en coût au débarquement. En particulier, vous devez vous assurer de ne pas configurer le système pour créer automatiquement des charges entrantes. Si les articles des commandes fournisseur sont inclus dans un voyage, ils ne peuvent pas être traités dans le cadre d’un chargement.

## <a name="goods-in-transit"></a>Marchandises en transit

L’une des principales caractéristiques du coût au débarquement est sa capacité à traiter les marchandises en transit. Le traitement des marchandises en transit vous permet de prendre la propriété financière des articles expédiés avant qu’ils ne soient physiquement reçus à l’entrepôt de destination. Le traitement des marchandises en transit est souvent nécessaire pour le commerce international.

### <a name="tms-goods-in-transit-features"></a>Fonctionnalités de marchandises en transit TMS

TMS ne prend actuellement pas en charge les marchandises en cours de traitement en transit.

### <a name="landed-cost-goods-in-transit-features"></a>Caractéristiques des marchandises au débarquement en transit

Le traitement des marchandises en transit est une caractéristique principale du coût au débarquement et fournit les fonctionnalités suivantes :

- **Marchandises dans les entrepôts de transit** – Un entrepôt de marchandises en transit peut être associé à chaque entrepôt dans Supply Chain Management. Les marchandises sont transférées aux marchandises dans les entrepôts de transit après la facturation du commande fournisseur d’origine. Les articles qui y sont physiquement réservés deviennent indisponibles à la consommation tant qu’ils ne sont pas reçus dans leur entrepôt physique. Par conséquent, vous pouvez prendre la propriété financière des marchandises en facturant le commande fournisseur.
- **Compte général des marchandises en transit** – Le coût au débarquement ajoute un compte de validation comptable spécifique au profil de validation des commandes fournisseur pour gérer les marchandises en cours de traitement en transit. Ce compte général de marchandises en transit fait office de compte de type "marchandises facturées non reçues". Lorsque la commande fournisseur d’origine est facturée et que l’ordre de transport est créé, le coût de la commande fournisseur direct est enregistré dans le compte général des marchandises en transit jusqu’à ce que les marchandises soient reçues à leur emplacement physique final.
- **Suivi des mises à jour des contrôles** – Les commandes de marchandises en transit prennent en charge la fonctionnalité de contrôle de suivi dans le coût au débarquement. Le contrôle de suivi vous permet de mettre à jour la date d’arrivée prévue des marchandises pendant leur transit. Le contrôle de suivi met ensuite à jour le voyage et les lignes de commande fournisseur associées. La date de livraison prévue est alors disponible pour la planification et la logistique.
- **Déclenchement de sur/sous-transactions** – Si un écart se produit entre les marchandises attendues sur une ligne de voyage et les marchandises réelles qui sont reçues à l’entrepôt, le coût au débarquement le résout en créant des transactions en sur et/ou en dessous. Vous pouvez ensuite gérer ces transactions, en fonction de la manière dont vous souhaitez les traiter, via une commande fournisseur ou un journal des mouvements. Les transactions plus et moins fournissent un lien vers le voyage, le commande fournisseur d’origine et le nouveau journal de mouvement ou commande fournisseur pour l’écart.
- **Marchandises en transit** – Le coût au débarquement introduit un nouveau document source connu sous le nom de *marchandises en ordre de transit*. Une commande de marchandises en transit vous permet de facturer la commande fournisseur d’origine pour prendre la propriété financière des articles. Lorsque la commande fournisseur est facturée, le nouveau document source est créé pour chaque ligne de commande fournisseur qui a une combinaison de dimensions de stock. Les marchandises sont ensuite physiquement déplacées vers un entrepôt de marchandises en transit, où elles sont physiquement réservées contre les marchandises en transit et ne peuvent être consommées que si les marchandises en transit sont reçues.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Frais divers et frais d’expédition

L’un des aspects les plus importants de la gestion des expéditions et des expéditions de marchandises est la reconnaissance des frais généraux associés aux expéditions. Ces frais généraux ne sont pas les coûts d’inventaire directs associés à un commande fournisseur et à une expédition ou à un voyage. Au lieu de cela, ce sont des coûts supplémentaires qui sont introduits par la nature du mouvement des marchandises du fournisseur vers votre organisation. Ces coûts peuvent inclure les frais de transport associés à l’expédition de marchandises d’un emplacement physique à un autre ou les frais de douane associés à l’importation de marchandises d’un fournisseur étranger.

Le coût au débarquement gère ces coûts en créant un type de structure de coûts appelé *coûts automobiles*. TMS gère ces coûts en utilisant la fonctionnalité de frais divers.

### <a name="tms-charge-and-cost-features"></a>Fonctionnalités de charge et de coût TMS

TMS utilise des frais divers pour gérer les coûts supplémentaires des charges affectées aux lignes de document source associées. Ces frais divers peuvent être définis au niveau de la ligne de commande fournisseur ou de l’en-tête de commande fournisseur.

Dans TMS, les frais divers peuvent être répartis ou divisés par le poids, le volume ou la quantité de l’inventaire. Les frais peuvent être divisés par les frais de transport ou accessoires. Des développements supplémentaires seront nécessaires pour utiliser des méthodes de répartition supplémentaires dans TMS.

### <a name="landed-cost-charge-and-cost-features"></a>Fonctionnalités de frais et de coût au débarquement

Le coût au débarquement fournit un ensemble de fonctions de coût qui gèrent les coûts supplémentaires associés à l’expédition des marchandises. Ces coûts sont connus sous le nom de coûts automobiles et ils sont appliqués au moment de la facturation initiale de l’expédition en utilisant le montant du coût estimé. Chaque type de coût est géré dans sa propre écriture. Une fois les factures réelles des frais généraux validées, les coûts estimés sont automatiquement mis à jour pour refléter les coûts réels.

De plus, les frais généraux associés à l’expédition des marchandises peuvent être facturés pendant le voyage depuis le port d’origine ou à tout moment après la réception des marchandises. Cette capacité offre une plus grande flexibilité pour la consommation de biens.

La liste suivante présente quelques concepts relatifs aux fonctionnalités de frais et de coût dans Coût au débarquement :

- **Zone de coût** – Les coûts et charges peuvent être affectés à différents niveaux, ou *zones de coût*, en voyage. Le coût peut être appliqué au niveau du voyage et réparti sur chaque élément du voyage. De plus, les coûts peuvent être appliqués au niveau du conteneur, du commande fournisseur, de l’article ou de l’ordre de transfert. Chaque charge de coût peut être gérée séparément dans les différents domaines et est décomposée en un coût par article.
- **Méthodes de répartition** – Plusieurs méthodes de répartition sont disponibles dans Coût au débarquement. Les frais de gestion peuvent être répartis en fonction de la quantité, du montant en dollars, de la valeur, du poids, du volume, de la mesure ou d’une mesure volumétrique définie par l’utilisateur.
- **Contrôle de compensation/d’écart** – Les frais de coût sont définis comme leur propre type de code de coût dans Coût au débarquement. Chaque type de code de coût vous permet de définir un compte de compensation pour les frais estimés, ainsi que des comptes de régularisation et d’écart de prix d’achat pour les écarts entre les coûts estimés et les coûts réels. Lorsque les coûts estimés sont initialement comptabilisés, il y a un crédit sur le compte de compensation. Une fois les factures réelles validées, les frais réels sont validés et les coûts estimés sont débités du compte de compensation.

## <a name="matching-freight-bills-and-invoices"></a>Mise en correspondance les facture des frais de transport et les factures

### <a name="tms-bill-and-invoice-matching-features"></a>Fonctions d’appariement de factures et de factures TMS

TMS peut faire correspondre les factures de transport qui contiennent les coûts et les factures estimés avec le coût réel du fret. Les factures peuvent être reçues par voie électronique ou sur papier. L’écart de correspondance entre le coût estimé et le coût réel n’affecte pas la valorisation des stocks.

Pour plus d’informations, consultez [Rapprocher le fret dans la gestion du transport](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Fonctions de rapprochement de factures et de facture de coût au débarquement

Le coût au débarquement peut faire correspondre les factures de transport aux frais estimés et facturer les frais réels aux coûts estimés. Au moment de la facturation, les frais de transport sont dans un journal de facturation et les coûts estimés sont effacés du compte de compensation. De plus, les frais réels sont imputés au coût des marchandises vendues pour l’article, ainsi que les écarts entre les frais estimés et les frais réels. Ce comportement permet une flexibilité dans le processus de facturation.

## <a name="tracking"></a>Suivi

Une caractéristique importante du TMS et du coût au débarquement est la possibilité de suivre les marchandises et d’identifier où elles se trouvent dans le trajet du point d’origine à l’entrepôt de destination finale. Le suivi vous permet de suivre et de mettre à jour où se trouvent les marchandises et quand elles devraient arriver à l’entrepôt pour être consommées. En plus de l’état des marchandises pendant leur voyage, le coût au débarquement fournit les dates prévues et réelles pour chaque étape du voyage.

### <a name="tms-tracking-features"></a>Fonctionnalités de suivi TMS

TMS fournit des fonctionnalités limitées pour le suivi des charges entrantes. Il affiche les dates et permet de construire une intégration pour trouver la position exacte (par exemple, sur la page **Statut du transport**).

Pour chaque segment d’itinéraire, vous pouvez saisir des horaires estimés et des heures d’arrivée.

### <a name="landed-cost-tracking-features"></a>Fonctionnalités de suivi des coûts fixes

Le coût au débarquement peut fournir un contrôle de suivi pour chaque voyage, du port d’origine à la destination finale. Le contrôle de suivi définit le statut du voyage. Le statut indique si le voyage est en cours, à la douane pour inspection ou en livraison locale en route vers l’entrepôt final. Le statut peut être défini au niveau de la ligne de commande d’achat, du conteneur et de l’en-tête du voyage. Par conséquent, vous disposez d’un contrôle plus granulaire.

De plus, une date prévue confirmée basée sur des délais spécifiés est associée à chaque étape d’un voyage. Les dates de livraison confirmées et prévues sont ajoutées à la ligne de commande fournisseur et aux marchandises en transit, et peuvent être utilisées pour la planification et la logistique. En plus des dates prévues, les dates réelles peuvent être mises à jour. Les étapes suivantes d’un voyage seront alors mises à jour en conséquence.

## <a name="multi-leg-journeys"></a>Parcours à plusieurs étapes

Le concept de voyage identifie où les marchandises sont dans le processus et contrôle le statut des marchandises pendant qu’elles sont en transit. Les marchandises peuvent passer par plusieurs étapes d’un voyage et vous pouvez associer divers coûts à une étape spécifique. Les exemples incluent un coût de fret sur la navigation d’un navire et les frais de transport local sur le transport de marchandises du port à la destination.

### <a name="tms-multi-leg-journey-features"></a>Fonctionnalités de voyage multi-segments TMS

Dans TMS, les itinéraires peuvent être décomposés en segments d’itinéraire pour représenter des trajets multi-segments. TMS peut attribuer des tarifs au comptant et des frais accessoires à des segments de route individuels.

Pour plus d’informations, consultez [Planifier des itinéraires de transport de marchandises avec plusieurs arrêts](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Fonctionnalités de voyage multi-étapes avec coût au débarquement

Le coût au débarquement fournit un cadre pour déplacer les marchandises du point d’origine à la destination à travers une série d’étapes, qui sont les arrêts ou les étapes d’un voyage. Les segments sont combinées pour créer des modèles de parcours, qui définissent la manière dont les marchandises sont déplacées du fournisseur vers votre organisation.

À chaque étape d’un parcours, vous pouvez définir plus en détail le statut de chaque ligne de commande fournisseur et les délais qui lui sont associés. Le délai de livraison combiné pour toutes les étapes est utilisé pour identifier la date de livraison estimée. Cependant, le traitement des marchandises en transit est nécessaire pour que les voyages à étapes multiples s’appliquent. Le trajet des marchandises au cours d’un voyage est géré dans un tableau spécifique au coût au débarquement.

## <a name="receiving-by-container"></a>Réception par conteneur

Il peut être important de gérer la manière dont les marchandises sont divisées et stockées sur un navire. Sur un navire, les marchandises peuvent être conservées dans un ou plusieurs conteneurs. Lorsque les marchandises sont reçues, elles sont reçues dans des conteneurs, et différents conteneurs au cours d’un voyage peuvent être reçus à des moments différents ou à des dates différentes.

Le TMS et le coût au débarquement fournissent des fonctionnalités pour gérer la réception des marchandises dans un conteneur. TMS utilise le concept de charges pour gérer les marchandises, les commande fournisseur et les ordres de transfert associés à un conteneur d’expédition. TMS prend en charge la réception sur la base d’une structure d’emballage qui est reçue via un préavis d’expédition (ASN). Le coût au débarquement utilise le concept de conteneurs d’expédition pour traiter les commande fournisseur et contrôler les frais généraux associés à un conteneur sur un navire.

### <a name="tms-receiving-by-container-features"></a>Fonctionnalité Réception par conteneur TMS

TMS prend en charge les ASN entrants, toutes les variantes de réception via l’application mobile Gestion des entrepôts et toutes les méthodes de réception via le client Supply Chain Management.

### <a name="landed-cost-receiving-by-container-features"></a>Fonctionnalité Réception par Coût au débarquement TMS

Pour prendre en charge la réception par conteneur, Landed cost crée des enregistrements de conteneur d’expédition et associe les commande fournisseur à un conteneur d’expédition spécifique en utilisant son ID de conteneur. Les frais généraux peuvent ensuite être appliqués à ce conteneur d’expédition et ventilés de manière à être associés aux commande fournisseur concernés.

Les conteneurs au coût au débarquement peuvent être reçus via un nouveau type de reçu appelé *marchandises en transit*, via les journaux d’arrivée ou via la réception d’appareils mobiles. Lorsque les journaux d’arrivée sont utilisés, les quantités peuvent être initialisées à partir des marchandises en ordre de transit ou des lignes de commande fournisseur d’origine dans le conteneur. Le coût au débarquement fournit deux types de travail pour la réception via l’application mobile Gestion des entrepôts.

Le coût au débarquement ne fournit pas d’ASN pour la réception électronique des marchandises. De plus, il ne prend pas en charge les flux de l’application mobile Gestion des entrepôts qui traitent la réception de la charge, la réception de contenants ou la réception mixte de contenants.

## <a name="rate-shopping-by-vendor"></a>Évaluer les achats par fournisseur

La consultation des frais permet à une entreprise de sélectionner un fournisseur de transport en fonction du prix le plus bas, de l’itinéraire le plus rapide ou d’une combinaison des deux facteurs.

### <a name="tms-rate-shopping-features"></a>Fonctionnalités de consultation des frais TMS

TMS vous permet d’identifier les fournisseurs et les solutions de routage pour les commandes entrantes et sortantes. Par exemple, vous pouvez identifier le parcours le plus rapide ou le moins cher pour une expédition.

TMS offre une optimisation complète des achats et du fret via le Workbench des itinéraires tarifaires, des options de tarification flexibles via le moteur de tarification, une API de moteur de tarification pour l’intégration avec des parties externes et une prise en charge du poids volumétrique.

Pour plus d’informations, voir [Moteurs de gestion du transport](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Fonctionnalités de consultation des frais du Coût au débarquement

Le coût au débarquement ne fournit qu’une assistance limitée pour les achats de tarifs par fournisseur. Bien que vous puissiez saisir des valeurs de transitaire, le coût au débarquement ne les compare pas entre plusieurs fournisseurs.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Enregistrement/départ du chauffeur avec prise de rendez-vous

Les fonctions d’enregistrement/départ des chauffeurs permettent au système de surveiller les arrivées et d’éviter les embouteillages aux quais de chargement.

### <a name="tms-driver-check-incheck-out-features"></a>Fonctionnalités arrivée/départ du chauffeur TMS

TMS vous permet de créer des *rendez-vous*. Un rendez-vous est un événement qui se produit à quai pour recevoir une commande fournisseur, expédier une commande client, ou traiter un chargement entrant ou sortant à une date et à une heure spécifiques. Les rendez-vous garantissent que des quais sont disponibles pour le chargement et le déchargement des marchandises, et ils aident à prévenir les situations où plusieurs transporteurs arrivent à un endroit en même temps.

Le système permet aux conducteurs de s’enregistrer à une porte de quai spécifique.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Fonctionnalités arrivée/départ du chauffeur Coût au débarquement

Le coût au débarquement peut stocker des estimations pour la date et l’heure auxquelles un conteneur sera livré.

## <a name="transfer-orders-and-additional-costs"></a>Ordres de transfert et frais supplémentaires

Souvent, les entreprises doivent être en mesure de transférer des marchandises entre les entrepôts. Lorsque ce type de transfert se produit, des coûts y sont associés et vous voudrez peut-être reconnaître ces coûts. Dans Coût au débarquement, les ordres de transfert peuvent être ajoutés à un voyage ou à un navire pour suivre le mouvement des marchandises d’un entrepôt ou d’un site à un autre, estimer le délai de livraison et la date de livraison prévue, et ajouter des frais généraux au transfert des marchandises.

### <a name="tms-transfer-order-cost-features"></a>Fonctionnalités de coût des ordres de transfert TMS

TMS prend en charge la création de frais de transport liés aux transferts. Bien que ces frais puissent être consultés à partir de l’ordre de transfert, le coût au débarquement n’est pas ajouté au coût de l’article. Le rapprochement du fret est pris en charge par la création d’une facture de fret basée sur ces frais. Cette facture de transport est ensuite comparée à une facture de transport du fournisseur.

### <a name="landed-cost-transfer-order-cost-features"></a>Fonctionnalités de coût des ordres de transfert des coûts fixes

Le coût au débarquement vous permet d’ajouter des ordres de transfert à un navire ou à un voyage. De cette manière, vous pouvez ajouter des frais d’expédition au voyage en tant que règlements de stock au moment de la réception de l’ordre de transfert. Les frais généraux peuvent être facturés pour les coûts réels et suivis par rapport à un voyage pour mettre à jour le coût des marchandises vendues. Bien que les ordres de transfert n’utilisent pas de marchandises dans le traitement du transit dans la mainlevée standard, ils peuvent être ajoutés aux voyages. Le coût au débarquement est ajouté au coût total de chaque article.