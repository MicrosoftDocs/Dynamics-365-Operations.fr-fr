---
title: Retours sur ventes
description: Cet article fournit des informations sur le processus d’ordre de retour. Elle comporte des informations sur les retours client et leurs effets sur l’évaluation des coûts et les quantités de stock disponible.
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnTable, ReturnTableListPagePreviewPane, ReturnTableReferences, SalesReturnExpiredOrdersPart, SalesReturnFindOrderFormPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e8045ec39b9caf9bf0dc2b2d331419efb54e6d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860404"
---
# <a name="sales-returns"></a>Retours sur ventes

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur le processus d’ordre de retour. Elle comporte des informations sur les retours client et leurs effets sur l’évaluation des coûts et les quantités de stock disponible.

Les clients peuvent retourner des articles pour différentes raisons. Par exemple, un article peut être défectueux, ou il peut ne pas répondre aux attentes du client. Le processus de retour démarre lorsqu’un client émet une demande de retour d’un article. Une fois la demande client reçue, un ordre de retour est créé.

## <a name="return-order-process"></a>Processus d’ordre de retour
L’illustration suivante fournit une vue d’ensemble du processus d’ordre de retour.  

[![Processus d’ordre de retour.](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Il existe deux types de processus d’ordre de retour : le retour physique et le retour de type Créditer uniquement.

-   **Retour physique** – L’ordre de retour autorise le retour physique des produits.
-   **Créditer uniquement** – L’ordre de retour autorise de créditer le client mais ne nécessite pas que le client retourne physiquement les produits.

### <a name="physical-return-order-process"></a>Processus d’ordre de retour physique

1.  **Création d’un ordre de retour.** Documentez formellement l’autorisation que le client retourne les produits défectueux ou non souhaités. L’ordre de retour ne nécessite pas que la société accepte les produits retournés ou accorde un crédit au client. Si le retour est accepté, vous pouvez autoriser l’envoi d’un article de remplacement avant que l’article défectueux ne soit retourné.
2.  **Arrivée à l’entrepôt pour inspection.** Réalisez une première inspection et une validation par rapport au bon d’ordre de retour. L’ordre de retour prend également en charge le contrôle des articles retournés pour une inspection et un contrôle qualité supplémentaires.
3.  **Déterminer la destination.** Finalisez le processus d’inspection et décidez ce qu’il convient de faire avec les produits retournés. Dans le cadre de cette étape, décidez si vous accordez un crédit au client, rejetez le retour de produit, ou acceptez le retour de produit, mettez au rebut le produit, puis envoyez un produit de remplacement au client.
4.  **Générer un bon de livraison.** Générez un bon de livraison, puis validez la décision de destination que vous avez prise à l’étape 3. Finalisez les processus logistiques.
5.  **Générer une facture.** Fermez l’ordre de retour.

### <a name="credit-only-process"></a>Processus de type Créditer uniquement

1.  **Création d’un ordre de retour.** Documentez formellement l’autorisation que le client reçoive un crédit sans retourner les produits défectueux ou non souhaités. Le code disposition **Créditer uniquement** autorise la décision à créditer le client sans retour physique.
2.  **Générer une facture.** Générez l’avoir, puis fermez l’ordre de retour.

## <a name="return-material-authorization"></a>Retour de marchandises
Le processus RMA (retour de marchandises) découle de la fonctionnalité de commande client. Un retour marchandises est enregistré comme un ordre de retour, lequel est créé comme une commande client et peut avoir une autre commande client associée, appelée ordre de remplacement. Les deux commandes client renvoient au numéro de retour marchandises d’origine.

-   **Ordre de retour** – Pour enregistrer un retour marchandises, vous créez un ordre de retour, qui est une commande ayant le type **Commande retournée.** Tous les modifications apportées aux informations de retour marchandises sont automatiquement mises à jour dans la commande client. Tant que l’ordre de retour a le statut **En cours**, il n’apparaît pas dans la liste des commandes client. Vous utilisez le retour marchandises pour gérer l’arrivée et la réception des articles retournés, ainsi que pour autoriser une action de crédit uniquement (voir la section **Codes disposition et actions de disposition**). Tous les autres processus de suivi doivent être gérés dans la commande client.
-   **Ordre de remplacement** – Lorsqu’un ordre de remplacement doit être expédié au client, le retour marchandises peut inclure une deuxième commande client associée. Vous pouvez créer manuellement l’ordre de remplacement pour le retour marchandises pour prendre en charge l’expédition immédiate. Sinon, il est possible de créer l’ordre de remplacement automatiquement une fois l’arrivée, l’inspection et la réception achevées pour l’article de retour marchandises ayant le code disposition indiquant le remplacement. L’ordre de remplacement a la même fonctionnalité que celle associée à une commande client. Par exemple, vous pouvez l’utiliser pour configurer un produit personnalisé en tant qu’article de remplacement, créer un ordre de fabrication pour réparer un article retourné, créer une commande fournisseur à livraison directe pour envoyer le produit de remplacement à partir d’un fournisseur, ou pour prendre en charge d’autres objectifs.

## <a name="create-a-return-order"></a>Création d’un ordre de retour
Le processus d’ordre de retour démarre lorsqu’un client contacte votre organisation pour renvoyer un produit défectueux ou non désiré et/ou pour être crédité. Une fois que votre organisation a accepté le retour, celui-ci est documenté par un ordre de retour. Cet ordre de retour devient l’élément essentiel du traitement interne du produit retourné. L’illustration suivante présente la procédure de création d’un ordre de retour.  

[![Procédure de création d’un ordre de retour.](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Créer un ne-tête d’ordre de retour

Lorsque vous créez un ordre de retour, les informations du tableau suivant doivent être incluses.

| Champ              | Description                                              | Commentaires                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Compte client   | Une référence au tableau Clients                       | Vous devez indiquer un compte client existant.                                                                                                                                                                                                                                                                                                  |
| Adresse de livraison   | Adresse à laquelle l’article est renvoyé                 | Par défaut, l’adresse de l’organisation est utilisée. Si un entrepôt spécifique est sélectionné dans l’en-tête, l’adresse de livraison est remplacée par l’adresse de livraison de l’entrepôt. Vous pouvez modifier cette adresse dans la page **Détails de l’ordre de retour**.                                                                                                  |
| Site/entrepôt     | Le site ou l’entrepôt qui reçoit le produit retourné | L’adresse de livraison pour l’ordre de retour est déterminée en fonction de l’adresse de livraison du site ou de l’entrepôt.                                                                                                                                                                                                                                 |
| Numéro de retour marchandises         | L’ID affecté à l’ordre de retour.              | Le numéro de retour marchandises est utilisé comme clé secondaire pendant l’intégralité du processus d’ordre de retour. Le numéro de retour marchandises affecté est fondé sur la souche de numéros de retour marchandises paramétrée dans la page **Paramètres de la comptabilité client**.                                                                                                                              |
| Date limite           | La dernière date à laquelle l’article peut être retourné.               | La valeur par défaut est calculée comme la date du jour plus la période de validité. Par exemple, si un retour est valable pendant seulement 90 jours à compter de la date de création de l’ordre de retour et que l’ordre de retour a été créé le 1er mai, la valeur du champ est **30 juillet**. La période de validité est définie dans la page **Paramètres de la comptabilité client**. |
| Code motif de retour | Le motif du client pour le retour du produit          | Le code motif est sélectionné dans la liste des codes motif définis par l’utilisateur. Vous pouvez actualiser ce champ à tout moment.                                                                                                                                                                                                                                    |
### <a name="create-return-order-lines"></a>Créer des lignes d’ordre de retour

Après avoir réalisé l’en-tête de retour, vous pouvez créer des lignes de retour à l’aide d’une des méthodes suivantes :

-   Entrez manuellement les détails de l’article, la quantité et les autres informations pour chaque ligne de retour.
-   Créez une ligne de retour à l’aide la fonction **Rechercher une commande client**. Il est recommandé d’utiliser cette fonction quand vous créez un ordre de retour. La fonction **Rechercher une commande client** établit une référence entre la ligne de retour et la ligne de commande client facturée, et extrait des détails de ligne tels que le numéro d’article, la quantité, le prix, la remise, et le coût à partir de la ligne de vente. Vous aide de référence garantissent que, lorsque le produit est retourné à la société, elle a la valeur du même coût unitaire qu’elle a été vendu à. La référence valide également que les ordres de retour ne sont pas créés pour une quantité supérieure à la quantité vendue sur la facture.

>[!NOTE] 
>Les lignes de retour faisant référence à une commande client sont traitées comme des corrections, ou des contrepassations de la vente. Pour plus d’informations, voir la section « Valider dans la comptabilité » plus loin dans cet article.

### <a name="charges"></a>Frais

Les frais et charges peuvent être ajoutés à l’ordre de retour via une ou plusieurs des méthodes suivantes :

-   Vous pouvez ajouter manuellement des frais à l’en-tête de l’ordre de retour, à la ligne d’ordre de retour, ou aux deux.
-   Les frais peuvent être ajoutés automatiquement à l’en-tête de l’ordre de retour en fonction du code motif du retour.
-   Les frais peuvent être ajoutés automatiquement à la ligne de l’ordre de retour, en fonction du code disposition de la ligne.

Les frais sont automatiquement ajoutés après que le code motif ou le code disposition a été affecté à la ligne. Si le code motif est modifié ultérieurement, l’entrée de frais existante ne sera pas supprimée, mais une nouvelle entrée de frais pourra être ajoutée, en fonction du nouveau code motif. Lorsque vous ajoutez des frais aux lignes d’ordre de retour, les frais calculés comme un pourcentage de la valeur de la ligne ou de la commande deviennent négatifs lorsque la valeur de ligne ou de commande est négative, à moins que le pourcentage ne soit également un nombre négatif. Les frais qui ont une valeur négative représentent un crédit pour le client.

### <a name="return-reason-codes"></a>Codes motif de retour

L’application de codes motif aux retours, vous facilitez l’analyse des schémas de retour. Les codes motif fournissent des informations sur la raison pour laquelle un client souhaite retourner des articles. Certaines organisations ont plusieurs codes motif. Ces organisations regroupent parfois les codes motif en groupes pour avoir une meilleure vue d’ensemble et pour la génération de rapports cumulés.

### <a name="disposition-codes-and-disposition-actions"></a>Codes et actions de disposition

Une étape importante du processus d’ordre de retour consiste à affecter un code disposition à la ligne d’ordre de retour dans le cadre de l’enregistrement de l’arrivée. Le code disposition détermine les informations suivantes :

-   **Les implications financières** – Le client doit-il doit être crédité pour les articles retournés et des frais doivent-ils être ajoutés à la ligne d’ordre de retour ?
-   **La destination de l’article retourné** – L’article doit-il être remis dans le stock, être mis au rebut, ou être retourné au client ?
-   **La logistique de l’article retourné** – Faut-il envoyer un article de remplacement au client ?

En plus de déterminer la destination des marchandises retournées, les codes disposition peuvent entraîner l’application de frais à la ligne de retour. Ils peuvent également être utilisés pour groupe les retours à des fins d’analyse statistique. Les codes disposition sont définis dans le cadre du paramétrage des ordres de retour. Toutefois, chaque code disposition doit faire référence à l’une des actions disposition intégrées. Le tableau suivant répertorie les codes disposition intégrés et leurs actions associées. **Important :** si un article ne doit pas être retourné, mais que le client doit quand même être crédité, affectez le code disposition **Crédit uniquement** à la ligne de retour.

<table>
<thead>
<tr class="header">
<th>Code disposition</th>
<th>Implications financières</th>
<th>Implications pour la logistique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Créditer uniquement</td>
<td><ul>
<li>Le client est crédité du prix de vente moins les frais.</li>
<li>La perte associée à la mise au rebut de l’article est validée dans la comptabilité.</li>
</ul></td>
<td>L’article ne doit pas être retourné. Cette action de disposition est utilisée dans les cas suivants :
<ul>
<li>il existe une confiance suffisante entre les parties.</li>
<li>Le coût de retour de l’article défectueux est prohibitif.</li>
<li>Les articles ne peuvent pas être acceptés dans le stock. En raison d’autres conditions, un retour physique n&#39;est pas nécessaire.</li>
</ul></td>
</tr>
<tr class="even">
<td>Crédit</td>
<td><ul>
<li>Le client est crédité du prix de vente moins les frais.</li>
<li>La valeur de stock est augmentée du coût de l’article retourné.</li>
</ul></td>
<td>L’article est retourné et est remis dans le stock.</td>
</tr>
<tr class="odd">
<td>Remplacer et créditer</td>
<td><ul>
<li>Le client est crédité du prix de vente moins les frais.</li>
<li>La valeur de stock est augmentée du coût de l’article retourné.</li>
<li>Une commande client distincte de remplacement est créée et est gérée séparément.</li>
</ul></td>
<td>L’article est retourné et est remis dans le stock.</td>
</tr>
<tr class="even">
<td>Remplacer et mettre au rebut</td>
<td><ul>
<li>Le client est crédité du prix de vente moins les frais.</li>
<li>La perte associée à la mise au rebut de l’article est validée dans la comptabilité.</li>
<li>Une commande client distincte de remplacement est créée et est gérée séparément.</li>
</ul></td>
<td>L’article est retourné et mis au rebut.</td>
</tr>
<tr class="odd">
<td>Retourner au client</td>
<td>Aucune, sauf les frais.</td>
<td>L’article est retourné mais est renvoyé au client après inspection. Cette action de disposition peut être utilisée si l’article a été délibérément endommagé, ou si la garantie a été annulée.</td>
</tr>
<tr class="even">
<td>Rebut</td>
<td><ul>
<li>Le client est crédité du prix de vente moins les frais.</li>
<li>La perte associée à la mise au rebut de l’article est validée dans la comptabilité.</li>
</ul></td>
<td>L’article est retourné ou mis au rebut.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Arrivée à l’entrepôt pour inspection
Avant de recevoir physiquement les articles retournés dans le stock en validant un bon de livraison, les articles doivent passer par l’enregistrement d’arrivée et une inspection facultative. L’illustration suivante présente une vue d’ensemble du processus d’arrivée. Les sections suivantes décrivent toutes les étapes présentées dans l’illustration.  

[![Processus d’arrivée.](./media/salesreturn03.png)](./media/salesreturn03.png)  

Le processus présente plusieurs variations qui ne sont pas abordées dans cet article. Voici quelques unes de ces variations.

-   N’utilisez pas la liste **Vue d’ensemble des arrivées** pour créer un journal des arrivées. Au lieu de cela, créez manuellement le journal des arrivées. Les ordres de retour auront **Commande client** comme référence.
-   Si vous utilisez la Gestion des entrepôts, générez des transports de palettes. La ligne de retour aura le statut **Arrivée** lors du transport de palette.
-   Enregistrez l’arrivée de l’article retourné directement à partir de la ligne d’ordre de retour, à l’aide de la fonction **Enregistrement**.

Pendant le processus d’arrivée, les retours sont intégrés au processus général pour les arrivées à l’entrepôt. Le processus d’arrivée prend également en charge la création d’ordres de contrôle pour les articles retournés qui doivent subir une inspection distincte.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identifier les produits dans la liste de vue d’ensemble des arrivées

La page **Vue d’ensemble des arrivées** répertorie toutes les arrivées entrantes prévues.

>[!NOTE] 
>Les arrivées provenant d’ordres de retour doivent être traitées séparément des autres types de transactions d’arrivée. Après avoir identifié un article entrant dans la page **Vue d’ensemble des arrivées** (par exemple, à l’aide du document de retour marchandise d’accompagnement), dans le volet Action, cliquez sur **Commencer une arrivée** pour créer et initialiser un journal des arrivées correspondant à l’arrivée.

### <a name="edit-the-arrival-journal"></a>Modifier le journal des arrivées

En définissant l’option **Gestion des contrôles** sur **Oui**, vous pouvez créer un ordre de contrôle pour la ligne de retour. Si une ligne a été soumise au contrôle pour inspection, vous ne pouvez pas spécifier le code disposition. 
 
Si vous définissez l’option **Gestion des contrôles** sur **Oui** dans le groupe de modèles de stock de l’article, l’option **Gestion des contrôles** de la page **Lignes de journal** sera marquée pour la ligne de journal des arrivées et ne pourra pas être modifiée. Si la ligne est soumise au contrôle, vous devez spécifier l’entrepôt de contrôle approprié. 

Si la ligne entrante n’est pas soumise à inspection, l’employé en charge des arrivées à l’entrepôt doit spécifier le code disposition directement sur la ligne de journal des arrivées puis valider le journal des arrivées. S’il ne convient pas d’affecter le même code disposition à toute la quantité de la ligne de retour, ou si la quantité complète de la ligne n’a pas été reçue, vous devez diviser la ligne. Si vous divisez une ligne de journal des arrivées, vous devez également diviser la ligne de retour (**SalesLine**) et créer un nouvel ID de lot. Vous pouvez diviser la ligne en réduisant la quantité de la ligne du journal des arrivées. Lorsque le journal est validé, il crée une nouvelle ligne de retour ayant le statut **Prévu** pour la quantité restante. Vous pouvez également diviser la ligne en cliquant sur **Fonctions** &gt; **Diviser**.

### <a name="process-the-quarantine-order"></a>Traiter de l’ordre de contrôle

Si les produits retournés sont envoyés à l’inspection à l’entrepôt de contrôle, le traitement supplémentaire est réalisé dans un ordre de contrôle. Un ordre de contrôle est créé pour chaque ligne d’arrivée envoyée au contrôle. Le code disposition indique le résultat du processus d’inspection. 

Vous pouvez fractionner un ordre de contrôle, tout comme vous pouvez fractionner le journal des arrivées. Si vous fractionnez l’ordre de contrôle, vous provoquez un fractionnement correspondant de la ligne de retour. Une fois le code disposition entré, complétez l’ordre de contrôle en utilisant, soit la fonction **Fin**, soit la fonction **Déclarer comme terminé**. Si vous sélectionnez **Déclarer comme terminé**, une nouvelle arrivée est créer dans l’entrepôt désigné. Vous pouvez ensuite traiter cette arrivée à l’aide de la page **Vue d’ensemble des arrivées**. 

Si l’arrivée provient d’un ordre de contrôle, vous ne pouvez pas modifier le code disposition affecté au cours de l’inspection. Si vous terminez l’ordre de contrôle à l’aide de la fonction **Fin**, le lot est automatiquement enregistré. Parfois, un article peut être renvoyé du contrôle au département d’expédition et de réception. Par exemple, l’inspecteur du contrôle peut ne pas savoir où enregistrer l’article dans le stock. Dans ce cas, le bon de livraison correspondant doit être mis à jour pour enregistrer correctement le code disposition spécifié en raison du contrôle et agir en conséquence. 

L’accusé de réception de la réception peut être envoyé au client lorsque la ligne de retour est enregistrée. Le rapport **Accusé de réception de retour** ressemble document d’ordre de retour. La rapport **Accusé de réception de retour** n’est pas journalisé ni autrement enregistré dans le système, et ce n’est pas une étape obligatoire dans le processus d’ordre de retour.

## <a name="replace-a-product"></a>Remplacement d’un produit
Il existe deux méthodes pour gérer le remplacement de produit :

-   **Remplacement avant** – Remplace un produit avant que le produit retourné ne soit reçu du client.
-   **Remplacement par code disposition** – Crée automatiquement une nouvelle ligne d’ordre de remplacement.

### <a name="up-front-replacement"></a>Remplacement avant

Dans le remplacement avant, l’article de remplacement peut être livré au client avant que l’article ne soit retourné. Cette méthode est utile, par exemple, si l’article est une pièce de machine qui ne peut pas être retirée tant qu’une pièce détachée n’est pas prête à la remplacer, ou simplement si vous souhaitez que votre client reçoive le produit de remplacement le plus tôt possible. L’ordre de remplacement avant est une commande client indépendante. Les informations d’en-tête sont initialisée à partir du client, et les informations de ligne sont initialisées à partir de l’ordre de retour. Vous pouvez modifier, traiter et supprimer l’ordre de remplacement indépendamment de l’ordre de retour. Lorsque vous supprimez un ordre de remplacement, vous recevez un message indiquant que l’ordre a été créé comme un ordre de remplacement. L’illustration suivante présente le processus du remplacement avant.  

![Processus de remplacement avant.](./media/SalesReturn04.png)

L’ordre de retour contient une référence à l’ordre de remplacement. Si un ordre de remplacement avant a été créé pour un ordre de retour avant que l’article défectueux ne soit retourné, vous ne pouvez pas sélectionner les codes disposition pour le remplacement après que l’article défectueux a été renvoyé.

### <a name="replacement-by-disposition-code"></a>Remplacement par code disposition

Si vous expédiez un article de remplacement au client, et que vous utilisez l’action de disposition **Remplacer et mettre au rebut** ou **Remplacer et créditer** dans l’ordre de retour, suivez le processus présenté dans l’illustration suivante.  

![Processus de remplacement lors de l’utilisation d’un code disposition.](./media/SalesReturn05.png)

L’article de remplacement sera livré à l’aide d’une commande client est indépendante, la commande client de remplacement. Cette commande client est créée lorsque le bon de livraison de l’ordre de retour est généré. L’en-tête de l’ordre utilise les informations du client référencé dans l’en-tête de l’ordre de retour. Les informations de ligne sont collectées à partir des informations entrées dans la page **Article de remplacement**. La page **Article de remplacement** doit être remplie pour les lignes ayant des actions de disposition commençant par le mot « remplacer ». Toutefois, ni la quantité ni l’identité de l’article de remplacement n’est validée ou limitée. Cela permet de traiter les cas où le client souhaite recevoir le même article, mais dans une taille ou une configuration différente, ainsi que les cas où le client souhaite un article complètement différent. Par défaut, un article identiques est entré dans la page **Article de remplacement**. Toutefois, vous pouvez sélectionner un autre article, à condition que la fonction ait été paramétrée. 

>[!NOTE] 
>Vous pouvez modifier et supprimer la commande client de remplacement une fois qu’elle a été créée.

## <a name="generate-a-packing-slip"></a>Générer un bon de livraison
Pour pouvoir recevoir des retours marchandises dans le stock, vous devez mettre à jour le bon de livraison relatif à la commande à laquelle appartiennent les articles. Toute comme le traitement de mise à jour de facture consiste à mettre à jour la transaction financière, le traitement de mise à jour de bon de livraison consiste à mettre à jour physiquement l’enregistrement de stock. En d’autres termes, ce processus valide les modifications apportées au stock. En cas de retour, les opérations affectées à l’action de disposition sont exécutées durant la mise à jour du bon de livraison. Lorsque vous générez le bon de livraison, les événements suivants se produisent :

-   Dans l’entrepôt, le processus standard est utilisé pour effectuer une réception physique. Les validations comptables sont générées si le groupe de modèles de stock (**Valider le stock physique**) et les paramètres de la comptabilité client (**Valider le bon de livraison dans la comptabilité**) sont définis correctement.
-   Les articles qui ont été marqués avec une action de disposition contenant le mot « rebut » sont mis au rebut, et une perte de stock est validée dans la comptabilité.
-   Les articles qui ont été marqués avec l’action de disposition **Retourner au client** sont réceptionnés et livrés au client. Ces articles n’ont aucun effet net sur le stock.
-   Une commande client de remplacement est créée. Cette commande client est basé sur les informations de la page **Article de remplacement**.

Vous pouvez générer le bon de livraison uniquement pour les lignes ayant le statut de retour **Enregistré**, et seulement pour la quantité complète indiquée dans la ligne de retour. Si plusieurs lignes de l’ordre de retour ont le statut **Enregistré**, vous pouvez générer le bon de livraison pour un sous-ensemble de lignes en supprimant les autres lignes de la page **Validation du bon de livraison**. 

Les retours partiels sont définis en termes de lignes d’ordre de retour, pas en termes d’expéditions de retour. Par conséquent, si vous recevez la quantité complète indiquée sur une ligne d’ordre de retour, mais rien en rapport avec les autres lignes, la livraison n’est pas partielle. En revanche, si une ligne d’ordre de retour indique que dix unités d’un article doivent être retournées et que vous n’en recevez que quatre, la livraison est partielle. Si tous les articles de retour prévus ne sont pas arrivés, vous pouvez mettre l’expédition de côté en attendant l’arrivée du reste de la quantité à retourner. Sinon, vous pouvez enregistrer et valider la quantité partielle. Dans le cadre du traitement de validation des bons de livraison, vous pouvez associer le numéro de référence du bon de livraison figurant sur les documents d’expédition du client aux lignes de commande. Cette association est purement indicative. Elle n’entraîne pas de mises à jour de transactions. 

De manière générale, vous pouvez ignorer le processus de bon de livraison et passer directement à la facturation. Dans ce cas, les étapes que vous auriez effectuées lors de la génération du bon de livraison sont effectuées lors de la facturation.

## <a name="generate-an-invoice"></a>Générer une facture
Bien que la page **Ordre de retour** contienne les informations et les actions nécessaires pour traiter les aspects logistiques spéciaux de l’ordre de retour, vous devez utiliser la page **Commande client** pour exécuter le processus de facturation. Votre organisation peut ensuite facturer les ordres de retour et les commandes client simultanément, et la même personne peut réaliser la facturation, selon les besoins. Pour afficher l’ordre de retour à partir de la page **Commande client**, cliquez sur le lien correspondant au numéro de commande client pour ouvrir la commande client associée. Vous pouvez également trouver l’ordre de retour dans la page **Toutes les commandes client**. Les ordres de retour sont des commandes client ayant le type de commande **Commande retournée**.

### <a name="credit-correction"></a>Correction de crédit

Dans le cadre du processus de facturation, vérifiez que tous les frais divers sont corrects. Pour que les validations dans la comptabilité deviennent des corrections (Storno), envisagez d’utiliser l’option **Correction de crédit** de l’onglet **Autre** de la page **Validation de la facture** quand vous validez la facture ou l’avoir.

> [!NOTE]
> Par défaut, l’option **Correction de crédit** est activée si l’option **Avoir comme correction** de la page **Paramètres de la comptabilité client** est activée. Cependant, il est recommandé de ne pas valider les retours avec la méthode Storno.

## <a name="create-intercompany-return-orders"></a>Créer des ordres de retour intersociétés
Les ordres de retour peuvent être réalisés entre deux sociétés de votre organisation. Les scénarios suivants sont pris en charge :

-   les retours intersociétés simples entre deux sociétés qui participent à une relation intersociétés
-   Une chaîne intersociétés qui est établie lorsqu’un ordre de retour client est créé au niveau de la société vendeuse
-   Une chaîne intersociétés qui est établie lorsqu’un ordre de retour fournisseur est créé au niveau de la société acheteuse
-   les retours à expédition directe entre un client externe et deux sociétés qui participent à une relation intersociétés

### <a name="setup"></a>Configuration

L’illustration suivante montre le paramétrage minimal requis pour que deux sociétés participent à une relation intersociétés et profitent du commerce intersociétés.  

![Paramétrage minimal.](./media/SalesReturn06.png)

Dans le scénario suivant, CompBuy est la société acheteuse, et CompSell est la société vendeuse. Généralement, la société vendeuse expédie les marchandises, soit à la société acheteuse soit, dans les scénarios d’expédition directe, directement au client final. Chez CompBuy, le fournisseur IC\_CompSell est défini comme un point de terminaison intersociétés associé à la société CompSell. Simultanément, Chez CompSell, le client IC\_CompBuy est défini comme un point de terminaison intersociétés associé à la société CompBuy. Les détails et les mises en correspondance de valeurs de la stratégie d’action appropriée doivent être définis dans les deux sociétés. Dans un scénario d’expédition directe, un ordre de retour intersociétés, qui est également une commande client intersociétés, est créé dans la société vendeuse. Le numéro de retour marchandises de l’ordre de retour intersociétés peut être repris dans la souche de numéros de retour marchandises chez CompSell, ou il peut être copié depuis le numéro de retour marchandises affecté à l’ordre de retour d’origine chez CompBuy. Les paramètres de numéro de retour marchandises de la stratégie d’action **PurchaseRequisition** chez CompBuy déterminent ces actions. Si le numéro de retour marchandises est synchronisé, vous devez prévoir de limiter le risque de conflits de numéros si les deux sociétés utilisent la même souche de numéros.

### <a name="simple-intercompany-returns"></a>Retour intersociétés simple

Ce scénario implique deux sociétés de la même organisation, comme le montre l’illustration suivante.  

![Retour intersociétés simple.](./media/SalesReturn07.png)

La chaîne de commande peut être établie lorsqu’un ordre de retour fournisseur est créée dans la société acheteuse ou qu’un ordre de retour client est créé dans la société vendeuse. La commande correspondante est créée dans l’autre société et s’assure que les informations d’en-tête et de ligne dans l’ordre de retour fournisseur reflètent les paramètres de l’ordre de retour client. L’ordre de retour créé peut inclure ou exclure la référence (**Rechercher une commande client**) à une facture client existante. Les bons de livraison et les factures des deux commandes peuvent être traités individuellement. Par exemple, vous n’êtes pas obligé de générer un bon de livraison pour l’ordre de retour fournisseur avant de générer le bon de livraison pour l’ordre de retour client.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Retours à expédition directe entre trois parties

Ce scénario peut être établi si une vente précédente du type **Livraison directe** a été effectuée et s’il existe une facture concernant le client dans la société qui interagit avec le client. Dans l’illustration suivante, la société CompBuy a précédemment vendu et facturé des produits au client Extern. Les produits ont été expédiés directement de la société CompSell au client via une chaîne de commandes intersociétés.  

![Retours à expédition directe entre trois parties.](./media/SalesReturn08.png)

Si le client Extern souhaite retourner les produits, un ordre de retour (RMA02) est créé pour le client dans la société CompBuy. Pour établir la chaîne intersociétés, l’ordre de retour doit être marqué pour la livraison directe. Lorsque vous utilisez la fonction **Rechercher une commande client** pour trouver la facture client du retour, une chaîne de commandes intersociétés incluant les documents suivants est établie :

-   **Ordre de retour d’origine :** RMA02 (société CompBuy)
-   **Commande fournisseur :** PO02 (société CompBuy)
-   **Ordre de retour intersociétés :** RMA\_00032 (société CompSell)

Une fois la chaîne intersociétés de livraison directe créée, tout le traitement et la manipulation physiques des retours doivent se produire dans le contexte de l’ordre de retour intersociétés, RMA\_00032 dans la société CompSell. Les produits ne peuvent pas être reçus à la société CompBuy. Lorsqu’un code disposition est affecté à l’ordre de retour intersociétés, il est synchronisé avec l’ordre de retour d’origine pour permettre la facturation appropriée de la commande d’origine.

## <a name="post-to-the-ledger"></a>Validation dans la comptabilité
Les validations comptables générées lorsque l’ordre de retour est facturé sont influencées par certains paramètres essentiels :

-   **Prix de revient du retour** – Pour les modèles de stock autres que **Coût standard**, le paramètre **Prix de revient du retour** détermine le coût de l’article lorsqu’il est repris dans le stock ou mis au rebut. Pour calculer la valeur correcte de l’inventaire, il est important de définir correctement le paramètre **Prix de revient du retour**. Si vous utilisez la fonction **Rechercher une commande client** pour créer une ligne d’ordre de retour faisant référence à une facture client, la valeur **Prix de revient du retour** est égale au prix de vente de l’article vendu. Sinon, la valeur du prix de revient provient de la définition de l’article ou peut être entrée manuellement.
-   **Correction de crédit/Storno** – Le paramètre **Correction de crédit** dans la page **Validation de la facture** détermine si les validations doivent être enregistrées comme positives (DR/CR) ou comme des entrées de correction, négatives.

Dans les exemples suivants, le prix de revient du retour est représenté comme **Prix de revient de stock**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Exemple 1 : l’ordre de retour ne fait pas référence à une facture client

L’ordre de retour ne fait pas référence à une facture client. L’article retourné est crédité. Le paramètre **Correction de crédit** n’est pas sélectionné lorsque la facture d’ordre de retour ou l’avoir sont générés.  

![L’ordre de retour ne fait pas référence à une facture client.](./media/SalesReturn09.png)  

> [!NOTE]
> Le prix de base de l’article sert de valeur par défaut pour le paramètre **Prix de vente de retour**. Le prix par défaut diffère du prix de revient au moment de la sortie du stock. Par conséquent, l’implication est qu’une perte de 3 a été subie. En outre, l’ordre de retour n’inclut pas la remise qui a été accordée au client sur la commande client. Par conséquent, un crédit excessif apparaît.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Exemple 2 : la correction de crédit est sélectionnée pour l’ordre de retour

L’exemple 2 est le même que l’exemple 1, mais le paramètre **Correction de crédit** est sélectionné lorsque la facture d’ordre de retour est générée.  

![Ordre de retour lorsque la correction de crédit est sélectionnée.](./media/SalesReturn10.png)  

>[!NOTE] 
>Les validations comptables sont entrées comme des corrections négatives.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Exemple 3 : la ligne d’ordre de retour est créée à l’aide de la fonction Rechercher une commande client

Dans cet exemple, la ligne d’ordre de retour est créée à l’aide de la fonction **Rechercher une commande client**. Le paramètre **Correction de crédit** n’est pas sélectionné quand la facture est générée.  

![Ligne d’ordre de retour créée à l’aide de la fonction Rechercher une commande client.](./media/SalesReturn11.png)  

> [!NOTE]
> **Remise** et **Prix de vente de retour** sont définis correctement. Par conséquent, une contrepassation exacte de la facture client est réalisée.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]