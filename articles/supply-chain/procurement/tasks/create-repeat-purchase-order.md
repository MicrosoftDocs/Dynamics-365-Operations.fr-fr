---
title: Créer une commande fournisseur répétée
description: Cet article vous montre comment créer une commande fournisseur répétée (CF) en copiant des lignes d’un document de commande fournisseur précédent dans un nouveau CF ou un CF existant.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608104"
---
# <a name="create-a-repeat-purchase-order"></a>Créer une commande fournisseur répétée

[!include [banner](../../includes/banner.md)]

Cet article vous montre comment créer une commande fournisseur répétée (CF) en copiant des lignes d’un document de commande fournisseur précédent dans un nouveau CF ou un CF existant. Il y a deux méthodes pour créer des commandes répétées. Vous pouvez utiliser les actions disponibles au niveau du document à partir du volet Actions ou vous pouvez utiliser les actions de détails de ligne. Les actions au niveau du document sont destinées à créer une commande fournisseur en ajoutant des lignes et des informations d’en-tête d’une autre commande, alors que l’action de détails de ligne sert principalement à ajouter des lignes à une commande existante. L’exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. Cette tâche est généralement effectuée par un agent des achats.

## <a name="create-a-new-repeat-purchase-order"></a>Créer une commande fournisseur répétée

1. Dans le volet de navigation, accédez à **Modules \> Approvisionnements \> Commandes fournisseur \> Toutes les commandes fournisseur**. D’abord, nous essayerons l’option pour copier les informations dans une nouvelle commande.  
1. Sélectionnez **Nouveau**.
1. Dans le champ **Compte fournisseur**, saisissez `US-101`.
1. Cliquez sur **OK**.
1. Dans le volet Action, ouvrez l’onglet **Commande fournisseur** et, dans le groupe **Copier**, sélectionnez **À partir de tous**. La boîte de dialogue **Copier à partir d’autres documents** s’ouvre. À partir d’ici, vous pouvez copier des commandes existantes vers votre commande. Il y a différentes options pour copier les lignes et différents types de documents à partir desquels vous pouvez copier. Nous verrons les options pour copier les lignes en premier.
1. Développez le raccourci **Paramètres**.

    - Le champ **Facteur de quantité** est utile si vous devez utiliser une quantité qui est différente de celle qui est sur la commande à partir de laquelle vous copiez. Par exemple, si vous voulez commander deux fois la quantité qui est dans les lignes à partir desquelles vous copiez, vous devez taper « 2 » dans ce champ et le système ajoutera alors des lignes où la quantité originale a été doublée.  
    - Le champ **Inverser le signe** prend aussi en charge la quantité commandée en changeant le signe de la quantité pour les lignes de commande qui sont ajoutées. Ceci peut être utile si vous devez contrepasser une transaction, en créant des lignes de commande qui annulent la transaction. Cette option est automatiquement choisie quand la page est ouverte à partir de l’action **Créer un avoir**.  
    - L’option **Copier les frais** vous permet de copier des frais dans la nouvelle commande à partir du document à partir duquel vous copiez les lignes de commande.  
    - L’option **Recalcul des prix** utilise les prix actuels et les remises plutôt que de les copier à partir du document à partir duquel vous copiez d’autres informations.  
    - L’option **Copier précisément** copie les valeurs de plusieurs champs de l’en-tête et des lignes de commande. Si cette option n’est pas sélectionnée, les valeurs par défaut seront utilisées pour plusieurs champs associés au fournisseur et aux produits, comme lorsque vous créez une nouvelle commande manuellement. Par exemple, si vous définissez **Copier précisément** sur *Oui* et copiez une commande qui remplace le compte de facturation par défaut du fournisseur, le même compte de facturation sera copié dans votre nouvelle commande. Si vous définissez **Copier précisément** sur *Non*, le compte de facturation par défaut du fournisseur sera utilisé à la place dans votre nouvelle commande. Les valeurs des champs suivants sont copiées lorsque **Copier précisément** est défini sur *Oui* :
        - Langue
        - Conditions de paiement
        - Mode de paiement
        - Spécification de paiement
        - Groupe souche de numéros
        - Escompte de règlement
        - Pourcentage de remise
        - Devise
        - Conditions de livraison
        - Mode de livraison
        - Dimension
        - Groupe de taxe de vente
        - Remplacer la taxe
        - Prix, taxe incluse
        - Transport
        - Port
        - Régime DEB
        - ID modèle
        - Nom de livraison
        - Adresse postale
        - Référence
        - ID table de référence
    - L’option **Supprimer des lignes d’achat** supprime toutes les lignes de commandes fournisseur qui existent déjà sur la commande fournisseur dans laquelle vous copiez, avant d’appliquer les nouvelles lignes. Utilisez cette option avec prudence, en effet elle supprime toutes les lignes existantes sans que vous en soyez averti.  
    - Si vous utilisez l’option **Copier l’en-tête de commande**, vous n’avez pas besoin de créer manuellement les informations d’en-tête sur votre nouvelle commande. Cette option entraînera l’utilisation des valeurs par défaut pour les champs associés au fournisseur. Si le document à partir duquel vous copiez contient des valeurs non définies par défaut que vous voulez copier, utilisez également l’option **Copier précisément**.
    - Il y a des sources de documents différentes à partir desquelles vous pouvez copier, chacune contient une section distincte sur cette page. Par exemple, la section **Commandes fournisseur** vous permet de copier à partir de commandes fournisseur existantes.  

1. Dans la section **Commandes fournisseur**, sélectionnez les lignes que vous voulez copier dans le Presse-papiers. Il est possible de choisir des lignes de commande fournisseur supplémentaires à partir d’autres commandes fournisseur et de les copier également sur votre commande. Il est également possible d’ajouter des lignes à partir d’autres types de documents d’achat. Les quelques étapes suivantes passent en revue les différentes options.  
1. Développez la section **Confirmation**. Vous pouvez sélectionner ici des confirmations de commandes fournisseur à partir desquelles copier. Les confirmations de commandes fournisseur sont identifiées par l’ID journal d’achat ou l’ID commande fournisseur.  
1. Développez la section **Accusés de réception de marchandises**. Vous pouvez sélectionner ici des journaux d’accusés de réception de marchandises à partir desquels copier. Les journaux d’accusés de réception de marchandises sont identifiés par le N° document d’accusé de réception de marchandises ou l’ID commande fournisseur.
1. Développez la section **Factures**. Ici vous pouvez choisir des factures fournisseur à partir desquelles copier. Ces factures sont identifiées par le N° document de facture ou l’ID commande fournisseur.
1. Développez la section **Lignes ou en-têtes sélectionnés à copier**. Cette vue montre un résumé de tous les documents et des lignes qui ont été sélectionnés pour être copiés dans votre commande.
1. Cliquez sur **OK**. Les 4 lignes que vous avez choisies ont été copiées sur votre nouvelle commande fournisseur.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copier les lignes dans une commande fournisseur existante  

Au lieu de copier une commande complète, il est plus courant de créer une nouvelle CF et de renseigner les informations sur l’en-tête de la CF, puis de copier chaque ligne à partir des commandes existantes.  

1. Sélectionnez la ligne **Commande fournisseur**.
1. Sélectionnez **À partir de tous**. La page qui s’ouvre est identique à celle montrée avant, mais différentes options sont choisies quand elle s’ouvre à partir de la vue des lignes de commande. Examinons les paramètres.
1. Développez la section **Paramètres**.

    - L’option **Supprimer les lignes d’achat** n’est pas sélectionnée. Ceci signifie que vous pouvez copier de nouvelles lignes dans votre commande sans supprimer les lignes existantes.
    - L’option **Copier l’en-tête de commande** n’est pas choisie non plus, car nous ajoutons seulement des lignes supplémentaires à la commande.
    - Pour cet exemple, nous copierons des lignes d’une commande fournisseur existante.

1. Sélectionnez la ligne pour la ligne de commande fournisseur souhaitée. Notez que la ligne de commande unique qui est sur cette commande fournisseur est également sélectionnée.  
1. Cliquez sur **OK**. La ligne de commande supplémentaire a été ajoutée à votre commande fournisseur.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]