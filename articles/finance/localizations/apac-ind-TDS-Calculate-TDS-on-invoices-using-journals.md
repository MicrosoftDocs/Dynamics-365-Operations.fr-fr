---
title: Calculer le TDS sur les factures à l'aide de journaux
description: Cette rubrique répertorie les étapes de calcul de la taxe déduite à la source (TDS) relatives aux journaux.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: cfe473f39ee729957924fd7c161aed01138cd507eea56766af35177891676f65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778891"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>Calculer le TDS sur les factures à l'aide de journaux

[!include [banner](../includes/banner.md)]

Cette rubrique répertorie les étapes de calcul de la taxe déduite à la source (TDS) relatives aux journaux.

Commencez par ouvrir la page **Journaux des opérations diverses** (**Comptabilité > Entrées de journal > Journaux des opérations**).

[![Journaux des opérations diverses.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Créez des lignes de journal à l'aide des formulaires de journal répertoriés dans le tableau. Sélectionnez le type de compte et le type de compte de compensation et saisissez le montant de la transaction. 

   > [!NOTE]
   > Sur la page **Journal des approbations de facture**, sélectionnez **Rechercher des N° documents** et sélectionnez les factures sur lesquelles calculer le TDS. Consultez les factures créées dans la page **Registre des factures** ou la page **Rechercher des N° documents**.  

2. Dans l'onglet **Général** de la page **N° document de journal**, affichez ou modifiez le groupe TDS par défaut défini pour le fournisseur ou le client, dans le champ **Groupe TDS**. Le montant TDS calculé sur les lignes de journal est basé sur la formule définie pour les codes TVA TDS dans le champ **Groupe TDS**. 

   > [!NOTE]
   > Le champ **Groupe de retenue à la source** et le champ **Groupe TCS** deviennent indisponibles lorsque vous sélectionnez un groupe TDS dans le champ **Groupe TDS**. Le champ **Groupe de retenue à la source** est disponible uniquement sur la page **Journal des opérations diverses**. TDS est calculé uniquement si la case **Calcul de la retenue à la source** est cochée pour le fournisseur ou le client sur les pages **Tous les fournisseurs** et **Tous les clients**.   

3. Sélectionnez l'onglet **Informations fiscales**. Sélectionnez les adresses alternatives d'une société configurées pour le nom de la société affiché dans ce champ, si nécessaire. Vous pouvez afficher le nom de la société dans le champ **Nom**, qui est sous le groupe de champs **Informations sur la société**. 

4. Affichez la nature de la catégorie du fournisseur ou du client dans le champ **Nature de la personne évaluée**, figurant sous le groupe de champs **Retenue à la source**. Dans le **Numéro de compte fiscal** (**TAN**), affichez le TAN du nom de la société sélectionnée qui est affiché.  

5. Sélectionnez **Retenue à la source** dans le menu **Retenue à la source** pour ouvrir la page **Opérations de retenue à la source temporaire**. Les champs suivants s'affichent dans le volet supérieur de la page **Opérations de retenue à la source temporaire**.

   - **Montant total de la retenue à la source** - TDS total calculé pour la transaction pour le groupe TDS.

   - **Valeur** - Pourcentage total utilisé pour calculer TDS pour la transaction. Le pourcentage total est basé sur la formule définie pour les codes de taxe TDS et attachée au groupe TDS.

   - **Montant de la retenue à la source ajusté au total** - Le montant total ajusté du TDS pour tous les codes de taxe du groupe TDS.

   - **TDS** - Si cette option est sélectionnée, un groupe TDS est attaché à la transaction.

  Les champs des onglets **Aperçu**, **Général** et **Ajustement** dans la page **Opérations de retenue à la source temporaire** affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.

6. Sélectionnez **Seuil** pour ouvrir la page **Seuil**. Consultez la limite de seuil et la limite de seuil d'exception définis pour le composant de taxe TDS associé à un code de taxe TDS spécifique sur cette page.

   Sélectionnez **Concepteur de formule** pour ouvrir l'écran **Concepteur de formule**. Consultez la formule définie pour un code de taxe TDS spécifique sur cette page. Fermez les pages **Concepteur de formule** et **Opérations de retenue à la source temporaire** pour revenir à la page **Justificatif de journal**.

8. Renseignez les informations demandées. Contrôlez et validez le journal. Le montant TDS calculé sur les factures d'achat est imputé au compte fournisseur. Le montant TDS qui a été calculé en fonction des factures client est imputé au compte fournisseur défini pour chaque code TVA TDS du groupe TDS. Les comptes clients et fournisseurs pour les codes TVA TDS sont définis sur la page **Codes de retenue à la source**.

9. Sélectionnez **Retenue à la source validée** pour ouvrir la page **Opérations** **de retenue** **à la source**. Dans le champ **Valeur**, le pourcentage total qui a été utilisé pour calculer TDS pour la transaction s'affiche.

   Les champs des onglets **Aperçu**, **Général** et **Montant** dans la page Opérations de retenue à la source temporaire affichent le montant TDS calculé et les détails du montant TDS ajusté pour chaque code de taxe TDS associé au groupe TDS.
