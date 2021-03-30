---
title: Rapprochement de relevés bancaires à l’aide du rapprochement bancaire avancé
description: La fonctionnalité de rapprochement bancaire avancé permet d’importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 Finance. Cette rubrique explique le processus de rapprochement.
author: saraschi2
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationWorksheet
audience: Application User
ms.reviewer: roschlom
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95c216d59cb5eadb24aa0ca00ab53866d697e6c2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226459"
---
# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Rapprochement de relevés bancaires à l’aide du rapprochement bancaire avancé

[!include [banner](../includes/banner.md)]

La fonctionnalité de rapprochement bancaire avancé permet d’importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Dynamics 365 Finance. Cette rubrique explique le processus de rapprochement.  

<a name="import-an-electronic-bank-statement"></a>Importer un relevé bancaire électronique
-----------------------------------

Vous importez vos relevés bancaires à l’aide de l’action **Importer un relevé** sur la page **Relevés bancaires**. Sur le relevé bancaire, le compte bancaire est identifié grâce à une combinaison de valeurs qui sont définies sur les détails du compte bancaire. Ces valeurs comprennent le nom de la banque, le numéro du compte bancaire, le numéro de routage, le code SWIFT et le numéro IBAN. 

Vous pouvez télécharger un relevé bancaire qui contient des informations pour un ou plusieurs comptes. S’il existe plusieurs comptes, les comptes peuvent être dans plusieurs entités juridiques.

-   Pour importer un fichier de relevé bancaire unique pour un seul compte, définissez l’option **Importer le relevé bancaire pour plusieurs comptes bancaires dans toutes les entités juridiques** sur **Non** et sélectionnez le compte bancaire associé au relevé. Cliquez sur **Parcourir** pour sélectionner le fichier de relevé bancaire associé, puis cliquez sur **Télécharger**.
-   Pour importer un fichier de relevé bancaire unique pour plusieurs comptes, définissez l’option **Importer le relevé bancaire pour plusieurs comptes bancaires dans toutes les entités juridiques** sur **Oui**. Cliquez sur **Parcourir** pour sélectionner le fichier de relevé bancaire associé, puis cliquez sur **Télécharger**.

Si des relevés du fichier électronique ne peuvent pas être associés à un compte bancaire ou s’ils sont associés à plusieurs comptes bancaires l’aide des champs d’identification, ils ne seront pas importés. Toutefois, les autres relevés du fichier peuvent encore être importés. L’utilisateur reçoit un message indiquant que l’importation des relevés bancaires était un échec pour des comptes bancaires spécifiques. Notez que l’utilisateur qui importe le fichier de relevé bancaire doit avoir accès à une entité juridique pour importer les relevés des comptes bancaires de cette entité juridique. 

Vous pouvez utiliser un fichier compressé pour télécharger plusieurs fichiers de relevé dans Finance en un seul processus. Pour importer plusieurs fichiers de relevé bancaire pour plusieurs comptes, combinez tous les fichiers de relevé bancaire en un seul fichier zip. Dans la boîte de dialogue **Importez les relevés bancaires**, définissez l’option **Importer le relevé bancaire pour plusieurs comptes bancaires dans toutes les entités juridiques** sur **Oui**. Cliquez sur **Parcourir** pour sélectionner le fichier zip contenant les fichiers de relevé bancaire, puis cliquez sur **Télécharger**. Le processus d’importation identifiera le fichier compressé et téléchargera chaque relevé inclus dans celui-ci, indépendamment de l’entité juridique du compte bancaire.

Une option **Rapprocher après importation** est disponible. Lorsque vous définissez cette option sur **Oui**, le système valide automatiquement le relevé bancaire, crée un nouveau rapprochement bancaire et une feuille de calcul et exécute l’ensemble de règles de correspondance par défaut quand le relevé bancaire est chargé. Cette fonctionnalité automatise le processus jusqu’au point où les transactions doivent être manuellement mises en correspondance.

## <a name="validate-the-bank-statement"></a>Valider le relevé bancaire
Pour valider un relevé, cliquez sur **Valider** sur la page **Relevés bancaires**. Les relevés bancaires doivent être validés avant de pouvoir être rapprochés. Cette étape est effectuée automatiquement si vous avez défini l’option **Rapprocher après l’importation** sur **Oui** au moment de l’importation. 

La validation du relevé bancaire permet de vérifier les informations suivantes :

-   Le relevé bancaire correspond au compte bancaire sélectionné.
-   La devise du relevé bancaire correspond à la devise du compte bancaire sélectionné.
-   Le solde d’ouverture du relevé correspond au solde de clôture du relevé précédent du compte bancaire.
-   La date ne chevauche pas la date d’un autre relevé bancaire pour le même compte bancaire.
-   Il n’existe aucun écart dans les dates de relevés pour le compte bancaire.
-   Les dates sur les lignes du relevé se situent entre la date de début et de date de fin du relevé bancaire.
-   Le solde d’ouverture et les montants des lignes récapitulatives sont égaux au solde de fin.

Lorsque la validation est terminée, le statut du relevé bancaire est mis à jour sur **Validé**. Un relevé bancaire doit être validé avant de pouvoir être rapproché.

## <a name="reconcile-the-bank-statement"></a>Rapprochez le relevé bancaire.
Une fois que vous avez importé un relevé bancaire électronique et validé le relevé sur la page **Relevés bancaires**, vous pouvez rapprocher le relevé bancaire à l’aide des pages **Rapprochement bancaire** et **Feuille de calcul de rapprochement bancaire**. 

Sur la page **Rapprochement bancaire**, cliquez sur **Nouveau** pour créer un rapprochement, puis sélectionnez le compte bancaire du relevé qui a été importé. Un compte bancaire peut avoir uniquement un rapprochement bancaire en cours. La date limite détermine les transactions de relevé bancaire et les transactions bancaires d’Operations qui figurent sur la feuille de calcul de rapprochement. Par défaut, la date système actuelle est utilisée comme date limite, mais vous pouvez modifier la date de rapprochement. Les informations d’en-tête restantes sont automatiquement extraites du relevé. Cette étape est effectuée automatiquement si vous avez défini l’option **Rapprocher après l’importation** sur **Oui** au moment de l’importation. 

Sur la page **Rapprochement bancaire**, cliquez sur **Feuille de calcul** pour ouvrir la page **Feuille de calcul de rapprochement bancaire**. Si vous avez défini l’option **Rapprocher après l’importation** sur **Oui**, l’ensemble de règles de correspondance par défaut est exécuté automatiquement pour le rapprochement. Pour exécuter manuellement des règles de correspondance, cliquez sur **Exécuter les règles de correspondance** pour sélectionner les ensembles de règles de correspondance ou les règles de correspondance à vérifier par rapport aux relevés bancaires. Si vous avez de nombreuses transactions à traiter, vous pouvez effectuer cette étape sous forme de traitement par lots. 

La page **Feuille de calcul de rapprochement bancaire** comporte quatre grilles qui contiennent des transactions. Les deux grilles supérieures affichent les transactions du relevé bancaire et d’Operations qui n’ont pas encore été associées. Les deux grilles inférieures affichent les transactions rapprochées. L’onglet **Détails de transaction de relevé bancaire** affiche les détails de la transaction de relevé bancaire non rapprochée qui est sélectionnée dans la grille supérieure. 

Il existe trois méthodes pour mettre en correspondance ou pour rapprocher des transactions de relevé bancaire :

-   Mettre en correspondance les transactions avec les transactions bancaires Operations.
-   Mettre en correspondance les transactions avec une transaction de relevé bancaire de contrepassation.
-   Marquer les transactions comme **Nouveau**, afin de les valider ultérieurement comme transactions bancaires dans Finance.

Pour mettre en correspondance des transactions manuellement, sélectionnez les transactions dans la grille **Transactions de relevé bancaire**, sélectionnez les transactions correspondantes dans la grille **Transactions bancaires Operations**, puis cliquez sur **Correspondance**. Les transactions sélectionnées sont déplacées dans les grilles supérieures pour les opérations non rapprochées vers les grilles inférieures pour les transactions rapprochées. En outre, le total des montants rapprochés et non rapprochés sont mis à jour. Vous pouvez avoir des correspondances de transactions une à une, plusieurs-à-une et plusieurs-à-plusieurs. Les correspondances doivent suivre les règles de différences de dates autorisées et de mappage de type de transaction. Ces règles sont définies sur la page **Paramètres de gestion de la trésorerie et de la banque**.

Des différences minimes peuvent se produire pendant le rapprochement. Vous pouvez mettre en correspondance une transaction de relevé bancaire unique et une transaction bancaire Operations unique qui présentent des différences minimes si celles-ci sont comprises dans le montant de tolérance défini par le champ **Différence minime autorisée** sur le compte bancaire. Le montant est affiché dans le champ **Montant de la correction** de la transaction bancaire Operations mise en correspondance. Lorsque le rapprochement bancaire est marqué comme rapproché, les corrections sont automatiquement validées à l’aide du compte principal défini dans le type de transaction bancaire associé. Les corrections ne sont pas prises en charge pour les types de document **Chèque** et **Dépôt**. 

Les contrepassations de transaction de relevé bancaire sont mises en correspondance à l’aide de la feuille de calcul de rapprochement. Deux lignes de relevé peuvent être mises en correspondance si les montants sont opposés, et si l’une des transactions est marquée comme une contrepassation. Vous pouvez également définir une règle de correspondance pour l’action **Effacer les lignes de relevés de contrepassation**.

Les transactions bancaires Operations de contrepassation doivent être rapprochées à l’aide de la page **Transactions bancaires Operations**. Vous pouvez rapprocher deux transactions bancaires Operations ensemble si les documents ont un compte bancaire, un type de document et une référence de paiement identiques, et s’ils ont des montants opposés. Vous pouvez également rapprocher un chèque annulé unique pour empêcher ces transactions de figurer sur la feuille de calcul de rapprochement. 

S’il y a des transactions initiées par la banque, telles que des intérêts, des commissions et des frais, qui ne sont pas encore dans Finance, vous pouvez les ajouter à un journal associé au rapprochement de relevé bancaire sélectionné. Sélectionnez une transaction de relevé bancaire dans la grille **Transactions de relevé bancaire** pour les opérations non rapprochées, puis cliquez sur **Marquer comme nouveau**. Le statut de la transaction est défini sur **Nouveau**, et la transaction est déplacée vers la grille **Transactions de relevé bancaire** pour les transactions rapprochées. Vous validez les transactions marquées **Nouveau** ultérieurement, à partir de la page **Relevé bancaire**. 

Vous pouvez supprimer la mise en correspondance des transactions qui ont été rapprochées incorrectement. Sélectionnez la transaction de relevé bancaire correspondante, puis cliquez sur **Sans correspondance**. Toutes les transactions associées sont déplacées vers les grilles supérieures pour les opérations non rapprochées, et le total des montants correspondants et sans correspondance sont mis à jour. 

Après avoir effectué votre processus de rapprochement, vous devez marquer la feuille de calcul de rapprochement bancaire comme étant rapprochée.  Ce processus valide automatiquement les montants de correction à l’aide des comptes définis sur la page **Type de transaction bancaire**.  Le rapprochement bancaire pour un relevé peut être marqué comme rapproché à tout moment, même s’il existe des lignes de relevé bancaire qui n’ont pas encore été rapprochées.  Les transactions qui ne correspondent pas passeront automatiquement à la prochaine feuille de calcul de rapprochement en tant que transactions de relevé de compte non rapprochées à rapprocher.  Notez qu’une fois qu’un rapprochement de relevé bancaire a été marqué comme rapproché, il ne peut pas être annulé.  Le rapprochement ne sera plus modifiable et vous n’aurez plus la possibilité de mettre à jour ce rapprochement.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Valider les transactions associées au rapprochement
Les transactions de relevé bancaire qui vous avez marquées comme **Nouveau** sur la feuille de calcul de rapprochement sont validées sur la page **Relevé bancaire**. Sur la page **Relevé bancaire**, sélectionnez l’ID de relevé pour afficher les détails du relevé. Sur le menu **Comptabilité**, vous pouvez utiliser les options **Afficher les distributions** et **Afficher la comptabilité** pour afficher des détails sur les nouvelles transactions et les écritures comptables associées. Sélectionnez l’option **Valider** pour valider les lignes de relevé bancaire qui sont marquées comme **Nouveau** dans la comptabilité. Notez que la validation ne peut être effectuée qu’une seule fois par relevé bancaire.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]