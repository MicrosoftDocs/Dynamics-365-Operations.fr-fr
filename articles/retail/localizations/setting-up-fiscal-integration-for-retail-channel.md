---
title: Paramétrer l'intégration fiscale pour les canaux de vente au détail
description: Cette rubrique donne des instructions pour paramétrer la fonctionnalité d'intégration fiscale pour les canaux de vente au détail.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 685340141ed35f4a2b57742328c69d3bbf9a73d2
ms.sourcegitcommit: 70aeb93612ccd45ee88c605a1a4b87c469e3ff57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "773325"
---
# <a name="set-up-the-fiscal-integration-for-retail-channels"></a>Paramétrer l'intégration fiscale pour les canaux de vente au détail

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introduction

Cette rubrique donne des instructions pour paramétrer la fonctionnalité d'intégration fiscale pour les canaux de vente au détail. Pour plus d'informations sur l'intégration fiscale, voir [Vue d'ensemble de l'intégration fiscale pour les canaux de vente au détail](fiscal-integration-for-retail-channel.md).

Le processus de paramétrage de l'intégration fiscale inclut les tâches générales suivantes :

1. configuration des connecteurs fiscaux qui représentent les périphériques ou les services fiscaux utilisés à des fins d'enregistrement fiscal, comme les imprimantes fiscales par exemple ;
2. configuration des fournisseurs de documents fiscaux qui seront enregistrés dans les périphériques ou services fiscaux par les connecteurs fiscaux ;
3. configuration du processus d'enregistrement fiscal qui définit une séquence des étapes d'enregistrement fiscal ainsi que les connecteurs fiscaux et les fournisseurs de documents fiscaux utilisés pour chaque étape ;
4. affectation du processus d'enregistrement fiscal aux profils de fonctionnalité du PDV ;
5. affectation des profils techniques de connecteur aux profils matériels.

## <a name="set-up-a-fiscal-registration-process"></a>Configurer un processus d'enregistrement fiscal

Avant d'utiliser la fonctionnalité d'intégration fiscale, vous devez configurer les paramètres suivants :

1. Mettez à jour les paramètres de vente au détail.

    1. Sur la page **Paramètres partagés de la vente au détail**, sous l'onglet **Général**, définissez l'option **Activer l'intégration fiscale** sur **Oui**. Sous l'onglet **Souches de numéros**, définissez les souches de numéros pour les références suivantes :

        - Numéro du profil technique fiscal
        - Numéro du groupe de connecteurs fiscaux
        - Numéro du processus d'enregistrement

    2. Sur la page **Paramètres de vente au détail**, définissez la souche de numéros pour le numéro de profil fonctionnel fiscal.

    > [!NOTE]
    > Les souches de numéros sont facultatives. Les numéros pour toutes les entités d'intégration fiscale peuvent être générés depuis les souches de numéros ou manuellement.

2. Téléchargez les configurations des connecteurs fiscaux et des fournisseurs de documents fiscaux.

    Un fournisseur de documents fiscaux est responsable de la génération des documents fiscaux qui représentent les transactions de vente au détail et les événements enregistrés sur le PDV dans un format également compatible avec un périphérique ou un service fiscal. Par exemple, un fournisseur de documents fiscaux peut générer une représentation de reçu fiscal au format XML.
    
    Un connecteur fiscal est responsable de la communication avec un périphérique ou un service fiscal. Par exemple, un connecteur fiscal peut envoyer un reçu fiscal qu'un fournisseur de documents fiscaux a créé au format XML vers une imprimante fiscale. Pour en savoir plus sur les composants de l'intégration fiscale, voir [Processus d'enregistrement fiscal et exemples d'intégration fiscale pour les périphériques fiscaux](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. Sur la page **Connecteurs fiscaux** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Connecteurs fiscaux**), téléchargez une configuration XML pour chaque périphérique ou service que vous prévoyez d'utiliser à des fins d'intégration fiscale.

        > [!TIP]
        > En sélectionnant **Affichage**, vous pouvez afficher tous les profils fonctionnels et techniques liés au connecteur fiscal actuel.

    2. Sur la page **Fournisseurs de documents fiscaux** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Fournisseurs de documents fiscaux**), téléchargez une configuration XML pour chaque périphérique ou service que vous prévoyez d'utiliser à des fins d'intégration fiscale.

        > [!TIP]
        > En sélectionnant **Affichage**, vous pouvez afficher tous les profils fonctionnels et techniques liés au fournisseur de documents fiscaux actuel.

    Pour des exemples de configuration des connecteurs fiscaux et fournisseurs de documents fiscaux, voir [Exemples fiscaux d'intégration dans le SDK de Retail](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > La mise en correspondance des données est considérée comme faisant partie du fournisseur de documents fiscaux. Pour paramétrer différentes mises en correspondance de données pour le même connecteur (par exemple, les réglementations spécifiques à chaque état), vous devez créer différents fournisseurs de documents fiscaux.

3. Créez des profils fonctionnels de connecteur et des profils techniques de connecteur.

    1. Sur la page **Profils fonctionnels du connecteur** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Profils fonctionnels du connecteur**), créez un profil fonctionnel du connecteur pour chaque combinaison de connecteur fiscal et de fournisseur de documents fiscaux associée à ce connecteur fiscal.

        1. Sélectionnez un nom de connecteur.
        2. Sélectionnez un fournisseur de document.

        Vous pouvez changer les paramètres de mise en correspondance des données dans un profil fonctionnel de connecteur. Pour rétablir les paramètres par défaut définis dans la configuration du fournisseur de documents fiscaux, sélectionnez **Mettre à jour**.

        **Exemples**
    
        |   | Formats | Exemple |
        |---|--------|---------|
        | **Paramètres de taux de TVA** | valeur : VATrate | 1 : 2 000, 2 : 1 800 |
        | **Mise en correspondance des codes de TVA** | VATcode : valeur | vat20 : 1, vat18 : 2 |
        | **Mise en correspondance des types de modes de paiement** | TenderType : Valeur | Disponibilités : 1, Carte : 2 |

        > [!NOTE]
        > Les profils fonctionnels du connecteur sont spécifiques à la société. Si vous prévoyez d'utiliser la même combinaison d'un connecteur fiscal et d'un fournisseur de documents fiscaux dans différentes sociétés, vous devez créer un profil fonctionnel de connecteur pour chaque entreprise.

    2. Sur la page **Profils techniques du connecteur** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Profils techniques du connecteur**), créez un profil technique du connecteur pour chaque connecteur fiscal.

        1. Sélectionnez un nom de connecteur.
        2. Sélectionnez un type de connecteur. Pour les périphériques associés à une station matérielle, sélectionnez **Local**.

            > [!NOTE]
            > Seuls les connecteurs locaux sont actuellement pris en charge.

        Les paramètres des onglets **Périphérique** et **Paramètres** dans un profil technique du connecteur peuvent être modifiés. Pour rétablir les paramètres par défaut définis dans la configuration du connecteur fiscal, sélectionnez **Mettre à jour**. Même si une nouvelle version d'une configuration XML est téléchargée, vous recevez un message stipulant que le connecteur fiscal actuel ou le fournisseur de documents fiscaux est déjà utilisé. Cette procédure ne remplace pas les modifications manuelles qui ont déjà été apportées aux profils fonctionnels du connecteur et des profils techniques du connecteur. Pour appliquer l'ensemble des paramètres par défaut depuis une nouvelle configuration, sur la page **Profils fonctionnels du connecteur** ou sur la page **Profils techniques du connecteur**, sélectionnez **Mettre à jour**.

4. Créez des groupes de connecteurs fiscaux.

    Un groupe de connecteurs fiscaux associe des profils fonctionnels des connecteurs fiscaux exécutant des fonctions identiques et utilisés à la même étape d'un processus d'enregistrement fiscal. Par exemple, si plusieurs modèles fiscaux d'impression peuvent être utilisés dans un magasin de vente au détail, les connecteurs fiscaux pour ces imprimantes fiscales peuvent être associés en un groupe de connecteurs fiscaux.
    
    1. Sur la page **Groupe de connecteurs fiscaux** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**), créez un nouveau groupe de connecteurs fiscaux.
    2. Ajoutez des profils fonctionnels dans le groupe de connecteurs. Sur l'onglet **Profils fonctionnels**, sélectionnez **Ajouter**, puis sélectionnez un numéro de profil. Chaque connecteur fiscal au sein d'un groupe de connecteurs ne peut avoir qu'un profil fonctionnel.
    3. Pour interrompre l'utilisation du profil fonctionnel, définissez **Désactiver** sur **Oui**. Cette modification affecte uniquement le groupe de connecteurs actuel. Vous pouvez continuer à utiliser le même profil fonctionnel dans d'autres groupes de connecteurs.

5. Créez un processus d'enregistrement fiscal.

    Un processus d'enregistrement fiscal est défini par la séquence des étapes d'enregistrement et du groupe de connecteurs utilisé dans chaque étape.
    
    1. Sur la page **Processus d'enregistrement fiscal** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d'intégration fiscale**), créez un enregistrement pour chaque processus unique d'enregistrement fiscal.
    2. Ajoutez les étapes d'enregistrement au processus :

        1. Sélectionnez **Ajouter**.
        2. Sélectionnez un type de connecteur fiscal.
        3. Dans le champ **Numéro du groupe**, sélectionnez un groupe de connecteurs fiscaux approprié.

6. Affectez les entités du processus d'enregistrement fiscal aux profils du PDV.

    1. Sur la page **Profils de fonctionnalité du PDV** (**Vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Profils du PDV \> Profils de fonctionnalité**), affectez le processus d'enregistrement fiscal à un profil de fonctionnalité du PDV. Sélectionnez **Modifier**, puis, dans l'onglet **Processus d'enregistrement fiscal**, dans le champ **Numéro du processus**, sélectionnez un processus.
    2. Sur la page **Profil matériel de PDV** (**Vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> Profils du PDV \> Profils du matériel**), affectez des profils techniques de connecteur à un profil matériel. Sélectionnez **Modifier**, ajoutez une ligne à l'onglet **Périphériques fiscaux**, puis dans le champ **Numéro de profil**, sélectionnez un profil technique de connecteur.

    > [!NOTE]
    > Vous pouvez ajouter plusieurs profils techniques à un profil matériel identique. Toutefois, un profil matériel ou un profil de fonctionnalité de PDV doit avoir une seule intersection avec n'importe quel groupe de connecteurs fiscaux.

    Le flux d'enregistrement fiscal est défini par le processus d'enregistrement fiscal ainsi que par certains paramètres de composants d'intégration fiscale : l'extension Commerce runtime (CRT) pour le fournisseur de documents fiscaux et l'extension de la station matérielle pour le connecteur fiscal.

    - L'abonnement des événements et des transactions à l'enregistrement fiscal est prédéfini dans le fournisseur de documents fiscaux.
    - Le fournisseur de documents fiscaux est également responsable de l'identification du connecteur fiscal utilisé pour l'enregistrement fiscal. Il correspond aux profils fonctionnels du connecteur inclus dans le groupe de connecteurs fiscaux spécifié pour l'étape actuelle du processus d'enregistrement fiscal avec le profil technique du connecteur attribué au profil matériel de la station matérielle à laquelle le PDV est relié.
    - Le fournisseur de documents fiscaux utilise les paramètres de mise en correspondance des données depuis la configuration du fournisseur de documents fiscaux pour transformer les données d'événement/de transaction, tels que les impôts et les paiements, tandis qu'un document fiscal est généré.
    - Lorsque le fournisseur de documents fiscaux génère un document fiscal, le connecteur fiscal peut soit l'envoyer au périphérique fiscal en l'état, soit l'analyser et le transformer en une séquence de commandes de l'API du périphérique, selon la manière dont la communication est gérée.

7. Sur la page **Processus d'enregistrement fiscal** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d'intégration fiscale**), sélectionnez **Valider** pour valider le processus d'enregistrement fiscal.

    Nous vous recommandons d'exécuter ce type de validation dans les cas suivants :
    
    - Après avoir exécuté tous les paramètres pour un nouveau processus d'enregistrement, y compris l'affectation des processus d'enregistrement aux profils de fonctionnalité du PDV et aux profils matériels.
    - Après avoir apporté des changements à un processus d'enregistrement fiscal, et une fois que ces changements sont susceptibles d'entraîner la sélection d'un autre connecteur fiscal lors de l'exécution (par exemple, si vous changez le groupe de connecteurs pour une étape de processus d'enregistrement fiscal, activez un profil fonctionnel de connecteur dans un groupe de connecteurs, ou ajoutez un nouveau profil fonctionnel de connecteur à un groupe de connecteurs).
    - Vous pouvez ensuite apporter des modifications à l'affectation des profils techniques du connecteur aux profils matériels.

8. Sur la page **Planification de la distribution**, exécutez les tâches **1070** et **1090** pour transférer des données vers la base de données des canaux.

## <a name="set-up-fiscal-texts-for-discounts"></a>Configurer les textes fiscaux pour les remises

Dans certains cas, un texte spécifique doit être imprimé sur un reçu fiscal si une remise est appliquée. Vous pouvez définir les textes fiscaux pour les remises sur la page **Groupe de connecteurs fiscaux** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Groupes de connecteurs fiscaux**).

- Pour les remises manuelles appliquées au PDV, vous devez configurer un texte fiscal pour le code d'informations ou le groupe de codes d'informations spécifié comme code d'informations **Remise de produit** dans le profil de fonctionnalité du PDV.

    1. Sur la page **Groupe de connecteurs fiscaux**, sélectionnez **Texte du reçu fiscal**.
    2. Dans l'onglet **Codes info**, sélectionnez **Ajouter**, puis sélectionnez un code info ou un groupe de codes info.
    3. Dans **Numéro de code info**, sélectionnez une valeur.
    4. Dans le champ **Numéro de sous-code**, sélectionnez une valeur si un sous-code est requis pour le code info sélectionné.
    5. Dans le champ **Texte du reçu fiscal**, spécifiez un texte fiscal qui doit être imprimé sur un reçu fiscal.
    6. Définissez l'option **Imprimer l'entrée utilisateur sur le reçu fiscal** sur **Oui** pour remplacer le texte d'un reçu fiscal avec les informations qu'un utilisateur renseigne manuellement dans le système du PDV. Cette option s'applique uniquement aux codes info dont la saisie est de type **Texte**.

    > [!NOTE]
    > Vous pouvez préciser un texte fiscal afin que plusieurs codes info soient compatibles avec les scénarios où les groupes de codes info, codes info associés et codes info déclenchés sont utilisés. Dans ces scénarios, le reçu fiscal contient les textes fiscaux depuis tous les codes info associés à la ligne de transaction lorsque la remise est appliquée.

- Pour les remises spécifiques au canal, vous devez définir un texte fiscal pour l'ID de remise.

    1. Sur la page **Groupe de connecteurs fiscaux**, sélectionnez **Texte du reçu fiscal**.
    2. Dans l'onglet **Remises**, sélectionnez **Ajouter**, puis sélectionnez un ID de remise.
    3. Dans le champ **Texte du reçu fiscal**, spécifiez un texte fiscal qui doit être imprimé sur un reçu fiscal.

    > [!NOTE]
    > Si plusieurs remises sont appliquées à la même ligne de transaction, le reçu fiscal contient les textes fiscaux de toutes les remises associées à cette ligne de transaction.

## <a name="set-error-handling-settings"></a>Définir les paramètres de traitement des erreurs

Les options de traitement des erreurs disponibles dans l'intégration fiscale sont définies dans le processus d'enregistrement fiscal. Pour plus d'informations sur le traitement des erreurs de l'intégration fiscale, voir [Gestion des erreurs](fiscal-integration-for-retail-channel.md#error-handling).

1. Sur la page **Processus d'enregistrement fiscal** (**Vente au détail \> Paramétrage du canal \> Intégration fiscale \> Processus d'intégration fiscale**), vous pouvez définir les paramètres suivants pour chaque étape du processus d'enregistrement fiscal :

    - **Autoriser Ignorer** – Ce paramètre active l'option **Ignorer** dans la boîte de dialogue de traitement des erreurs.
    - **Autoriser Marquer comme enregistrée** – Ce paramètre active l'option **Marquer comme enregistrée** dans la boîte de dialogue de traitement des erreurs.

2. Les options **Ignorer** et **Marquer comme enregistrée** dans la boîte de dialogue de traitement des erreurs nécessite l'autorisation **Autoriser Ignorer ou Marquer comme enregistrée**. Par conséquent, sur la page **Groupes d'autorisations** (**Vente au détail \> Employés \> Groupes d'autorisations**), activez l'autorisation **Autoriser Ignorer ou Marquer comme enregistrée**.
3. Les options **Ignorer** et **Marquer comme enregistrée** permettent aux opérateurs de renseigner des informations supplémentaires lorsque l'enregistrement fiscal échoue. Pour rendre cette fonctionnalité disponible, vous devez spécifier les codes info **Ignorer** et **Marquer comme enregistrée** sur un groupe de connecteurs fiscaux. Les informations que les opérateurs saisissent sont ensuite enregistrées comme transaction de code info liée à la transaction fiscale. Pour plus d'informations sur les codes info, voir [Codes info et groupes de codes info](../info-codes-retail.md).

    > [!NOTE]
    > La fonction de déclenchement **Produit** n'est pas prise en charge pour les codes info utilisés pour **Ignorer** et **Marquer comme enregistrée** dans les groupes de connecteurs fiscaux.

    - Sur la page **Groupe de connecteurs fiscaux**, sous l'onglet **Codes info**, sélectionnez les codes info ou les groupes de codes info dans les champs **Ignorer** et **Marquer comme enregistrée**.

    > [!NOTE]
    > Un document fiscal et un document non fiscal peuvent être générés à chaque étape d'un processus fiscal d'enregistrement. Une extension de fournisseur de documents fiscaux identifie chaque type de transaction ou d'événement comme associé à des documents fiscaux ou non fiscaux. La fonctionnalité de gestion des erreurs s'applique uniquement aux documents fiscaux.
    >
    > - **Document fiscal** – Désigne un document obligatoire qui doit être enregistré avec succès (par exemple, un reçu fiscal).
    > - **Document non fiscal** – Désigne un document supplémentaire pour la transaction ou l'événement (par exemple, un bordereau de carte cadeau).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configurer les états X/Z fiscaux depuis le PDV

Pour activer les états X/Z fiscaux à exécuter depuis le PDV, vous devez ajouter de nouveaux boutons à la mise en page d'un écran de PDV.

- Sur la page **Groupes de boutons**, suivez les instructions d'installation dans [Ajouter un bouton d'opération personnalisé à la mise en page d'un écran de PDV dans Retail Siège](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) pour installer le concepteur et mettre à jour la mise en page d'un écran de PDV.

    1. Permet de sélectionner la mise en page à mettre à jour. 
    2. Ajoutez un nouveau bouton, puis définissez la propriété de bouton **Imprimer X fiscal**.
    3. Ajoutez un nouveau bouton, puis définissez la propriété de bouton **Imprimer Z fiscal**.
    4. Sur la page **Planification de la distribution**, exécutez la tâche **1090** pour transférer les changements vers la base de données des canaux.

