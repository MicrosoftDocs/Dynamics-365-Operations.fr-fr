---
title: Importer des données d'une filiale à partir de fichiers
description: Cette rubrique explique comment préparer les données de systèmes externes afin qu'elles puissent être importées dans Microsoft Dynamics 365 Finance.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: f8e220599d8df9f560da1862f0909cbbaa3c7330
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249093"
---
# <a name="import-subsidiary-data-from-files"></a>Importer des données d'une filiale à partir de fichiers

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment préparer les données de systèmes externes afin qu'elles puissent être importées dans Microsoft Dynamics 365 Finance. Vous devez utiliser la page **Consolider avec l'importation** (**Consolidations \> Consolider avec l'importation**) pour préparer le transfert de données d'une filiale à partir de systèmes externes.

1. Créez l'entité juridique de succursale pour la consolidation. Pour plus d’informations sur la création d’entités juridiques, consultez [Créer une entité juridique](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Pour plus d'informations, voir [Préparer une entité juridique en vue de son utilisation dans le processus de consolidation](prepare-company-for-consolidation.md) et [Paramétrer une entité juridique filiale pour la consolidation](set-up-subsidiary-company-for-consolidation.md).

2. Préparez un fichier qui contiendra les données importées. Pour plus d’informations sur le processus d'importation, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Exportez les données dans un fichier en suivant les étapes du « Processus d’importation et d’exportation de données » dans [Vue d’ensemble de tâches d’importation et d’exportation de données](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Vous pouvez utiliser ce processus pour consolider les données à partir d'une autre instance de Dynamics 365 Finance ou de Dynamics 365 Business Central. Si vous importez des données à partir de systèmes externes, elles doivent être au format décrit dans [Exportation des données d'une filiale dans des fichiers](export-subsidiary-data-to-file.md).
4. Allez dans **Consolidations \> Consolider avec importation**. Sur la page **Consolider avec importation**, sur l'onglet **Critères**, spécifiez les détails de l'état et/ou de l'importation en définissant les champs suivants.

    | Champ                                 | Valeur de l'état | Valeur de l'importation |
    |---------------------------------------|----------------------|----------------------|
    | Description                           | Non applicable | Entrez une description afin d'identifier l'importation. |
    | Compte principal                          | Définissez la plage de comptes que le rapport doit inclure. Si vous ne définissez pas de plage, tous les comptes seront inclus. | Définissez la plage de comptes que l'importation doit inclure. Si vous ne définissez pas de plage, tous les comptes seront inclus. |
    | Période de consolidation                  | Définissez la plage de dates à consolider. | Définissez la plage de dates à consolider. |
    | Inclure les montants réels                | Définissez cette option sur **Oui** pour inclure les chiffres réels. | Définissez cette option sur **Oui** pour inclure les chiffres réels. |
    | Inclure les montants du budget                | Définissez cette option sur **Oui** pour inclure les montants budgétaires dans les consolidations. | Définissez cette option sur **Oui** pour inclure les montants budgétaires dans les consolidations. |
    | Regénérer les soldes lors du processus de consolidation | Définissez cette option sur **Oui** si le processus de régénération doit effacer complètement le solde et les nouveaux enregistrements, et recréer le solde depuis le début. | Définissez cette option sur **Oui** si le processus de régénération doit effacer complètement le solde et les nouveaux enregistrements, et recréer le solde depuis le début. |
    | Modèles de budget                         | Non applicable | Si vous avez choisi d'importer les montants budgétaires, entrez les modèles à consolider. |
    | Type de taux du budget                      | Non applicable | Entrez le type de taux de change du budget. |

6. Si vous avez des devises comptables différentes, utilisez les champs de l'onglet **Conversion de devises** pour configurer la traduction effectuée lors de la consolidation.

    | Champ                      | Description  |
    |----------------------------|-------------|
    | Entité juridique source        | Sélectionnez l'entité juridique à partir de laquelle vous importez. |
    | Devise comptable source | Cette devise par défaut est la devise associée à l'entité juridique source que vous avez sélectionnée dans le champ **Entité juridique source**. |
    | Comptes De et À       | Définissez la plage de comptes à importer à partir de l'entité juridique source. |
    | Type de taux de change         | Sélectionnez le type de taux de change. Les types de taux de change sont attribués lorsque vous créez un compte principal. Pour plus d’informations, voir [Créer un compte principal](tasks/create-main-account.md). |
    | Appliquer le taux de change de   | Saisissez une date pour appliquer le taux de change en vigueur à cette date. Vous pouvez également saisir la valeur à utiliser comme taux de change. |
    | Taux de change              | La valeur par défaut dépend du type de taux de change sélectionné dans le champ **Type de taux de change**. Si vous avez entré un taux de change défini par l'utilisateur, vous pouvez définir un taux. |

7. Définissez l'option **Exécuter en arrière-plan** sur **Oui** pour permettre au processus d'importation de s'exécuter en arrière-plan.
8. Définissez l'option **Traitement par lots** sur **Oui** pour exécuter la consolidation comme un traitement par lots à un moment précis. Pour exécuter la consolidation immédiatement, sélectionnez **OK**. 

Les transactions et soldes spécifiés pour la consolidation dans les filiales sont ajoutés aux comptes appropriés dans l'entité juridique consolidée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]