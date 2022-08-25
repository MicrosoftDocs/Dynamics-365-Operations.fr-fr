---
title: Formulaire 1099 dans le secteur public
description: Cet article donne des conseils et des informations sur la manière de configurer la fonctionnalité du Formulaire 1099 pour la comptabilité fournisseur dans le secteur public.
author: brpotter
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: USA
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 26181
ms.assetid: 10f56dea-ea2d-48ea-9622-4ef715eb1179
ms.search.industry: Public sector
ms.search.form: LedgerTransVoucher, SysConfiguration, Tax1099Summary, VendTableListPage
ms.openlocfilehash: 389639be6cd3be4a5a9b15a6e94054d081114a79
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279792"
---
# <a name="form-1099-in-the-public-sector"></a>Formulaire 1099 dans le secteur public

[!include [banner](../includes/banner.md)]

Cet article donne des conseils et des informations sur la manière de configurer la fonctionnalité du Formulaire 1099 pour la comptabilité fournisseur dans le secteur public.

Le formulaire d’impôt 1099 est requis si vous faites affaire avec des fournisseurs assujettis à la taxe 1099 des États-Unis. Cet article décrit la fonctionnalité 1099 disponible pour le secteur public. Nous vous recommandons également d’examiner les modifications apportées à la règle d’administration fiscale (IRS) pour l’exercice applicable avant de configurer et de traiter les relevés 1099. Si vous faites affaire avec des fournisseurs assujettis à la taxe 1099 des États-Unis, vous devez faire le suivi du montant que vous payez à chaque fournisseur et déclarer cette information aux autorités fiscales américaines à la fin de l’année civile. Les fournisseurs sont généralement des organisations qui fournissent des services à votre organisation. Les fournisseurs peuvent également être des personnes bien distinctes des employés. Vous devez également envoyer un relevé à chaque fournisseur 1099 avec lequel vous faites affaire, pour informer le fournisseur du montant que vous déclarez aux autorités fiscales. Les organisations juridiques du secteur public qui ont une adresse principale aux États-Unis peuvent soumettre le formulaire 1099-G ou le formulaire 1099-S à l’administration fiscale. Le formulaire d’impôt sur le revenu 1099-G est utilisé pour déclarer les revenus provenant de sources gouvernementales, comme les remboursements fiscaux locaux ou nationaux, les allocations de chômage. les subventions, ou les aides. Le formulaire d’impôt sur le revenu 1099-G est utilisé pour déclarer les revenus provenant de la vente ou de l'échange de certains types de biens immobiliers. Dans Dynamics 365 Finance, les procédures de configuration 1099 ne doivent généralement être effectuées qu'une seule fois. Toutefois, vous pouvez utiliser ces informations ultérieurement si vous souhaitez modifier ou afficher des entrées existantes.

## <a name="tips"></a>Conseils
-   Sur de nombreuses pages, vous observerez peut-être que le champ **Produit brut S-2** ne s’affiche pas. Ce champ ne s’affiche pas si le montant est le même que le montant du champ **Fédéral réglé 1099**.
-   Un état 1099 individuel est associé à chaque facture 1099-S. Vous pouvez utiliser l’état **Détail de la taxe 1099** pour afficher des informations détaillées 1099-S.
-   Sur les lignes de nombreux journaux, vous ne pouvez pas entrer un montant S-2. Ce montant est le même que le champ de montant 1099. Toutefois, vous pouvez entrer les détails S-2 sur l'onglet **1099** de ces pages. Par ailleurs, vous ne pouvez pas sélectionner **S-5** sur ces pages, car vous devez entrer ce montant manuellement dans le champ **Part de la taxe foncière S-5 supportée par l’acheteur**.

## <a name="how-do-i-view-or-specify-vendor-settlement-for-1099s"></a>Comment afficher ou préciser le règlement fournisseur pour les 1099 ?
Utilisez la page **Règlement fournisseur pour les 1099** pour entrer ou afficher les montants 1099 qui s’appliquent à vos fournisseurs, préparer les relevés 1099, imprimer des copies pour les fournisseurs, et créer des fichiers d’exportation. La personne ou l’organisation désignée comme émetteur 1099 peut envoyer les relevés 1099 à l’administration fiscale en utilisant des supports magnétiques ou en les déposant électroniquement. Sinon, vous pouvez sélectionner un compte fournisseur sur la page **Tous les fournisseurs** dans Comptabilité fournisseur ou Approvisionnements, cliquer sur **Fournisseur** dans le volet Action, puis cliquer sur **Règlement fournisseur pour les 1099**. **Remarques**

-   Vous pouvez modifier la valeur dans le champ **Zone 1099** sur le raccourci **Rapport 1099** dans la page de détails du fournisseur. Si vous sélectionnez **G-2** et si vous tentez de mettre à jour l’ensemble des enregistrements de fournisseur, vous êtes invité à confirmer la mise à jour. Les informations G-2 sont généralement entrées uniquement après l’analyse attentive de chaque fournisseur.
-   Sur la page **Règlement fournisseur pour les 1099**, même si un montant S-2 est inférieur à l’exigence minimale, vous devez toujours le déclarer à l’administration fiscale. Par exemple, le montant S-2 est 0 (zéro), et l’option **Transfert S-4 ou propriété ou service reçus** est sélectionnée. Dans ce cas, l’option **À déclarer à l’administration fiscale** est également sélectionnée.

## <a name="how-do-i-update-1099-information"></a>Comment mettre à jour les informations 1099 ?
Vous pouvez également utiliser la page **Règlement fournisseur pour les 1099** pour saisir ou mettre à jour les informations 1099 pour un fournisseur. Vous pouvez mettre à jour les montants minimaux par défaut pour les champs de formulaire 1099-G ou 1099-S, s’ils sont inclus. **Remarques**

-   Certains champs sont volontairement omis. Par exemple, le champ **S-5** est omis, car il est utilisé pour les taxes foncières et le montant minimal exigé par l’administration fiscale ne s’applique pas. En outre, il est possible de configurer les montants 1099-G et 1099-S sur cette page, sans pour autant pouvoir suivre et imprimer les informations fournisseur 1099-G ou 1099-S.
-   L’IRS pourrait exiger que, si un seul montant sur une page dépasse le montant minimum, tous les montants doivent être déclarés, même si tous les autres montants sont inférieurs au montant minimum.


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la comptabilité fournisseur dans le secteur public](../public-sector/accounts-payable-public-sector.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
