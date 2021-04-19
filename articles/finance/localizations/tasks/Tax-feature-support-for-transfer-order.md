---
title: Prise en charge de la fonction de taxe pour les ordres de transfert
description: Cette rubrique explique la prise en charge de la nouvelle fonctionnalité de taxe pour les ordres de transfert à l’aide du service de calcul des taxes.
author: kailiang
ms.date: 03/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 55597e4f0f40677e793b4c182e4b0ced01057751
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832559"
---
# <a name="tax-feature-support-for-transfer-orders"></a>Prise en charge de la fonction de taxe pour les ordres de transfert

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Cette rubrique fournit des informations sur le calcul des taxes et l’intégration de la validation dans les ordres de transfert. Cette fonctionnalité vous permet de configurer le calcul et la validation des taxes dans les ordres de transfert pour les transferts de stock. En vertu de la réglementation de l’Union européenne (UE) sur la taxe sur la valeur ajoutée (TVA), les transferts de stock sont considérés comme des livraisons intracommunautaires et des acquisitions intracommunautaires.

Pour configurer et utiliser cette fonctionnalité, vous devez effectuer trois étapes principales :

1. **Configuration RCS :** dans Regulatory Configuration Service, configurez la fonctionnalité de taxe, les codes taxe et l’applicabilité des codes taxe pour la détermination du code taxe dans les ordres de transfert.
2. **Configuration Finance :** dans Microsoft Dynamics 365 Finance, activez la fonctionnalité **Taxe dans l’ordre de transfert**, configurez les paramètres du service de taxe pour le stock et configurez les paramètres fiscaux de base.
3. **Configuration du stock :** paramétrez la configuration du stock pour les transactions d’ordre de transfert.

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a>Configurer RCS pour les taxes et les transactions d’ordre de transfert

Suivez ces étapes pour configurer la taxe impliquée dans un ordre de transfert. Dans l’exemple présenté ici, l’ordre de transfert va des Pays-Bas vers la Belgique.

1. Sur la page **Fonctionnalité de taxe**, sur l’onglet **Versions**, sélectionnez la version provisoire de la fonctionnalité, puis sélectionnez **Modifier**.

    ![Sélection de Modifier](../media/image1.png)

2. Sur la page **Configuration des fonctionnalités de taxe**, sur l’onglet **Codes taxe**, sélectionnez **Ajouter** pour créer de nouveaux codes taxe. Pour cet exemple, trois codes taxe sont créés : **NL-Exempt**, **BE-RC-21** et **BE-RC+21**.

    - Lorsqu’un ordre de transfert est expédié depuis un entrepôt aux Pays-Bas, le code d’exonération de TVA néerlandais (**NL-Exempt**) est appliqué.
      
        Créez le code taxe **NL-Exempt**.
        1. Sélectionnez **Ajouter**, entrez **NL-Exempt** dans le champ **Code taxe**.
        2. Sélectionnez **Par montant net** dans le champ **Composant de taxe**.
        3. Sélectionnez **Enregistrer**.
        4. Sélectionnez **Ajouter** dans la table **Taux**.
        5. Faites basculer l’option **Est exonéré** sur **Oui** dans la section **Général**.

        ![Code taxe NL-Exempt](../media/image2.png)

    - Lorsqu’un ordre de transfert est reçu dans un entrepôt de Belgique, le mécanisme de taxe au preneur est appliqué en utilisant les codes taxe **BE-RC-21** et **BE-RC+21**.
        
        Créez le code taxe **BE-RC-21**.      
        1. Sélectionnez **Ajouter**, entrez **BE-RC-21** dans le champ **Code taxe**.
        2. Sélectionnez **Par montant net** dans le champ **Composant de taxe**.
        3. Sélectionnez **Enregistrer**.
        4. Sélectionnez **Ajouter** dans la table **Taux**.
        5. Entrez **-21** dans le champ **Taux de taxe**.
        6. Faites basculer l’option **Est une taxe au preneur** sur **Oui** dans la section **Général**.
        7. Sélectionnez **Enregistrer**.

        ![Code taxe BE-RC-21 pour les taxes au preneur](../media/image3.png)
        
        Créez le code taxe **BE-RC+21**.
        1. Sélectionnez **Ajouter**, entrez **BE-RC-21** dans le champ **Code taxe**.
        2. Sélectionnez **Par montant net** dans le champ **Composant de taxe**.
        3. Sélectionnez **Enregistrer**.
        4. Sélectionnez **Ajouter** dans la table **Taux**.
        5. Entrez **21** dans le champ **Taux de taxe**.
        6. Sélectionnez **Enregistrer**.

        ![Code taxe BE-RC+21 pour les taxes au preneur](../media/image4.png)

3. Définissez l’applicabilité des codes taxe.

    1. Sélectionnez **Gérer les colonnes**, puis sélectionnez les colonnes à utiliser pour créer le tableau d’applicabilité.

        > [!NOTE]
        > Assurez-vous d’ajouter les colonnes **Processus d’entreprise** et **Directions de taxe** à la table. Les deux colonnes sont essentielles à la fonctionnalité de taxe dans les ordres de transfert.

    2. Ajoutez des règles d’applicabilité. Ne laissez pas vides les champs **Codes taxe**, **Groupe de taxes** et **Groupe de taxes d’article**.
        
        Ajoutez une nouvelle règle pour l’expédition des ordres de transfert.
        1. Sélectionnez **Ajouter** dans la table **Règles d’applicabilité**.
        2. Dans le champ **Processus d’entreprise**, sélectionnez **Stock** pour rendre la règle applicable à un ordre de transfert.
        3. Dans le champ **Expédier depuis le pays/ la région**, entrez **NLD**.
        4. Dans le champ **Expédier vers le pays/ la région**, entrez **BEL**.
        5. Dans le champ **Direction de taxe**, sélectionnez **Sortie** pour rendre la règle applicable à l’expédition des ordres de transfert.
        6. Dans le champ **Codes taxe**, sélectionnez **NL-Exempt**.
        7. Dans les champs **Groupe de taxes** et **Groupe de taxes d’article**, saisissez le groupe de taxes de vente et le groupe de taxes de vente d’article associés qui sont définis dans votre système Finance.
        
        Ajoutez une autre règle pour la réception des ordres de transfert.
        1. Sélectionnez **Ajouter** dans la table **Règles d’applicabilité**.
        2. Dans le champ **Processus d’entreprise**, sélectionnez **Stock** pour rendre la règle applicable à un ordre de transfert.
        3. Dans le champ **Expédier depuis le pays/ la région**, entrez **NLD**.
        4. Dans le champ **Expédier vers le pays/ la région**, entrez **BEL**.
        5. Dans le champ **Direction de taxe**, sélectionnez **Entrée** pour rendre la règle applicable à la réception des ordres de transfert.
        6. Dans le champ **Codes taxe**, sélectionnez **BE-RC+21** et **BE-RC-21**.
        7. Dans les champs **Groupe de taxes** et **Groupe de taxes d’article**, saisissez le groupe de taxes de vente et le groupe de taxes de vente d’article associés qui sont définis dans votre système Finance.

        ![Règles d’applicabilité](../media/image5.png)

4. Complétez et publiez la nouvelle version de la fonctionnalité de taxe.

    [![Changer le statut de la nouvelle version](../media/image6.png)](../media/image6.png)

## <a name="set-up-finance-for-transfer-order-transactions"></a>Configurer Finance pour les transactions d’ordre de transfert

Procédez comme suit pour activer et paramétrer les taxes pour les ordres de transfert.

1. Dans Finance, accédez à **Espaces de travail** \> **Gestion des fonctionnalités**.
2. Dans la liste, recherchez et sélectionnez la fonctionnalité **Taxe dans l’ordre de transfert**, puis sélectionnez **Activer maintenant** pour l’activer.

    > [!IMPORTANT]
    > La fonctionnalité **Taxe dans l’ordre de transfert** dépend entièrement du service de taxe. Par conséquent, elle ne peut être activée qu’après avoir installé le service de taxe.

    ![Fonctionnalités Taxe dans l’ordre de transfert](../media/image7.png)

3. Activez le service de taxe et sélectionnez le processus d’entreprise **Inventaire**.

    > [!IMPORTANT]
    > Vous devez effectuer cette étape pour chaque entité juridique dans Finance pour laquelle vous souhaitez rendre disponibles le service de taxe et la fonctionnalité de taxe dans les ordres de transfert.

    1. Accédez à **Taxe** \> **Paramétrage** \> **Configuration de taxe** \> **Configuration du service de taxe**.
    2. Dans le champ **Processus d’entreprise**, sélectionnez **Inventaire**.

    ![Définition du champ Processus d’entreprise](../media/image8.png)

4. Vérifiez que le mécanisme de taxe au preneur est configuré. Accédez à **Comptabilité** \> **Paramétrage** \> **Paramètres** puis, sur l’onglet **Taxe au preneur**, vérifiez que l’option **Activer la taxe au preneur** est définie sur **Oui**.

    ![Activer l’option de taxe au preneur](../media/image9.png)

5. Vérifiez que les codes taxe, les groupes de taxe, les groupes de taxes d’article et les numéros d’immatriculation de TVA associés ont été configurés dans Finance conformément aux instructions du service de taxe.
6. Créez un compte de transit provisoire. Cette étape n’est requise que lorsque la taxe appliquée à un ordre de transfert n’est pas applicable à un mécanisme d’exonération de taxe ou de taxe au preneur.

    1. Accédez à **Taxe** \> **Paramétrage** \> **Taxe de vente** \> **Groupes de validations dans la comptabilité**.
    2. Dans le champ **Transit provisoire**, sélectionnez un compte général.

    ![Sélection d’un compte de transit provisoire](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a>Configurer l’inventaire de base pour les transactions d’ordre de transfert

Suivez ces étapes pour configurer l’inventaire de base afin d’activer les transactions d’ordres de transfert.

1. Créez des sites d’expédition et de livraison pour vos entrepôts dans différents pays ou régions, et ajoutez l’adresse principale de chaque site.

    1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Entrepôt** \> **Sites**.
    2. Sélectionnez **Nouveau** pour créer le site que vous attribuerez ultérieurement à un entrepôt.
    3. Répétez l’étape 2 pour tous les autres sites que vous devez créer.

    > [!NOTE]
    > L’un des sites que vous créez doit être nommé **Transit**. Dans les étapes ultérieures de cette procédure, vous affecterez ce site à l’entrepôt de transit, de sorte que les documents d’inventaire liés à la taxe puissent être validés dans les transactions « expédition » et « réception » pour les ordres de transfert. L’adresse du site de transit n’a pas d’importance pour le calcul de la taxe. Par conséquent, vous ne pouvez pas le laisser vide.

    ![Paramétrage des sites](../media/image11.png)

2. Créez des entrepôts d’expédition, de transit et de livraison. Les informations d’adresse conservées dans un entrepôt remplaceront l’adresse du site lors du calcul de la taxe.

    1. Accédez à **Gestion des entrepôts** \> **Configuration** \> **Entrepôt** \> **Entrepôts**.
    2. Sélectionnez **Nouveau** pour créer un entrepôt et affectez-le au site correspondant.
    3. Répétez l’étape 2 pour créer un entrepôt pour chaque site, selon les besoins.

    ![Paramétrage d’entrepôts](../media/image12.png)

    > [!NOTE]
    > Pour un entrepôt d’expédition, un entrepôt de transit doit être sélectionné dans le champ **Entrepôt de transit** pour les transactions d’ordre de transfert.
    >
    > ![Sélection d’un entrepôt de transit](../media/image13.png)

3. Vérifiez que la configuration de la validation du stock est paramétrée pour les transactions d’ordre de transfert.

    1. Accédez à **Gestion des stocks** \> **Paramétrage** \> **Validation** \> **Validation**.
    2. Sur l’onglet **Inventaire**, vérifiez qu’un compte général est configuré pour les deux validations **Sortie de stock** et **Réception de stock**.

        ![Configuration des validations Sortie de stock et Réception de stock](../media/image14.png)

    3. Vérifiez qu’un compte général est configuré pour la validation **Somme à payer entre unités**.

        ![Configuration de la validation Somme à payer entre unités](../media/image15.png)

    4. Vérifiez qu’un compte général est configuré pour la validation **Somme à recevoir entre unités**.

        ![Configuration de la validation Somme à recevoir entre unités](../media/image16.png)
