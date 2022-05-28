---
title: Fonctionnalité de facturation fractionnée
description: Cette rubrique décrit la configuration et la fonctionnalité de fractionnement des factures par adresse de livraison et numéro de compte fiscal (TAN).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f1dac8d51c24009dcf0c4acbc49f06f32abf0dec
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724667"
---
# <a name="split-invoice-functionality"></a>Fonctionnalité de facturation fractionnée

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la configuration et la fonctionnalité de fractionnement des factures par adresse de livraison et numéro de compte fiscal (TAN).

Sur la page **Paramètres des comptes fournisseurs**, dans l'onglet **Général**, sélectionnez la case à cocher **Reçu de produit** ou **Facture** et fractionner un reçu de produit ou une facture qui a des adresses de livraison et des TAN différents sur la page **Commande fournisseur**. La facture validée sera ensuite divisée par adresse de livraison et TAN.

Dans l'onglet **Mise à jour récapitulative**, sur le raccourci **Fractionner basé sur**, sur la ligne **Informations de livraison**, définissez l'option **Confirmation**, **Prélèvement**, **Bon de livraison** ou **Facture** sur **Oui** pour enregistrer et fractionner une confirmation, une liste de prélèvement, un bon de livraison ou une facture où différentes adresses de livraison et TAN sont définis pour différentes lignes de facture sur la page **Commande client**. La facture validée sera d'abord divisée par adresse de livraison, puis sur la base du TAN.

> [!IMPORTANT]
> - Si aucune option pour **Informations de livraison** n'est définie sur **Oui**, la facture sera enregistrée comme une seule facture. Aucun fractionnement de facture n'aura lieu.
> - Pour fractionner et valider un bon de livraison où les lignes de facture ont des adresses de livraison et des TAN différents, vous devez définir l'option **Bon de livraison** pour **Informations de livraison** sur **Oui**.
> - Pour fractionner et valider une facture où les lignes de facture ont des adresses de livraison et des TAN différents, vous devez définir l'option **Facture** pour **Informations de livraison** sur **Oui**.
> - Pour fractionner et valider une facture où les lignes de facture ont des adresses de livraison différentes mais le même TAN, vous devez définir l'option **Facture** pour **Informations de livraison** sur **Non**. La facture validée sera divisée par adresse de livraison.

## <a name="example"></a>Exemple

Dans cet exemple, l'option **Facture** pour **Informations de livraison** est paramétrée sur **Oui** dans l'onglet **Mise à jour récapitulative** de la page **Paramètres des comptes fournisseurs**. Une facture d'achat est validée avec la configuration suivante pour les adresses de livraison et les TAN sur les lignes :

- **Ligne d'article 1 :** Adresse de livraison 1, TAN-ABCD12345A
- **Ligne d'article 2 :** Adresse de livraison 1, TAN-ABCD12345A
- **Ligne d'article 3 :** Adresse de livraison 2, TAN-ABCE12345B
- **Ligne d'article 4 :** Adresse de livraison 3, TAN-ABCD12345A

Dans ce cas, la facture originale est scindée en deux factures et validée de la manière suivante :

- La facture 1 est validée pour la ligne d'article 1 et la ligne d'article 2, car les deux lignes ont la même adresse de livraison et TAN.
- La facture 2 est validée pour la ligne d'article 3.
- La facture 3 est validée pour la ligne d'article 4.
