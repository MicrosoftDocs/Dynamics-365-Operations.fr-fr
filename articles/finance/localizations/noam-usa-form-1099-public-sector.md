---
title: Écran 1099 dans le secteur public
description: Cet article donne des conseils et des informations sur la manière de configurer la fonctionnalité du formulaire 1099 de déclaration d'honoraires pour la comptabilité fournisseur dans le secteur public.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 26181
ms.assetid: 10f56dea-ea2d-48ea-9622-4ef715eb1179
ms.search.region: USA
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66b311a02238aae5c08f71c64c751444cb187410
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770401"
---
# <a name="form-1099-in-the-public-sector"></a>Écran 1099 dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article donne des conseils et des informations sur la manière de configurer la fonctionnalité du formulaire 1099 de déclaration d'honoraires pour la comptabilité fournisseur dans le secteur public.

Le formulaire 1099 de déclaration d'honoraires est requis si vous entretenez des relations commerciales avec des fournisseurs américains assujettis à la taxe sur les honoraires. Cette rubrique décrit la fonctionnalité 1099 de déclaration d'honoraires disponible pour le secteur public. Il est également recommandé d'analyser les modifications apportées à la règle d'administration fiscale pour l'exercice applicable avant de paramétrer et de compléter les relevés 1099 de déclaration des honoraires. Si vous entretenez des relations commerciales avec des fournisseurs américains assujettis à la taxe sur les honoraires, vous devez effectuer le suivi du montant réglé à chaque fournisseur et le déclarer à l'administration fiscale des États-Unis à la fin de l'année civile. Les fournisseurs sont généralement des organisations qui fournissent des services à votre organisation. Les fournisseurs peuvent également être des personnes bien distinctes des employés. Vous devez également envoyer un relevé 1099 d'honoraires à chaque fournisseur avec lequel vous entretenez des relations commerciales. Celui-ci l'informe du montant déclaré à l'administration fiscale. Les organisations du secteur public juridique ayant une adresse principale aux États-Unis peuvent envoyer le formulaire 1099 G ou S de déclaration d'honoraires à l'administration fiscale. Le formulaire 1099 G de déclaration de l'impôt sur le revenu est utilisé pour signaler les revenus provenant du gouvernement, comme les remboursements fiscaux locaux ou nationaux, les indemnités-chômage et les subventions. Le formulaire 1099 S de déclaration des revenus est utilisé pour déclarer les revenus issus de certaines taxes foncières. Généralement, dans Dynamics 365 Finance, les procédures de paramétrage 1099 doivent être effectuées une seule fois. Toutefois, vous pouvez utiliser ces informations ultérieurement si vous souhaitez modifier ou afficher des entrées existantes.

## <a name="tips"></a>Conseils
-   Sur de nombreuses pages, vous observerez que le champ **Produit brut S-2** ne s'affiche pas. Ce champ ne s'affiche pas si le montant est identique à celui figurant dans le champ **Déclaration d'honoraires locale réglée**.
-   Un état 1099 individuel est associé à chaque facture 1099-S. Vous pouvez utiliser l'état **Détail de la taxe sur les honoraires** pour afficher des informations détaillées sur le formulaire 1099 S.
-   Sur les lignes de nombreux journaux, il est impossible de saisir un montant S-2. Ce montant est identique à celui figurant dans le champ de montant 1099. Toutefois, vous pouvez saisir les informations du formulaire S-2 sous l'onglet **1099** de ces pages. Par ailleurs, vous ne pouvez pas sélectionner **S-5** sur ces pages, car vous devez saisir ce montant manuellement dans le champ **Part de la taxe foncière S-5 supportée par l'acheteur**.

## <a name="how-do-i-view-or-specify-vendor-settlement-for-1099s"></a>Comment afficher ou préciser le règlement fournisseur pour les déclarations d'honoraires ?
Utilisez la page **Règlement fournisseur pour les déclarations d'honoraires** pour saisir ou afficher les montants des honoraires qui s'appliquent aux fournisseurs, préparer les relevés 1099 de déclaration d'honoraires, imprimer des copies pour les fournisseurs et créer des fichiers d'exportation. La personne ou l'organisation désignée comme émetteur de déclaration d'honoraires peut envoyer les relevés 1099 de déclaration d'honoraires à l'administration fiscale via un support magnétique ou par transmission électronique. À défaut, vous pouvez sélectionner un compte fournisseur sur la page **Tous les fournisseurs** dans Comptabilité fournisseur ou Approvisionnements, cliquer sur **Fournisseur** dans le volet Actions, puis cliquer sur **Règlement fournisseur pour les déclarations d'honoraires**. **Remarques**

-   Vous pouvez modifier la valeur dans le champ **Zone de déclaration des honoraires** sur l'organisateur **Générer la déclaration des honoraires** dans la page de détails du fournisseur. Si vous sélectionnez **G-2** et si vous tentez de mettre à jour l'ensemble des enregistrements de fournisseur, vous êtes invité à confirmer la mise à jour. Les informations G-2 sont généralement entrées uniquement après l'analyse attentive de chaque fournisseur.
-   Sur la page **Règlement fournisseur pour les déclarations d'honoraires**, même si un montant S-2 est inférieur à l'exigence minimale, vous devez toujours le déclarer à l'administration fiscale. Par exemple, le montant S-2 est 0 (zéro), et l'option **Transfert S-4 ou propriété ou service reçus** est sélectionnée. Dans ce cas, l'option **À déclarer à l'administration fiscale** est également sélectionnée.

## <a name="how-do-i-update-1099-information"></a>Comment mettre à jour les informations de déclaration d'honoraires ?
Vous pouvez également utiliser la page **Règlement fournisseur pour les déclarations d'honoraires** pour saisir ou mettre à jour les informations de déclaration d'honoraires pour un fournisseur. Vous pouvez mettre à jour les montants minimaux par défaut pour les champs de formulaire G ou S, s'ils sont inclus. **Remarques**

-   Certains champs sont volontairement omis. Par exemple, le champ **S-5** est omis, car il est utilisé pour les taxes foncières et le montant minimal exigé par l'administration fiscale ne s'applique pas. En outre, il est possible de paramétrer les montants 1099-G et 1099-S sur cette page, sans pour autant pouvoir suivre et imprimer les informations fournisseur 1099-G ou 1099-S.
-   Si le montant d'un formulaire est supérieur au montant minimal, l'administration fiscale peut exiger que tous les montants soient déclarés, même s'ils sont inférieurs au montant minimal.


<a name="additional-resources"></a>Ressources supplémentaires
--------

[Vue d'ensemble de la comptabilité fournisseur dans le secteur public](../public-sector/accounts-payable-public-sector.md)



