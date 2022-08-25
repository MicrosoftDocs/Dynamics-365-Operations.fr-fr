---
title: API de tarification commerciale
description: Cet article décrit diverses API de tarification fournies par le moteur de tarification Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294116"
---
# <a name="commerce-pricing-apis"></a>API de tarification commerciale

[!include [banner](../includes/banner.md)]

Cet article décrit diverses API de tarification fournies par le moteur de tarification Microsoft Dynamics 365 Commerce.

Le moteur de tarification Dynamics 365 Commerce fournit les API suivantes au serveur de vente au détail qui peuvent être utilisées par des applications externes pour prendre en charge divers scénarios de tarification :

- **GetActivePrices** – Cette API obtient le prix calculé d’un produit, y compris les remises simples.
- **CalculateSalesDocument** – Cette API calcule les prix et les remises pour les produits à des quantités données s’ils sont achetés ensemble.
- **GetAvailablePromotions** - Cette API obtient des remises applicables pour les produits dans le panier. 
- **AddCoupons** – Cette API ajoute des coupons à un panier.
- **RemoveCoupons** – Cette API supprime les coupons d’un panier.

Pour plus d’informations sur l’utilisation des API au serveur de vente au détail dans des applications externes, consultez [Utiliser les API au serveur de vente au détail dans des applications externes](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

L'API *GetActivePrices* a été introduite dans la version 10.0.4 de Commerce. Cette API obtient le prix calculé d’un produit, y compris les remises simples. Elle ne calcule pas les remises multilignes et suppose que chaque produit d’une demande d’API a une quantité de 1. Cette API peut également prendre une liste de produits en entrée et consulter le prix de produits individuels en masse.

L'API *GetActivePrices* prend en charge les rôles Commerce **Employé**, **Client**, **Anonyme**, et **Application**.

Le principal cas d’utilisation des API *GetActivePrices* est la page de détails du produit (PDP), où les détaillants souhaitent présenter le meilleur prix pour un produit, y compris les remises effectives.

Le tableau suivant montre les paramètres d’entrée pour l'API *GetActivePrices*.

| Name                                    | Sous-nom | Type | Obligatoire/facultatif | Description |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | ProjectionDomain | Requis | |
|                                         | ChannelId | long | Requis | |
|                                         | CatalogId | long | Requis | |
| productIds                              | | IEnumerable\<long\> | Requis | La liste des produits pour lesquels calculer les prix. |
| activeDate                              | | DateTimeOffset | Requis | La date à laquelle les prix sont calculés. |
| customerId                              | | chaîne | Facultatif | Numéro du compte client. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Facultatif | Les niveaux d’affiliation et de fidélité |
|                                         | AffiliationId | long | Requis | L'ID d'affiliation. |
|                                         | LoyaltyTierId | long | Facultatif | L'ID du niveau de fidélité. |
| includeSimpleDiscountsInContextualPrice | | bool | Facultatif | Définissez ce paramètre sur **vrai** pour inclure des remises simples dans le calcul du prix. La valeur par défaut est **false**. |
| includeVariantPriceRange                | | bool | Facultatif | Définissez ce paramètre sur **vrai** pour obtenir les prix minimum et maximum parmi toutes les variantes d’un produit maître. La valeur par défaut est **false**. |
| includeAttainablePricesAndDiscounts     | | bool | Facultatif | Définissez ce paramètre sur **vrai** pour obtenir des prix et des remises accessibles. La valeur par défaut est **false**. |

**Demande de corps d'échantillon**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Corps de réponse d'échantillon**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

L'API *CalculateSalesDocument* a été introduite dans la version 10.0.25 de Commerce. Cette API calcule les prix et les remises pour les produits à des quantités données s’ils sont achetés ensemble dans une commande. Le calcul des prix derrière l'API *CalculateSalesDocument* prend en compte à la fois les remises sur une seule ligne et les remises sur plusieurs lignes.

Le principal cas d’utilisation pour l'API *CalculateSalesDocument* est le calcul de prix dans des scénarios où le contexte du panier complet ne persiste pas (comme les devis de vente). Les scénarios e-commerce en point de vente (PDV) et Commerce peuvent également bénéficier de ce cas d’utilisation. Un prix total inférieur lorsque les articles du panier sont calculés comme un ensemble (par exemple, pour des offres groupées discrètes, des produits liés ou recommandés, ou des produits qui ont déjà été ajoutés au panier) peut persuader les clients d’ajouter des produits au panier.

Le modèle de données pour la demande et la réponse de l'API *CalculateSalesDocument* est **Panier**. Cependant, dans le contexte de cette API, le modèle de données est nommé **SalesDocument**. Étant donné que la plupart des propriétés sont facultatives et que seules quelques-unes d’entre elles affectent le calcul du prix, seuls les champs liés au prix sont affichés dans le tableau suivant. Nous vous déconseillons d’impliquer d’autres champs dans la demande d’API.

La portée de l'API *CalculateSalesDocument* n’est que le calcul des prix et des remises. Les taxes et les frais ne sont pas impliqués.

Le tableau suivant montre les paramètres d’entrée à l’intérieur de l’objet nommé **salesDocument**.

| Name             | Sous-nom | Type | Obligatoire/facultatif | Description |
|------------------|----------|------|-------------------|-------------|
| ID               | | chaîne | Requis | L'identificateur du document des ventes. |
| CartLines        | | IList\<CartLine\> | Facultatif | La liste des lignes pour lesquelles calculer les prix et les remises. |
|                  | ID produit | long | Requis dans l'étendue de CartLine | L'ID d'enregistrement de produit. |
|                  | ItemId | chaîne | Facultatif | L'identificateur de l'article. Si une valeur est fournie, elle doit correspondre à la valeur du paramètre **ProductId**. |
|                  | InventoryDimensionId | chaîne | Facultatif | L'identificateur de la dimension de stock. Si une valeur est fournie, la combinaison des valeurs **ItemId** et **InventoryDimensionId** doivent correspondre à la valeur du paramètre **ProductId**. |
|                  | Quantity | decimal | Requis dans l'étendue de CartLine | La quantité du produit. |
|                  | UnitOfMeasureSymbol | chaîne | Facultatif | L'unité du produit. Par défaut, si aucune valeur n’est fournie, l’API utilise l’unité de vente du produit. |
| CustomerId       | | chaîne | Facultatif | Numéro du compte client. |
| LoyaltyCardId    | | chaîne | Facultatif | L'identificateur de la carte de fidélité. Tout compte client associé à la carte de fidélité doit correspondre à la valeur du paramètre **CustomerId** (s’il est fourni). La carte de fidélité ne sera pas prise en compte si elle est introuvable ou si son statut est **Bloqué**. |
| AffiliationLines | | IList\<AffiliationLoyaltyTier\> | Facultatif | Les lignes du niveau d’affiliation de la fidélité. Si les valeurs **CustomerId** et/ou **LoyaltyCardId** sont fournies, les lignes de niveau d’affiliation de fidélité correspondantes seront fusionnées avec les lignes fournies dans la valeur **AffiliationLines**. |
|                  | AffiliationId | long | Requis dans l'étendue de AffiliationLoyaltyTier | L'ID d'enregistrement de l'affiliation. |
|                  | LoyaltyTierId | long | Requis dans l'étendue de AffiliationLoyaltyTier | L'ID de l'enregistrement du niveau de fidélité. |
|                  | AffiliationTypeValue | int | Requis dans l'étendue de AffiliationLoyaltyTier | Une valeur qui indique si la ligne d’affiliation est du type **General** (**0**) ou du type **Loyalty** (**1**). Si ce paramètre est réglé sur **0**, l’API prend la valeur **AffiliationId** comme identificateur et ignore la valeur **LoyaltyTierId**. Si c'est réglé sur **1**, l’API prend la valeur **LoyaltyTierId** comme identificateur et ignore la valeur **AffiliationId**. |
|                  | ReasonCodeLines | Relance\<ReasonCodeLine\> | Requis dans l'étendue de AffiliationLoyaltyTier | Lignes de code Reason. Ce paramètre n’a aucun effet sur le calcul du prix mais est requis dans le cadre de l'objet **AffiliationLoyaltyTier**. |
|                  | CustomerId | chaîne | Requis dans l'étendue de AffiliationLoyaltyTier | Numéro du compte client. |
| Coupons          | | IList\<Coupon\> | Facultatif | Les coupons qui ne sont pas applicables (inactifs, expirés ou introuvables) ne seront pas pris en compte dans le calcul du prix. |
|                  | Code | chaîne | Requis dans l'étendue de Coupon | Le code de coupon. |
|                  | CodeId | chaîne | Facultatif | L'identificateur du code de coupon. Si une valeur est fournie, elle doit correspondre à la valeur du paramètre **Code**. |
|                  | DiscountOfferId | chaîne | Facultatif | L’identificateur de la remise. Si une valeur est fournie, elle doit correspondre à la valeur du paramètre **Code**. |

**Corps de demande d'échantillon**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

L’objet cart entier est renvoyé comme corps de réponse. Pour vérifier les prix et les remises, vous devez vous concentrer sur les champs du tableau suivant.

| Name           | Sous-nom | Type | Description |
|----------------|----------|------|--------------|
| NetPrice       | | decimal | Le prix net de l'ensemble du document de vente avant application des remises. |
| DiscountAmount | | decimal | Le montant total de la remise de l'ensemble du document de vente. |
| TotalAmount    | | decimal | Le montant total de l'ensemble du document de vente. |
| CartLines      | | IList\<CartLine\> | Lignes calculées qui incluent les détails du prix et de la remise. |
|                | Prix | decimal | Le prix du produit à l'unité. |
|                | NetPrice | decimal | Le prix net de la ligne avant application des remises (= *Prix* &times; *Quantité*). |
|                | DiscountAmount | decimal | Le montant de la remise. |
|                | TotalAmount | decimal | Le résultat final de la tarification totale de la ligne. |
|                | PriceLines | IList\<PriceLine\> | Détails du prix, y compris la source du prix (prix de base, ajustement de prix ou accord commercial) et le montant. |
|                | DiscountLines | IList\<DiscountLine\> | Détails de la remise. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

Étant donné un panier comportant plusieurs lignes de panier, l'API *GetAvailablePromotions* renvoie toutes les remises applicables pour les lignes de panier. 

Le principal cas d’utilisation de l'API *GetAvailablePromotions* est la page du panier, où les détaillants souhaitent présenter les remises appliquées ou les coupons disponibles pour le panier actuel.

Le tableau suivant montre les paramètres d’entrée pour l'API *GetAvailablePromotions*.

| Name        | Type | Obligatoire/facultatif | Description |
|-------------|------|-------------------|-------------|
| clé         | chaîne | Requis | L'ID du panier. |
| cartLineIds | IEnumerable\<string\> | Facultatif | Définissez ce paramètre pour renvoyer les remises uniquement pour les lignes de panier sélectionnées. |

**Corps de réponse d'échantillon**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddCoupons

L'API *AddCoupons* prend en charge l’ajout d’une liste de coupons à un panier. Il renvoie l’objet panier après l’ajout des coupons.

Le tableau suivant montre les paramètres d’entrée pour l'API *AddCoupons*.

| Name                 | Type | Obligatoire/facultatif | Description |
|----------------------|------|-------------------|-------------|
| clé                  | chaîne | Requis | L'ID du panier. |
| couponCodes          | IEnumerable\<string\> | Requis | Les codes de coupon à ajouter au panier. |
| isLegacyDiscountCode | bool | Facultatif | Définissez ce paramètre sur **vrai** pour indiquer que le coupon est un code de remise hérité. La valeur par défaut est **false**. |

## <a name="removecoupons"></a>RemoveCoupons

L'API *RemoveCoupons* prend en charge la suppression d’une liste de coupons d’un panier. Elle renvoie l’objet panier après la suppression des coupons.

Le tableau suivant montre les paramètres d’entrée pour l'API *RemoveCoupons*.

| Name        | Type | Obligatoire/facultatif | Description |
|-------------|------|-------------------|-------------|
| clé         | chaîne | Requis | L'ID du panier. |
| couponCodes | IEnumerable\<string\> | Requis | Les codes de coupon à supprimer du panier. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
