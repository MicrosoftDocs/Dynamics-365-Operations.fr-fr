---
title: Biens à double usage
description: Cet article explique comment suivre les produits identifiés comme des biens à double usage, stocker les numéros de certificat pour chaque produit concerné et pays de destination, et imprimer des numéros de certificat valides sur les factures, bons de livraison et/ou commandes client concernés.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COODualUseCerts, COORules, COODualUseCountries
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 5147a837be91aab519c373e624acc036f9293641
ms.sourcegitcommit: 555de844b8ba02fe095c28a2d447fc7c441ae549
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460546"
---
# <a name="dual-use-goods"></a>Biens à double usage

[!include [banner](../includes/banner.md)]

Les biens à double usage sont généralement des articles qui ont des applications à la fois civiles et militaires. Par exemple, un produit chimique peut être utilisé comme engrais ou comme explosif. De nombreux pays ont des réglementations spéciales qui s’appliquent à l’exportation, à l’importation et au transport des biens à double usage. Par conséquent, il est important que les entreprises impliquées dans le commerce international de biens à double usage se tiennent informées des différentes politiques et certifications.

La fonctionnalité des biens à double usage aide les entreprises à suivre les produits identifiés comme des biens à double usage, stocker les numéros de certificat pour chaque produit concerné et pays de destination, et imprimer des numéros de certificat valides sur les factures, bons de livraison et/ou commandes client concernés. Elle permet de garantir que, lorsque vos produits sont expédiés, ils incluent toujours des certifications à jour.

Prenons le scénario suivant :

1. La page **Configuration du pays pour les biens à double usage** de votre système indique que les expéditions vers la France nécessitent une certification.
2. La page **Détails du produit lancé** pour le produit X-100 indique qu’il s’agit d’un bien à double usage. Ensemble, le code, la catégorie, le groupe et le régime indiquent la classe de contrôle des exportations à laquelle appartient le produit.
3. La page **Certificats des biens à double usage** inclut un certificat pour le produit X-100 lorsqu’il est expédié vers la France. Ce certificat expire le 1er janvier 2020.
4. Le 17 juin 2020, vous créez une commande client pour une société cliente basée en France et la commande comprend le produit X-100.
5. Lorsque vous confirmez la commande client, le système détermine les informations suivantes :

    1. La commande comprend-elle des produits à double usage ?
    2. Si la commande comprend des biens à double usage, le pays de destination exige-t-il des certificats de double usage ?
    3. Si le pays exige des certificats de double usage, existe-t-il un certificat valide pour chaque bien à double usage pour le pays de destination ?

6. La commande comprend le produit X-100, le produit est expédié en France et un certificat français existe pour le produit. Cependant, le certificat a expiré. Par conséquent, le message d’avertissement suivant s’affiche : « Les certificats des produits à double usage pour un ou plusieurs articles à double usage de cette commande client ne sont pas valides. Voulez-vous procéder à la confirmation ? »

Cet article explique comment configurer tous les paramètres requis pour configurer les biens à double usage et prendre en charge ce scénario.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>Définir les exigences du double usage pour chaque pays concerné

Les différents pays ont des exigences différentes en ce qui concerne les biens à double usage. Vous utilisez la page **Configuration du pays pour les biens à double usage** pour garder une trace des pays qui exigent un certificat ou non. Les informations que vous spécifiez ici sont vérifiées lorsque vous créez des commandes client ; il vous est alors rappelé de fournir les certifications requises.

Pour configurer les informations sur les exigences de double usage pour différents pays, procédez comme suit.

1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Produits à double usage \> Configuration du pays pour les biens à double usage**.
2. Sélectionnez une configuration de pays existante pour la modifier, ou sélectionnez **Nouveau** dans le volet Actions pour créer une nouvelle configuration de pays.
3. Définissez les valeurs suivantes pour la configuration de pays sélectionnée ou nouvelle.

    | Champ | Description |
    |---|---|
    | Pays/région | Sélectionnez le pays pour lequel vous suivez les exigences. |
    | Certificat obligatoire | Cochez cette case pour les pays qui exigent une certification pour les biens à double usage. Décochez-la pour les pays qui n’exigent pas cette certification. |

## <a name="create-dual-use-categories"></a>Créer des catégories de double usage

Les biens à double usage doivent souvent être classés en fonction de leur numéro de classification du contrôle des exportations (ECCN). Le code ECCN est un code alphanumérique qui catégorise les articles en fonction de facteurs tels que la marchandise et la technologie. La page **Catégories de biens à double usage** vous aide à dresser une liste des catégories que vous utilisez, à des fins de création de rapports.

Pour paramétrer des catégories de biens à double usage, procédez comme suit.

1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Produits à double usage \> Catégories de biens à double usage**.
2. Sélectionnez une catégorie pour la modifier ou sélectionnez **Nouveau** dans le volet Actions pour créer une nouvelle catégorie.
3. Définissez les valeurs suivantes pour la catégorie sélectionnée ou la nouvelle catégorie.

    | Champs | Description |
    |---|---|
    | Code de double usage | Entrez le code ECCN complet (par exemple, *3A001*).|
    | Catégorie de produits à double usage | Entrez la partie Catégorie de la liste de contrôle du commerce (CCL) du code ECCN. Par exemple, pour le code ECCN *3A001*, cette valeur est *3*. |
    | Groupe à double usage | Saisissez la partie Groupe de produits du code ECCN. Par exemple, pour le code ECCN *3A001*, cette valeur est *A*. |
    | Régime applicable aux biens à double usage | Entrer le code de régime pour l’article. Ce code identifie la raison pour laquelle l’article est classé comme bien à double usage. Par exemple, pour le code ECCN *3A001*, cette valeur est *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Appliquer des catégories de biens à double usage aux produits

Pour identifier un produit comme un bien à double usage et lui appliquer une catégorie de double usage, procédez comme suit.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Sélectionnez ou créez un produit pour ouvrir sa page **Détails des produits lancés**.
1. Dans l’organisateur **Commerce extérieur**, définissez l’option **Produits à double usage** sur **Oui** pour identifier le produit actuel comme un bien à double usage.
1. Définissez le champ **Code de double usage** sur le code qui s’applique au produit actuel. (Vous avez défini ce code sur la page **Catégories de biens à double usage**.)

> [!NOTE]
>
> Le système effectue les contrôles à double usage suivants lorsqu’il génère une confirmation de vente :
>
> 1. La commande comprend-elle des produits à double usage ?
> 1. Si c’est le cas, le pays de destination exige-t-il des certificats de double usage ?
> 1. Si c’est le cas, existe-t-il un certificat pour chaque bien à double usage pour le pays de destination et ces certificats sont-ils valides pour les dates d’expédition confirmées ?
> 1. Si les réponses aux questions 1 et 2 sont « Oui » et la réponse à la question 3 est « Non », alors le système affiche un avertissement pour informer l’utilisateur qu’il manque des certificats à double usage pour un ou plusieurs biens à double usage dans le bon de commande. L’utilisateur devrait probablement obtenir les certificats requis et réessayer, mais pourrait à la place ignorer l’avertissement et procéder à la confirmation de vente s’il le souhaite.

## <a name="set-up-dual-use-certificates"></a>Paramétrer des certificats de biens à double usage

Vous utilisez la page **Certificats de double usage** pour configurer et gérer les certificats à double usage requis pour chaque produit et pays. Vous pouvez suivre les détails de chaque certificat, tels que le pays et les dates de validité. Vous pouvez également définir des options pour spécifier où ces informations doivent être imprimées. Par exemple, les informations peuvent être imprimées sur la facture, le bon de livraison et/ou la commande client. Cette configuration est vérifiée lorsque vous créez une commande client.

1. Accédez à **Gestion des informations sur les produits \> Paramétrage \> Conformité des produits \> Produits à double usage \> Certificats de double usage**.
2. Sélectionnez un certificat existant à modifier ou sélectionnez **Nouveau** dans le volet Actions pour créer un nouveau certificat.
3. Définissez les valeurs suivantes pour le certificat sélectionné ou le nouveau certificat.

    | Champ | Description |
    |---|---|
    | numéro d’article | Sélectionnez le numéro d’article du bien à double usage auquel ce certificat s’applique. |
    | Pays/région | Le pays ou la région de destination où vous devez utiliser ce certificat. |
    | Numéro de certificat | Le numéro qui apparaît sur le certificat délivré au fournisseur ou au client. |
    | Effective | Sélectionnez la date de début de validité du certificat.|
    | Expiration | Sélectionnez la date de fin de validité du certificat. |
    | Imprimer sur la facture | Cochez cette case pour imprimer le numéro de certificat sur les factures adressées au pays spécifié pendant la plage de dates spécifiée. |
    | Imprimer sur le bon de livraison | Cochez cette case pour imprimer le numéro de certificat sur les bons de livraison adressés au pays spécifié pendant la plage de dates spécifiée. |
    | Imprimer sur la commande client | Cochez cette case pour imprimer le numéro de certificat sur les commandes client adressées au pays spécifié pendant la plage de dates spécifiée. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
