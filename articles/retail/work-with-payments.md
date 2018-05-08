---
title: Modes de paiement dans un centre d'appels
description: "Cette rubrique décrit les différentes méthodes de paiement que vous pouvez utiliser dans un centre d'appels de Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fe8dd3136f14e182e261a4dce57eef0b1946d304
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="payment-methods-in-a-call-center"></a>Modes de paiement dans un centre d'appels

[!include [banner](includes/banner.md)]

Dans Microsoft Dynamics 365 for Retail, la configuration du canal de centre d'appels inclut un paramètre **Activer l'achèvement de commande**. Ce paramètre permet de garantir que toutes les commandes que les utilisateurs du canal créent sont lancées vers le traitement des commandes uniquement si elles ont un acompte ou un paiement pré-autorisé qui correspond aux tolérances approuvées. Si le paramètre **Activer l'achèvement de la commande** est activé, les utilisateurs du centre d'appels peuvent entrer des paiements pour des commandes client à l'aide des fonctionnalités de traitement des paiements du centre d'appels. Si le paramètre est désactivé, les utilisateurs du centre d'appels ne peuvent pas utiliser les fonctionnalités de traitement de paiement du centre d'appels, mais ils peuvent encore appliquer des acomptes aux commandes client à l'aide de la fonctionnalité de Comptabilité client standard.

Lors de la configuration du canal, une société peut définir les modes de paiement autorisés pour un canal de centre d'appels. Le canal de centre d'appels utilise les mêmes modes de paiement définis pour les canaux de magasin de vente au détail.

Pour configurer les modes de paiement d'un canal de centre d'appels, accédez à **Retail** \> **Canaux** \> **Centres d'appels** \> **Tous les centres d'appels**, puis, dans le menu **Paramétrage**, sélectionnez l'option **Modes de paiement**.

Lorsque vous créez un mode de paiement, il existe cinq fonctions de mode de paiement que vous pouvez affecter.

| Fonction            | Description |
|---------------------|-------------|
| Standard              | Utilisez la fonction **Normal** sur votre mode de paiement lorsque vous définissez des modes de paiement comme au comptant ou par N° document. Lorsque ces types de paiements s'appliquent à une commande client du centre d'appels, ils sont directement validés comme des acomptes sur le compte client. Le N° document d'acompte est validé dans l'historique de transactions client, où il sera systématiquement réglé avec la facture de la commande client lorsque les factures sont créées. |
| Vérification               | Utilisez la fonction **Chèque** lorsque vous définissez un instrument de chèque bancaire comme forme de paiement. Lorsque ce type de paiement est appliqué à une commande client, l'utilisateur doit entrer le numéro de chèque du client dans le cadre du traitement d'application de paiement. Les paiements par chèque sont toujours traités comme des acomptes lorsqu'ils sont appliqués. Quant à la fonction de paiement **Normal**, ces N° document d'acompte sont systématiquement réglés avec les factures créées pour la commande. |
| Cartes               | Les types de paiement par carte représentent n'importe quel type de paiement qui nécessite l'entrée d'un numéro de carte défini sur la carte de paiement du client. Ils comprennent les cartes de crédit et les cartes cadeaux. Lorsque vous configurez ces types de paiements, vous devez utiliser le menu **Paramétrage de carte** pour définir les ID carte associés à ce mode de paiement. Lors de la saisie de commande, les utilisateurs peuvent indiquer si le paiement par carte est un acompte, à l'aide de l'option **Acompte** qui apparaît sur la page de saisie de paiement. Sauf si l'entreprise nécessite des acomptes, le flux standard d'un véritable paiement par carte de crédit est un processus en deux étapes, dans lequel l'autorisation est obtenue lors de la saisie de la commande, puis le paiement est réglé puis collecté sur la carte du client au moment de la facturation. Pour les paiements par carte cadeau, l'acompte est recommandé, car le solde de la carte cadeau doit être réduit immédiatement afin que le client ne puisse pas appliquer la même valeur ailleurs. |
| Client            | La fonction **Client** sur un mode de paiement implique que le paiement est appliqué à la limite de crédit du client ou placé « sur son compte. » Dans Retail, une limite de crédit peut être affecté à un client et peut être validée lors de la saisie de commande. Les paiements effectués à l'aide d'un mode de paiement lié à la fonctionnalité **Client** créent un passif par rapport au compte client. Puis, lorsque la commande client est facturée, un solde dû est affiché. Dans ce cas, les clients envoient généralement un paiement, en fonction des conditions données. Sinon, un N° document de crédit en cours précédent sur le compte client peut être appliqué pour régler le solde dû. Notez que même si vous définissez ce mode de paiement, il n'apparaît pas parmi les options de sélection de paiement dans la saisie de commande du centre d'appels à moins que l'indicateur **Autoriser en compte** soit défini sur l'enregistrement client pour le client avec lequel vous travaillez. Cet indicateur est accessible sous l'onglet **Valeurs par défaut de paiement** de l'enregistrement client. |
| Vider la caisse/transférer | La fonction **Vider la caisse/transférer** n'est pas utilisée par le centre d'appels. Elle s'applique uniquement lorsque vous définissez les modes de paiement que l'application de point de vente (PDV) utilise dans un canal de magasin. |

À mesure que les modes de paiement sont définis, ils doivent être liés à une comptabilité ou à un compte bancaire. Si vous ignorez cette étape, les utilisateurs reçoivent des erreurs lorsqu'ils essayent d'enregistrer le type de paiement.

## <a name="refund-payment-methods"></a>Modes de paiement de remboursement

Pour les scénarios de traitement des remboursements, le centre d'appels utilise également des modes de paiement définis dans Comptabilité client. Pour configurer ces modes de paiement, accédez à **Retail** \> **Paramétrage de canal** \> **Paramétrage de centre d'appels** \> **Méthodes de remboursement du centre d'appels**. Vous devez effectuer cette configuration pour traiter les chèques de remboursement aux clients. Par exemple, si un client a payé initialement pour une commande au comptant ou à l'aide d'un chèque, l'utilisateur peut avoir besoin d'envoyer au client un chèque de remboursement via la Comptabilité client. Dans ce cas, les types de paiement au comptant et par chèque dans le centre d'appels doivent être mis en correspondance avec le mode de paiement approprié dans Comptabilité client pour garantir que le remboursement soit correctement traité.

En outre, si un utilisateur traite un ordre de retour en tant qu'utilisateur du centre d'appels dans Retail, mais qu'il ne peut pas lier le retour à une vente d'origine, le mode de paiement **Retour** doit être défini dans les paramètres du centre d'appels. Accédez à **Retail** \> **Paramétrage du canal** \> **Paramétrage du centre d'appels** \> **Paramètres du centre d'appels**, puis, dans l'onglet **Retour marchandises/Retour**, dans le champ **Mode de paiement**, vérifiez qu'un mode de paiement est défini. Le mode de paiement est le mode de paiement utilisé pour les remboursements. Généralement, il est défini comme méthode de vérification ou méthode de compte client.

