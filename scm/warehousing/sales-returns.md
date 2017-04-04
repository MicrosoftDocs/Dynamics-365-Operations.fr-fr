---
title: Retours sur ventes
description: "Cette rubrique fournit des informations sur le processus pour les ordres de retour. Elle comporte des informations sur les retours client et leurs effets sur les quantités d&quot;évaluation des coûts et de stock disponible."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Retours sur ventes

Cette rubrique fournit des informations sur le processus pour les ordres de retour. Elle comporte des informations sur les retours client et leurs effets sur les quantités d'évaluation des coûts et de stock disponible.

Les clients peuvent retourner des articles pour différents motifs. Par exemple, un article peut être défectueux, ou il peut ne pas disposer des attentes du client. Les démarrage de retour de processus lorsqu'un client publie une demande de retourner un article. Une fois la demande du client soit reçue, un ordre de retour est créé dans Microsoft Dynamics 365 pour les opérations.

## <a name="return-order-process"></a>Processus d'ordre de retour
L'illustration suivante fournit une vue d'ensemble du processus d'ordre de retour.  

![salesreturns01 [] (. /media/salesreturns01.jpg)](. /media/salesreturns01.jpg)  

Il existe deux types de processus d'ordre de retour : retour et crédit physiques uniquement.

-   ** Le retour physiques ** – L'ordre de retour autorise le retour physique des produits.
-   ** Le crédit uniquement ** – L'ordre de retour autorise un crédit client mais ne le nécessite pas que le retour de client physiquement les produits.

### <a name="physical-return-order-process"></a>Processus physique d'ordre de retour

1.  ** Création d'un ordre de retour. ** Nom formellement l'autorisation pour le client retourne tous les produits défectueux ou non souhaités. L'ordre de retour ne nécessite pas que la société accepte les produits retournés ou fournissent un crédit pour le client. Si le retour est acceptée, vous pouvez autoriser un article de remplacement à envoyer avant que l'article défectueux renvoyé.
2.  ** Arrivez dans l'entrepôt pour l'inspection. ** Effectuer une première inspection et un contrôle par rapport à le bon de commande de retour. L'ordre de retour prend également en charge le contrôle des retours marchandises pour l'inspection et le contrôle de la qualité supplémentaires.
3.  ** Déterminer la destination. ** Finaliser le processus d'inspection, et décidez à mettre fin actions à entreprendre avec les produits retournés. Dans le cadre de cette étape, décidez si vous créditerez le client, rejeter le retour de produit, ou acceptez le retour de produit, rebut le produit, puis envoyez un produit de remplacement au client.
4.  ** Génération d'un bon de livraison. ** Générez un bon de livraison, puis validez la décision de destination que vous avez prise dans l'étape 3. Finaliser les processus à prévisionnel de logistique.
5.  ** Générer une facture. ** Fermez l'ordre de retour.

### <a name="credit-only-process"></a>Créditez que le processus

1.  ** Création d'un ordre de retour. ** Nom formellement l'autorisation pour que le client reçoive un crédit sans retourner les produits défectueux ou non souhaités. ** Crédit uniquement ** code disposition autorise la décision à créditer le client sans retour physiques.
2.  ** Générer une facture. ** Générez l'avoir, puis fermez l'ordre de retour.

## <a name="return-material-authorization"></a>Autorisation de matériel de retour
Autorisation de matériel de retour (RMA) traitant les versions dans la fonctionnalité de commande client. Un retour marchandises est enregistré comme un ordre de retour, qui est créée comme commande client, et peut avoir une autre commande client est associée, appelé ordre de remplacement. Les deux commandes client renvoient au numéro d'origine de retour marchandises.

-   ** Ordre de retour ** – Permet d'enregistrer un retour marchandises, vous créez un ordre de retour, qui est une commande client dont le type affecté, ** Commande retournée. ** Tous les modifications apportées aux informations de retour marchandises est automatiquement mis à jour d'une commande client. Tant que l'ordre de retour a le statut ** en cours **, il n'apparaît pas dans la liste des commandes client. Vous utilisez retour marchandises pour gérer l'arrivée et la réception des articles retournés, ainsi que pour autoriser une action de disposition de crédit uniquement (voir la section ** codes disposition et des actions de disposition **). Tous les autres processus de suivi doivent être traités dans la commande client.
-   ** L'ordre de remplacement ** – Lorsqu'un ordre de remplacement doit être expédiés au client, le retour marchandises peut inclure une deuxième commande client associée. Vous pouvez créer manuellement l'ordre de remplacement pour le retour marchandises prenne en charge l'expédition automatique. Sinon, l'ordre de remplacement peut être créé automatiquement après l'arrivée, l'inspection, et la réception sont effectuées pour la ligne de retour marchandises ayant code disposition indiquant le remplacement. L'ordre de remplacement a la même fonctionnalité associée à une commande client. Par exemple, vous pouvez l'utiliser pour configurer un produit personnalisé en tant qu'article de remplacement, créer un ordre de fabrication de réparer un retour marchandises, de créer une commande fournisseur directe de la livraison d'envoyer le remplacement d'un fournisseur, ou pour prendre en charge l'autre fin.

## <a name="create-a-return-order"></a>Création d'un ordre de retour
Les le processus d'ordre de retour lorsque contacts client votre organisation pour le renvoi d'un produit défectueux ou non désiré et/ou à créditer. Lorsque votre organisation s'est engagée le retour, le retour est documenté par un ordre de retour. Cet ordre de retour devient point de traiter interne du produit retourné. L'illustration suivante présente la procédure de création d'un ordre de retour.  

[procédure![pour créer un ordre de retour (]. /media/salesreturn02.png)](. /media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Créent une en-tête de l'ordre de retour

Lorsque vous créez un ordre de retour, les informations du tableau suivant doit être incluse.

| Champ              | description ;                                              | Commentaires                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Compte client   | Référence à la table des clients                       | Vous devez indiquer un compte client existant.                                                                                                                                                                                                                                                                                                  |
| Adresse de livraison   | Adresse de l'article est retourné à                 | Par défaut, l'adresse de l'organisation est utilisée. Si un entrepôt spécifique est sélectionné dans l'en-tête, l'adresse de livraison est remplacée par l'adresse de livraison de l'entrepôt. Vous pouvez modifier cette adresse sur ** les détails de l'ordre de retour ** la page.                                                                                                  |
| Relations entre les sites/entrepôt     | Le site ou entrepôt qui reçoit le produit retourné | L'adresse de livraison pour l'ordre de retour est déterminée selon l'adresse de livraison du site ou de l'entrepôt.                                                                                                                                                                                                                                 |
| Numéro de retour marchandises         | ID affecté à l'ordre de retour              | Le numéro de retour marchandises est utilisé comme clé secondaire pendant le processus d'ordre de retour. Le numéro de retour marchandises qui est affecté selon la souche de numéros de retour marchandises paramétrée sous ** des paramètres des ventes ** la page.                                                                                                                              |
| Date limite           | Dernière date de l'article peut être renvoyé               | La valeur par défaut est calculée comme la date actuelle plus la période de validité. Par exemple, si un retour est valable que 90 jours de date de fin de l'ordre de retour est créé, et l'ordre de retour a été créé le 1er mai, la valeur du champ est ** 30-July **. La période de validité est définie sur ** des paramètres des ventes ** la page. |
| Code motif de retour | Le motif du client pour retourner le produit          | Un code motif est sélectionné dans la liste des codes motif définis par l'utilisateur. Vous pouvez mettre ce champ à jour à tout moment.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Créez les lignes d'ordre de retour

Après avoir effectué l'en-tête de retour, vous pouvez créer des lignes de retour à l'aide d'une des méthodes suivantes :

-   Entrez manuellement les détails de l'article, la quantité, et d'autres informations pour chaque compte principal de retour.
-   Créez un compte de retour à l'aide ** commande client de trouver ** de la fonction. Il est recommandé d'utiliser cette fonction que si vous créez un ordre de retour. ** Commande client de trouver ** la fonction établit une référence du compte principal de retour à la ligne de commande client facturée, et extrait des détails de ligne tels que le numéro d'article, la quantité, le prix, la remise, et les valeurs de coût de la ligne de vente. Vous aide de référence garantissent que, lorsque le produit est retourné à la société, elle a la valeur du même coût unitaire qu'elle a été vendu à. La référence valide également que les ordres de retour ne sont pas créés pour une quantité supérieure à la quantité a été vendue sur la facture.

** Remarque : ** Les lignes de retour dont une référence à une commande client sont traitées comme corrections, ou contrepassations, entrez la vente. Pour plus d'informations, voir « valider la section dans Comptabilité », plus loin dans cette rubrique.

### <a name="charges"></a>Frais

Les frais et les frais peuvent être ajoutés à l'ordre de retour dans un ou plusieurs des méthodes suivantes :

-   Vous pouvez ajouter manuellement des frais à l'en-tête de l'ordre de retour, à la ligne d'ordre de retour, ou les deux.
-   Les frais peuvent être ajoutés automatiquement à l'en-tête de l'ordre de retour {{en:as_a_function_of}} {{fonction:as_a_function_of}} de codes motif de retour.
-   Les frais peuvent être ajoutés automatiquement à la ligne d'ordre de retour, selon le code disposition de la ligne.

Les frais sont automatiquement ajoutés après que le code motif ou code disposition de retour soit affecté à la ligne. Si le code motif est modifié ultérieurement, l'entrée existante de frais ne sera pas supprimée, mais une nouvelle entrée de frais peut être ajoutée, selon le nouveau code motif. Lorsque vous ajoutez des frais aux lignes d'ordre de retour, les frais calculés comme un pourcentage de la ligne ou la valeur d'ordre devienne négatif lorsque la ligne ou la ligne d'ordre est négative, à moins qu'un pourcentage doit également disposer d'un nombre négatif. Les frais qui ont une valeur négative représentent un crédit au client.

### <a name="return-reason-codes"></a>Codes motif de retour

Lorsque vous appliquez des codes motif aux retours, vous pouvez faciliter les modèles de retour pour analyser. Codes motif fournissent des informations sur la raison pour laquelle un client souhaite retourner des articles. Certaines organisations ont plusieurs codes motif. Ces l'organisation peut regrouper les codes motif en groupes de codes motif à remporter une meilleure vue d'ensemble et pour la génération d'états cumulée.

### <a name="disposition-codes-and-disposition-actions"></a>Codes disposition et actions de disposition

Une étape majeure du processus d'ordre de retour est l'affectation de code disposition à la ligne d'ordre de retour dans le cadre de l'enregistrement de pointage à l'arrivée. Code de disposition détermine les informations suivantes :

-   Des que ** les implications financières ** – Le client doit doit être crédité pour les retours marchandises, et les frais être ajouté à la ligne d'ordre de retour ?
-   Des que ** la destination du retour marchandises ** – doit -elle en l'article peut doit doit être ajoutée au stock, elle être mise au rebut, soit il être retournée au client ?
-   ** La logistique du retour marchandises ** – un article de remplacement devrait-il être publié au client ?

Outre déterminer comment les marchandises retournées sont cédées, codes disposition peuvent entraîner des frais divers à appliquer à la principale de retour. Ils peuvent également être utilisés pour des retours pour des analyses statistiques. Codes disposition sont définis dans le cadre de le paramétrage des ordres de retour. Toutefois, chaque code disposition doit référencer une des actions intégrées de destination. Le tableau suivant répertorie les codes disposition intégrés et leurs actions. ** Important : ** Si un article est retourné, mais le client doit encore être crédité, affectent ** crédit uniquement ** code disposition à la principale de retour.

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
<li>Le client est crédité le prix de vente moins les frais ou frais.</li>
<li>La perte de mise au rebut de l'article est validée dans la comptabilité.</li>
</ul></td>
<td>L'article ne doit pas être retourné. Cette action de disposition est utilisée dans les cas suivants :
<ul>
<li>Il existe de confiance nécessaire entre les parties.</li>
<li>Coût de retourner l'article défectueux est prohibitif.</li>
<li>Il ne peut pas autoriser les articles en stock. En raison d'autres conditions, un retour physique n'est pas nécessaire.</li>
</ul></td>
</tr>
<tr class="even">
<td>Crédit</td>
<td><ul>
<li>Le client est crédité le prix de vente moins les frais ou frais.</li>
<li>La valeur de stock a augmenté par le coût du retour marchandises.</li>
</ul></td>
<td>L'article est retourné et est ajouté en stock.</td>
</tr>
<tr class="odd">
<td>Remplacer et créditer</td>
<td><ul>
<li>Le client est crédité le prix de vente moins les frais ou frais.</li>
<li>La valeur de stock a augmenté par le coût du retour marchandises.</li>
<li>Une commande client distincte pour un remplacement est créée et est gérée séparément.</li>
</ul></td>
<td>L'article est retourné et est ajouté en stock.</td>
</tr>
<tr class="even">
<td>Remplacer et mettre au rebut</td>
<td><ul>
<li>Le client est crédité le prix de vente, moins de tous les frais ou frais.</li>
<li>La perte de mise au rebut de l'article est validée dans la comptabilité.</li>
<li>Une commande client distincte pour un remplacement est créée et est gérée séparément.</li>
</ul></td>
<td>L'article est retourné et au rebut.</td>
</tr>
<tr class="odd">
<td>Retourner au client</td>
<td>Aucun, sauf tous frais ou frais.</td>
<td>L'article est retourné mais est retourné au client après inspection. Cette action de disposition peut être utilisée si l'article a été endommagé donc volontairement, ou si la garantie a été annulée.</td>
</tr>
<tr class="even">
<td>Rebut</td>
<td><ul>
<li>Le client est crédité le prix de vente moins les frais ou frais.</li>
<li>La perte de mise au rebut de l'article est validée dans la comptabilité.</li>
</ul></td>
<td>L'article est retourné ou au rebut.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Arrivée dans l'entrepôt pour l'inspection
Avant physiquement recevoir des retours marchandises dans le stock lors de la validation d'un bon de livraison, les articles doivent passer par l'enregistrement entrants et une inspection facultative. L'illustration suivante fournit une vue d'ensemble du processus entrants. Les sections suivantes décrivent chaque étape affichée dans l'illustration.  

[processus d'arrivée d'![] (. /media/salesreturn03.png)](. /media/salesreturn03.png)  

Le processus a plusieurs autres variations qui ne sont pas concernées dans cette rubrique. Voici certaines de ces écarts :

-   N'utilisez pas ** vue d'ensemble des arrivées ** liste pour créer un journal des arrivées. Au lieu de cela, créez manuellement le journal des arrivées. Les ordres de retour auront ** commande client ** comme référence.
-   Si vous utilisez la gestion des entrepôts, de générer des transports de palettes. Compte principal de retour aura le statut ** arrivé ** lors de le transport de palettes.
-   Enregistrer l'arrivée de retour marchandises directement de la ligne d'ordre de retour, à l'aide ** enregistrement ** de la fonction.

Au cours de le processus d'arrivée, les retours sont intégrés au processus général pour les arrivées d'entrepôt. Le processus d'arrivée prend également en charge la création des ordres de contrôle pour les retours marchandises qui doivent subir une inspection distincte.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identifiez les produits dans la liste de vue d'ensemble des arrivées

** Vue d'ensemble des arrivées ** la page répertorie toutes les arrivées prévues entrantes. ** Remarque : ** Les arrivées des ordres de retour doivent être traitées séparément d'autres types de transactions entrants. Après avoir identifié un module entrant sur ** vue d'ensemble des arrivées ** page (par exemple, à l'aide de documents accompagnant ARM), dans le volet Actions, cliquez sur ** arrivée de début ** permet de créer et lancer un journal des arrivées qui correspond à l'arrivée.

### <a name="edit-the-arrival-journal"></a>Modifiez le journal des arrivées

En définissant ** gestion des contrôles ** l'option ** Oui **, vous pouvez créer un ordre de contrôle pour le compte principal de retour. Si une ligne a été soumise au contrôle pour l'inspection, vous ne pouvez pas spécifier le code disposition. ** Remarque : ** Si vous définissez ** gestion des contrôles ** l'option ** Oui ** au groupe de modèles de stock de l'article, ** gestion des contrôles ** l'option sous ** des lignes de journal ** la page sera marqué pour la ligne de journal des arrivées et ne peuvent pas être modifié. Si la ligne est soumise au contrôle, vous devez spécifier l'entrepôt de contrôle approprié. Si la ligne entrante n'est pas soumise pour inspection, le commis entrants d'entrepôt doit spécifier un code disposition directement sur la ligne de journal des arrivées puis valider le journal des arrivées. Si le même code disposition est affecté à la totalité du compte principal de retour, ou si la quantité complète de la ligne n'a pas été reçue, vous devez diviser la ligne. Si vous fractionnez une ligne de journal des arrivées, vous également fractionner le compte principal de retour (** SalesLine **) et créez un nouveau numéro de lot. Vous pouvez diviser la ligne en réduisant la quantité de la ligne de journal des arrivées. Lorsque le journal est validé, il crée une nouvelle principale de retour qui ont un statut ** prévu ** pour la quantité restante. Vous pouvez également diviser la ligne en cliquant sur ** des fonctions ** &gt; ** Fractionner **.

### <a name="process-the-quarantine-order"></a>Traitez l'ordre de contrôle

Si les produits retournés sont envoyés à inspecter dans l'entrepôt de contrôle, tout traitement supplémentaire est complété dans un ordre de contrôle. Un ordre de contrôle est créé pour chaque ligne d'arrivée envoyée au contrôle. Code de disposition indique le résultat du processus d'inspection. Vous pouvez fractionner un ordre de contrôle, comme vous pouvez fractionner le journal des arrivées. Si vous fractionnez l'ordre de contrôle, vous avez provoque un fractionnement correspondant du compte principal de retour. Une fois qu'un code disposition soit entré, complétez l'ordre de contrôle en utilisant ** fin ** de la fonction ou ** déclaration de fin ** la fonction. Si vous sélectionnez ** générez déclaration de fin **, une nouvelle entrée est créée dans l'entrepôt désigné. Vous pouvez ensuite traiter cette entrée à l'aide ** vue d'ensemble des arrivées ** de la page. Si l'arrivée provient d'un ordre de contrôle, vous ne pouvez pas modifier le code de disposition affecté au cours de l'inspection. Si vous fermez l'ordre de contrôle à l'aide de le ** fin ** travaillez, le lot est automatiquement enregistré. Par exemple, un article peut être renvoyé du contrôle au département d'expédition et de réception. Par exemple, le contrôleur de contrôle ne peut pas savoir où enregistrer l'article en stock. Dans ce cas, le bon de livraison correspondant doit être correctement mis à jour pour enregistrer et agir sur code disposition spécifié en raison de le contrôle. L'accusé de réception de la réception peut être envoyé à un client lorsque le compte principal de retour est enregistrée. ** Accusé de réception de retour ** le rapport ressemble au bon de commande de retour. ** Accusé de réception de retour ** le rapport n'est pas journalisé ou n'est donc pas enregistré dans le système, et ce n'est pas une étape obligatoire dans le processus d'ordre de retour.

## <a name="replace-a-product"></a>Remplacement d'un produit
Il existe deux méthodes pour gérer le remplacement de produit :

-   ** Remplacement avant – ** remplacez un produit avant le produit retourné soit reçu du client.
-   ** Le remplacement par le code disposition ** – créez automatiquement une ligne de commande de remplacement.

### <a name="up-front-replacement"></a>Remplacement avant

En remplacement franc, l'article de remplacement peut être livré au client avant que l'article soit retourné. Cette méthode est utile, par exemple, l'article est une pièce de machine qui ne peut pas être supprimée tant qu'une pièce détachée soit disponible pour prendre sa place, ou si vous souhaitez juste votre client possèdent le produit de remplacement tôt possible. L'ordre franc de remplacement est une commande client indépendante. Les informations d'en-tête est initiée du client, et les informations de ligne est lancée de l'ordre de retour. Vous pouvez modifier, traiter, et supprimer l'ordre de remplacement indépendamment de l'ordre de retour. Lorsque vous supprimez un ordre de remplacement, vous recevez un message indiquant que l'ordre a été créé comme un ordre de remplacement. L'illustration suivante présente le processus pour le remplacement franc.  

[processus franc de remplacement d'![] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

L'ordre de retour contient la référence à l'ordre de remplacement. Si un ordre franc de remplacement n'est créé pour un ordre de retour avant que l'article défectueux soit retourné, vous ne pouvez pas sélectionner des codes disposition pour le remplacement après que l'article défectueux renvoyé.

### <a name="replacement-by-disposition-code"></a>Remplacement par le code disposition

Si vous expédiez un article de remplacement au client, et vous utilisez ** remplacez et mettre au rebut ** ou ** remplacez et créditer ** l'action de disposition sur l'ordre de retour, utilisez le processus qui s'affiche dans l'illustration suivante.  

[processus de remplacement![lorsque le code disposition est utilisé] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

L'article de remplacement est fourni à l'aide d'une commande client est indépendante, la commande client de remplacement. Cette commande client est créée lorsque le bon de livraison pour l'ordre de retour est généré. L'en-tête de commande utilise les informations du client référencé dans l'en-tête de l'ordre de retour. La ligne les informations collectées de les informations entrées dans ** article de remplacement ** la page. ** Article de remplacement ** la page doit être terminée pour les lignes ayant des actions de disposition qui commencent par le mot « remplacent ». Toutefois, et la quantité ni l'identité de l'article de remplacement n'est validée ou est limitée. Ceci permet des dossiers laquelle le client souhaite que le même article mais dans une configuration ou une taille différente, ainsi que les cas où les clients demande un article complètement différent. Par défaut, un article identiques est entré dans ** article de remplacement ** la page. Toutefois, vous pouvez sélectionner un autre article, à condition que la fonction paramétrée. ** Remarque : ** Vous pouvez modifier et supprimer la commande client de remplacement une fois qu'elle soit créé.

## <a name="generate-a-packing-slip"></a>Générez un bon de livraison
Avant que les articles retournés soient reçus dans le stock, vous devez mettre à jour le bon de livraison pour l'ordre des articles appartiennent. Toute comme le processus de mise à jour de facture consiste à mettre à jour la transaction financière, le processus de mise à jour du bon de livraison est la mise à jour physique de l'enregistrement de stock. En d'autres termes, ce processus valide les modifications apportées au stock. En cas de retour, les opérations affectées à l'action de disposition sont exécutées durant la mise à jour du bon de livraison. Lorsque vous générez le bon de livraison, les événements suivants se produisent :

-   Dans l'entrepôt, le processus standard est utilisé pour effectuer une réception physique. Les validations comptables sont générées si le groupe de modèles de stock (** stock physique de valider **) et les paramètres des ventes (** bon de livraison dans la comptabilité **) sont définis en conséquence.
-   Les articles qui ont été marqués avec une action de disposition qui contient le mot « rebut » sont mis au rebut, et une perte de stock est validé dans la comptabilité.
-   Les articles qui ont été marqués avec ** retour au client ** l'action de disposition sont reçus et livrées au client. Ces articles n'ont aucun effet net dans le stock.
-   Une commande client de remplacement est créée. Cette commande est basé sur les informations de ** article de remplacement ** la page.

Vous pouvez générer le bon de livraison uniquement pour les lignes dont le statut de retour ** enregistré **, et uniquement pour la quantité complète indiquée dans le compte principal de retour. Si plusieurs lignes de l'ordre de retour ont ** enregistré ** le statut, vous pouvez générer le bon de livraison pour un sous-ensemble des lignes en supprimant les autres lignes ** valider le bon de livraison ** de la page. Les retours partiels sont définis en termes de lignes d'ordre de retour, pas en termes d'expéditions de retour. Par conséquent, si vous recevez la quantité complète indiquée sur une ligne d'ordre de retour, mais rien en rapport avec les autres lignes de l'ordre de retour, la livraison n'est pas partielle. Toutefois, si une ligne d'ordre de retour nécessite que 10 unités d'un article doivent être retournées, mais vous les quatre unités - réceptrices, la livraison est partielle. Si les retours marchandises ne sont pas tous arrivés, vous pouvez définir l'expédition de côté en attendant le reste de la quantité retournée à l'arrivée. Sinon, vous pouvez enregistrer et valider la quantité partielle. Dans le cadre de le processus de validation des bons de livraison, vous pouvez associer le numéro de référence du bon de livraison des documents d'expédition du client aux lignes de commande. Cette association est facultative et pour la référence uniquement. Elle n'entraîne pas de mises à jour de transactions. Il vous pouvez ignorer le processus de bon de livraison et accéder directement à la facturation. Dans ce cas, les étapes que vous auriez effectuées lors de la génération du bon de livraison sont effectuées lors de la facturation.

## <a name="generate-an-invoice"></a>Générer une facture
Bien que ** ordre de retour ** la page contienne les informations et les actions nécessaires afin de traiter les aspects logistiques spéciaux de l'ordre de retour, vous devez utiliser ** commande client ** la page pour exécuter le processus de facturation. Votre organisation peut ensuite facturer des ordres de retour et des commandes client simultanément, et la même personne peut réaliser la facturation, comme requis. Pour afficher l'ordre de retour ** commande client ** de la page, cliquez sur le lien correspondant au numéro de commande client ouvre la commande client associée. Vous pouvez également trouver l'ordre de retour sous ** toutes les commandes client ** la page. Les ordres de retour sont des commandes client ayant le type de commande ** Commande retournée **.

### <a name="credit-correction"></a>Correction de crédit

Dans le cadre de le processus de facturation, vérifiez que tous les frais divers sont corrects. Pour ce qui deviendra les validations comptables des corrections (Storno), envisagez d'utiliser ** correction de crédit ** l'option sous ** autre ** l'onglet ** facture de validation ** de la page lorsque vous validez la facture ou avoir. ** Remarque : ** Par défaut, ** correction de crédit ** l'option est activée si ** avoir comme correction ** l'option sous ** des paramètres des ventes ** la page a été activée. Cependant, il est recommandé de ne pas validez les retours avec le terme Storno.

## <a name="create-intercompany-return-orders"></a>Créer des ordres de retour intersociétés
Les ordres de retour peuvent être indiqués entre deux sociétés de votre organisation. Les scénarios suivants sont pris en charge :

-   L'intersociétés simples se retournent entre deux sociétés qui participe à une relation intersociétés
-   Une chaîne intersociétés qui est établie lorsqu'un ordre de retour de client est créé dans la société de vente
-   Une chaîne intersociétés qui est établie lorsqu'un ordre de retour de fournisseur est créé à la société acheteuse
-   L'expédition directe de livraison revient entre un client externe et deux sociétés qui participe à une relation intersociétés

### <a name="setup"></a>Configuration

L'illustration suivante à la quantité minimale paramètre requis pour que deux sociétés participe à une relation intersociétés et de tirent profit du commerce intersociétés.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

Dans le scénario suivant, CompBuy est la société acheteuse, et CompSell est la société de vente. Généralement, les marchandises de vente d'expéditions de société à la société acheteuse ou, dans des scénarios directs d'expédition de la livraison, directement au client final. Dans CompBuy, le fournisseur IC\_CompSell est défini comme point de terminaison intersociétés associé à la société CompSell. En même temps, dans CompSell, le client IC\_CompBuy est défini comme point de terminaison intersociétés associé à la société CompBuy. Les détails de stratégie d'action et les mises en correspondance appropriés de valeur doit être définis dans les deux sociétés. Dans un scénario direct d'expédition de la livraison, un ordre de retour intersociétés, qui est également une commande client intersociétés, est créé dans la société de vente. Le numéro de retour marchandises de l'ordre de retour intersociétés peut être prélevé de la souche de numéros de retour marchandises dans CompSell, ou il peut être copiée depuis le numéro de retour marchandises affecté à l'ordre de retour d'origine dans CompBuy. Les paramètres de numéro de retour marchandises de ** PurchaseRequisition ** la stratégie d'action dans CompBuy déterminent ces actions. Si le numéro de retour marchandises est synchronisé, vous devez envisager de limiter le risque d'un différend de numéros si les deux sociétés utilisent la souche de numéros.

### <a name="simple-intercompany-returns"></a>Retours simples intersociétés

Ce scénario implique deux sociétés de la même organisation, comme le montre l'illustration suivante.  

[retour seul intersociétés![] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

La chaîne de commande peut être établie lorsqu'un ordre de retour de fournisseur est créée dans la société de commande fournisseur ou un ordre de retour de client est créé dans la société de vente. Dynamics 365 pour les opérations crée la commande correspondante dans l'autre société et s'assure que les informations d'en-tête et de ligne dans l'ordre de retour de fournisseur reflète les paramètres de l'ordre de retour client. L'ordre de retour et créé peut inclure ou exclure la référence (** commande client de trouver **) à une facture client existante. Les bons de livraison et factures des deux ordres peuvent être traités individuellement. Par exemple, vous ne devez pas générer un bon de livraison pour l'ordre de retour de fournisseur avant de générer le bon de livraison pour l'ordre de retour client.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>L'expédition directe de livraison revient entre trois parties

Ce scénario peut être établie si une vente précédente ** la livraison directe ** du type a été effectuée, et si une facture par rapport à le client existe dans la société qui interagit avec le client. Dans l'illustration suivante, la société CompBuy a précédemment vendue et les produits facturés au client externe. Les articles ont été prélevés directement de la société CompSell au client via une chaîne de commandes intersociétés.  

[la livraison directe de la livraison![revient entre trois parties] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Si le client externe souhaite retourner les produits, un ordre de retour (RMA02) est créé pour le client dans la société CompBuy. Pour établir la chaîne intersociétés, l'ordre de retour soit marqué pour la livraison directe. Lorsque vous utilisez ** commande client de trouver ** fonction pour prélever la facture client pour revenir, une chaîne de commandes intersociétés incluant les documents suivants est établie :

-   ** Ordre de retour d'origine : ** RMA02 (société CompBuy)
-   ** Commande fournisseur : ** PO02 (société CompBuy)
-   ** Ordre de retour intersociétés : ** Retour marchandises\_00032 (société CompSell)

Une fois la chaîne directe intersociétés de livraison créée, gérer et traiter tout physiques des retours doivent se produire dans le contexte de l'ordre de retour intersociétés, retour marchandises\_00032 à la société CompSell. Les produits ne peuvent pas être reçus à la société CompBuy. Lorsqu'un code disposition est affecté à l'ordre de retour intersociétés, il est synchronisé avec l'ordre de retour d'origine pour permettre de la facturation appropriée de la commande d'origine.

## <a name="post-to-the-ledger"></a>Permet de valider dans la comptabilité
Les validations comptables générées à l'ordre de retour est facturé sont influencées par certains paramètres essentiels :

-   ** Le prix de vente de retour ** – Pour les modèles de stock autres que ** coût standard **, ** le prix de vente de retour ** le paramètre détermine le coût de l'article s'il a accepté en stock ou au rebut. Pour calculer une évaluation du stock adéquate, il est important que vous définissez ** le prix de vente de retour ** le paramètre correctement. Si vous utilisez ** commande client de trouver ** fonction pour créer une ligne d'ordre de retour qui a une référence à une facture client, ** le prix de vente de retour ** La valeur est égal au prix de revient de l'article qui est vendu. Sinon, la valeur du prix de revient provient de l'article défini ou entrée manuellement.
-   ** La correction/Storno de crédit ** – ** correction de crédit ** le paramètre sous ** facture de validation ** la page détermine si les validations doivent être enregistrées comme des entrées (DR/CR) positives ou comme corrigeant, les entrées négatives.

Dans les exemples suivants, le prix de vente de retour est représenté en tant que ** Inv. Prix de revient **.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Exemple 1 : L'ordre de retour ne référence pas une facture client

L'ordre de retour ne référence pas une facture client. Le retour marchandises est crédité. ** Correction de crédit ** le paramètre n'est pas sélectionné lorsque la facture d'ordre de retour, ou l'avoir, est générée.  

[l'ordre de retour d'![ne référence pas un client invoic] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

** Remarque : ** Le prix de base de données d'articles est utilisé par défaut pour ** le prix de vente de retour ** le paramètre. Le prix par défaut diffère du prix de revient au moment de la sortie de stock. Par conséquent, l'implication est qu'une perte de 3 a été effectuée. En outre, l'ordre de retour n'inclut pas la remise qui a été fournie au client sur la commande client. Par conséquent, un crédit sont se produit.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Exemple 2 : La correction de crédit est activée pour l'ordre de retour

L'exemple 2 est le même que l'exemple 1, mais ** correction de crédit ** le paramètre est sélectionné lorsque la facture d'ordre de retour est générée.  

[ordre de retour![lesquels la correction de crédit est activée] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

** Remarque : ** Les validations comptables sont entrées comme des corrections négatives.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Exemple 3 : La ligne d'ordre de retour est créée à l'aide de la fonction de commande client de trouver

Dans cet exemple, la ligne d'ordre de retour est créée à l'aide ** commande client de trouver ** de la fonction. ** Correction de crédit ** le paramètre n'est pas sélectionné de la facture.  

[ligne d'ordre de retour![créée à l'aide de la commande client de trouver] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

** Remarque : ** ** Remise ** et ** le prix de vente de retour ** sont correctement. Par conséquent, une contrepassation précise de la facture client se produit.


