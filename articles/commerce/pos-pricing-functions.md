---
title: Fonctions de tarification dans le PDV
description: Cet article décrit diverses fonctions de prix et de remise dans l'application point de vente (PDV) de Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-14
ms.openlocfilehash: 210798ac192ee251594ec8ff9d23dab31ec2043e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473685"
---
# <a name="pricing-functions-in-pos"></a>Fonctions de tarification dans le PDV

[!include [banner](includes/banner.md)]

Cet article décrit diverses fonctions de prix et de remise dans l'application point de vente (PDV) de Microsoft Dynamics 365 Commerce.

L'application PDV de Dynamics 365 Commerce fournit des fonctionnalités riches qui permettent aux travailleurs de première ligne d’effectuer des opérations store commerce. Le tableau suivant présente les fonctions de prix et de remise actuellement disponibles dans l’application.

| Fonction                       | Opérations PDV |
|--------------------------------|----------------|
| Afficher les prix                    | [Vérification de prix](#price-check) |
| Afficher les remises                 | [Afficher toutes les remises](#view-all-discounts)<br>[Afficher les remises disponibles](#view-available-discounts) |
| Substituer les prix                | [Remplacement de prix](#price-override) |
| Appliquer ou supprimer des remises      | [Montant de la remise ligne](#line-discount-amount)<br>[Pourcentage de la remise ligne](#line-discount-percent)<br>[Montant de remise totale](#total-discount-amount)<br>[Pourcentage de remise totale](#total-discount-percent)<br>[Supprimer les remises système de la transaction](#remove-system-discounts-from-transaction)<br>[Réappliquer les remises système](#reapply-system-discounts) |
| Appliquer ou supprimer des coupons        | [Ajouter un code coupon](#add-coupon-code)<br>[Supprimer le code coupon](#remove-coupon-code) |
| Calculer les prix et les remises | [Recalculer](#recalculate) |

Pour plus d’informations sur la façon dont les opérations précédentes peuvent être configurées dans l’application PDV et si elles prennent en charge le mode hors connexion, voir [Opérations de point de vente (PDV) en ligne et hors connexion](pos-operations.md).

## <a name="price-check"></a>Vérification de prix

L'opération de **Vérification du prix** permet aux utilisateurs du PDV de rechercher des prix préconfigurés pour un produit spécifique.

## <a name="view-all-discounts"></a>Afficher toutes les remises

L'opération **Voir toutes les remises** permet aux utilisateurs du PDV de rechercher toutes les promotions effectives actuellement en cours dans le canal du magasin. Plus précisément, cette opération répertorie toutes les remises qui correspondent à l’une des conditions suivantes :

- Le groupe de prix de la remise correspond au groupe de prix du magasin.
- Le groupe de prix de la remise est associé à un programme d’affiliation ou de fidélité.
- Le groupe de prix de la remise est associé à un catalogue lui-même associé au magasin.

L'opération **Voir toutes les remises** présente uniquement les remises qui ne sont pas en concurrence avec une remise déjà appliquée. Ce comportement permet de garantir que, si un vendeur informe un client d’une remise et si le client exécute l’action requise (par exemple, il achète un article supplémentaire pour bénéficier d’une remise de 10 %), la remise est appliquée à la transaction. Les remises basées sur les coupons ne sont affichées que si le paramètre **Appliquer sans code coupon** est activée.

À l’intérieur de l'opération **Voir toutes les remises**, les utilisateurs de PDV peuvent rechercher des remises par nom et description, et ils peuvent filtrer les remises en fonction de la nécessité ou non d’un coupon.

## <a name="view-available-discounts"></a>Afficher les remises disponibles

L'opération **Voir les remises disponibles** permet aux utilisateurs du PDV de visualiser toutes les remises applicables à une ligne sélectionnée dans une transaction ou à l’ensemble de la transaction. Les remises applicables à une ligne sélectionnée incluent les remises déjà appliquées et les remises qui n’ont pas encore été appliquées mais qui peuvent l’être (par exemple, des remises mixtes qui nécessitent des articles supplémentaires). Si une remise applicable est liée à un coupon où le paramètre **Appliquer sans code promo** est activé, l’utilisateur du PDV peut également utiliser la fonction **Appliquer Coupon** à l’intérieur de cette opération pour échanger le coupon directement, sans avoir à saisir ou à scanner des codes de coupon ou des codes à barres de coupon.

## <a name="price-override"></a>Remplacement de prix

L'opération **Remplacement du prix** permet aux utilisateurs du PDV de remplacer le prix de vente d’un produit dans une transaction. Cette opération ne fonctionne que pour les produits configurés pour autoriser les remplacements de prix.

## <a name="line-discount-amount"></a>Montant de la remise ligne

L'opération **Montant de la remise de ligne** permet aux utilisateurs du PDV d’entrer un montant de remise pour un article de ligne dans une transaction. Cette opération ne s’applique qu’aux articles en promotion, et elle respecte la valeur du **Montant maximum de remise de ligne** spécifiée dans le groupe d’autorisations de PDV pour l’utilisateur.

## <a name="line-discount-percent"></a>Pourcentage de la remise ligne

L'opération **Pourcentage de la remise de ligne** permet aux utilisateurs du PDV d’entrer un pourcentage de remise pour un article de ligne dans une transaction. Cette opération ne s’applique qu’aux articles en promotion, et elle respecte la valeur du **Pourcentage maximum de remise de ligne** spécifiée dans le groupe d’autorisations de PDV pour l’utilisateur.

## <a name="total-discount-amount"></a>Montant de remise totale

L'opération **Montant total de remise** permet aux utilisateurs du PDV d’entrer un montant de remise pour une transaction. Cette opération ne s’applique qu’aux articles en promotion, et elle respecte la valeur du **Montant maximum total de remise** spécifiée dans le groupe d’autorisations de PDV pour l’utilisateur. Si le montant de la remise entré dépasse le montant total maximum de remise, l’opération est bloquée et aucun flux de remplacement d’autorisation n’est déclenché. Actuellement, un montant total de remise ne peut pas être appliqué à un panier contenant à la fois des articles soldés et des articles retournés.

## <a name="total-discount-percent"></a>Pourcentage de remise totale

L'opération **Pourcentage total de remise** permet aux utilisateurs du PDV d’entrer un pourcentage de remise pour une transaction. Cette opération ne s’applique qu’aux articles en promotion, et elle respecte la valeur du **Pourcentage total maximum de remise** spécifiée dans le groupe d’autorisations de PDV pour l’utilisateur. Si le pourcentage de la remise entré dépasse le pourcentage total maximum de remise, l’opération est bloquée et aucun flux de remplacement d’autorisation n’est déclenché. Actuellement, un pourcentage total de remise ne peut pas être appliqué à un panier contenant à la fois des articles soldés et des articles retournés.

## <a name="remove-system-discounts-from-transaction"></a>Supprimer les remises système de la transaction

L'opération **Supprimer les remises système de la transaction** permet aux utilisateurs du PDV d’effacer toutes les remises système appliquées (y compris les remises basées sur des coupons) d’une transaction. Une fois cette opération effectuée, le moteur de tarification commence à exclure les remises système de l'étendue du calcul des remises. L'opération **Supprimer les remises système de la transaction** ne supprime pas les remises manuelles.

## <a name="reapply-system-discounts"></a>Réappliquer les remises système

L'opération **Réappliquer les remises système** permet aux utilisateurs du PDV de réappliquer les remises calculées par le système à une transaction si les remises ont été supprimées à l’aide de l’opération **Supprimer les remises système de la transaction**. Une fois cette opération effectuée, le moteur de tarification commence à inclure toutes les remises système dans l'étendue du calcul des remises.

## <a name="add-coupon-code"></a>Ajouter un code coupon

L'opération **Ajouter un code coupon** permet aux utilisateurs du PDV d’ajouter un coupon à une transaction en saisissant un code de coupon. Autrement, les utilisateurs du PDV peuvent scanner un code à barres de coupon ou le saisir à l'aide du clavier numérique sur l'écran **Transactions**.

## <a name="remove-coupon-code"></a>Supprimer le code coupon

L'opération **Supprimer le code coupon** permet aux utilisateurs du PDV de sélectionner et de supprimer un ou plusieurs coupons actuellement appliqués à une transaction.

## <a name="recalculate"></a>Recalculer

L'opération **Recalculer** permet aux utilisateurs du PDV de déclencher le calcul des prix à la demande. Cette opération est requise lorsque le verrouillage des prix et/ou le calcul différé des prix sont activés, et que l’utilisateur du PDV souhaite recalculer les prix et les remises après les modifications du panier ou de la commande. L'opération **Recalculer** recalcule toujours la totalité de la commande. Il ne peut pas être utilisé pour recalculer des lignes de vente sélectionnées. Pour appliquer des remises manuelles à une ligne de vente verrouillée dans le PDV, les utilisateurs du PDV doivent d’abord utiliser l'opération **Recalculer** pour déverrouiller toutes les lignes de vente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
