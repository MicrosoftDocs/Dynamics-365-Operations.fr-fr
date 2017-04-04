---
title: Approvisionnements dans le secteur public en France
description: "Cet article explique comment les fonctionnalités standard associées aux approvisionnements ont été étendues pour les entités françaises du secteur public. Ces fonctionnalités permettent de répondre aux besoins du Code des marchés publics."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AgreementClassification, PurchAgreement, SysPolicy
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19891
ms.assetid: 3d3c89eb-5d6b-4d79-879b-ad6bf4bade35
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 2265af7696164d68c3bb89569bf44fc2694472da
ms.lasthandoff: 03/31/2017


---

# <a name="procurement-and-sourcing-in-the-public-sector-in-france"></a>Approvisionnements dans le secteur public en France

Cet article explique comment les fonctionnalités standard associées aux approvisionnements ont été étendues pour les entités françaises du secteur public. Ces fonctionnalités permettent de répondre aux besoins du Code des marchés publics. 

<a name="set-spending-thresholds-by-procurement-category"></a>Définition de seuils de dépense par catégorie d'approvisionnement
-----------------------------------------------

Pour définir des seuils de dépenses pour les achats dans les catégories d'approvisionnement définies par la Clé de Contrôle Marché, vous pouvez utiliser la règle de stratégie d'achat **Seuils de dépense par catégorie**. La mise en œuvre de cette règle de stratégie d'achat afin de contrôler les seuils de dépense par catégorie vous permet d'utiliser les attributs de la date d'effet, les montants des dépenses prévues, ainsi que les montants des seuils afin de prendre en charge vos pratiques d'approvisionnement et d'aider à garantir l'utilisation décisive et efficace des fonds publics.

## <a name="create-tranches-and-lots"></a>Création de tranches et lots
Pour créer des tranches et des lots, vous pouvez créer une hiérarchie de contrats d'achat parent et enfant. Les contrats d'achat enfants sont utilisés comme tranches et lots du contrat d'achat parent. La hiérarchie des contrats d'achat possède des caractéristiques spécifiques :

-   Un utilisateur peut afficher le contrat d'achat parent et voir l'activité globale du parent et de tous ses contrats enfants associés. Cette fonctionnalité permet de disposer d'une vue d'ensemble pour examiner et contrôler l'activité liée aux contrats d'achat.
-   Certaines valeurs du contrat d'achat parent sont automatiquement transférées aux contrats enfants. Par exemple, les stratégies associées à la publicité comparative peuvent être affectées au contrat d'achat parent. Elles seront ensuite appliquées à tous les contrats enfants liés à ce parent.
-   Les contrats d'achat peuvent avoir un fournisseur principal, des fournisseurs secondaires et des sous-traitants. Le fournisseur principal peut être affecté au contrat d'achat parent et un fournisseur secondaire ou un sous-traitant peut être affecté à des contrats enfants spécifiques.

**Remarque :** si vous avez ajouté des lignes à un contrat d'achat, celui-ci ne peut pas être utilisé en tant que contrat parent. Le bouton **Créer un contrat enfant** ne sera donc plus accessible. De même, si vous avez créé un contrat d'achat enfant, vous ne pouvez pas ajouter de lignes au contrat d'achat parent. Pour voir la relation entre les contrats d'achat parent et enfant, utilisez la page **Arborescence des contrats d'achat**.

## <a name="set-up-purchase-agreement-access-and-limits"></a>Définition de l'accès à un contrat d'achat et des limites
Vous pouvez paramétrer des contrats d'achat de sorte que seuls les départements approuvés ont accès au contrat. Vous pouvez également limiter le montant que chaque département peut dépenser dans le cadre du contrat d'achat. Les utilisateurs qui tentent de dépasser le montant maximum alloué à un département spécifique, reçoivent un message et se trouvent dans l'impossibilité de confirmer le déblocage du montant ou le traitement de la facture. Pour être en mesure d'utiliser cette capacité, vous devez d'abord définir les paramètres suivants dans la section **Général** de la page **Paramètres de la comptabilité fournisseur** :

-   Dans le champ **Structure de compte**, sélectionnez la structure de compte à utiliser sur la page **Accès du département au contrat d'achat** pour contrôler l'accès aux contrats d'achat. La structure de compte doit comprendre le segment de dimension financière que vous utilisez pour contrôler l'accès aux contrats d'achat.
-   Dans le champ **Dimension financière**, sélectionnez la dimension financière que vous utilisez pour contrôler l'accès aux contrats d'achat. La plupart des organisations utilisent la dimension de département, mais certaines organisations limitent l'accès aux contrats à différentes entités au sein de l'organisation.

## <a name="manage-information-about-subcontractors-certifications-and-milestones-on-purchase-agreements"></a>Gestion des informations relatives aux sous-traitants, aux certifications et aux jalons dans les contrats d'achat
Vous pouvez créer des classifications de contrat d'achat qui ajoutent des champs administratifs aux contrats d'achat qui utilisent la classification.

-   Pour ajouter des informations sur les sous-traitants aux contrats d'achat, sélectionnez ** les sous-traitants ** l'option dans la classification de contrat d'achat.  Les contrats d'achat peuvent avoir un fournisseur principal, des fournisseurs secondaires et des sous-traitants. Le fournisseur principal peut être affecté au contrat d'achat parent et un fournisseur secondaire ou un sous-traitant peut être affecté à des contrats enfants spécifiques.
-   Pour ajouter aux contrats d'achat des informations relatives aux certifications pour les fournisseurs, sélectionnez l'option **Certifications** de la classification de contrat d'achat. Les informations de certification permettent de générer un état que vous pouvez utiliser pour vérifier que les fournisseurs répondent bien aux exigences en matière de certification.
-   Pour ajouter aux contrats d'achat des informations relatives aux jalons et aux tâches, sélectionnez l'option **Activités** de la classification de contrat d'achat.

 


