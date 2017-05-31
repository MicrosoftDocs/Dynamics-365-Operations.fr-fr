---
title: "Espace de travail mobile Collaboration du fournisseur pour l&quot;application Microsoft Dynamics 365 for Operations"
description: "Avec l&quot;espace de travail mobile de collaboration du fournisseur, vos fournisseurs sont constamment informés des commandes qui leur ont été adressées pour approbation et reçoivent des informations sur les commandes et contacts récemment créés ou mis à jour."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e19fee87dae6e5d425f36dac0db4ea89534a8510
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espace de travail mobile Collaboration du fournisseur pour l'application Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Avec l'espace de travail mobile de collaboration du fournisseur, vos fournisseurs sont constamment informés des commandes qui leur ont été adressées pour approbation et reçoivent des informations sur les commandes et contacts récemment créés ou mis à jour.

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
<td>En savoir plus sur la plateforme mobile Microsoft Dynamics 365 for Operations</td>
<td><a href="https://ax.help.dynamics.com/en/wiki/mobile-development-handbook/">Plateforme mobile Dynamics 365 for Operations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Assurez-vous d'utiliser un environnement disposant de la version 1611 de Microsoft Dynamics 365 for Operations et de la mise à jour 3 de Microsoft Dynamics for Operations (novembre 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000">Appareil mobile sur lequel Dynamics 365 for Operations est installé</span></td>
<td><span style="color: #000000">Téléchargez l'application Dynamics 365 for Operations à partir de votre magasin d'applications mobiles.</span></td>
</tr>
<tr class="even">
<td>Correctif de la Base de connaissances 4013633</td>
<td>Installez le correctif pour activer les espaces de travail fournis dans Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000"><span style="color: #000000">Correctif de la Base de connaissances 3216943</span> </span></td>
<td>Installez le correctif pour activer l'espace de travail mobile de collaboration du fournisseur.</td>
</tr>
<tr class="even">
<td>L'utilisateur fournisseur doit avoir accès à l'interface Web de collaboration du fournisseur dans Dynamics 365 for Operations et paramétrer un utilisateur de collaboration du fournisseur.</td>
<td>Suivez les étapes décrites dans les rubriques suivantes pour paramétrer et utiliser l'interface Web de collaboration du fournisseur.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Utiliser la Collaboration du fournisseur pour travailler avec des fournisseurs externes</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Gérer les utilisateurs de la fonctionnalité de collaboration fournisseur</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Paramétrer et mettre à jour la collaboration fournisseur</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Utiliser la collaboration du fournisseur pour travailler avec des clients dans Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Vue d'ensemble
L'espace de travail mobile Collaboration du fournisseur tient les fournisseurs informés des nouvelles commandes fournisseur, de sorte qu'ils puissent y répondre dans le client Web Dynamics 365 for Operations. 

**Remarque :** l'espace de travail mobile doit être utilisé comme complément de l'interface Web de collaboration du fournisseur, mais pas comme un outil de remplacement. 

Avec l'espace de travail mobile de collaboration du fournisseur, vos fournisseurs peuvent afficher les nouvelles commandes fournisseur qui leur sont soumises pour approbation. Il affiche les informations de commande fournisseur, telles que les produits, la quantité et les dates de livraison requises. Les informations sur les prix sont disponibles, en fonction de la configuration pour chaque fournisseur. 

Lorsqu'un utilisateur se connecte en tant que fournisseur, il peut voir quelles sont les commandes fournisseur qui ont reçu une réponse et quelles commandes sont toujours en attente d'une action du client. Le fournisseur peut avoir suggéré une autre date de livraison qui n'a pas encore été acceptée par le client, de sorte que la commande fournisseur est en attente d'une action du client. Le fournisseur peut également voir la liste des commandes fournisseur qui ont été confirmées mais n'ont pas encore été livrées. 

Pour répondre à une commande fournisseur, le fournisseur doit utiliser l'interface Web de collaboration du fournisseur disponible dans le client Web Dynamics 365 for Operations. C'est également à cet endroit que le fournisseur obtient plus d'informations sur la commande, comme les documents joints, l'adresse de livraison par ligne et les frais associés au fournisseur. 

Avec un rôle de sécurité spécial, le fournisseur peut afficher les personnes à contacter enregistrées pour un compte fournisseur. Avec le même rôle de sécurité, le fournisseur peut afficher le statut de toute demande utilisateur qui a été soumise. 

La création de contacts et la soumission de nouvelles demandes utilisateur doivent être effectuées dans l'interface de collaboration du fournisseur disponible dans le client Web Dynamics 365 for Operations. 

Avec l'espace de travail mobile, votre fournisseur peut :

-   afficher les nouvelles commandes fournisseur envoyées au fournisseur ;
-   afficher les commandes fournisseur auxquelles le fournisseur a répondu et qui sont en attente d'une action du client ;
-   afficher les commandes fournisseur qui sont dans l'état confirmé et n'ont pas été entièrement reçues ;
-   afficher les coordonnées de la personne à contacter enregistrée pour le compte fournisseur (nécessite un rôle de sécurité supplémentaire) ;
-   afficher les informations et suivre l'état d'une demande utilisateur soumise par le fournisseur (nécessite un rôle de sécurité supplémentaire).

## <a name="get-started"></a>Mise en route
Pour démarrer sur votre périphérique mobile :

1.  Dans votre magasin d'application mobile, téléchargez et installez l'application Microsoft Dynamics 365 for Operations.
2.  Démarrez l'application sur votre appareil.
3.  Entrez votre URL Dynamics 365.
4.  Entrez la société à laquelle vous vous connectez. Par exemple, entrez **USMF**.
5.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer le nom d'utilisateur et le mot de passe de votre compte Microsoft Dynamics 365 for Operations.

Une fois connecté à l'application, aucun espace de travail n'est visible. Pour afficher les espaces de travail sur votre application mobile, vous devez d'abord publier les espaces de travail souhaités sur l'application Dynamics 365 for Operations. Vous devez disposer de l'autorisation Administration du système de publier l'espace de travail.

1.  Démarrez Dynamics 365 for Operations.
2.  Accédez à **Administration système** &gt; **Paramétrage** &gt; **Paramètres système**.
3.  Sélectionnez **Gérer l'application mobile**.
4.  Sélectionnez l'espace de travail **Collaboration du fournisseur** pour le publier sur la plateforme mobile.
5.  Sélectionnez **Publier l'espace de travail**.
6.  Actualisez votre appareil pour afficher les espaces de travail publiés.
7.  Sélectionnez l'espace de travail **Collaboration du fournisseur**. Vous accédez à la page suivante.

    [![application mobile collaboration du fournisseur](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>contacts ;
La page **Contacts** vous permet d'afficher tous les contacts qui ont été paramétrés pour le compte fournisseur. Elle présente le nom de la personne à contacter, son e-mail principal, ainsi que les alias d'utilisateur, le cas échéant. Elle affiche également si le compte d'utilisateur de la personne à contacter est actif. Lorsque vous sélectionnez un contact, vous en voyez les détails tels que les entités juridiques pour lesquelles la personne est un contact et les coordonnées telles qu'un numéro de téléphone ou une adresse e-mail différente.

## <a name="user-requests"></a>Demandes de l’utilisateur
La page **Demandes de l'utilisateur** vous permet d'afficher toutes les demandes utilisateur que vous avez envoyées via l'interface Web de collaboration du fournisseur et suivre leur état. Lorsque vous sélectionnez une demande utilisateur, vous pouvez voir ce qui a été demandé, ajouter ou désactiver un utilisateur, modifier la sécurité et voir les rôles de sécurité qui ont été demandés pour l'utilisateur.

## <a name="purchase-orders-ready-for-review"></a>Commandes fournisseur prêtes pour examen
La page **Commandes fournisseur prêtes pour examen** vous permet d'afficher toutes les commandes fournisseur soumises par le client et qui n'ont pas reçu de réponse. Vous pouvez sélectionner des informations concernant la commande, par exemple les produits qui ont été demandés et leur date de livraison. Les informations sur les prix ne sont disponibles que si elles sont configurées pour le fournisseur. Vous pouvez voir si la commande fournisseur comporte des notes ou des pièces jointes. Pour ouvrir les pièces jointes, vous devez utiliser la collaboration du fournisseur dans le client Web. Sélectionnez **Ligne de commande fournisseur** pour afficher toutes les lignes avec leurs détails. Notez que pour chaque ligne, un indicateur permet de voir s'il existe des notes ou des pièces jointes ou s'il existe une adresse de livraison différente de celle qui apparaît dans l'en-tête. Pour répondre à la commande fournisseur, vous devez utiliser le client Web de collaboration de fournisseur.

## <a name="awaiting-customer-action"></a>En attente d'une action du client
La page **En attente d'une action du client** vous permet de trouver les commandes fournisseur auxquelles vous, ou quiconque de votre société qui a également accès à la collaboration du fournisseur, a répondu. Les commandes fournisseur ne sont visibles dans cette liste que si le client a besoin d'effectuer l'une des actions suivantes sur la commande fournisseur.

-   Si la commande fournisseur a été rejetée, le client doit mettre la jour la commande envoyée et l'envoyer de nouveau, ou l'annuler et la renvoyer. Lorsque la commande fournisseur est envoyée de nouveau, elle disparaît de la page **En attente d'une action du client**.
-   Si la commande fournisseur a été acceptée avec des modifications, le client doit mettre à jour la commande d'origine et la renvoyer pour examen, ou la mettre à jour conformément aux modifications et la confirmer immédiatement. Dans les deux cas, la commande fournisseur disparaît de la page **En attente d'une action du client**.
-   Si la commande fournisseur a été acceptée et apparaît dans la page **En attente d'une action du client**, c'est parce qu'elle n'a pas été confirmée automatiquement quand elle a été acceptée. Elle attend qu'un agent des achats passe l'état de la commande à Confirmé. De manière générale, la commande fournisseur est considérée comme un accord conclu entre le client et le fournisseur dès que le fournisseur accepte la commande. Passer la commande fournisseur à l'état Confirmé est une formalité.

En sélectionnant la commande fournisseur, des informations supplémentaires apparaissent concernant la réponse. Vous pouvez voir les détails de ligne et la réponse pour chaque ligne. La ligne de statut indique lesquelles des réponses suivantes ont été données.

-   Accepté
-   Rejeté/e
-   Accepter avec les modifications
-   Remplacé/Remplacement
-   Fractionner en plan de livraison/Ligne de plan de livraison

Remarquez un indicateur qui affiche **Livraison en cours**=oui/non ; il permet d'indiquer les lignes qui ne seront pas livrées. La raison peut en être que la ligne a été rejetée, ou remplacée lorsque la livraison des lignes originales n'est pas prévue, ou que la ligne a été fractionnée en plusieurs lignes de plan de livraison et que la ligne d'origine n'est pas prévue d'être livrée conformément à la demande de la commande reçue. Toutes les modifications apportées à la réponse de la ligne de commande sont affichées, à l'exception des notes et pièces jointes téléchargées, que vous pouvez voir à l'aide de l'interface Web de collaboration du fournisseur.

## <a name="open-confirmed-orders"></a>Commandes confirmées en cours
Lorsque la commande fournisseur est confirmée par le client, ce qui implique qu'elle est passée au statut Confirmé, elle apparaît dans la liste des commandes confirmées en cours. Elle restera dans la liste jusqu'à ce qu'elle soit enregistrée comme reçue par le client.





