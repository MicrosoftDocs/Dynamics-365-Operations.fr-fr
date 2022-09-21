---
title: Paramètres de tarification
description: Cet article décrit les différents paramètres de gestion des prix et des remises dans Microsoft Dynamics 365 Commerce headquarters.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-11
ms.openlocfilehash: 79130e0ef285d6bd5e544f2d6a6368c0393fa7fa
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474040"
---
# <a name="pricing-settings"></a>Paramètres de tarification

[!include [banner](../includes/banner.md)]

Cet article décrit les différents paramètres de gestion des prix et des remises dans Microsoft Dynamics 365 Commerce headquarters. Ces paramètres permettent aux organisations de définir le comportement de tarification dans leur solution Commerce pour répondre à des besoins commerciaux spécifiques.

## <a name="company-level-pricing-settings"></a>Paramètres de tarification au niveau de l’entreprise

La plupart des paramètres de tarification sont au niveau de l’entreprise et peuvent être trouvés sur **Paramètres Commerce \> Prix et remises** dans Commerce headquarters.

### <a name="best-price-and-compound-concurrency-control-model"></a>Modèle de contrôle d'accès concurrentiel de la remise au meilleur prix et cumulée

Le paramètre **Modèle de contrôle d’accès concurrentiel de la remise au meilleur prix et cumulée** détermine comment le moteur de tarification traite plusieurs remises dans le mode de concurrence **meilleur prix** ou **cumulé**. 

Si le paramètre est réglé sur **Meilleur prix et composé dans la priorité, ne jamais composer dans plusieurs priorités**, toutes les remises **cumulées** qui ont la même priorité de prix sont composées. Le résultat cumulé est alors en concurrence avec toute remise au **meilleur prix** qui ont la même priorité de tarification, le meilleur prix est appliqué et toutes les remises qui ont une priorité de tarification inférieure sont ignorées.

Si le paramètre est réglé sur **Meilleur prix uniquement dans la priorité, toujours composer dans plusieurs priorités**, toute remise **cumulée** sont traitées comme remises au **meilleur prix**. Au sein d’une priorité de tarification, une seule remise l’emporte. Si cette remise unique est une remise au **meilleur prix** ou **cumulée**, elle est composée par toutes les remises supplémentaires au **meilleur prix** ou **cumulées** avec une priorité de tarification inférieure.

### <a name="discount-compound-behavior"></a>Comportement de remise cumulée

Le paramètre **Comportement de remise cumulée** détermine comment le moteur de tarification calcule plusieurs remises cumulées.

Si le paramètre est réglé sur **Cumulé**, une remise est appliquée au-dessus d’une autre de manière cumulative. Si définie sur **Composé sur le prix d’origine**, toutes les remises sont traitées indépendamment les unes des autres et appliquées au même prix d’origine.

Par exemple, vous souhaitez combiner des remises de 10 % et de 20 % pour un produit dont le prix d’origine est de 100 USD. Si vous réglez le paramètre **Comportement de remise cumulée** sur **Cumulé**, le prix final sera 72 USD (100 USD &times; 90 % &times; 80 %). Si vous le définissez sur **Composé sur le prix d’origine**, le prix final sera 70 USD (100 USD – 10 USD – 20 USD).

### <a name="enable-competition-between-exclusive-threshold-and-other-periodic-discounts"></a>Permettre la concurrence entre un seuil de remise exclusif et d’autres remises périodiques

Si le paramètre **Permettre la concurrence entre un seuil de remise exclusif et d’autres remises périodiques** est défini sur **Oui**, le moteur de tarification fait concurrence aux remises exclusives avec seuil et aux remises exclusives sans seuil. La priorité de tarification s’applique toujours. Le comportement des remises de seuil au **meilleur prix** et **cumulée** reste inchangé. En d’autres termes, ils ne concurrencent pas les remises sans seuil.

### <a name="manual-line-discount-and-system-discount"></a>Remise manuelle de ligne et remise système

Le paramètre **Remise manuelle de ligne et remise système** détermine comment le moteur de tarification applique une remise de ligne manuelle et une remise système à la même ligne. La remise manuelle sur la ligne peut s’ajouter à la remise système, ou elle peut remplacer la remise système. Lorsque la remise ligne manuelle et la remise système sont cumulées, la logique de calcul respecte le paramètre **Comportement de remise cumulée**. Une remise manuelle totale qui s’applique à l’ensemble de la commande ne respecte pas ce paramètre.

### <a name="keep-items-on-the-same-sales-line-for-discount-price-rounding"></a>Conserver les articles sur la même ligne de vente pour l'arrondi de prix après remise

Parfois, le montant d’une remise sur quantité ne peut pas être divisé de manière égale par la quantité éligible (par exemple, si le montant de la remise est de 10 USD pour trois unités achetées). Dans ces cas, le paramètre **Conserver les articles sur la même ligne de vente pour l’arrondi de prix après remise** détermine comment le moteur de tarification applique et distribue le montant de la remise. Si le paramètre est réglé sur **Oui**, le montant de la remise est appliqué dans son ensemble et n’est pas fractionné. S’il est défini sur **Non**, le montant de la remise est réparti sur la quantité admissible et arrondi. Par exemple, un montant de remise de 10 USD pour trois unités est divisé en 3,33 USD pour une unité, 3,33 USD pour la deuxième unité et 3,34 USD pour la troisième unité.

### <a name="apply-discounts-to-key-in-price-products"></a>Appliquer des remises aux produits dont le prix a été saisi

Le paramètre **Appliquer des remises aux produits dont le prix a été saisi** détermine si les remises peuvent être appliquées avec les « prix saisis » qui sont entrés dans le point de vente (PDV). Le paramètre **Entrer un prix** dans la configuration du produit détermine si et comment un produit prend en charge le prix de saisie.

### <a name="apply-discounts-to-price-overrides"></a>Appliquer les remises aux remplacements de prix

Le paramètre **Appliquer les remises aux remplacements de prix** détermine si les remises peuvent être appliquées avec les remplacements de prix.

### <a name="distribute-discounts-for-least-expensive-discounts"></a>Distribue les remises pour les remises les moins coûteuses

Pour les remises mixtes qui utilisent le type de calcul « le moins cher », le paramètre **Distribue les remises pour les remises les moins coûteuses** détermine si le moteur de tarification distribue la remise sur les lignes.

Si le paramètre est défini sur **Non**, la remise s’applique uniquement aux lignes les moins chères. Par exemple, pour une remise mixte « achetez-en 2, obtenez-en 1 gratuit », l’article le moins cher sera gratuit, et les deux autres articles resteront au prix fort. Dans ce cas, un client qui retourne les deux articles à prix plein recevra toujours le troisième article gratuitement. Ce scénario pourrait entraîner une perte pour le détaillant.

Si le paramètre est défini sur **Oui**, le moteur de tarification distribue la remise sur toutes les lignes applicables. Ce paramètre peut aider à réduire la perte sur les retours.

### <a name="manually-calculate-multi-line-prices-and-discounts"></a>Calculer manuellement les prix et remises multi-lignes

Le paramètre **Calculer manuellement les prix et remises multi-lignes** contrôle si le moteur de tarification utilise le calcul différé des prix et des remises pour l’application PDV et le canal du centre d’appels. Si le paramètre est réglé sur **Oui**, le moteur de tarification ne calcule pas immédiatement les remises multilignes (telles que les remises sur quantité, les remises de seuil et les remises mixtes) chaque fois qu’une commande client est créée ou modifiée dans l’application PDV ou le canal du centre d’appels.

> [!NOTE]
> Dans Commerce version 10.0.30 et versions antérieures, le paramètre **Calculer manuellement les prix et remises multi-lignes** ne contrôle que le canal du centre d’appels. Un paramètre **Calculer manuellement les prix et remises multi-lignes** distinct dans le profil de fonctionnalité contrôle le comportement de calcul du prix dans l’application PDV. Dans Commerce version 10.0.31, les deux paramètres sont regroupés en un seul paramètre au niveau de l’entreprise.

### <a name="retention-period-in-days"></a>Période de rétention en jours

Le paramètre **Période de rétention en jours** indique combien de jours après la date d’expiration (si une date d’expiration est définie) ou la date de désactivation (si aucune date d’expiration n’est définie) une remise doit être systématiquement supprimée. Si le paramètre est défini sur **0** (zéro), aucune suppression automatique ne se produit.

> [!NOTE]
> Dans Commerce version 10.0.30 et antérieure, ce paramètre est nommé **Nombre de jours après lesquels les remises arrivées à expiration doivent être supprimées**.

### <a name="coupon-bar-code"></a>Code-barres du coupon

Le paramètre **Code-barres du coupon** détermine quel code à barres spécifique est utilisé pour générer des codes à barres de coupon. Les utilisateurs peuvent sélectionner l’un des codes à barres prédéfinis qui sont configurés sur la page **Configuration du code à barres**. Pour plus d’informations sur les codes-barres et les masques de code-barres, voir [Configurer les codes-barres](set-up-bar-codes.md) et [Configurer des masques de code-barres](set-up-bar-code-masks.md).

### <a name="coupon-code-must-be-manually-applied-to-return-transactions"></a>Le code coupon doit être appliqué manuellement pour renvoyer des transactions

Le paramètre **Le code coupon doit être appliqué manuellement pour renvoyer des transactions** s’applique uniquement aux transactions de retour pour lesquelles aucun ticket de caisse n’est fourni. Définissez le paramètre sur **Non** si les codes de coupon doivent être automatiquement appliqués à la transaction. Définissez-le sur **Oui** si les codes de coupon doivent être ajoutés manuellement à la transaction.

### <a name="use-sales-agreements-set-up-for-the-organization"></a>Utiliser les contrats de vente configurés pour l’organisation

Pour les commandes interentreprises (B2B), si le paramètre **Utiliser les contrats de vente configurés pour l’organisation** est réglé sur **Oui**, le moteur de tarification utilise les accords de vente définis pour l’organisation dans la hiérarchie client de l’utilisateur pour déterminer le prix basé sur le contrat. Si le paramètre est défini sur **Non**, ou si la hiérarchie client n’est pas définie, le moteur de tarification recherche les contrats de vente définis pour l’utilisateur afin de déterminer le prix basé sur le contrat. Pour plus d’informations sur les hiérarchies de clients pour le commerce électronique B2B, voir [Gérer les partenaires commerciaux B2B à l’aide des hiérarchies de clients](b2b/partners-customer-hierarchies.md).

## <a name="channel-level-pricing-settings"></a>Paramètres de tarification au niveau du canal

Les paramètres suivants permettent aux organisations de contrôler le comportement de tarification dans des canaux de vente spécifiques.

### <a name="enable-order-price-control"></a>Activer le contrôle du prix de la commande

Le paramètre **Activer le contrôle du prix de la commande** est situé sur le raccourci **Général** de la page **Configuration du centre d’appels**. Le paramètre détermine si le moteur de tarification applique une restriction sur l’opération de remplacement de prix dans le canal du centre d’appels. Il fonctionne en collaboration avec le paramètre au niveau du produit **Autoriser l’ajustement du prix**.

Si le contrôle du prix de la commande est désactivé, tout utilisateur du centre d’appels peut apporter des modifications de prix sur les lignes de vente du canal du centre d’appels, que les produits correspondants autorisent ou non l’ajustement des prix.

Si le contrôle du prix de la commande est activé, seuls les produits dont le paramètre **Autoriser l’ajustement du prix** est défini sur **Oui** autorisent les remplacements de prix dans les commandes client du canal du centre d’appels, et un code de motif doit être fourni sur les lignes de vente correspondantes. Un utilisateur du centre d’appels ne peut modifier le prix de vente que jusqu’à la valeur **Pourcentage de majoration des coûts** qui est définie sur **Retail et Commerce \> Configuration du canal \> Configuration du centre d’appels\> Remplacer les autorisations**. Si un remplacement de prix dépasse ce pourcentage, l’utilisateur doit soumettre une demande, qui est ensuite traitée via un flux de travail Commerce prédéfini pour examen et approbation. Pour plus d’informations sur les flux de travail Commerce, consultez [Vue d’ensemble du système de flux de travail](/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system).

## <a name="product-level-pricing-settings"></a>Paramètres de tarification au niveau du produit

Les paramètres suivants appliquent les règles de tarification au niveau du produit et peuvent être trouvés sur la page **Configuration du produit** d’une organisation.

### <a name="allow-price-adjust"></a>Autoriser l'ajustement du prix

Si le paramètre **Autoriser l’ajustement du prix** est réglé sur **Oui**, un remplacement de prix peut être appliqué au produit dans les commandes client du canal du centre d’appels.

### <a name="key-in-price"></a>Entrer un prix

Le paramètre **Prix de saisie** détermine si un prix de saisie est obligatoire lorsqu’un produit est ajouté à une transaction de vente dans le PDV. Il définit également les restrictions de valeur de prix correspondantes.

### <a name="zero-price-valid"></a>Prix zéro valide

Le paramètre **Prix zéro valide** détermine si les prix de vente prédéfinis, calculés par le système ou ajustés manuellement pour un produit peuvent être 0 (zéro). Définissez le paramètre sur **Oui** si un prix de zéro est autorisé. Ce paramètre peut également être spécifié au niveau de la catégorie à partir de la hiérarchie de produit Commerce.

### <a name="prevent-all-discounts"></a>Empêcher toutes les remises

En réglant le paramètre **Empêcher toutes les remises** sur **Oui**, vous empêchez tous les types de remises (y compris les remises manuelles) d’être appliquées à un produit. Ce paramètre peut également être spécifié au niveau de la catégorie à partir de la hiérarchie de produit Commerce.

> [!NOTE]
> Ce paramètre ne limite pas l’opération de remplacement de prix, car elle définit le prix de base et n’est pas considérée comme une remise.

### <a name="prevent-manual-discounts"></a>Empêcher les remises manuelles

En réglant le paramètre **Empêcher toutes les remises manuelles** sur **Oui**, vous empêchez les remises manuelles de ligne ou de transaction d’être appliquées à un produit. Toutes les autres réductions peuvent toujours être appliquées. Ce paramètre peut également être spécifié au niveau de la catégorie à partir de la hiérarchie de produit Commerce.

> [!NOTE]
> Ce paramètre ne limite pas l’opération de remplacement de prix, car elle définit le prix de base et n’est pas considérée comme une remise.

### <a name="prevent-retail-discounts"></a>Empêcher les remises de vente au détail

Si le paramètre **Empêcher les remises au détail** est défini sur **Oui**, les remises **simple**, **quantité**, **seuil**, **mix and match** et **expédition** ne peuvent pas être appliquées à un produit. Toutes les autres remises (y compris les remises manuelles) peuvent toujours être appliquées.

### <a name="prevent-tender-based-discounts"></a>Empêcher les remises basées sur les appels d'offre

Si le paramètre **Empêcher les remises basées sur les appels d’offre** est défini sur **Oui**, une remise **basée sur l’offre** ne peut pas être appliquée à un produit. Toutes les autres remises (y compris les remises manuelles) peuvent toujours être appliquées.

Les détaillants choisissent souvent d’exclure certaines produits, tels que les nouveaux articles ou des articles en demande, des remises basées sur un article (comme des remises simples et des remises sur la quantité). Toutefois, ils pourraient toujours vouloir appliquer des remises basées sur l’offre si un client paie à l’aide du mode de paiement préféré. Pour obtenir ce résultat, les détaillants peuvent désactiver les paramètres **Empêcher toutes les remises** et **Empêcher les remises basées sur le mode de paiement** sur **Non**, et les paramètres **Empêcher les remises sur la vente au détail** et **Empêcher les remises manuelles** sur **Oui**.

## <a name="deprecated-or-removed-settings"></a>Paramètres déconseillés ou supprimés

Les paramètres de tarification suivants ont été supprimés ou sont sur le point d’être supprimés de Dynamics 365 Commerce.

| Paramètre | Motif de la suppression ou de l’abandon | Statut de l’abandon ou de la suppression |
|---------|-----------------------------------|-------------------------------|
| Chevauchement du traitement des remises | Nous avons fourni ce paramètre dans les paramètres Commerce pour contrôler la façon dont le moteur de tarification recherche et détermine la meilleure combinaison de remise à appliquer. L’option **Meilleure remise** impose toutes les combinaisons de remise possibles lors du calcul du prix. L’option **Meilleure performance** est une option optimisée qui utilise un algorithme heuristique avancé et une méthode classement de la valeur marginale pour hiérarchiser, évaluer et déterminer la meilleure combinaison de remises en temps opportun. L’option **Calcul équilibré** dans la base de code actuelle fonctionne exactement comme l’option **Meilleure performance**. Par conséquent, il s’agit essentiellement d’une option dupliquée. Pour aider à améliorer les performances, le moteur de tarification a été mis à jour afin qu’il n’utilise que l’option **Meilleure performance** comme option standard. Par conséquent, ce paramètre n’est plus applicable. | Obsolète dans la version 10.0.21 et sera supprimé en octobre 2022. |
| Autoriser les ajustements de prix à augmenter le prix du produit | Nous avons fourni ce paramètre pour contrôler si la fonction d’ajustement des prix permettait d’augmenter les prix du produit. Si le paramètre est désactivé, les organisations peuvent utiliser la fonction d’ajustement de prix uniquement pour définir le prix unitaire d’un produit en dessous de son prix de base et du prix de vente de l’accord commercial. Nous déconseillons ce paramètre, car la fonction d’ajustement des prix a été mise à jour pour prendre en charge les ajustements bidirectionnels (augmentation ou diminution) par défaut. | Obsolète dans la version 10.0.30 et sera supprimé en octobre 2023. |
| Activer l'état des prix pour le magasin de vente au détail | Nous avions ce paramètre pour contrôler si la fonction **Rapport de prix** est disponible pour une utilisation sur la page de configuration du magasin. Nous déconseillons ce paramètre, car la page de configuration du magasin a été mise à jour pour toujours fournir la fonction **Rapport de prix** en tant que fonction standard. | Obsolète dans la version 10.0.31 et sera supprimé en octobre 2023. |
| Utiliser la date du jour pour calculer les prix | Le moteur de tarification de Dynamics 365 Supply Chain Management prend en charge le calcul des prix en fonction de la date d’expédition demandée ou de la date de réception demandée ainsi que de la date actuelle. Le moteur de tarification de Commerce ne prend en charge que le calcul des prix en fonction de la date du jour. Pour les clients qui utilisent à la fois les fonctionnalités Supply Chain Management et Commerce, nous avons fourni ce paramètre et recommandé aux clients de toujours le définir sur **Oui** afin que les deux moteurs de tarification puissent fonctionner ensemble. Nous déconseillons ce paramètre, car il ne modifie pas fondamentalement le comportement de calcul et est redondant. | Obsolète dans la version 10.0.31 et sera supprimé en octobre 2023. |
| Prix maximal | Nous avons fourni ce paramètre dans le profil de fonctionnalité pour contrôler si seuls les produits dont le prix de vente est inférieur au prix maximum spécifié peuvent être vendus via le point de vente dans des magasins spécifiques. Nous avons déprécié ce paramètre en raison de la faible utilisation des fonctionnalités. | Obsolète dans la version 10.0.31 et sera supprimé en octobre 2023. |
| Appliquer les remises au prix unitaire | Ce paramètre était destiné à contrôler si les prix et les remises sont arrondis au niveau du prix unitaire ou au niveau de la ligne de vente lors du calcul du prix. Nous l’avons déprécié, car il n’est utilisé nulle part dans la base de code actuelle. | Obsolète dans la version 10.0.31 et sera supprimé en octobre 2023. |
| Calculer manuellement les remises pour plusieurs articles | Nous avons fourni ce paramètre pour contrôler si le moteur de tarification utilise un calcul de prix différé pour le canal du magasin de détail. Si le paramètre est réglé sur **Oui**, le moteur de tarification ne calcule pas immédiatement les remises multilignes (telles que les remises sur quantité, les remises de seuil et les remises mixtes) chaque fois qu’une commande client est créée ou modifiée dans l’application PDV. Nous avons décidé de consolider ce paramètre avec un paramètre similaire dans les paramètres de Commerce pour effectuer un contrôle omnicanal. | Obsolète dans la version 10.0.31 et sera supprimé en octobre 2023. |

Pour obtenir la liste complète des fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce, voir [Fonctionnalités supprimées ou obsolètes dans Dynamics 365 Commerce](get-started/removed-deprecated-features-commerce.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
