---
title: Paramétrer un catalogue externe pour PunchOut eProcurement
description: Cette rubrique décrit l'utilisation d'un catalogue externe ou catalogue PunchOut pour collecter les informations de devis d'un fournisseur et les ajouter à une demande.
author: mkirknel
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchVendorPortalRequests, CatExternalCatalogConfiguration, CatCXMLCartLogList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dc6a38b1a9eebdee64762671bb501e5e1294399
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428265"
---
# <a name="set-up-an-external-catalog-for-punchout-e-procurement"></a>Paramétrer un catalogue externe pour PunchOut eProcurement

[!include [banner](../includes/banner.md)]

L'utilisation du catalogue externe vous permet de vous assurer que les informations sur les produits et les prix que vous traitez par la suite dans Supply Chain Management sont exactes et actualisées. La demande peut ensuite être approuvée et convertie en commande fournisseur et une commande peut être passée auprès du fournisseur.

Lorsque le catalogue externe est paramétré et qu'un employé prépare une demande, une option permet de rediriger vers un site externe, le catalogue externe, et de renvoyer le panier créé sur le site externe. Cette communication est basée sur le protocole cXML et doit être paramétrée entre les systèmes de l'organisation d'achat et de vente.

Pour paramétrer la communication, votre fournisseur doit fournir des informations que vous utilisez dans la configuration du catalogue externe, comme l'identité, le domaine de la société de l'acheteur, par exemple, « DUNS » et « numéro DUNS », les informations d'identification et l'URL d'accès au catalogue du fournisseur.

## <a name="setting-up-an-external-catalog"></a>Paramétrage d'un catalogue externe

Le catalogue externe permet à un employé qui entre une demande d'achat d'être redirigé vers un site externe pour sélectionner des produits. Les produits sélectionnés par l'employé dans le catalogue externe sont renvoyés avec des informations tarifaires actualisées, pour être ensuite ajoutés à la demande d'achat. L'objectif est que les employés ne puissent pas passer une commande sur le site externe. Lors du paramétrage du catalogue externe, vous devez vous assurer que l'objectif du site accessible par le catalogue externe est de collecter des informations de devis, et non de passer une commande réelle.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>Pour paramétrer un catalogue fournisseur externe, procédez comme suit :

1. Paramétrez une hiérarchie des catégories d'approvisionnement. Pour plus d'informations, voir [Paramétrer des stratégies pour les hiérarchies de catégories d'approvisionnement](tasks/set-up-policies-procurement-category-hierarchies.md).
2. Enregistrez le fournisseur dans Supply Chain Management. Avant de paramétrer des configurations pour accéder au catalogue d'un fournisseur externe, vous devez paramétrer le fournisseur et le contact associé dans Microsoft Dynamics 365. Le fournisseur du catalogue externe doit également être ajouté à la catégorie d'approvisionnement sélectionnée. Pour plus d'informations sur l'enregistrement des fournisseurs, voir [Gérer les utilisateurs de la fonctionnalité de collaboration fournisseur](manage-vendor-collaboration-users.md). Pour plus d'informations sur l'affectation des fournisseurs à une catégorie d'approvisionnement, voir [Approuver les fournisseurs pour des catégories d'approvisionnement spécifiques](tasks/approve-vendors-specific-procurement-categories.md).
3. Vérifiez que les unités de mesure et la devise utilisées par le fournisseur sont paramétrées. Pour plus d'informations sur la création d'une unité de mesure, voir [Gérer des unités de mesure](../pim/tasks/manage-unit-measure.md).
4. Configurez le catalogue fournisseur externe conformément aux exigences relatives au site de catalogue externe de votre fournisseur. Pour plus de détails sur cette tâche, voir [Configurer le catalogue fournisseur externe](#configure-the-external-vendor-catalog).
5. Testez les configurations du catalogue externe du fournisseur pour vérifier que les paramètres sont valides et que vous pouvez accéder au catalogue externe du fournisseur. Utilisez l'action **Valider les paramètres** pour valider le message de paramétrage de la demande que vous avez défini. Ce message doit entraîner l'ouverture du site du catalogue externe du fournisseur dans une fenêtre du navigateur. Pendant la validation, il est impossible de commander des articles et des services au fournisseur. Pour commander des articles et des services, vous devez accéder au catalogue du fournisseur à partir d'une demande d'achat.
6. Activez le catalogue externe à l'aide du bouton **Activer le catalogue** sur la page **Catalogues externes**. Le catalogue externe doit être activé pour que les employés peuvent l'utiliser. Vous pouvez désactiver le catalogue externe à tout moment.


## <a name="configure-the-external-vendor-catalog"></a>Configurer le catalogue fournisseur externe

Cette section fournit des informations supplémentaires sur la tâche 4 de la section précédente.

1. Entrez le nom et la description du catalogue externe du fournisseur. Le nom que vous entrez s'affiche sur le chariot qui représente le catalogue externe visible par les employés qui créent une demande. Les employés peuvent cliquer sur le chariot pour ouvrir le catalogue sur le site du catalogue externe du fournisseur.
2. Ajoutez une image à l'aide de l'action **Image du catalogue externe**. L'image s'affiche sur le chariot qui représente le catalogue externe visible par les employés qui créent une demande. Notez que la largeur et la hauteur de l'image doivent être égales. Sinon, l'image ne s'affichera pas correctement.
3. Indiquez si le site Web du catalogue externe du fournisseur doit apparaître dans la même fenêtre de navigateur que celle où l'employé a créé la demande, ou s'il doit s'ouvrir dans une nouvelle fenêtre.
4. Sélectionnez le fournisseur pour le catalogue. Dans la liste **Entités juridiques**, il existe une ligne pour chaque entité juridique dans laquelle le fournisseur est paramétré. Pour autoriser les utilisateurs à demander des produits directement à partir du catalogue du fournisseur dans certains entités juridiques mais pas dans d'autres, vous pouvez utiliser le bouton **Empêcher l'accès** ou **Autoriser l'accès** pour chaque entité juridique dans laquelle vous souhaitez que le catalogue soit disponible ou non.
5. Dans le champ **Expiration par défaut (jours)**, entrez le nombre de jours pendant lesquels un devis reçu du catalogue externe est valide et peut être utilisé pour effectuer des achats auprès du fournisseur externe. Lorsqu'un devis est créé et extrait du site du catalogue externe du fournisseur, il est valide à partir de la date système actuelle, et reste valide pendant le nombre de jours entrés dans ce champ.
6. Cliquez sur le bouton **Ajouter** pour commencer à mettre en correspondance les catégories d'approvisionnement avec le catalogue externe. Puis, dans la liste Nom de la catégorie, sélectionnez une catégorie. La liste des catégories est un superensemble de catégories d'approvisionnement avec lesquelles le fournisseur a été mis en correspondance dans toutes les entités juridiques paramétrées pour le fournisseur.

    > [!NOTE]
    > Les stratégies d'approvisionnement sont utilisées pour autoriser ou limiter l'accès aux catégories pour l'entité juridique d'achat ou l'unité opérationnelle de réception. Le pointage vers un catalogue externe requiert que l'accès soit autorisé à au moins une des catégories d'approvisionnement mises en correspondance avec le catalogue.

7. Paramétrez le message de demande de paramétrage cXML qui est envoyé au fournisseur. Le format du message généré automatiquement est le modèle minimal requis pour démarrer une session. Renseignez les valeurs des balises.

À tout moment, vous pouvez recharger le modèle de message généré par le système en cliquant sur **Restaurer le format du message**. 
Notez que si vous restaurez le format du message, le message actuel sera remplacé par le format de message généré automatiquement, qui contient des balises vides.

### <a name="cxml-setup-message"></a>Message de paramétrage cXML
Vous trouverez ci-dessous une description des balises incluses dans le modèle :

| Champ | Description | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|Domaine de la société de l'acheteur.|
|< Header >< From >< Credential>< Identity >< /Identity > | Identité de la société de l'acheteur.|
|< Header >< To >< Credential domain=”” > | Domaine de la société du fournisseur.|
|< Header >< To >< Credential>< Identity >< /Identity> | Identité de la société du fournisseur.|
|< Header >< Sender >< Credential domain=”” > | Domaine de la société de l'acheteur.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | Identité de la société de l'acheteur.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|Secret partagé pour la société de l'acheteur.|
|< Request deploymentMode=”” >|Déploiement de test ou de production.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|URL du point de terminaison PunchOut du fournisseur.|

### <a name="extrinsic-elements"></a>Éléments extrinsèques

Les informations supplémentaires représentent un élément extrinsèque, comme un nom d'utilisateur basé sur un utilisateur qui exécute un pointage. L'élément extrinsèque est défini lorsque le PunchOut se produit et il peut être envoyé dans le message de configuration de la demande.
Votre fournisseur peut exiger de recevoir un élément extrinsèque dans la demande de paramétrage. Dans ce cas, vous devez ajouter l'élément extrinsèque à la liste des éléments extrinsèques dans la section **Format du message** de la page **Catalogue externe**.
Spécifiez un nom pour l'élément extrinsèque que le fournisseur peut identifier, et mettez-le en correspondance avec une valeur. Les options pour les valeurs sont : Nom d'utilisateur, E-mail de l'utilisateur ou Valeur aléatoire.
Pour plus d'informations sur le protocole cXML, voir le [site web cXML.org](http://cxml.org/).

## <a name="post-back-message"></a>Message de publication
Le message de publication est le message reçu du fournisseur lorsque l'utilisateur procède à la validation à partir du site externe et retourne dans Supply Chain Management. Les messages de publication ne peuvent pas être configurés. Les messages sont basés sur la définition du protocole cXML. Voici les informations qui peuvent faire partie du message de publication reçu sur une ligne de demande.

| Message reçu du fournisseur | Copié vers la ligne de réquisition|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |Quantité|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|ID article externe|
|< ItemDetail>< UnitPrice >< Money currency=”” >| Devise|
|< ItemDetail >< UnitPrice >< Money >< /Money >| Prix unitaire|
|< ItemDetail >< Description ShortName=”” >|Nom du produit|
|< ItemDetail >< Description >< /Description >|Inclus dans la description de l'article ; nom du produit si ShortName n'est pas spécifié.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|Unité|
|< ItemDetail >< Classification >< /Classification >|Inclus dans la description de l'article|
|< ItemDetail >< Classification domain=”” >|Inclus dans la description de l'article|

## <a name="delete-an-external-catalog"></a>Suppression d'un catalogue externe
Supprimez un catalogue externe avec l'action Supprimer sur la page.

Si un produit figurant dans le catalogue fournisseur externe a été demandé, ce catalogue ne peut pas être supprimé. En revanche, le statut du catalogue fournisseur externe est défini sur Inactif. Si vous souhaitez supprimer l'accès au site du catalogue fournisseur externe sans supprimer ce dernier, modifiez le statut du catalogue externe sur Inactif.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Améliorations des cXML d’achat](purchasing-cxml-enhancements.md)
- [Utiliser des catalogues externes pour PunchOut eProcurement](use-external-catalogs-for-punchout.md)