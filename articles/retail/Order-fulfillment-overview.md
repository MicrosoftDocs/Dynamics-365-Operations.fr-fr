---
title: Exécution des commandes en magasin
description: Cette rubrique fournit une vue d'ensemble de l'exécution des commandes en magasin.
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: b3eeda217e00b33962561bcb2ee6185275f52fe2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "363681"
---
# <a name="store-order-fulfillment"></a>Exécution des commandes en magasin

[!include [banner](includes/banner.md)]

De nombreuses détaillants souhaitent optimiser l'exécution des commandes en autorisant les magasins à exécuter les commandes. L'exécution des commandes au niveau du magasin permet de faciliter les scénarios de surstock pour un magasin spécifique, ou peut être nécessaire d'un point de vue logistique dans les cas où un magasin a des capacités supplémentaires ou est situé à une distance d'expédition proche du client. Pour répondre à ce besoin, une opération d'exécution de commandes unifiée est disponible dans le point de vente.

Pour les commandes à exécuter dans un magasin spécifique, l'entrepôt du magasin est indiqué sur l'en-tête ou les lignes de la commande.

L'opération d'exécution des commandes dans le point de vente fournit une zone de travail unique dans le point de vente qui peut être utilisée pour traiter les commandes. Cela va de l'acceptation de la commande à son marquage comme expédiée en passant par l'activation du prélèvement en magasin.

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Accéder à l'opération d'exécution de commandes unifiée dans le point de vente

L'opération d'exécution des commandes, [ID opération 928](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-operations) peut être utilisée pour accéder à la zone de travail d'exécution des commandes dans le point de vente.

L'opération d'exécution des commandes ne dispose pas de sa propre autorisation prédéfinie, mais à l'avenir, les utilisateurs pourront utiliser l'autorisation **Autoriser la récupération de commandes** pour appeler l'opération à partir du point de vente.

Au niveau du point de vente, un paramètre de configuration est disponible pour déterminer si une ligne de commande doit être acceptée manuellement à partir du point de vente. Si cette option de configuration n'est pas définie, les lignes de commande sont acceptées par défaut. Si cette option de configuration est activée, les utilisateurs du point de vente devront sélectionner l'autorisation **Autorisation l'acceptation de commandes** pour accepter les commandes à partir du point de vente.

Les lignes de commande peuvent également être rejetées à partir du point de vente. Le rejet d'une ligne de commande signifie qu'elle n'est pas exécutée dans ce magasin et qu'elle est renvoyée pour réaffectation à un autre magasin ou entrepôt. L'autorisation de rejet d'une ligne de commande est accordée via l'autorisation **Autoriser le rejet de commandes**.

## <a name="order-fulfillment-operation-parameters"></a>Paramètres de l'opération d'exécution des commandes

L'exécution des commandes fournit des paramètres prédéfinis qui peuvent être appliqués à l'opération lorsqu'elle est appelée dans le point de vente. Lorsque le paramètre **Toutes les commandes** est configuré, toutes les commandes sont affichées lorsque l'opération est utilisée. Le paramètre **Commandes à expédier** affiche uniquement les commandes à expédier à partir du magasin et le paramètre **Commandes pour prélèvement** affiche les commandes à prélever en magasin.

## <a name="orders-for-fulfillment"></a>Commandes à exécuter

L'opération d'exécution des commandes affiche uniquement les commandes à prélever ou expédier à partir du magasin actuel. Les commandes d'autres magasins à exécuter ne sont pas répertoriées lors de l'utilisation de l'opération d'exécution des commandes.

## <a name="line-selection"></a>Sélection de lignes

Les lignes peuvent être sélectionnées à l'aide de la fonction **Sélectionner** dans le volet Actions. Lorsque la fonction **Sélectionner** est activée, plusieurs lignes peuvent être sélectionnées pour traitement. Vous pouvez effacer les lignes sélectionnées en cliquant à nouveau sur la même ligne.

## <a name="line-details"></a>Détails de ligne

Les détails de la ligne peuvent être affichés à l'aide du menu volant Détails de la ligne. Lorsque ce menu est utilisé, trois onglets sont disponibles pour afficher des informations supplémentaires pour la ligne sélectionnée. Le premier onglet, **Détails de la ligne** affiche les détails de la ligne proprement dite, comme la quantité commandée et la quantité restante. Des détails supplémentaires sont fournis, notamment la quantité prélevée, emballée et facturée ainsi que le mode de livraison et l'adresse de livraison. L'onglet **Détails de la commande** fournit des informations sur l'en-tête de commande, notamment le client, l'ID client, le numéro de commande, le total de la commande et le solde. L'onglet **Stock** affiche des informations sur la ligne sélectionnée en termes d'inventaire physique disponible, d'inventaire réservé et d'inventaire commandé.

Si plusieurs lignes sont sélectionnées, le menu volant des détails de la ligne de commande indique uniquement que plusieurs lignes sont sélectionnées. Pour afficher les détails d'une seule ligne, effacez les lignes jusqu'à ce qu'il n'en reste qu'une seule.

## <a name="pending-order-lines"></a>Lignes de commande en attente

L'opération d'exécution de commandes unifiée offre la possibilité d'accepter manuellement les commandes. Par défaut, les commandes à exécuter dans le magasin sont déjà acceptées. Toutefois, si les processus d'entreprise indiquent qu'un collaborateur au niveau du magasin doit accepter les commandes, l'acceptation manuelle peut être activée au niveau du magasin de vente au détail. Pour activer l'acceptation de commandes, accédez à **Vente au détail** \> **Canaux** \> **Magasins de vente au détail** \> **Tous les magasins de vente au détail**. Ouvrez le magasin souhaité et, sous l'onglet **Général**, localisez le sous en-tête **Exécution des commandes**. Ce sous en-tête comporte une option **Acceptation manuelle** qui est définie sur **Non** par défaut. En définissant cette option sur **Oui** et en synchronisant les modifications de la base de données du canal, les lignes de commande peuvent suivre le processus d'acceptation.

Les collaborateurs disposant de l'autorisation **Autoriser l'acceptation de commandes** peuvent ouvrir l'opération d'exécution des commandes et sélectionner les lignes à accepter. Une fois que les lignes ont été acceptées, leur statut passe de **En attente** à **Accepté** et le reste du processus d'exécution des commandes peut se poursuivre. Lorsque le paramètre **Acceptation manuelle** est activé, les commandes ne sont pas traitées tant qu'elles n'ont pas été acceptées.

Les commandes à prélever en magasin n'ont jamais l'état **En attente**. Cela permet d'éviter le scénario où un client arrive dans le magasin et la ligne de commande ne peut pas être traitée car un collaborateur disposant du privilège approprié n'est pas disponible.

## <a name="accepted-order-lines"></a>Lignes de commande acceptées

Les commandes dont l'état de la ligne est **Accepté** peuvent suivre le reste du processus d'exécution de commandes dans le point de vente. Une fois qu'une commande a été acceptée, toute autre action peut être effectuée sur la ligne de commande.

Par exemple, une ligne de commande acceptée peut être sélectionnée et prélevée directement sans passer par le processus de prélèvement et d'emballage.

## <a name="line-actions"></a>Actions sur la ligne

### <a name="pick"></a>Prélever

La catégorie d'actions **Prélever** facilite le processus de prélèvement des lignes de commande sur les étagères. L'action de prélèvement ne peut être exécutée que sur les lignes de commande qui ont déjà été acceptées.

**Action : Prélèvement**

- **Statut POS résultant :** Prélèvement
- **Statut résultant de l'arrière-guichet :** Aucune modification

Une fois qu'une commande a été acceptée, les lignes peuvent être sélectionnées et marquées comme **Prélèvement**. Marquer une ligne comme **Prélèvement** permet d'indiquer que le travail de prélèvement est déjà exécuté sur une ligne. Cela permet d'éviter que deux collaborateurs tentent de prélever les mêmes lignes de commande en même temps.

**Action : Imprimer la liste des prélèvements**

- **Statut résultant :** Prélèvement
- **Statut résultant de l'arrière-guichet :** Aucune modification

Les listes de prélèvements peuvent être imprimées dans le point de vente pour aider les collaborateurs à exécuter le processus de prélèvement. Une liste de prélèvements imprimée peut être utilisée par le collaborateur qui effectue le prélèvement pour lui permettre de marquer manuellement les produits comme prélevés sur la liste des prélèvements.

Le format de prélèvement est configuré dans Dynamics 365 for Retail et ajouté au profil de réception. Pour plus d'informations sur le paramétrage des profils de réception, voir [Modèles de réception et impression](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).

Si des lignes sont sélectionnées et une liste de prélèvements est imprimée pour ces lignes, elles sont automatiquement mises à jour avec le statut **Prélèvement**.

**Action : Marquer comme prélevé**

- **Statut résultant :** Prélevé ou partiellement prélevé
- **Statut résultant de l'arrière-guichet :** Prélevé ou partiellement prélevé

Une fois que le processus de prélèvement physique a été exécuté, les lignes peuvent être marquées comme **Prélevées**. Lorsque vous sélectionnez une ligne et la marquez comme **Prélevée**, un appel en temps réel est effectué pour mettre à jour la ligne de commande dans Dynamics 365 for Retail. Une fois que la ligne a été marquée comme **Prélevée** dans le point de vente, le statut dans l'arrière-guichet est également mis à jour sur **Prélevé** et les transactions de stock reflètent que la quantité spécifiée a été décrémentée.

Lorsque les commandes sont traitées dans le temps, des quantités partielles peuvent être traitées pour une ligne spécifique. Si une ligne est sélectionnée et l'action **Marquer comme prélevé** est exécutée et la quantité est supérieure à un, l'utilisateur est invité à saisir la quantité. La quantité restante à prélever est remplie automatiquement. Si une quantité inférieure à la quantité restante est spécifiée, le statut de la ligne devient **Partiellement prélevé**. Lorsque la ligne de commande est mise à jour dans l'arrière-guichet, elle reflète également le statut partiellement prélevé et la quantité saisie par l'utilisateur est utilisée pour la mise à jour du stock.

Si une ligne de commande est prélevée par erreur, le processus d'annulation du prélèvement doit être exécuté sur la ligne de commande dans l'arrière-guichet. Aucune action d'annulation du prélèvement n'est actuellement prise en charge dans le point de vente.

Des lignes de commande issues de différentes commandes peuvent être sélectionnées et marquées comme **Prélèvement**, imprimées sur la même liste de prélèvements ou marquées comme **Prélevées**.

### <a name="pack"></a>Emballage

Les lignes de commande peuvent être conditionnées à tout moment une fois que la ligne de commande a été acceptée.

**Action : Imprimer le bon de livraison**

- **Statut résultant :** Emballé ou partiellement emballé
- **Statut résultant de l'arrière-guichet :** Livré ou partiellement livré

Cette action marque les lignes comme emballées ou partiellement emballées et imprime un bon de livraison. Un bon de livraison peut être imprimé pour valider les produits qui ont fait l'objet d'un emballage commun. Le format de prélèvement est configuré dans Dynamics 365 for Retail et ajouté au profil de réception. Pour plus d'informations sur le paramétrage des profils de réception, voir [Modèles de réception et impression](https://docs.microsoft.com/dynamics365/unified-operations/retail/receipt-templates-printing).

**Action : Marquer comme emballé**

- **Statut résultant :** Emballé ou partiellement emballé
- **Statut résultant de l'arrière-guichet :** Livré ou partiellement livré

L'action **Marquer comme emballé** peut être utilisée pour indiquer que les lignes sont emballées sans imprimer un bon de livraison. Les actions **Imprimer le bon de livraison** et **Marquer comme emballé** génèrent des transactions de stock dans l'arrière-guichet. Les lignes d'emballage dans le point de vente entraînent la génération des journaux de bons de livraison dans l'arrière-guichet.

Si une ligne de commande est emballée par erreur, le journal des bons de livraison doit être corrigé dans l'arrière-guichet.

Seules les lignes appartenant à la même commande et présentant le même mode de livraison peuvent être emballées en même temps.

Actuellement, l'option de marquage des lignes de prélèvement en magasin comme **Emballées** est désactivée. Cette fonction sera ajoutée dans une prochaine version. Le processus de création de bons de livraison sera amélioré pour prendre en charge l'injection des informations d'expédition tierces dans le traitement des bons de livraison.

### <a name="pick-up"></a>Prélever

Les commandes à prélever en magasin peuvent être directement prélevées une fois qu'elles sont récupérées dans le point de vente. Les commandes à prélever en magasin ne sont pas soumises à acceptation.

**Action : Prélever**

- **Statut résultant :** Facturé ou partiellement facturé
- **Statut résultant de l'arrière-guichet :** Facturé ou partiellement facturé

Si une ligne est sélectionnée pour prélèvement à partir d'une opération d'exécution de commandes unifiée, toute la commande est chargée dans le point de vente et la quantité totale pour la ligne sélectionnée est marquée. D'autres lignes de la commande sont également chargées dans la vue des transactions du point de vente, mais avec la quantité marquée comme zéro.

Une fois que les lignes à prélever ont été chargées dans la vue des transactions, la transaction peut être traitée normalement.

Les lignes qui ont été entièrement facturées par prélèvement ne s'affichent plus dans le traitement unifié des commandes. Les lignes qui ont été partiellement prélevées continuent à s'afficher dans l'opération d'exécution de commandes unifiée jusqu'à ce qu'elles soient entièrement prélevées.

Si une ligne est prélevée par erreur, un retour doit être effectué pour corriger l'erreur.

Seules les lignes appartenant à la même commande et présentant le même mode de livraison peuvent être prélevées en même temps.

### <a name="shipping"></a>Expédition

Les lignes de commande à expédier à partir du magasin peuvent être traitées via l'opération d'exécution de commandes unifiée à l'aide de l'action **Expédier**. Si l'acceptation manuelle des lignes de commande est configurée au niveau du canal, les commandes doivent être acceptées avant d'être expédiées. Une fois qu'une ligne de commande a été acceptée et que son statut est **En attente** ou autre, les lignes peuvent être expédiées.

**Action : Expédier**

- **Statut résultant :** Facturé ou partiellement facturé
- **Statut résultant de l'arrière-guichet :** Facturé ou partiellement facturé

Les lignes expédiées à partir de l'opération d'exécution de commandes unifiée sont facturées à partir de l'arrière-guichet comme si la commande était facturée directement à partir de l'arrière-guichet. Les lignes expédiées à partir de l'opération d'exécution de commandes unifiée ne sont pas chargées dans la vue des transactions et aucune offre n'est effectuée lors de l'expédition des lignes.

Les lignes de commande qui ont été entièrement expédiées ne s'affichent plus dans l'opération d'exécution de commandes unifiée. Les lignes partiellement expédiées continuent à s'afficher dans l'opération d'exécution de commandes unifiée jusqu'à ce qu'elles soient entièrement expédiées.

Seules les lignes appartenant à la même commande peuvent être expédiées simultanément. Si les lignes d'une même commande ont plusieurs modes de livraison, elles peuvent quand même être sélectionnées simultanément pour expédition.

### <a name="reject"></a>Rejeter

Les lignes ou les lignes partielles peuvent être rejetées. Elles peuvent ainsi être réaffectées de l'arrière-guichet vers un autre magasin ou entrepôt. Les lignes ne peuvent être rejetées que si elles n'ont pas encore été prélevées ou emballées. Pour rejeter une ligne qui a déjà été prélevée ou emballée, le prélèvement ou l'emballage de cette ligne doit être annulé.

**Action : Rejeter**

- **Statut résultant :** Rejeté
- **Statut résultant de l'arrière-guichet :** Aucune modification

Les lignes de commande rejetées sont visibles dans l'espace de travail **Traitement et recherche de commande client**. Effacez le filtre de personne dans l'espace de travail pour afficher toutes les lignes de commande rejetées dans les magasins. L'onglet **Lignes de commande rejetées** sous la section **Commandes et favoris** affiche les détails de la ligne de commande. En outre, les utilisateurs peuvent cliquer sur le bouton **Lignes de commande rejetées** sous la section **Synthèse** pour accéder à la vue des commandes client. Toutes les commandes avec une ou plusieurs lignes de commande rejetées s'affichent. Si la gestion distribuée des commandes (DOM) est activée, les commandes rejetées sont automatiquement réaffectées aux magasins appropriés pour exécution. Cependant, ces lignes de commande peuvent également être réaffectées manuellement. Pour cela, sélectionnez la ligne indiquant **Rejeté** comme **Statut d'exécution** et modifiez le site ou l'entrepôt si nécessaire. Cliquez sur le menu déroulant **Mettre à jour la ligne** et cliquez sur **Réinitialiser le statut d'exécution** pour modifier le statut d'exécution de **Rejeté** à **Accepté** ou **En attente**, selon le paramètre d'exécution des commandes. Une fois que le statut d'exécution est réinitialisé, les collaborateurs du magasin peuvent afficher les lignes de commande dans POS.

## <a name="line-quantity-tracking"></a>Suivi de la quantité de ligne

Une ligne de commande dont la quantité est supérieure à un peut être traitée dans le temps, ce qui génère plusieurs sous-états pour les lignes de commande. Par exemple, si un concepteur a un projet qui nécessite 500 tableaux, mais il ne prélève ou ne livre que quelques tableaux à la fois au cours du projet, des quantités peuvent être prélevées, emballées et expédiées en même temps.

Chaque fois qu'une ligne est sélectionnée, le montant restant de la ligne est renseigné automatiquement pour indiquer que la quantité restante est en cours de traitement. Prenons l'exemple ci-dessus : si 200 tableaux ont déjà été prélevés et la ligne des tableaux est sélectionnée pour prélèvement, la quantité restante de 300 tableaux est automatiquement remplie dans la quantité. Ceci est également valable si 200 tableaux ont déjà été facturés. Dans ce cas, seule la quantité restante est remplie automatiquement.

Continuons avec l'exemple ci-dessus : si 200 tableaux sont marqués comme emballés et l'expédition est sélectionnée, le montant total de 500 tableaux est automatiquement renseigné. Si seuls 200 tableaux sont expédiés, le système suppose que les tableaux précédemment emballés sont en cours d'expédition et la quantité emballée est décrémentée. Si 201 tableaux sont expédiés, les tableaux emballés sont d'abord décrémentés, le tableau restant étant décrémenté de la quantité restante.

## <a name="line-statuses"></a>Statuts des lignes

Les lignes de commande dans le point de vente ont plusieurs statuts pour refléter l'état de la ligne de commande. Les statuts du point de vente et de l'arrière-guichet ne correspondent pas systématiquement. Le statut des lignes de commande est accessible via le point de vente à l'aide des opérations d'exécution des commandes. Dans l'arrière-guichet, les lignes de commande sont accessibles à partir des détails de la commande. Les détails de la commande sont accessibles via le menu **Vente au détail** \> **Clients** \> **Toutes les commandes client**. Sélectionnez **ID commande** pour afficher les détails de la commande. Dans les détails de la commande, sélectionnez l'onglet **Commande client**, puis sélectionnez **Statut détaillé** sous le sous en-tête **Afficher**.

- **En attente** – Les lignes de commande qui ont été affectées à un magasin, mais n'ont pas encore été acceptées ont le statut **En attente** lorsqu'elles sont affichées dans le point de vente. Les lignes en attente d'acceptation dans le point de vente ont le statut **Traitement des commandes** dans l'arrière-guichet.
- **Accepté** – Les lignes de commande qui ont été acceptées manuellement ou automatiquement ont le statut **Accepté** lorsqu'elles sont affichées dans le point de vente. Les lignes avec le statut **Accepté** indiquent **Traitement des commandes** dans l'arrière-guichet.
- **Prélèvement** – Les lignes en cours de prélèvement au niveau du point de vente ont le statut **Prélèvement**. Ces mêmes lignes ont le statut **Traitement des commandes** lorsqu'elles sont affichées dans l'arrière-guichet.
- **Prélevé** et **Partiellement prélevé** – Les lignes qui ont été prélevées ou partiellement prélevées dans le point de vente ont le statut **Prélevé** ou **Partiellement prélevé**. Ces mêmes lignes dans l'arrière-guichet ont également le statut **Prélevé** ou **Partiellement prélevé**.
- **Emballé** et **Partiellement emballé** – Les lignes qui ont été emballées ou partiellement emballées dans le point de vente ont le statut **Emballé** ou **Partiellement emballé**. Ces mêmes lignes dans l'arrière-guichet ont également le statut **Livré** ou **Partiellement livré**.
- **Partiellement facturé** – Les lignes qui ont été partiellement prélevées ou partiellement expédiées ont le statut **Partiellement facturé** dans le point de vente et l'arrière-guichet.
- **Facturé** – Les lignes qui ont été entièrement facturées dans le point de vente ne s'affichent plus pour exécution. Dans l'arrière-guichet, le statut de ces lignes est **Facturé**.

## <a name="order-fulfillment-filtering"></a>Filtrage de l'exécution des commandes

L'exécution des commandes dans le point de vente inclut le filtrage pour aider l'utilisateur à trouver facilement ce dont il a besoin. Les filtres peuvent être modifiés via le volet Actions en bas de l'écran **Point de vente**. Par défaut, un filtre **Type de livraison** est appliqué, selon le paramétrage de l'opération. Si l'opération est configurée avec le paramètre **Toutes les commandes**, ce filtre est appliqué lors de l'accès à l'opération d'exécution des commandes. Ceci est également valable pour les paramètres **Prélèvement en magasin** et **Expédier à partir du magasin**. Les autres filtres qui peuvent être appliqués à la vue d'exécution des commandes sont les suivants :

- Numéro de client
- Nom du client
- E-mail du client
- Numéro de commande
- Mode de livraison
- Numéro d'accusé de réception
- ID référence de canal
- Numéro de magasin d'origine
- Statut de ligne
- Date de création
- Date de livraison
- Date de réception
