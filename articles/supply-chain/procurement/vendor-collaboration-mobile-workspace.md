---
title: Espace de travail de collaboration fournisseur sur téléphone mobile
description: Cet article fournit des informations sur l’espace de travail mobile Collaboration du fournisseur. Cet espace de travail permet aux fournisseurs d’être constamment informés des commandes fournisseur qui leur ont été envoyées pour approbation. Ils peuvent également afficher des informations sur les bons de commande et les contacts nouveaux et mis à jour.
author: GalynaFedorova
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: gfedorova
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 75c044d1133e1c4765cd97f4ab7e2a08ba998c35
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112148"
---
# <a name="vendor-collaboration-mobile-workspace"></a>Espace de travail de collaboration fournisseur sur téléphone mobile

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Cet article fournit des informations sur l’espace de travail mobile **Collaboration du fournisseur**. Cet espace de travail permet aux fournisseurs d’être constamment informés des commandes fournisseur qui leur ont été envoyées pour approbation. Ils peuvent également afficher des informations sur les bons de commande et les contacts nouveaux et mis à jour.

Cet espace de travail mobile est destiné à être utilisé avec l’application mobile de finances et d’opérations (Dynamics 365).

## <a name="overview"></a>Présentation 
L’espace de travail mobile **Collaboration du fournisseur** tient les fournisseurs informés des nouvelles commandes fournisseur, de sorte qu’ils puissent y répondre dans le client Web. 

>[!NOTE]
> L’espace de travail mobile doit être utilisé comme complément de l’interface Web de collaboration du fournisseur, mais pas comme un outil de remplacement. 

Vos fournisseurs peuvent utiliser l’espace de travail mobile **Collaboration du fournisseur** pour afficher les nouvelles commandes fournisseur qui leur sont soumises pour approbation. Il affiche les informations sur les commandes fournisseur, telles que les produits, les quantités et les dates de livraison requises. Les informations sur les prix sont également disponibles, en fonction de la configuration de chaque fournisseur. 

Un utilisateur qui se connecte en tant que fournisseur peut voir quelles commandes fournisseur ont reçu une réponse et quelles commandes sont toujours en attente d’une action du client. Par exemple, une commande fournisseur peut être en attente d’une action du client, car le fournisseur a suggéré une autre date de livraison qui n’a pas encore été acceptée par le client. Le fournisseur peut également voir la liste des commandes fournisseur qui ont été confirmées mais n’ont pas encore été livrées. 

Pour répondre à une commande fournisseur, le fournisseur doit utiliser l’interface Web de collaboration du fournisseur disponible dans le client Web. Le fournisseur peut également obtenir plus d’informations sur la commande, comme les documents joints, l’adresse de livraison par ligne et les frais associés au fournisseur. 

Les fournisseurs ayant un rôle de sécurité spécial peuvent afficher les personnes à contacter enregistrées pour un compte fournisseur. Le même rôle de sécurité permet à un fournisseur d’afficher le statut de toute demande utilisateur qui a été soumise. 

L’interface Web de collaboration du fournisseur disponible dans le client Web doit être utilisée pour créer des contacts et envoyer de nouvelles demandes de l’utilisateur. 

L’espace de travail mobile **Collaboration du fournisseur** permet à un fournisseur d’effectuer les tâches suivantes :

-   Afficher les nouvelles commandes fournisseur envoyées au fournisseur.
-   Afficher les commandes fournisseur auxquelles le fournisseur a répondu et qui sont en attente d’une action du client.
-   Afficher les commandes fournisseur qui ont été confirmées mais n’ont pas encore été entièrement reçues.
-   Afficher les coordonnées de la personne à contacter enregistrée pour le compte fournisseur. (Cette tâche nécessite un rôle de sécurité supplémentaire.)
-   Afficher les informations sur une demande utilisateur soumise par le fournisseur, et suivre l’état de la demande. (Cette tâche nécessite un rôle de sécurité supplémentaire.)

## <a name="prerequisites"></a>Conditions préalables
Les conditions préalables varient, en fonction de la version de Microsoft Dynamics 365 qui a été déployée pour votre organisation.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Conditions requises si vous utilisez Supply Chain Management
Si Supply Chain Management a été déployé pour votre organisation, l’administrateur système doit publier l’espace de travail mobile **Collaboration du fournisseur**. Pour obtenir des instructions, voir [Publier un espace de travail mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Conditions requises si vous utilisez la version 1611 de Microsoft Dynamics 365 for Operations avec Platform Update 3 ou version ultérieure
Si la version 1611 de Microsoft Dynamics 365 for Operations avec Platform Update 3 ou version ultérieure a été déployée pour votre organisation, l’administrateur système doit effectuer les tâches préalables suivantes. 

<table>
<thead>
<tr class="header">
<th>Logiciel requis</th>
<th>Rôle</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Le KB 3216943 doit être implémenté si vous utilisez Platform Update 3.</td>
<td>Administrateur système</td>
<td>Le KB 3216943 est une mise à jour binaire qui est requise si vous utilisez Platform Update 3. Pour implémenter ce KB, l’administrateur système doit procéder comme suit :
<ol>
<li>Téléchargez KB 3216943 depuis Microsoft Dynamics Lifecycle Services (LCS).</li>
<li>Installez la mise à jour binaire, qui est fournie en tant que package déployable. Pour plus d’informations sur l’application d’un package déployable, voir <a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Appliquer un package déployable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Le KB 4013633 doit être implémenté.</td>
<td>Administrateur système</td>
<td>Le KB 4013633 est une mise à jour X++ ou un correctif de métadonnées qui contient l’espace de travail mobile <strong>Stock disponible</strong>. Pour implémenter le KB 4013633, un administrateur système doit procéder comme suit :
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Téléchargez le correctif de métadonnées à partir de LCS</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installez le correctif de métadonnées</a>.</li><li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Créez un module déployable</a> contenant le modèle <strong>SCMMobile</strong> et téléchargez le module déployable vers LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Appliquer le package déployable</a>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L’espace de travail mobile <strong>Collaboration du fournisseur</strong> doit être publié.</td><td>Administrateur système</td>
<td>Voir <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publier un espace de travail mobile</a>.</td>
</tr>
<tr class="even">
<td>L’utilisateur fournisseur doit avoir accès à l’interface Web de collaboration du fournisseur dans le client Web et paramétrer un utilisateur de collaboration du fournisseur.</td><td>Acheteurs et administrateur système</td>
<td>Suivez les étapes décrites dans les articles suivants pour paramétrer et utiliser l’interface Web de collaboration du fournisseur.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Utiliser la Collaboration du fournisseur pour travailler avec des fournisseurs externes</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Paramétrer et mettre à jour la collaboration fournisseur</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Utiliser la collaboration du fournisseur avec les clients dans Supply Chain Management</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Télécharger et installer l’application mobile

Téléchargez et installez l’application mobile de finances et d’opérations (Dynamics 365) :

-   [Pour téléphones Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Pour les iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Connexion à l’application mobile
1.  Démarrez l’application sur votre appareil mobile.
2.  Saisissez votre URL Microsoft Dynamics 365.
4.  Lorsque vous vous connectez pour la première fois, vous êtes invité à entrer vos nom d’utilisateur et mot de passe. Entrez vos informations d’identification.
5.  Une fois que vous êtes connecté, les espaces de travail disponibles pour votre société s’affichent. Notez que si votre administrateur système publie un nouvel espace de travail ultérieurement, vous devrez actualiser la liste des espaces de travail mobiles.

    [![Extraire pour actualiser.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>Utiliser l’espace de travail mobile Collaboration du fournisseur
Lorsque vous sélectionnez l’espace de travail mobile **Collaboration du fournisseur**, les options suivantes s’affichent.

![Espace de travail de collaboration fournisseur sur téléphone mobile.](./media/vendor-collaboration-mobile-app.png)

L’espace de travail mobile **Collaboration du fournisseur** inclut les pages suivantes.

### <a name="contacts"></a>Contacts
La page **Contacts** vous permet d’afficher tous les contacts qui ont été paramétrés pour le compte fournisseur. Elle affiche le nom de la personne à contacter, l’adresse e-mail principale et l’alias de l’utilisateur, si la personne à contacter a un alias. Cette page indique également si le compte d’utilisateur de la personne à contacter est actif. Lorsque vous sélectionnez un contact, vous en voyez les détails tels que les entités juridiques pour lesquelles la personne est un contact. Vous pouvez également afficher les coordonnées telles qu’un numéro de téléphone ou une adresse e-mail différente.

### <a name="user-requests"></a>Demandes de l’utilisateur
La page **Demandes de l’utilisateur** vous permet d’afficher toutes les demandes utilisateur que vous avez envoyées via l’interface Web de collaboration du fournisseur. Vous pouvez également suivre le statut de ces demandes. Lorsque vous sélectionnez une demande utilisateur, vous pouvez voir ce qui a été demandé, ajouter ou désactiver un utilisateur, modifier la sécurité et voir les rôles de sécurité qui ont été demandés pour l’utilisateur.

### <a name="purchase-orders-ready-for-review"></a>Commandes fournisseur prêtes pour examen
La page **Commandes fournisseur prêtes pour examen** vous permet d’afficher toutes les commandes fournisseur envoyées par le client, mais qui n’ont pas encore reçu de réponse. Vous pouvez sélectionner des informations concernant la commande, par exemple les produits qui ont été demandés et leur date de livraison. Les informations sur les prix sont également disponibles, en fonction de la configuration du fournisseur.

Vous pouvez également voir si la commande fournisseur comporte des notes ou des pièces jointes. Toutefois, pour ouvrir des notes et des pièces jointes, vous devez utiliser l’interface Web de collaboration du fournisseur disponible dans le client Web. Sélectionnez **Ligne de commande fournisseur** pour afficher toutes les lignes avec leurs détails. Pour chaque ligne, un indicateur permet de voir s’il existe des notes ou des pièces jointes, ou si l’adresse de livraison est différente de celle qui apparaît dans l’en-tête.

Pour répondre à la commande fournisseur, vous devez utiliser l’interface Web de collaboration du fournisseur disponible dans le client Web.

### <a name="awaiting-customer-action"></a>En attente d’une action du client
La page **En attente d’une action du client** vous permet de trouver les commandes fournisseur auxquelles vous, ou une autre personne de votre société qui a accès à la collaboration du fournisseur, avez répondu. Les commandes fournisseur ne sont visibles dans cette liste que si le client doit effectuer l’une des actions suivantes sur la commande fournisseur :

-   Si la commande fournisseur a été rejetée, le client doit mettre à jour ou annuler la commande d’origine et la renvoyer. Lorsque la commande fournisseur est renvoyée, elle n’apparaît plus sur la page **En attente d’une action du client**.
-   Si la commande fournisseur a été acceptée avec des modifications, le client doit mettre à jour la commande d’origine et la renvoyer pour examen, ou la mettre à jour conformément aux modifications demandées et la confirmer immédiatement. Dans les deux cas, la commande fournisseur n’apparaît plus sur la page **En attente d’une action du client**.
-   Si la commande fournisseur a été acceptée, mais apparaît toujours sur la page **En attente d’une action du client**, elle n’a pas été confirmée automatiquement quand elle a été acceptée. Elle attend qu’un agent des achats passe l’état de la commande à **Confirmé**. De manière générale, une commande fournisseur est considérée comme un accord conclu entre le client et le fournisseur dès que le fournisseur accepte la commande. Par conséquent, la mise à jour sur l’état **Confirmé** est une simple formalité.

Lorsque vous sélectionnez une commande fournisseur, des informations supplémentaires apparaissent concernant la réponse. Vous pouvez voir les détails de ligne et la réponse pour chaque ligne. La ligne de statut indique lesquelles des réponses suivantes ont été données :

-   Acceptée
-   Rejeté
-   Accepter avec les modifications
-   Remplacé/Remplacement
-   Fractionner en plan de livraison/Ligne de plan de livraison

Notez que le champ **Livraison** est défini sur **Oui** ou **Non** pour indiquer si les lignes seront livrées. Une ligne peut ne pas être livrée pour les raisons suivantes :

- La ligne a été rejetée.
- Un remplacement a été effectué, et la ligne d’origine n’est pas prévue d’être livrée conformément à la demande de la commande reçue.
- La ligne a été fractionnée en plusieurs lignes de plan de livraison, et la ligne d’origine n’est pas prévue d’être livrée conformément à la demande de la commande reçue.

Toutes les modifications apportées à la réponse de la ligne de commande sont affichées, à l’exception des notes et des pièces jointes téléchargées. Pour afficher les notes et les pièces jointes, vous devez utiliser l’interface Web de collaboration du fournisseur disponible dans le client Web.

### <a name="open-confirmed-orders"></a>Commandes confirmées en cours
Lorsque la commande fournisseur est confirmée par le client (son statut est passé à **Confirmé**), elle apparaît dans la liste des commandes confirmées en cours. Elle restera dans la liste jusqu’à ce qu’elle soit enregistrée comme reçue par le client.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

