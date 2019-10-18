---
title: Acquérir les actifs via l'approvisionnement
description: Cette rubrique décrit comment paramétrer l'intégration entre Immobilisations et Comptabilité fournisseur pour créer automatiquement des immobilisations à partir de commandes fournisseur ou de factures fournisseur ou pour valider automatiquement des transactions d'acquisition et d'ajustement d'acquisition pour des immobilisations.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b07fdf6e5f4afa4f6df84138c809e402b7944dfb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177710"
---
# <a name="acquire-assets-through-procurement"></a>Acquérir les actifs via l'approvisionnement

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment paramétrer l'intégration entre Immobilisations et Comptabilité fournisseur pour créer automatiquement des immobilisations à partir de commandes fournisseur ou de factures fournisseur ou pour valider automatiquement des transactions d'acquisition et d'ajustement d'acquisition pour des immobilisations. Une ligne d'achat crée un actif, quelle que soit la quantité figurant sur la ligne d'achat. Si vous avez besoin de créer plusieurs immobilisations, vous devez créer plusieurs lignes d'achat.

 Vous devez choisir l'une des méthodes d'intégration suivantes disponibles pour Immobilisations et Achats et l'utiliser pour toutes les immobilisations :
-   Vous créez manuellement une immobilisation avant d'ajouter le numéro d'immobilisation à la ligne correspondante de la commande fournisseur ou de la facture fournisseur. Une transaction d'acquisition est validée automatiquement pour l'actif lorsque vous validez la facture fournisseur. Il s'agit de la méthode par défaut.
-   Vous créez manuellement une immobilisation avant d'ajouter le numéro d'immobilisation à la ligne correspondante de la commande fournisseur ou de la facture fournisseur. Aucune transaction d'acquisition n'est validée pour l'actif lorsque vous validez la facture fournisseur.
-   Une immobilisation est créée automatiquement lorsque vous validez un accusé de réception de marchandises ou une facture fournisseur dont la case à cocher Créer une nouvelle immobilisation est activée. Une transaction d'acquisition est validée automatiquement pour l'actif lorsque vous validez la facture fournisseur.
-   Une immobilisation est créée automatiquement lorsque vous validez un accusé de réception de marchandises ou une facture fournisseur dont la case à cocher Créer une nouvelle immobilisation est activée. Aucune transaction d'acquisition n'est validée pour l'actif lorsque vous validez la facture fournisseur.

Sélectionnez l'une des deux premières méthodes si vous préférez créer manuellement des immobilisations, puis affectez le numéro d'immobilisation à la commande fournisseur ou à la facture fournisseur. Sélectionnez l'une des deux dernières méthodes si vous souhaitez bénéficier d'une approche plus souple : vous pourrez ainsi créer des immobilisations manuellement ou créer une immobilisation automatiquement à partir d'informations d'immobilisation figurant dans les détails de la ligne. 

Que vous choisissiez la création manuelle d'immobilisations ou une approche plus souple, il est nécessaire de décider si une transaction d'acquisition peut être validée uniquement dans Immobilisations ou lors de la validation d'une facture fournisseur. Certaines organisations préfèrent que les utilisateurs créent manuellement des acquisitions et des transactions d'acquisitions dans Immobilisations à l'aide d'entrées de journal ou de propositions. 

Cette rubrique détaille chaque méthode.

## <a name="methods-for-manually-creating-fixed-assets"></a>Méthodes permettant de créer manuellement des immobilisations
Lorsque vous validez une facture fournisseur comportant un numéro d'immobilisation si l'option Autoriser l'acquisition d'actifs à partir d'Achats est sélectionnée sur la page Paramètres des immobilisations, l'acquisition est validée automatiquement et le statut de l'actif devient Ouvert(e). 

S'il est impossible de valider une acquisition, vous pouvez entrer manuellement une transaction d'acquisition dans Immobilisations ou utiliser une proposition d'acquisition dans le journal des immobilisations afin de créer plusieurs transactions d'acquisition simultanément.

> [!NOTE]                                                                                                                              
> Si Immobilisations est configuré pour limiter la validation des transactions d'acquisition à un groupe d'utilisateurs spécifique, vous devez appartenir à celui-ci pour pouvoir valider des transactions d'acquisition à partir de factures.

## <a name="methods-for-automatically-creating-fixed-assets"></a>Méthodes permettant de créer automatiquement des immobilisations
Lorsque vous validez un accusé de réception de marchandises dont l'option Créer une nouvelle immobilisation est sélectionnée pour une ligne, une immobilisation est créée avec le statut Pas encore acquise. Puis, lorsque vous validez une facture fournisseur avec une nouvelle immobilisation, une transaction d'acquisition est validée pour le nouvel actif et le statut de l'actif devient Ouvert(e), à condition qu'Immobilisations soit paramétré pour autoriser les acquisitions d'actif émanant d'Achats et que vous soyez membre d'un groupe d'utilisateurs autorisé à valider des transactions d'acquisition. 

Si l'option Nouvelle immobilisation ? n'était pas activée sur la ligne d'achat lorsque vous avez validé l'accusé de réception de marchandises, mais l'était lorsque vous avez validé la facture fournisseur, l'immobilisation est créée et prend le statut Ouvert(e), si Immobilisations accepte la création et l'acquisition. Un actif supplémentaire n'est pas créé lorsque vous avez validé une facture fournisseur créée lors de la validation de l'accusé de réception de marchandises.

### <a name="capitalization-threshold"></a>Seuil de capitalisation

Lorsque vous utilisez une méthode dans laquelle l'actif est créé et acquis automatiquement, vous pouvez paramétrer le système de manière à vérifier si le montant de l’achat de l'actif correspond à un seuil de capitalisation spécifié pour les amortissements des immobilisations. Dans ce cas, l'option Amortissement est activée dans les registres pour l'immobilisation lors de sa création à partir de la Comptabilité fournisseur. 

Un seuil de capitalisation est un montant en devise qui détermine si des immobilisations sont amorties lorsqu'elles atteignent la somme indiquée. Par exemple, si vous achetez une immobilisation et si le montant d'achat est inférieur au seuil de capitalisation, l'immobilisation n'est pas conçue pour s'amortir ; si le montant d'achat atteint ou dépasse le seuil, l'immobilisation est conçue pour s'amortir. 

Vous pouvez paramétrer le seuil de capitalisation sur la page Groupes d'immobilisations.

## <a name="scenario"></a>Scénario
Le scénario suivant décrit un cycle complet d'un intégration d'Immobilisations et d'Achats, ainsi qu'un exemple de paramétrage et l'utilisation de propositions d'acquisition. 

Dans ce scénario, le système est paramétré comme suit :

-   Des actifs sont créés automatiquement lors de la validation d'accusés de réception de marchandises ou de factures fournisseur, mais Immobilisations est paramétré pour empêcher la validation de transactions d'acquisition à partir d'Achats.
-   Les comptes sont spécifiés dans le champ Type de compte pour les comptes de type de réception et émission d'immobilisations dans la page Groupes d'articles.
-   Le seuil de capitalisation du groupe ordinateurs (COMP) s'élève à 1 500 euros.
-   Votre tâche consiste à entrer une commande fournisseur pour un nouvel ordinateur portable destiné à un employé, à valider cette commande fournisseur, à vérifier que l'employé des expéditions valide un accusé de réception de marchandises, à valider la facture fournisseur et à vérifier que le comptable met à jour le statut de l'actif de l'ordinateur portable sur Ouvert(e).

Pour commencer, accédez à la page Commande fournisseur afin d'entrer des détails sur l'ordinateur portable dont le prix est de 1 600. Vous sélectionnez l'option Nouvelle immobilisation ? sur l'organisateur Immobilisations des lignes de la commande fournisseur, sélectionnez COMP comme groupe d'immobilisations, puis enregistrez la commande fournisseur. 

À la réception de l'ordinateur portable, un employé des expéditions entre et valide un accusé de réception de marchandises afin d'enregistrer l'opération. L'actif de l'ordinateur portable est créé avec le statut Pas encore acquise. Le montant dépasse le seuil de capitalisation. Par conséquent, l'option Amortissement est activée dans les registres pour l'actif de l'ordinateur portable. Les transactions suivantes ont eu lieu.

| Description                               | Compte             | Débit    | Crédit   |
|-------------------------------------------|---------------------|----------|----------|
| Achat, achats de l'accusé de réception de marchandises        | Réceptions non facturées | 1 600,00 |          |
| Achat, contrepartie des achats de l'accusé de réception de marchandises | Achats cumulés   |          | 1 600,00 |

Vous validez ensuite la facture fournisseur de l'ordinateur portable. Le statut de l'ordinateur portable est inchangé car Immobilisations est paramétré pour empêcher la validation d'une transaction d'acquisition d'actif au moment de la validation d'une facture fournisseur. L'option Créer une nouvelle immobilisation était sélectionnée lors de la validation de la facture fournisseur. Par conséquent, le compte de type réception d'immobilisations a été utilisé. Le compte Sortie d'immobilisations n'a pas été utilisé, car aucune acquisition n'a été validée ; il le sera ultérieurement lorsque le comptable de votre organisation validera une transaction d'acquisition dans Immobilisations à l'aide de propositions d'acquisition. 

Les transactions suivantes ont eu lieu.

| Description                               | Compte             | Débit    | Crédit   |
|-------------------------------------------|---------------------|----------|----------|
| Achat, contrepartie des achats de l'accusé de réception de marchandises | Achats cumulés   | 1 600,00 |          |
| Solde fournisseur                            | Achats    |          | 1 600,00 |
| Achat, Réception d’immobilisation             | Dépenses d'ordinateur    | 1 600,00 |          |
| Achat, achats de l'accusé de réception de marchandises        | Réceptions non facturées |          | 1 600,00 |

Enfin, le comptable révise toutes les immobilisations présentant le statut Pas encore acquise. Par conséquent, le nouvel actif de l'ordinateur portable est traitée. Le comptable ouvre alors la page Proposition d'acquisition à partir des lignes de journal des immobilisations, puis crée des transactions d'acquisition pour tous les actifs auxquels une facture est associée mais qui présentent encore le statut Pas encore acquise. Lors de la validation du journal, le statut de l'actif de l'ordinateur devient Ouvert(e). Le compte Sortie d'immobilisations est crédité et le compte d'acquisition d'actif est débité. 

Voici des variations de ce scénario :

-   Si Immobilisations est paramétré pour autoriser la validation de transactions d'acquisition d'actif lors de la validation de factures fournisseur, le comptable n'a pas besoin d'utiliser des propositions d'acquisition dans Immobilisations car la transaction d'acquisition est créée. De plus, des comptes différents sont mis à jour lorsque vous validez la facture fournisseur. Au lieu de dépenses d'ordinateur, le compte de stock de réception d'immobilisations est débité, et deux transactions supplémentaires se produisent : le compte d'acquisition d'actif est débité et le compte de stock de sortie d'immobilisations est crédité.
-   Si l'option Créer une nouvelle immobilisation n'est pas sélectionnée lors de la validation de l'accusé de réception de marchandises, aucun actif n'est alors créé. Si vous sélectionnez l'option Créer une nouvelle immobilisation avant de valider la facture fournisseur, l'actif est créé avec le statut Pas encore acquise ou avec le statut Ouvert(e) si vous validez également des transactions d'acquisition avec les factures fournisseur.
-   Si l'ordinateur portable coûte 1 400 euros au lieu de 1 600 euros, le seuil de capitalisation n'est pas atteint. Par conséquent, l'immobilisation est créée et l'option Amortissement est désactivée.
-   Si un registre des factures est utilisé, vous utilisez la page Journal des approbations de facture, après la validation du registre, pour récupérer le N° document, lier la commande fournisseur à la facture fournisseur, sélectionner l'option Créer une nouvelle immobilisation, puis valider la facture fournisseur. Si vous êtes membre d'un groupe d'utilisateurs qui peut créer des transactions d'acquisition, l'acquisition est créée et l'actif présente le statut Ouvert(e).
-   En cas de réception d'une quantité partielle, aucune acquisition d'actif n'est créée pour la première facture fournisseur en raison des restrictions du groupe d'utilisateurs. Vous ne pouvez valider une acquisition pour la seconde facture fournisseur qui complète la quantité commandée que si une transaction d'acquisition a été entrée pour la première facture fournisseur et si vous êtes membre d'un groupe d'utilisateurs autorisé à valider des acquisitions.


Pour plus d'informations, voir [Intégration des immobilisations](fixed-asset-integration.md).



