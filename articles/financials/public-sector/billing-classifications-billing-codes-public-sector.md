---
title: Classifications de facturation et codes facturation dans le secteur public
description: "Les organisations du secteur public peuvent utiliser les classifications de facturation et des codes de facturation pour gérer les factures financières."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustBillingClassification, CustBillingCode, CustCustomField
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19491
ms.assetid: 47624566-0b4c-41dc-9cd4-801e213b5da3
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8cf735a8ff33833aac748d17e33d4de5740ed875
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="billing-classifications-and-billing-codes-in-the-public-sector"></a>Classifications de facturation et codes facturation dans le secteur public

[!include[banner](../includes/banner.md)]


Les organisations du secteur public peuvent utiliser les classifications de facturation et des codes de facturation pour gérer les factures financières. 

<a name="billing-classifications"></a>Classifications de facturation
-----------------------

Les classifications de facturation permettent de regrouper les factures financières similaires pour le traitement et l'affichage. Par exemple, une agence de transit peut louer de l'espace dans chaque station de transit à des cafés et d'autres fournisseurs. En créant une classification de facturation pour des baux, l'agence peut automatiquement appliquer les mêmes conditions de paiement et utiliser la même série de lettres de relance pour tous les baux. L'agence peut également afficher les factures pour tous les baux ensemble, même si ces baux ne partagent pas les mêmes dimensions financières. Les classifications de facturation incluent les informations suivantes :

-   Code de classification de facturation (jusqu'à 15 caractères alphanumériques)
-   Description (jusqu'à 60 caractères)
-   Conditions de paiement
-   Informations sur les intérêts
-   Souche de numéros pour le numéro de facture
-   Souche de numéros pour les avoirs.
-   Souche de numéros pour les lettres de relance
-   Codes de facturation qui peuvent être affectés à des factures qui utilisent cette classification de facturation.

Vous pouvez utiliser les classifications de facturation pour contrôler la priorité de règlement des factures financières. Pour plus d'informations, voir [Priorité de règlement dans le secteur public](settlement-priority-public-sector.md). Une classification de facturation peut inclure de nombreux codes facturation, mais chaque code facturation peut être affecté à une seule classification de facturation. Lorsque vous sélectionnez une classification de facturation dans une facture financière, seuls les codes facturation répertoriés dans la classification de facturation sont disponibles pour la facture. Avant de paramétrer des classifications de facturation, vérifiez que vous avez paramétré les conditions de paiement, les codes intérêt, les profils de validation, les séries de lettres de relance, les souches de numéros et les codes facturation que vous prévoyez d'utiliser dans les classifications de facturation.

## <a name="billing-codes"></a>Codes facturation
Les codes facturation fournissent un ensemble de valeurs par défaut et de taux de facturation pour un type défini de service ou de frais. Les valeurs que vous définissez pour chaque code facturation sont renseignées automatiquement dans la ligne de facture financière lorsque le code facturation est sélectionné. Par exemple, un département de gestion des déchets peut facturer à certains clients de nouveaux conteneurs. Ils auraient un code facturation « Nouveau conteneur » contenant les informations de facturation pour ces conteneurs. Lorsque le département crée une facture financière et sélectionne le code facturation « Nouveau conteneur » sur une ligne de facture, les valeurs par défaut de code facturation sont entrées automatiquement. Les codes facturation incluent les informations suivantes :

-   Code facturation (jusqu'à 10 caractères alphanumériques)
-   Description (jusqu'à 60 caractères ; qui sera imprimée sur la facture)
-   Date d'effet et date d'expiration
-   Informations sur les taxes
-   Informations sur les intérêts
-   Répartition comptable
-   Informations sur les taux
-   Informations sur le projet (si activé dans la page de paramètres Comptabilité client)
-   Champs personnalisés

Généralement, les valeurs par défaut provenant du code facturation peuvent être modifiées dans la facture financière. Toutefois, vous pouvez définir le code facturation de sorte à autoriser ou empêcher les modifications apportées à certains champs. Pour davantage de détails, voir Factures financières dans le secteur public. Les codes facturations peuvent également être associés à des définitions de validation. Lorsqu'un code facturation est utilisé sur une ligne de facture, la définition de validation associée au code facturation est utilisée pour valider la transaction dans la comptabilité. Pour plus d'informations sur les définitions de validation, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).

### <a name="custom-fields"></a>Champs personnalisés

Vous pouvez créer des champs personnalisés pour les codes facturation. Ces champs permettent de recueillir des données associées à des frais de facturation spécifiques. Par exemple, le service de contrôle des animaux d'une municipalité peut utiliser des champs personnalisés pour enregistrer le type d'animal et la date de sa dernière vaccination contre la rage. Étant donné que vous affectez des champs personnalisés à des codes facturation, vous devez créer vos champs personnalisés avant de créer des codes facturation. Il existe six types de champs personnalisés. Vous pouvez définir une valeur par défaut pour tout champ personnalisé. Les valeurs par défaut peuvent être modifiées dans la facture financière.

-   **Devise** – Les champs de devise acceptent uniquement les nombres à deux décimales. Vous pouvez spécifier le les valeurs minimale et maximale pour le champ.
-   **Décimal** – Les champs décimaux acceptent uniquement les nombres décimaux à quatre décimales. Vous pouvez définir des valeurs minimale et maximale pour le champ.
-   **Texte** – Les champs de texte peuvent contenir toute sorte de texte, et toute entrée dans ces champs est interprétée comme du texte. Vous pouvez définir une longueur maximale pour le champ.
-   **Entier** – Les champs de nombres entiers acceptent uniquement des nombres entiers. Vous pouvez définir des valeurs minimale et maximale pour le champ.
-   **Booléen** – Les champs booléens autorisent les sélections oui/non.
-   **Date** – Les champs de date acceptent uniquement les dates. La date est stockée au format mm/jj/aaaa.

## <a name="do-i-have-to-use-billing-classifications"></a>Dois-je utiliser les classifications de facturation ?
Bien que vous ne soyez pas obligé d'activer les classifications de facturation, nous vous recommandons vivement de le faire. De nombreuses capacités dédiées au secteur public dans l'application Comptabilité sont disponibles uniquement lorsque les classifications de facturation sont activées. Une fois que vous avez activé les classifications de facturation, toutefois, le champ Classification de facturation devient obligatoire dans les factures financières. Pour plus d'informations sur les classifications de facturation et les codes facturation, voir [Classifications de facturation et codes facturation dans le secteur public](free-text-invoices-public-sector.md).

## <a name="how-do-i-enable-billing-classifications"></a>Comment activer les classifications de facturation ?
Activez les classifications de facturation sur la page **Paramètres de la comptabilité client**. Dans la section **Général**, dans l'organisateur **Paramétrage des ventes**, sélectionnez **Utiliser les classifications de facturation**. Les pages sur lesquelles vous créez des classifications de facturation et des codes facturation sont disponibles avant que vous activiez les classifications de facturation. Vous devez paramétrer toutes vos classifications de facturation et codes facturation avant de les activer. Une fois que vous avez activé les classifications de facturation, chaque facture financière doit être dotée d'une classification de facturation. **Remarque** : si vous prévoyez d'utiliser les classifications de facturation pour déterminer la priorité de règlement des factures financières, vous devez activer l'attribut **Facturation** sur la page **Priorité de règlement** après avoir activé les classifications de facturation. Pour plus d'informations, voir [Priorité de règlement dans le secteur public](settlement-priority-public-sector.md).

## <a name="do-i-have-to-create-new-billing-codes-when-billing-rates-change"></a>Dois-je créer des codes facturation lorsque les taux les facturation changent ?
Lorsque les codes facturation doivent être mis à jour, il n'est pas nécessaire d'en créer de nouveaux. Au lieu de cela, vous pouvez créer plusieurs versions du code facturation, avec des dates d'effet et d'expiration pour chaque version. À la date d'effet, le système commencera automatiquement à utiliser la version mise à jour.

## <a name="can-i-assign-the-same-billing-code-to-more-than-one-billing-classification"></a>Puis-je affecter le même code facturation à plusieurs classification de facturation ?
Non, mais il existe tout de même une manière d'obtenir les résultats dont vous avez besoin. Supposons que votre organisation utilise une classification de facturation distincte pour chaque département. Trois de ces départements ont besoin d'un code facturation pour des contrats de licence. Vous ne pouvez pas affecter un code facturation unique « Contrat de licence » à trois classifications de facturation, mais vous pouvez créer un ensemble de trois codes facturation identiques, puis en affecter un à chaque département.






