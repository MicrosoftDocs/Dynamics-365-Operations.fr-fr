---
title: Traitement des remboursements dans les centres d'appels
description: Cette rubrique explique comment les remboursements sont effectués via les centres d'appels en cas de retour ou d'annulation de commandes ou de lignes de commande.
author: hhainesms
manager: annbe
ms.date: 01/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: fd49835a24dc6ec429ac4b01f363f1be937628ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214721"
---
# <a name="refund-payment-processing-in-call-centers"></a>Traitement des remboursements dans les centres d'appels

Cette rubrique explique comment les remboursements sont effectués via les centres d'appels en cas de retour ou d'annulation de commandes ou de lignes de commande.

Un utilisateur qui crée un ordre de retour pour un client en tant qu’utilisateur du centre d’appels dans Microsoft Dynamics 365 Commerce Headquarters doit utiliser la page **Ordre de retour** pour créer l’autorisation initiale de retour marchandises (RMA). La RMA définit les produits que le client souhaite retourner ou échanger, et permet de créer un retour de la commande client ayant un type de commande de **Commande retournée**. Ce retour de commande est utilisé pour suivre l'enregistrement du retour d'inventaire et les notes de crédit ou remboursements de paiement qui sont enregistrés.

Si l'option **Activer l'achèvement de la commande** est définie sur **Oui** pour le canal du centre d'appels, l'utilisateur du centre d'appels qui crée le RMA doit exécuter le flux de traitement de fin de commande en sélectionnant **Terminer** sur la page **Ordre de retour**. La fonction **Terminer** fournit un récapitulatif de retour calculé qui décrit le montant du remboursement dû. De plus, lorsqu'elle est correctement configurée, elle crée systématiquement une ligne de remboursement en échange du retour de commande.

La logique du centre d'appels détermine le mode de paiement pour la ligne de remboursement, en fonction du mode de paiement utilisé pour la commande d'origine. Si le retour de commande créée n'est pas lié à une commande d'origine, un mode de paiement par défaut issu d'un paramètre système est appliqué.

## <a name="how-a-call-center-determines-which-payment-method-to-apply-to-a-return-order"></a>Détermination du mode de paiement à appliquer à un retour de commande par le centre d'appels

Le centre d'appels utilise le mode de paiement de la commande d'origine pour déterminer le mode de paiement à appliquer à un retour de commande. Voici comment ce processus fonctionne pour les modes de paiement originaux suivants :

- **Normal** (espèces) ou **Chèque** - Lorsqu'un ordre de retour créé fait référence à une commande originale qui a été payée en utilisant le type de paiement normal (espèces) ou par chèque, l'application du centre d'appels référence les configurations sur la page **Modes de remboursement du centre d'appels**. Cette page permet aux organisations de définir, par devise de commande, la manière d'effectuer les remboursements aux clients pour les commandes payées à l'origine à l'aide du type de paiement normal ou par chèque. La page **Modes de remboursement du centre d'appels** permet également aux organisations de choisir si un chèque de remboursement généré par le système est envoyé au client ou si un crédit de compte client est créé par rapport au solde du compte client interne. Dans ces scénarios, la logique du centre d'appels fait référence à la devise de l'ordre de retour, puis utilise la valeur **Mode de paiement au détail** de cette devise pour créer une ligne de paiement de remboursement sur la commande client de retour. Plus tard, un journal de paiement des comptes clients (AR) qui utilise le mode de paiement AR mis en correspondance est lié à la devise.

    L'illustration suivante montre la configuration d'un scénario dans lequel un client retourne des produits à partir d'une commande client liée à la devise USD, qui a été initialement payée à l'aide du type de paiement normal ou chèque. Dans ce scénario, un remboursement sera émis au client via un chèque de remboursement généré par le système. La mode de paiement AR **REF-CHK** a été configuré comme type de paiement par chèque de remboursement.

    ![Configuration des méthodes de remboursement du centre d'appels pour les paiements par chèque et normaux](media/callcenterrefundmethods.png)

- **Carte de crédit** - Lorsqu'une commande de retour fait référence à une commande d'origine payée à l'aide d'une carte de crédit, la logique du centre d'appels pour les remboursements applique la même carte de crédit d'origine à la commande de retour.
- **Carte de fidélité** - Lorsqu'une commande de retour fait référence à une commande d'origine payée à l'aide d'une carte de fidélité client, la logique du centre d'appels pour les remboursements applique le remboursement à la même carte de fidélité.
- **Carte cadeau** (interne) - Lorsqu'une commande de retour fait référence à une commande d'origine payée à l'aide d'une carte-cadeau émise depuis Dynamics 365 Commerce (fonctionnalité de carte-cadeau interne), la logique du centre d'appels pour les remboursements applique le remboursement au même numéro de carte-cadeau d'origine.
- **Carte cadeau** (externe) - Lorsqu'une commande de retour fait référence à une commande d'origine payée à l'aide d'une carte-cadeau tierce externe, la logique du centre d'appels pour les remboursements applique le mode de paiement de retour par défaut défini sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**.

Si le type de paiement de la commande d'origine est inconnu pour une raison quelconque, ou si plusieurs modes de paiement ont été utilisés pour payer la commande d'origine, la logique du centre d'appels applique le mode de paiement de retour par défaut défini sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**.

L'illustration suivante montre le champ **Mode de paiement** sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**.

![Champ Mode de paiement sur l'onglet Retour marchandises/Retour de la page Paramètres du centre d'appels](media/callcenterrefundparameters.png)

> [!NOTE]
> Les règles de traitement des remboursements décrites précédemment s'appliquent également aux commandes ou aux lignes de commande annulées par un utilisateur du centre d'appels dans Commerce Headquarters. Si l'annulation d'une commande ou de lignes de commande spécifiques entraîne des trop-perçus, les mêmes règles seront utilisées pour générer des lignes de paiement de remboursement.

En règle générale, une commande de retour passe par un processus standard, où le stock est reçu (ou mis au rebut), un bon de livraison est validé par rapport à la commande de retour, puis un processus de validation de facture est exécuté pour la commande de retour. La commande de retour est liée et systématiquement générée dans le cadre du processus de création de la commande de retour. Dans les scénarios typiques, les remboursements ne sont pas émis aux clients tant que la facture de la commande de retour n'est pas validée.

### <a name="what-happens-when-an-invoice-is-posted-on-a-return-sales-order"></a>Que se passe-t-il lorsqu'une facture est validée sur une commande client de retour ?

Les scénarios suivants expliquent ce qu'il se passe lorsqu'une facture est validée sur une commande client de retour.

- Si le paiement du remboursement sur la commande de retour concerne une carte de crédit, une logique supplémentaire est invoquée lors de la validation de la facture. Cette logique appelle le processeur de paiement pour rembourser le paiement sur la carte de crédit du client. Un justificatif de remboursement client est également créé et systématiquement imputé sur le compte du client. Ce journal de paiement sera réglé sur le justificatif de note de crédit de la commande de retour.
- Si le remboursement qui doit être émis concerne un type de paiement par chèque, un justificatif de paiement client qui utilise le mode de paiement AR est créé et doit être validé ou imprimé manuellement avant que le justificatif de paiement puisse être imputé sur le compte client. Pour traiter le chèque de remboursement, les utilisateurs peuvent utiliser la page **Journal des paiements client** dans les comptes clients ou la page **Traitement du chèque de remboursement** dans Retail et Commerce.
- Si le paiement de remboursement qui doit être émis concerne le type de paiement carte-cadeau interne ou carte de fidélité, lors de la facturation du bon de retour, le justificatif de paiement de remboursement est créé et imputé sur le compte client. Cette étape de facturation ajoute également le montant du remboursement au solde de la carte-cadeau ou au solde des points de fidélité suivis en interne par le client.
- Si un mode de paiement qui utilise la fonction **Client** (par exemple, un compte client) est lié au retour de la commande client, les validations de limite de crédit sont ignorées lors du traitement du paiement. Aucun justificatif de paiement n'est créé ou affiché dans ce contexte. Lorsqu'un type de paiement client est utilisé sur une commande de retour, le justificatif de note de crédit créé par le processus d'enregistrement de facture sert de justificatif de crédit client et indique un remboursement sur le solde AR du client.

## <a name="advance-credit"></a>Crédit préalable

Lorsqu'un utilisateur traite des commandes de retour en tant qu'utilisateur d'un centre d'appels dans un centre d'appels où l'option **Activer l'achèvement de la commande** est définie sur **Oui**, une exception au processus décrit précédemment pour l'enregistrement des paiements de remboursement peut se produire si l'utilisateur du centre d'appels qui crée l'ordre de retour définit l'option **Avance de crédit** sur **Oui** sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**. Dans ce cas, le remboursement du paiement a lieu immédiatement après la soumission de la commande de retour en utilisant la fonction **Soumettre** sur la page **Récapitulatif du retour**. Le système crée immédiatement un justificatif de paiement client d'acompte pour la valeur de retour, même si la commande de retour elle-même n'a pas encore été facturée. Cette approche peut être utilisée dans les situations où une organisation doit émettre des remboursements aux clients à l'avance en raison de problèmes de service client, et elle ne veut pas exiger que le retour en stock soit effectué avant que les remboursements ne soient émis.

## <a name="replacement-orders"></a>Ordres de remplacement

Lorsqu'un ordre de retour est émis, la fonction **Ordre de remplacement** peut être utilisée pour générer une nouvelle commande pour le client. Cette approche peut être utilisée dans des scénarios d'échange. La fonction **Commande de remplacement** crée une autre commande client pour les nouveaux articles qui doivent être envoyés, mais un lien de référence croisée sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels** relie la commande de remplacement, le Retour marchandises et la commande client retournée.

Lorsque les paiements d'une commande de remplacement sont traités, les organisations ont deux options :

- Rembourser le client pour la commande de retour, en fonction du mode de paiement d'origine, puis collecter un paiement séparé pour la commande de remplacement. Aucune configuration supplémentaire n'est requise pour utiliser cette option.
- Définissez l'option **Appliquer le crédit** sur **Oui** sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**. Dans ce cas, un mode de paiement client est systématiquement appliqué à la fois à la commande de retour et à la commande de remplacement. Cette option permet d'empêcher l'émission de tout paiement de remboursement externe. Elle permet également d'éviter tout traitement de paiement sur la transaction. Cela peut être utile dans les situations où un échange régulier est en cours de traitement et où l'organisation préfère utiliser le justificatif de crédit généré lorsque la commande de retour est facturée pour payer la facture générée par la commande de remplacement. Quand l'option **Appliquer le crédit** est définie sur **Oui**, l'organisation doit régler manuellement la note de crédit avec la facture de la commande de remplacement une fois que ces deux documents financiers ont été générés.

L'option **Appliquer le crédit** ne peut être définie sur **Oui** que lorsque la commande de retour est liée à une commande de remplacement. Dans ce cas, le mode de paiement client qui sera utilisé pour payer systématiquement le retour et l'ordre d'échange est défini par le champ **Appliquer le mode de paiement des crédits** sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**. Seul un paiement du type de paiement de la fonction **Client** peut être sélectionné dans ce champ.

> [!NOTE]
> Pour un ordre de retour qui n'a pas de commande de remplacement liée, si **Oui** est défini pour l'option **Appliquer le crédit**, cela n'aura aucun effet sur la logique de paiement des ordres de retour, car ce paramètre ne s'applique qu'aux commandes de remplacement.

![Champ Appliquer le mode de paiement des crédits sur l'onglet Retour marchandises/Retour de la page Paramètres du centre d'appels](media/callcenterrefundparameters1.png)

> [!IMPORTANT]
> Si les utilisateurs qui créent des commandes de remplacement prévoient d'utiliser l'option **Appliquer le crédit**, ils ne doivent pas exécuter la fonction **Compléter** sur l'ordre de retour avant de définir l'option **Appliquer le crédit** sur **Oui**. Une fois la fonction **Compléter** exécutée, le paiement du remboursement est calculé et appliqué à la commande client de retour. Toute tentative de définir l'option **Appliquer le crédit** sur **Oui** après qu'un paiement de remboursement a déjà été calculé et appliqué ne déclenchera pas un recalcul du paiement de remboursement, et le mode de paiement sélectionné dans le champ **Appliquer le mode de paiement des crédits** ne sera pas appliqué. Si l'option **Appliquer le crédit** doit être utilisée dans ce contexte, l'utilisateur doit supprimer la commande de remplacement et le retour de marchandises, puis recommencer et créer un nouveau retour de marchandises. Cette fois, l'utilisateur doit s'assurer que l'option **Appliquer le crédit** est définie sur **Oui** avant que la fonction **Compléter** soit exécutée.

## <a name="payment-overrides-for-call-center-returns"></a>Remplacements de paiement pour les retours de centre d'appels

Bien que la logique du centre d'appels détermine systématiquement le mode de paiement du remboursement de la manière décrite plus haut dans cette rubrique, les utilisateurs peuvent parfois souhaiter annuler ces paiements. Par exemple, un utilisateur peut modifier ou supprimer des lignes de paiement de remboursement existantes et appliquer de nouvelles lignes de paiement. Les remboursements calculés par le système ne peuvent être modifiés que par les utilisateurs disposant des autorisations de remplacement appropriées. Ces autorisations peuvent être configurées sur la page **Remplacer les autorisations** dans Retail et Commerce. Pour effectuer un remplacement de paiement de remboursement, l'utilisateur doit être lié à un rôle de sécurité où l'option **Autoriser un autre paiement** est définie sur **Oui** sur la page **Remplacer les autorisations**.

![Autoriser une autre option de paiement sur la page Remplacer les autorisations](media/overridepermissions.png)

Une organisation peut également définir l'option **Autoriser le remplacement du paiement** sur **Oui** sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**. Dans ce cas, un code de dérogation de sécurité doit être sélectionné dans le champ **Code de remplacement de sécurité**. Le code de remplacement de sécurité est un code alphanumérique qui doit être géré en externe, car les utilisateurs ne peuvent pas l'afficher dans Commerce Headquarters après sa définition. Seules quelques personnes de confiance clés dans une organisation doivent connaître le code de remplacement de sécurité. Quand l'option **Autoriser le remplacement du paiement** est définie sur **Oui**, si des utilisateurs qui ne disposent pas des autorisations de rôle appropriées tentent de modifier le mode de paiement sur une commande de retour, ils auront la possibilité de saisir le code de remplacement de sécurité. S'ils ne le connaissent pas, ou si un responsable ou un superviseur ne peut pas le saisir sur la page pour eux, ils ne pourront pas remplacer le mode de paiement de retour.

> [!NOTE]
> Si le code de remplacement de sécurité est perdu ou oublié, l'organisation devra le réinitialiser en définissant un nouveau code de remplacement de sécurité dans le champ **Code de remplacement de sécurité** sur l'onglet **Retour marchandises/Retour** de la page **Paramètres du centre d'appels**.

![Paramètres de remplacement de paiement dans l'onglet Retour marchandises/Retour de la page Paramètres du centre d'appels](media/overridepaymentparameter.png)

> [!IMPORTANT]
> Avant que les organisations n'essaient d'annuler les remboursements qui utilisent des types de paiement par carte de crédit, elles doivent vérifier que leur processeur de carte de crédit autorise les retours non liés. De nombreux processeurs exigent que les remboursements soient reportés sur la carte d'origine. Toute tentative d'émettre un remboursement sur une carte qui n'a pas de capture précédente peut entraîner des échecs de publication avec le processeur.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modes de paiement dans les centres d’appels](work-with-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]