---
title: "L&quot;espace de travail de collaboration portable héritées pour Microsoft Dynamics 365 pour l&quot;application Opérations"
description: "Avec l&quot;espace de travail de collaboration portable du fournisseur, vos fournisseurs peuvent rester à jour des commandes fournisseur qui ont été soumises aux cibles pour approbation et d&quot;afficher des informations sur les nouvelles et mises à jour commandes fournisseur et les contacts."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>L'espace de travail de collaboration portable héritées pour Microsoft Dynamics 365 pour l'application Opérations

Avec l'espace de travail de collaboration portable du fournisseur, vos fournisseurs peuvent rester à jour des commandes fournisseur qui ont été soumises aux cibles pour approbation et d'afficher des informations sur les nouvelles et mises à jour commandes fournisseur et les contacts.

<a name="prerequisites"></a>Conditions préalables
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>description ;</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Disposer connaissances Microsoft Dynamics 365 pour la plateforme mobiles d'opérations</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dynamics 365 pour la plateforme mobiles d'opérations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 pour les opérations</td>
<td>Assurez-vous que vous utilisez un environnement avec Microsoft Dynamics 365 pour la version 1611 d'opérations et Microsoft Dynamics pour la mise à jour 3 de plateforme Opérations (novembre 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Appareil mobile qui a Dynamics 365 pour l'application Opérations installée</span></td>
<td><span style="color: #000000;">Téléchargez Dynamics 365 pour l'application Opérations de votre magasin portable d'application.</span></td>
</tr>
<tr class="even">
<td>Base de connaissances 3215650 de correctif</td>
<td>Installez le correctif pour activer des espaces de travail qui sont définis dans Dynamics 365 pour les opérations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">Base de connaissances 3216943 de correctif</span></span></td>
<td>Installez le correctif pour activer l'espace de travail de portable de collaboration de fournisseur.</td>
</tr>
<tr class="even">
<td>Utilisateur fournisseur doit avoir accès à l'interface Web de collaboration du fournisseur dans Dynamics 365 pour les opérations et paramétrer un utilisateur de collaboration de fournisseur.</td>
<td>Suivez les étapes décrites dans les rubriques suivantes pour paramétrer et utiliser l'interface Web de collaboration de fournisseur.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">La collaboration de fournisseur avec les fournisseurs externes</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Paramétrer et mettre à jour la collaboration fournisseur</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">La collaboration de fournisseur avec les clients dans Dynamics 365 pour les opérations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Vue d'ensemble
L'espace de travail de collaboration portable du fournisseur comprend des fournisseurs informés sur les nouvelles commandes fournisseur afin qu'ils puissent voir et répondre aux commandes fournisseur dans Dynamics 365 pour le client Web Opérations.  

** Remarque : ** L'espace de travail portable utiliser comme -vous à l'interface Web de collaboration de fournisseur, mais comme pas remplacement.  

Avec l'espace de travail de collaboration portable du fournisseur, vos fournisseurs peuvent afficher les nouvelles commandes fournisseur soumises pour approbation. Elle affiche les informations de commande fournisseur, telles que des produits, la quantité, et les dates de livraison demandés. Les informations sur les prix sont disponibles, en fonction de la configuration pour chaque fournisseur.  

Lorsqu'un utilisateur se connecte comme fournisseur, ils ont accès à des commandes fournisseur ont été complétés, ou les commandes fournisseur attendent toujours l'action de client. Le fournisseur peut avoir suggéré une autre date de livraison qui n'a pas encore été acceptée avec le client pour la commande fournisseur est en attente d'action du client. Le fournisseur verra également la liste des commandes fournisseur qui ont été confirmées mais non encore livrées.  

Pour répondre à une commande fournisseur, le fournisseur doit utiliser l'interface Web de collaboration de fournisseur disponible dans Dynamics 365 pour le client Web Opérations. Elle permet également de le fournisseur obtiennent plus d'informations sur la commande, tels que des documents joints, l'adresse de livraison par ligne, et les frais associés au fournisseur.  

Avec un rôle de sécurité requis, le fournisseur peut afficher que les personnes à contacter sont enregistrés pour un compte fournisseur. Avec le même rôle de sécurité, le fournisseur peut afficher le statut de toute demande de l'utilisateur qui a été envoyée.  

Création de contacts et soumettre de nouvelles demandes de l'utilisateur doivent être effectués dans l'interface de collaboration de fournisseur disponible dans Dynamics 365 pour le client Web Opérations.  

Avec l'espace de travail mobile, votre fournisseur peut :

-   Nouvelles commandes fournisseur de vue soumises au fournisseur.
-   Les commandes fournisseur de vue que le fournisseur a répondu à et attendent une action de client.
-   Permet d'afficher les commandes fournisseur basées dans un rapport confirmé et n'ont pas été entièrement reçues.
-   Affichez les informations de personne à contacter enregistrée pour le compte fournisseur (nécessite un rôle de sécurité supplémentaire).
-   Affichez les informations et suivre le statut d'une demande de l'utilisateur soumise par le fournisseur (nécessite un rôle de sécurité supplémentaire).

## <a name="get-started"></a>Mise en route
Pour obtenir commencé sur votre périphérique mobile :

1.  Dans votre magasin portable d'application, chargez et installez Microsoft Dynamics 365 pour l'application Opérations.
2.  Démarrez l'application de votre périphérique.
3.  Permet d'entrer l'URL de Dynamics 365.
4.  Entrez la société pour signer dans en. Par exemple, entrez ** USMF **.
5.  La première fois que vous vous connectez, vous êtes invité à entrer le nom d'utilisateur et le mot de passe pour votre Microsoft Dynamics 365 pour le compte d'opérations. 

Après avoir connexion l'application, aucun espaces de travail sont visibles. Pour afficher des espaces de travail de votre application mobile, vous devez d'abord envoyer des espaces de travail souhaités à Dynamics 365 pour l'application Opérations. Vous devez disposer de l'autorisation Administration du système de publier l'espace de travail.

1.  Début Dynamics 365 pour les opérations.
2.  Allez ** Administration du système ** &gt; ** au paramétrage ** &gt; ** des paramètres système **.
3.  Sélectionnez ** de gérer l'application mobile **.
4.  Sélectionnez l'espace de travail de collaboration ** fournisseur ** pour publier à la plateforme portable.
5.  Sélectionnez ** publiez l'espace de travail **.
6.  Permet d'actualiser le périphérique pour voir des espaces de travail émis.
7.  Sélectionnez ** collaboration de fournisseur ** l'espace de travail. Vous la page suivante.

[fournisseur-collaboration-mobile-application d'![] (. /media/vendor-collaboration-mobile-app.png)](. /media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>contacts ;
** Contacts ** la page permet d'afficher tous les contacts qui ont été paramétrés pour le compte fournisseur. Elle présente le nom de la personne à contacter, le principal e-mail, ainsi que les utilisateurs alias, le cas échéant. Il affiche également si le compte de l'utilisateur de la personne à contacter est active. Lorsque vous sélectionnez un contact, les détails de contact, tels que pour les entités juridiques la personne est un contact, et les informations de contact comme le numéro de téléphone ou adresse e-mail différent.

## <a name="user-requests"></a>Demandes de l’utilisateur
** Demandes de l'utilisateur ** la page permet d'afficher toutes les demandes de l'utilisateur que vous avez envoyées via l'interface Web de collaboration de fournisseur et suivre le statut. Lorsque vous sélectionnez une demande de l'utilisateur, vous pouvez afficher ce qui a été demandé, ajoutez ou désactivation d'un utilisateur, modifiez la sécurité, puis consultez les rôles de sécurité ont été demandés pour l'utilisateur.

## <a name="purchase-orders-ready-for-review"></a>Commandes fournisseur prêtes pour révision
** Commandes fournisseur prêtes pour la révision ** la page permet d'afficher toutes les commandes fournisseur soumises par le client et avoir répondu. Vous pouvez afficher des informations sélectionnées sur la commande, par exemple lequel des produits ont été demandés et heure de livraison. Les informations sur les prix sont disponibles que si cela est configuré pour le fournisseur.  

Vous pouvez voir si la commande fournisseur a des notes ou des pièces jointes. Pour ouvrir les pièces jointes, vous devez utiliser la collaboration du fournisseur dans le Web client. Sélectionnez ** ligne de commande fournisseur ** pour afficher toutes les lignes avec les détails. Notez que pour chaque ligne, un indicateur affiche si des notes ou des pièces jointes ou s'il existe une adresse de livraison différente que ce qui s'affiche dans l'en-tête.  

Pour répondre à la commande fournisseur, vous devez utiliser le Web client de collaboration de fournisseur.

## <a name="awaiting-customer-action"></a>En attente d'une action du client
** Attente du début de l'action client ** la page vous permet de trouver les commandes fournisseur auxquelles vous, ou quiconque de votre société qui a également accès à la collaboration de fournisseur, a répondu. Les commandes fournisseur sont uniquement visibles dans cette liste si les besoins du client pour effectuer une des actions suivantes sur la commande fournisseur.

-   Si la commande fournisseur a été rejetée, le client ou devait imposer la commande envoyé et l'envoyer à jour de nouveau, ou d'annuler l'ordre et le renvoyer. Lorsque la commande fournisseur est émise, elle disparaîtra ** l'action en attente de client ** de la page.
-   Si la commande fournisseur a été acceptée avec des modifications, un client doit mettre la commande d'origine et le renvoyer à jour pour révision, ou mettre la fonction de les modifications et confirmez- à jour à jour la fois. Dans les deux cas, la commande fournisseur disparaîtra ** l'action en attente de client ** de la page.
-   Si la commande fournisseur a été acceptée et apparaît dans ** l'action en attente de client ** la page, elle est dû au fait que la commande fournisseur n'a pas été confirmée automatiquement lorsque l'acceptation a été effectuée. Elle est en attente d'agent des achats pour modifier l'ordre Confirmée. Généralement, la commande fournisseur est considéré comme un accord conclu entre le client et le fournisseur dès que le fournisseur accepte la commande. Déplacer la commande fournisseur à l'état est confirmé est une formalité.

En sélectionnant la commande fournisseur, les informations supplémentaires apparaissent sur la réponse. Vous pouvez afficher les détails de ligne et la réponse pour chaque ligne. La ligne de statut indique les réponses suivantes sont données.

-   Accepté
-   Rejeté/e
-   Accepter avec les modifications
-   Substitué/substitut
-   Fractionner dans le programme/ligne de programme

Notez que les élements un indicateur ** fournissant ** =yes/no, utilisé pour indiquer que les lignes ne sont pas produites. Cela peut être dû au fait que la ligne a été rejetée, ou substitué où ne devrait pas à ce que les lignes originales soient livrées, ou il ne devrait pas à ce qu'une ligne après fractionnée en plusieurs lignes de programme et ligne d'origine soit livrée comme demandée dans l'ordre reçu.  

Toutes les modifications apportées à la réponse de la ligne de commande sont affichées, à l'exception de les notes et les pièces jointes téléchargées, que vous pouvez voir à l'aide de l'interface Web de collaboration de fournisseur.

## <a name="open-confirmed-orders"></a>Open est confirmé des ordres
Lorsque la commande fournisseur est confirmée par le client, ce qui implique de faire que la commande fournisseur est modifiée en l'état est confirmé, il apparaît dans l'ordre confirmé en cours. Elle restera dans la liste jusqu'à ce qu'elle soit enregistrée comme reçu par le client.


