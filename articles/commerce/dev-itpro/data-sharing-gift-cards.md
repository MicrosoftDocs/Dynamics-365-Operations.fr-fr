---
title: Partage de données entre sociétés pour les cartes cadeaux
description: Cet article explique comment configurer Microsoft Dynamics 365 Commerce pour utiliser la fonctionnalité de partage de données de Dynamics 365 Finance dans les zones de données pour synchroniser les données des cartes-cadeaux.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: bc0df6c4aac72907e8523069e3f1ae100780dc3c
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473929"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Partage de données entre sociétés pour les cartes cadeaux

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer Microsoft Dynamics 365 Commerce pour utiliser la fonctionnalité de partage de données de Dynamics 365 Finance pour synchroniser les données des cartes-cadeaux. La fonctionnalité de partage d’enregistrements de données peut ensuite être utilisée pour partager des données inter-entreprises entre deux zones de données. De cette manière, la table de cadeaux internes Commerce peut partager des données entre deux entités de l’entreprise. Pour plus d’informations sur le partage de données inter-entreprises dans Dynamics 365 Finance, voir [Partage de données inter-entreprises](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Termes clés

| Terme | Description |
|---|---|
| Société | Entité juridique dans l’environnement Dynamics 365 Finance. |
| Carte cadeau | Produit de carte cadeau interne Dynamics 365 Commerce. |

## <a name="prerequisites"></a>Logiciels requis

Les utilisateurs doivent configurer leur environnement pour le partage de données inter-entreprises comme décrit dans [Partage de données inter-entreprises](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

**RetailGiftCardTable** doit avoir le champ **DataSharingType** défini sur **Dupliquer** pour activer le partage d’enregistrements en double (DRS) pour la table des cartes-cadeaux. Pour plus d’informations, voir [Partage de données inter-entreprises pour les développeurs](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Configurer le partage de données inter-entreprises pour les cartes cadeaux

Pour configurer le partage de données inter-entreprises pour les cartes cadeaux, procédez comme suit.

1. Dans Commerce headquarters, accédez à **Administration système \> Paramétrage \> Configurer le partage de données inter-sociétés**.
1. Dans le volet Action, sélectionnez **Nouveau** pour ajouter un enregistrement de partage de données.
1. Dans le champ **Nom**, saisissez un nom pour l’enregistrement de partage de données (par exemple, **Cartes cadeaux**).
1. Dans la section **Tables et champs à partager**, sélectionnez **Ajouter**.
1. Dans la boîte de dialogue **Partager une nouvelle table**, dans le champ **Nom de la table**, entrez **RETAILGIFTCARDTABLE** (table descartes-cadeaux de détail). Le champ **Étiquette de table** doit être automatiquement défini sur **Table de cartes cadeaux**.
1. Veillez à ce que les cases **Enregistrer les données par entreprise**, **A un index unique**, et **Pas encore partagé** soient toutes cochées. La sélection de ces cases à cocher déclenche des validations liées à la fonctionnalité de partage de données.
1. Sélectionnez **Ajouter une table**. L’enregistrement **Table de cartes-cadeaux (RetailGiftCardTable)** devrait maintenant apparaître sous **Tables et champs à partager**. Sélectionnez le symbole caret (^) pour afficher tous les champs de table qui sont automatiquement associés à la table pour le partage.
1. Dans la section **Sociétés qui partagent les enregistrements dans ces tables**, sélectionnez **Ajouter** pour ajouter une entreprise avec laquelle partager des données.
1. Dans la ligne sous **Entreprise**, sélectionnez une entreprise dans la liste déroulante.
1. Dans le champ **Nom**, entrez le nom de l’entreprise.
1. Répétez les étapes 8 à 10 pour ajouter d’autres lignes d’entreprise.
1. Lorsque vous avez terminé d’ajouter des lignes d’entreprise, dans le volet Actions, sélectionnez **Activer**.
1. Vous recevez un message d’avertissement indiquant : « Il est recommandé d’effectuer cette action uniquement en dehors des heures de bureau. Toute opération de transaction simultanée échouera pour les tables de la stratégie. Voulez-vous continuer ? » Sélectionnez **Oui** pour confirmer.
1. Vous recevez un message d’avertissement indiquant « Souhaitez-vous copier maintenant toutes les données existantes entre toutes les sociétés partagées ? » Sélectionnez **Oui** pour confirmer.

Une fois que vous avez accepté les deux messages, les tables commenceront à copier les données dans les entreprises configurées. Les soldes qui se produisent avec une carte-cadeau d’entreprise seront alors visibles pour l’autre entreprise.

## <a name="additional-resources"></a>Ressources supplémentaires

[FAQ Paiements](payments-retail.md)

[Module Validation](../add-checkout-module.md)

[Module Paiement](../payment-module.md)
