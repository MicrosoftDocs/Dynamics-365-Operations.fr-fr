---
title: Imprimer les informations fiscales sur les documents d'ordre de transfert
description: Cette rubrique explique comment les informations fiscales déterminées par le service de calcul des taxes peuvent être imprimées sur les documents d'ordre de transfert.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: d55767ef47e01edd11099f644134cfa48ea70e18
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675724"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Imprimer les informations fiscales sur les documents d'ordre de transfert

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Cette rubrique explique comment imprimer les informations fiscales sur les documents d'ordre de transfert. Vous pouvez imprimer le document de facture pro forma d'un ordre de transfert pour les transferts de stock qui sont considérés comme des livraisons intracommunautaires et des acquisitions intracommunautaires en vertu de la réglementation de l'Union européenne (UE) sur la taxe sur la valeur ajoutée (TVA). 

Les données fiscales suivantes sont ajoutées aux documents d'ordre de transfert :

- Les noms et les adresses de livraison et de livraison pour le transfert de stock
- Les numéros d'identification fiscale du fournisseur et du destinataire
- Le prix unitaire et la base d'imposition des marchandises livrées
- Le code fiscal, le taux de taxe, le montant de la taxe et les directives fiscales

Pour configurer ces données, vous devez effectuer les principales étapes suivantes.

1. [Activer et configurer la fonction de taxe pour les ordres de transfert](tasks/Tax-feature-support-for-transfer-order.md).
2. [Créer et configurer plusieurs numéros d'identification fiscale pour une entité juridique](emea-multiple-vat-registration-numbers.md).
3. Configurez le code d'exonération, la description, les directives fiscales et le code d'impression dans les codes de taxe. Pour cet exemple, trois codes taxe sont créés et synchronisés dans Microsoft Dynamics 365 Finance : **NL-Exempt**, **BE-RC-21** et **BE-RC+21**.

    1. Dans Finance, accédez à **Taxes** \> **Paramétrage** \> **Taxe de vente** \> **Codes d’exonération fiscale**.
    2. Sélectionnez **Modifier**, et entrez une description pour le code d'exonération **CE**. Par exemple, entrez **Envois CE détaxés avec numéro d'enregistrement fiscal**.
    3. Accédez à **Taxe** \> **Taxes indirectes** \> **Taxe** \> **Codes taxe**.
    4. Sélectionnez le code fiscal **BE-RC-21**, puis sélectionnez **Instructions relatives à la taxe**.
    5. Sélectionnez **Nouveau**.
    6. Dans le champ **Langue**, sélectionnez **EN-US**. Ensuite, dans le champ **Texte**, entrez **Document fixant le transfert de biens au sens de l'article 138. 2. c) de la Directive TVA de l'UE 2006/112/CE**.
    7. Fermez la page.
    8. Dans le raccourci **Général**, dans le champ **Imprimer**, sélectionnez **Taux de taxe de vente**.
    8. Sélectionnez le code fiscal **NL-Exempt**, puis sur le raccourci **Général**, dans le champ **Imprimer**, sélectionnez **Taux de taxe de vente**.

    > [!NOTE] 
    > Le code fiscal, le taux de taxe et la description d'exonération de taxe ne sont pas imprimés sur les documents d'ordre de transfert si aucune description de code d'exonération ou directive fiscale n'est conservée pour le code fiscal.

## <a name="print-the-transfer-order---shipment-document"></a>Imprimer l'ordre de transfert - document d'expédition

Après l'expédition d'un transfert, suivez ces étapes pour imprimer l'ordre de transfert - document d'expédition.

1. Accédez à **Gestion des stocks** \> **Recherches et rapports** \> **Ordres de transfert** \> **Expédition**.
2. Dans l'onglet **Paramètres**, dans le groupe **Imprimer**, activez **Informations fiscales**.
3. Dans l'onglet **Enregistrements à inclure**, sélectionnez **Filtre**, sélectionnez le numéro de l'ordre de transfert, puis sélectionnez **OK**.
4. Sélectionnez **OK** pour imprimer l'ordre de transfert - document d'expédition.

## <a name="print-the-transfer-order---receipt-document"></a>Imprimer l'ordre de transfert - document de réception

Après la réception d'un transfert, suivez ces étapes pour imprimer l'ordre de transfert - document de réception.

1. Accédez à **Gestion des stocks** \> **Recherches et rapports** \> **Ordres de transfert** \> **Réception**.
2. Dans l'onglet **Paramètres**, dans le groupe **Imprimer**, activez **Informations fiscales**.
3. Dans l'onglet **Enregistrements à inclure**, sélectionnez **Filtre**, sélectionnez le numéro de l'ordre de transfert, puis sélectionnez **OK**.
4. Sélectionnez **OK** pour imprimer l'ordre de transfert - document de réception.

## <a name="print-the-transfer-overview-document"></a>Imprimer le document d'aperçu du transfert

Suivez ces étapes pour imprimer le document de présentation du transfert.

> [!NOTE]
> Les informations fiscales ne sont disponibles que lorsque l'ordre de transfert a été expédié ou reçu.

1. Accédez à **Gestion des stocks** \> **Recherches et rapports** \> **Ordres de transfert** \> **Vue d'ensemble du transfert**.
2. Dans l'onglet **Paramètres**, dans le groupe **Imprimer**, activez **Informations fiscales**.
3. Dans l'onglet **Enregistrements à inclure**, sélectionnez **Filtre**, sélectionnez le numéro de l'ordre de transfert, puis sélectionnez **OK**.
4. Sélectionnez **OK** pour imprimer le document d'aperçu du transfert.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
