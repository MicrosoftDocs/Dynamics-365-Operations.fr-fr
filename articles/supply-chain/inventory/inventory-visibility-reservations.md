---
title: Réservations Inventory Visibility
description: Cet article explique comment configurer la fonctionnalité de réservation pour créer des réservations, consommer des réservations et/ou annuler la réservation de quantités en stock spécifiées à l’aide de la visibilité des stocks.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762720"
---
# <a name="inventory-visibility-reservations"></a>Réservations Inventory Visibility

[!include [banner](../includes/banner.md)]

Cet article décrit un cas d’utilisation typique des réservations provisoires et explique comment les configurer dans Inventory Visibility. Il comprend des informations sur la façon de créer des réservations provisoires, de les compenser lors de la consommation physique et d’ajuster ou d’annuler la réservation de certaines quantités de stocks.

## <a name="sample-use-case-for-soft-reservation"></a>Exemple de cas d’utilisation pour la réservation provisoire

Les réservations provisoires aident les organisations à obtenir une source unique de vérité pour les stocks disponibles, en particulier pendant l’exécution des commandes. Cette fonctionnalité est utile dans les organisations qui réunissent les conditions suivantes :

- L’organisation dispose d’au moins deux systèmes différents qui prennent directement les commandes sortantes.
- L’organisation est très stricte et souhaite éviter la double réservation des stocks de produits, ce qui peut se produire si plusieurs systèmes sont capables de surréserver la dernière pièce en stock. Cette situation est évitée si tous les systèmes de commande peuvent effectuer des appels d’API de réservation provisoire instantanés vers Inventory Visibility, qui fournit une source unique de vérité pour la disponibilité des stocks.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title="Réservation provisoire Inventory Visibility" width="720" />](media/inventory-visibility-soft-reservation.png)

L’illustration précédente montre le fonctionnement de la réservation provisoire et met en évidence les opérations suivantes :

- Votre niveau de stocks initial est synchronisé avec Visibility des stocks de Microsoft Dynamics 365 Supply Chain Management.
- Les réservations provisoires sont validées depuis chacun des canaux ou systèmes de commande vers Inventory Visibility. Le complément Inventory Visibility valide la disponibilité des stocks et essaie d’effectuer une réservation provisoire. Si la réservation provisoire réussit, Inventory Visibility ajoute à la quantité réservée provisoirement, déduit de la quantité disponible pour réservation (AFR) et répond avec un ID de réservation provisoire.
- À ce stade, la quantité de stocks physiques reste la même.
- Vous pouvez ensuite synchroniser des commandes réservées provisoirement individuelles ou agrégées (lignes de commande) dans Supply Chain Management pour effectuer des réservations fermes et les envoyer à l’entrepôt ou mettre à jour la quantité de stocks finale.
- Vous pouvez configurer le système pour [compenser les réservations provisoires](#offset-scm) lorsque les stocks physiques sont mis à jour dans Supply Chain Management.

Les réservations provisoires sont généralement créées, consommées et annulées en utilisant les appels d’API vers le service Inventory Visibility.

> [!NOTE]
> Vous avez la possibilité de configurer Supply Chain Management (et d’autres systèmes tiers) pour compenser automatiquement la quantité réservée en utilisant Inventory Visibility. La quantité compensée est supprimée des enregistrements de réservation dans la visibilité des stocks.
>
> Par défaut, la fonction de compensation est automatiquement activée lorsque vous activez la fonction de réservation provisoire.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Activer et configurer la fonction de réservation

Pour activer la fonctionnalité de réservation, procédez comme suit.

1. Connectez-vous à Power Apps et ouvrez **Inventory Visibility**.
1. Ouvrez la page **Configuration**.
1. Sur l’onglet **Gestion des fonctionnalités**, activez la fonctionnalité *OnHandReservation*.
1. Connectez-vous à votre environnement Supply Chain Management.
1. Accédez à l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez la fonction *Intégration de la visibilité du stock avec compensation de réservation* (nécessite la version 10.0.22 ou ultérieure).
1. Accédez à **Gestion des stocks \> Paramétrage \> Paramètres d’intégration de la visibilité du stock**, ouvrez l’onglet **Compensation de réservation** et effectuez les réglages suivants :

    - **Activer la compensation des réservations** : définissez-le sur *Oui* pour activer cette fonctionnalité.
    - **Modificateur de la compensation des réservations** : sélectionnez le statut de la transaction de stock qui compensera les réservations effectuées dans Inventory Visibility. Ce paramètre détermine l’étape de traitement de la commande qui déclenche les compensations. L’étape est tracée par le statut du mouvement de stock de la commande. Sélectionnez l’une des valeurs suivantes :

        - *En commande* : les commandes dont le statut est défini sur *En commande* envoient une demande de compensation lors de leur création. La quantité de compensation sera la quantité de la (ligne de) commande créée.
        - *Réserver* : les commandes dont le statut est défini sur *Réserver* envoient une demande de compensation lorsqu’elles sont soit en ordre réservé, soit physiquement réservées. Lorsque vous compensé au statut *Réserver*, la commande envoie une demande de compensation à tout nouveau statut de stock qui se rapproche le plus du prélèvement réservé (par exemple, prélèvement, bon de livraison enregistré ou facturé). Ce problème se produit même si vous ignorez la réservation dans Supply Chain Management et passez à un autre statut de stock (par exemple, si vous passez de la libération dans l’entrepôt au prélèvement et à l’emballage). La demande n’est déclenchée qu’une seule fois. Si elle a été déclenchée lors du prélèvement, elle ne duplique pas la compensation lorsqu’un bon de livraison est validé. La quantité de compensation est identique à la quantité du statut de la transaction de stock au moment du déclenchement de la compensation (en d’autres termes, le statut *Commandé réservé*/*Réserve physique* ou un autre statut ultérieur, sur la ligne de commande correspondante).

1. Reconnectez-vous à l’application Inventory Visibility, accédez à la page **Configuration**, puis, dans l’onglet **Réservation provisoire**, passez en revue la hiérarchie de réservations provisoires par défaut. Ajoutez de nouvelles dimensions à la hiérarchie si nécessaire.
1. Dans la section **Définir un mappage de réservation provisoire**, affichez les paramètres par défaut. Par défaut, les quantités de stocks réservées provisoirement sont enregistrées par rapport à la mesure physique `softreservephysical` de la source de données `iv`. La mesure calculée *Disponible pour réservation* est mappée à `availabletoreserve`. Pour mettre à jour la mesure calculée `availabletoreserve`, accédez à la page **Configuration**, puis, dans l’onglet **Mesure calculée**, développez et modifiez la mesure calculée.

Pour plus d’informations, voir [Configurer la visibilité des stocks](inventory-visibility-configuration.md).

> [!NOTE]
> La hiérarchie de réservation décrit la séquence de dimensions qui doit être spécifiée lors des réservations. Elle fonctionne de la même manière que la hiérarchie d’index pour les requêtes disponibles même si elle est utilisée indépendamment afin que les utilisateurs puissent spécifier les détails de la dimension pour effectuer des réservations plus précises.
>
> Votre hiérarchie de réservations provisoires doit contenir `SiteId` et `LocationId` en tant que composants, car ils construisent la configuration de la partition d’Inventory Visibility.

Pour plus d’informations sur la configuration des réservations, consultez la rubrique [Configuration des réservations](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Utiliser la fonction de réservation dans la visibilité des stocks

Lorsque vous appelez l’API de réservation, le système marque la réservation des marchandises et des quantités spécifiées.

Voici un exemple de scénario et un exemple de corps de requête d’API. La société Contoso commercialise le produit D0002 (Armoire) sur son site d’e-commerce. Un client commande une petite armoire rouge sur le site web. Contoso décide d’exécuter cette commande en utilisant les dimensions suivantes :

- ID organisation = usmf
- Site = 1
- Entrepôt = 11
- Produit = D0002
- Couleur = rouge
- Taille = petit modèle

Contoso a déjà configuré une connexion d’API vers Inventory Visibility à partir de son propre système d’e-commerce. Lorsque la commande est reçue, le système déclenche instantanément un appel d’API pour effectuer une réservation provisoire de l’armoire dans Inventory Visibility.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Créer des réservations provisoires en utilisant l’API de réservation

Les réservations se font dans le service de visibilité des stocks en soumettant une requête POST à l’URL du service, telle que `/api/environment/{environmentId}/onhand/reserve`.

Pour une réservation, le corps de la requête doit contenir un ID d’organisation, un ID de produit, des quantités réservées et des dimensions.

Lorsque vous appelez l’API de réservation, vous pouvez contrôler la validation de la réservation en spécifiant le paramètre booléen `ifCheckAvailForReserv` dans le corps de la requête. Une valeur `True` signifie que la validation est requise, alors qu’une valeur `False` signifie que la validation n’est pas requise. La valeur par défaut est `True`.

Si vous souhaitez annuler une réservation ou annuler la réservation de quantités de stock spécifiées, définissez la quantité sur une valeur négative et définissez le paramètre `ifCheckAvailForReserv` sur `False` pour ignorer la validation.

Voici un exemple du corps de la demande qui fait référence à la commande client dans le contexte précédent.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

Une demande de réservation provisoire réussie renvoie un *ID de réservation provisoire* pour chaque enregistrement de réservation. L’ID de réservation provisoire n’est pas un identificateur unique pour un enregistrement de réservation provisoire individuel, mais une combinaison de l’ID produit et des valeurs de dimension associées à la demande de réservation provisoire. Vous pouvez enregistrer l’ID de réservation provisoire sur la ligne de commande lorsque vous synchronisez les commandes réservées avec succès avec Supply Chain Management ou un autre système ERP pour la compensation.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a>Réservations provisoires de compensation dans Supply Chain Management

Vous pouvez compenser une quantité réservée provisoirement après que la quantité d’une commande est physiquement déduite dans Supply Chain Management ou un autre système ERP. Inventory Visibility offre une intégration de compensation des réservations provisoires prête à l’emploi avec Supply Chain Management.

Pour compenser une réservation provisoire, procédez comme suit.

1. Connectez-vous à Supply Chain Management.
1. Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Recréez la commande client externe et ajoutez une ligne de vente qui utilise exactement les mêmes valeurs d’ID produit, d’organisation, de site, d’entrepôt et de dimensions.
1. Sur le raccourci **Lignes de commande client**, sélectionnez la ligne de commande que vous venez de entrer, puis sélectionnez **Stock \> ID de Réservation** dans la barre d’outils.
1. Suivez l’une des procédures suivantes :

    - Copiez l’ID de réservation provisoire dans votre réponse de demande de réservation provisoire et collez-le dans le champ **ID de réservation**.
    - Laissez le champ **ID de réservation** vide mais cochez la case **Compensation automatique du service d’inventaire**. Le système détermine automatiquement le produit et les dimensions de produit à compenser, en fonction de l’ID article et des valeurs de dimension saisies sur la ligne sélectionnée.

1. Cliquez sur **OK**.
1. Alors que la même ligne de commande est toujours sélectionnée, réservez physiquement la quantité commandée en sélectionnant **Inventaire \> Réservation** dans la barre d’outils du raccourci **Lignes de commande client**.
1. Si vous aviez précédemment défini le champ **Modificateur de compensation de réservation** sur *Réservé*, la compensation est déclenchée lorsque la ligne de commande est définie sur le statut *Réserve physique* ou *Réserver les articles commandés*. Un traitement par lots s’exécute une fois par minute pour synchroniser les demandes de compensation de Supply Chain Management vers Inventory Visibility.

> [!NOTE]
> Pour les statuts de transaction qui incluent un modificateur de compensation de réserve spécifié, la mise à jour de la transaction compense l’enregistrement de réservation correspondant lorsque toutes les conditions suivantes sont remplies :
>
> - L’ID de réservation sur la transaction de stock correspond à l’ID de réservation de l’enregistrement de réservation dans Inventory Visibility.
> - Les dimensions de la transaction de stock correspondent aux dimensions de l’enregistrement de réservation dans Inventory Visibility.
> - Les modifications du statut du mouvement de stock déclenchent des compensations pour les réservations lorsque le statut du mouvement de stock reflète le fait qu’un processus de commande a été terminé ou ignoré.

Les quantités compensées suivent les quantités de stocks spécifiées sur les transactions de stock appropriées. Une compensation ne prend effet que si la quantité réservée reste dans Inventory Visibility.

### <a name="cancel-or-revert-a-soft-reservation"></a>Annuler ou rétablir une réservation provisoire

Si une ligne de commande d’origine est annulée ou supprimée et que vous devez rétablir la réservation provisoire correspondante, validez une quantité négative contenant exactement les mêmes informations dans le corps de votre requête API.
