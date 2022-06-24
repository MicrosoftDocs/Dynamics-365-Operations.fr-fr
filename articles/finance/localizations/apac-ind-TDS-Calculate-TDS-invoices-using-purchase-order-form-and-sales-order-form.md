---
title: Calculer les factures TDS à l’aide du formulaire de commande fournisseur et du formulaire de commande client
description: Cet article répertorie les étapes de calcul de la taxe déduite à la source (TDS) sur différents types de factures.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 72883741ee7eed6b0296736c80dd648c882ae53e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853283"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>Calculer les factures TDS à l’aide du formulaire de commande fournisseur et du formulaire de commande client

[!include [banner](../includes/banner.md)]

Cet article répertorie les étapes de calcul de la taxe déduite à la source (TDS) sur différents types de factures à l’aide des pages **Commande fournisseur**, **Journal des achats**, **Commande globale** et **Commande client**.

1. Créez une commande fournisseur, un journal d’achats, une commande fournisseur globale ou une commande client à l’aide de la page répertoriée. Entrez les détails requis.

2. Sélectionnez l’onglet **Installer** pour afficher la nature de la personne évaluée du fournisseur ou du client. Ces informations sont répertoriées dans le champ **Nature de la personne évaluée**, sous le champ **Groupe de retenue à la source**.

3. Dans le champ **Groupe TDS**, affichez ou modifiez le groupe TDS par défaut défini pour le fournisseur ou le client.

   > [!NOTE]
   > Le champ **Groupe TCS** n’est pas disponible lorsque vous sélectionnez un groupe TDS dans le champ **Groupe TDS**. TDS est calculé uniquement si la case **Calcul de la retenue à la source** est cochée pour le fournisseur ou le client sur la page **Tous les fournisseurs** ou **Tous les clients**.  

4. Créez des lignes d’articles dans l’onglet **Lignes** et entrez les détails requis.

5. Sélectionnez l’onglet **Configurer** (au niveau de la ligne) pour afficher ou modifier le groupe TDS défini au niveau de l’en-tête. Le groupe TDS s’affiche dans le champ **Groupe TDS**, qui est sous le groupe de champs **Groupe de retenue à la source**.

6. Sélectionnez l’onglet **Informations fiscales** et sélectionnez les adresses alternatives configurées pour le nom de la société affiché dans ce champ. Le nom de l’entreprise s’affiche dans le champ **Nom**, qui est sous le groupe de champs **Informations sur la société**. 

   Le TAN du nom de l’entreprise sélectionné s’affiche dans le champ **Numéro de compte fiscal** (**TAN**), sous le groupe de champs **Retenue à la source**. 

7. Sélectionnez **Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**. Affichez les champs suivants dans le volet supérieur de la page **Opérations de retenue à la source temporaire**.

   - **Montant** **total de la** **retenue** **à la** **source** - TDS total calculé pour la transaction pour le groupe TDS.

   - **Valeur** - Pourcentage total utilisé pour calculer TDS pour la transaction. Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.

   - **Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.

   - **TDS** - Si cette option est sélectionnée, un groupe TDS est attaché à la transaction.

Les champs des onglets **Aperçu**, **Général** et **Ajustement** dans la page **Opérations de retenue à la source temporaire** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.

8. Sélectionnez **Seuil** pour ouvrir la page **Seuil**. Consultez la limite de seuil définie pour la composant de taxe TDS associée à un code de taxe TDS spécifique sur cette page.

9. Sélectionnez **Concepteur de formule** pour ouvrir la page **Concepteur de formule**. Consultez la formule définie pour un code de taxe TDS spécifique sur cette page. 

10. Validez la facture. Le montant TDS calculé sur les factures d’achat est enregistré sur le compte fournisseur et le montant TDS calculé sur les factures de vente est enregistré sur le compte client défini pour chaque code TVA TDS du groupe TDS. Les comptes clients et fournisseurs pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.

11. Sélectionnez le bouton **Recherche** **> Facture > Retenue à la source validée** pour ouvrir la page **Opérations de retenue à la source**. Vous pouvez afficher le pourcentage total qui a été utilisé pour calculer TDS pour la transaction dans le champ **Valeur**.

Les onglets **Aperçu**, **Général** et **Montant** sur la page **Opérations de retenue à la source** affichent les informations de TDS calculées pour la transaction. Affichez les informations de calcul TDS pour chaque code de taxe TDS associé au groupe TDS.
