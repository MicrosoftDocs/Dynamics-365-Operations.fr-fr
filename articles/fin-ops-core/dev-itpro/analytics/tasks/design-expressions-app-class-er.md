---
title: Concevoir des expressions de génération d’états électroniques pour appeler les méthodes de classe d’application
description: Cette rubrique décrit la procédure de réutilisation de la logique d’application existante dans les configurations d’états électroniques en appelant les méthodes requises des classes d’application des expressions ER.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81fae8d3603677afd7dd4b09b9073805f73582b4
ms.sourcegitcommit: e6b4844a71fbb9faa826852196197c65c5a0396f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7751704"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Concevoir des expressions de génération d’états électroniques pour appeler les méthodes de classe d’application

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit la réutilisation de la logique d’application existante dans les configurations [d’états électroniques](../general-electronic-reporting.md) en appelant les méthodes requises des classes d’application des expressions ER. Les valeurs des arguments pour les classes d’appel peuvent être définies dynamiquement au moment de l’exécution. Par exemple, les valeurs peuvent être basées sur des informations contenues dans le document d’analyse, pour garantir son exactitude.

Dans le cadre de cette rubrique, vous allez concevoir un processus qui analyse des relevés bancaires entrants pour une mise à jour des données d’application. Vous recevrez les relevés bancaires entrants sous forme de fichiers texte (.txt) contenant les codes de numéro de compte bancaire international (IBAN). Dans le cadre du processus d’importation des relevés bancaires, vous devez valider l’exactitude du code IBAN à l’aide de la logique qui est déjà disponible.

## <a name="prerequisites"></a>Conditions préalables

Les procédures de cette rubrique sont destinées aux utilisateurs auxquels le rôle **Administrateur système** ou **Développeur d’états électroniques** a été affecté.

Ces procédures peuvent être effectuées à l’aide d’un ensemble de données quelconque.

Pour les effectuer, vous devez également télécharger et enregistrer localement le fichier suivant : [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

Dans cette rubrique, vous créerez les configurations ER requises pour la société fictive, Litware, Inc. Par conséquent, avant d’effectuer les procédures décrites dans cette rubrique, vous devez effectuer les étapes suivantes.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, vérifiez que le fournisseur de configuration pour l’exemple de société **Litware, Inc.** est disponible et marqué comme actif. Si vous ne voyez pas ce fournisseur de configuration, vous devez d’abord effectuer les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Importer une nouvelle configuration du modèle ER

1. Dans la page **Configurations de localisation**, dans la section **Fournisseurs de configurations**, sélectionnez la vignette du fournisseur de configurations **Microsoft**.
2. Sélectionnez **Référentiels**.
3. Sur la page **Référentiels de localisation**, sélectionnez **Afficher les filtres**.
4. Pour sélectionner l’enregistrement du référentiel global, ajoutez un champ de filtre **Nom**.
5. Dans le champ **Nom**, entrez **Global**. Sélectionnez ensuite l’opérateur de filtre **contient**.
6. Sélectionnez **Appliquer**.
7. Sélectionnez **[Ouvrir](../er-download-configurations-global-repo.md#open-configurations-repository)** pour passer en revue la liste des configurations ER dans le référentiel sélectionné.
8. Sur la page **Référentiel de configurations**, dans l’arborescence de configuration, sélectionnez **Modèle de paiement**.
9. Dans l’organisateur **Versions**, si le bouton **Importer** est disponible, sélectionnez-le, puis sélectionnez **Oui**.

    Si le bouton **Importer** n’est pas disponible, vous avez déjà importé la version sélectionnée de la configuration ER **Modèle de paiement**.

10. Fermez la page **Référentiel de configuration**, puis la page **Référentiels de localisation**.

## <a name="add-a-new-er-format-configuration"></a>Ajouter une nouvelle configuration du format ER

Ajoutez un nouveau format ER pour analyser les relevés bancaires entrants au format TXT.

1. Dans la page **Configurations de localisation**, sélectionnez la vignette **Configurations des états**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, sélectionnez **Modèle de paiement**.
3. Sélectionnez **Créer une configuration**. 
4. Dans la boîte de dialogue déroulante, procédez comme suit :

    1. Dans le champ **Nouveau**, entrez **Format basé sur le PaymentModel du modèle du paiement**.
    2. Dans le champ **Nom**, saisissez **Format d’importation des relevés bancaires (exemple)**.
    3. Dans le champ **Prend en charge l’importation de données**, sélectionnez **Oui**.
    4. Sélectionnez **Créer une configuration** pour terminer la création de la configuration.

## <a name="design-the-er-format-configuration--format"></a>Créer la configuration du format ER – Format

Concevez un format ER qui représente la structure attendue du fichier externe au format TXT.

1. Pour la configuration de format **Format d’import de relevé bancaire (exemple)** que vous avez ajoutée, sélectionnez **Concepteur**.
2. Sur la page **Concepteur de formats**, dans l’arborescence de la structure du format du volet gauche, sélectionnez **Ajouter racine**.
3. Dans la boîte de dialogue qui s’affiche, procédez comme suit :

    1. Dans l’arborescence, sélectionnez **Texte\\Séquence** pour ajouter un composant de format **Souche**.
    2. Dans le champ **Nom**, entrez **Racine**.
    3. Dans le champ **Caractères spéciaux**, sélectionnez **Nouvelle ligne – Windows (CR LF)**. Selon ce paramètre, chaque ligne du fichier d’analyse devra être considérée comme un enregistrement distinct.
    4. Cliquez sur **OK**.

4. Sélectionnez **Ajouter**.
5. Dans la boîte de dialogue qui s’affiche, procédez comme suit :

    1. Dans l’arborescence, sélectionnez **Texte\\Souche**.
    2. Dans le champ **Nom**, entrez **Lignes**.
    3. Dans le champ **Multiplicité**, sélectionnez **Un plusieurs**. En fonction de ce paramètre, au moins une ligne doit être présente dans le fichier d’analyse.
    4. Cliquez sur **OK**.

6. Dans l’arborescence, sélectionnez **Racine\\Lignes**, puis sélectionnez **Ajouter la souche**.
7. Dans la boîte de dialogue qui s’affiche, procédez comme suit :

    1. Dans le champ **Nom**, entrez **Champs**.
    2. Dans le champ **Multiplicité**, sélectionnez **Un seul**.
    3. Cliquez sur **OK**.

8. Dans l’arborescence, sélectionnez **Racine\\Lignes\\Champs**, puis sélectionnez **Ajouter**.
9. Dans la boîte de dialogue qui s’affiche, procédez comme suit :

    1. Dans l’arborescence, sélectionnez **Texte\\Chaîne**.
    2. Dans le champ **Nom**, entrez **IBAN**.
    3.. Cliquez sur **OK**.

10. Cliquez sur **Enregistrer**.

La configuration est à présent définie de manière à ce que chaque ligne du fichier d’analyse contienne le code IBAN.

![Configuration de format Format d’importation de relevé bancaire (exemple) sur la page Concepteur de format.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>Créer la configuration du format ER – Mappage avec un modèle de données

Concevez un mappage de format ER qui utilise les informations du fichier d’analyse pour remplir un modèle de données.

1. Sur la page **Concepteur de format**, sur le volet Action, sélectionnez **Mapper le format au modèle**.
2. Sur la page **Mappage de modèles à la source de données**, sur le volet Action, sélectionnez **Nouveau**.
3. Dans le champ **Définition**, sélectionnez **BankToCustomerDebitCreditNotificationInitiation**.
4. Dans le champ **Nom**, saisissez **Mappage au modèle de données**.
5. Cliquez sur **Enregistrer**.
6. Sélectionnez **Concepteur**.
7. Sur la page **Concepteur de mappage de modèle**, dans l’arborescence **Types de sources de données**, sélectionnez **Dynamics 365 for Operations\\Classe**.
8. Dans la rubrique **Sources d’informations**, sélectionnez **Ajouter une racine** pour ajouter une source de données qui appelle la logique applicative existante pour la validation des codes IBAN.
9. Dans la boîte de dialogue qui s’affiche, procédez comme suit :

    1. Dans le champ **Nom**, entrez **Vérifier\_codes**.
    2. Dans le champ **Classe**, saisissez ou sélectionnez **ISO7064**.
    3. Cliquez sur **OK**.

10. Dans l’arborescence **Types de sources de données**, procédez comme suit :

    1. Développez la source de données du **format**.
    2. Développez **format\\Racine : Séquence (Racine)**.
    3. Développez **format\\Racine : Séquence (Racine)\\Lignes : Séquence 1..\* (Lignes)**.
    4. Développez **format\\Racine : Séquence (Racine)\\Lignes : Séquence 1..\* (Lignes)\\Champs : Séquence 1..1 (Champs)**.

11. Dans l’arborescence **Modèle de données**, procédez comme suit :

    1. Développez le champ **Paiements** du modèle de données.
    2. Développez **Paiements\\Compte créditeur(CompteCréditeur)**.
    3. Développez **Paiements\\Compte créditeur(CompteCréditeur)\\Identification**.
    4. Développez **Paiements\\Compte créditeur(CompteCréditeur)\\Identification\\IBAN**.

12. Suivez ces étapes pour lier les composants du format configuré aux champs du modèle de données :

    1. Sélectionnez **format\\Racine : Séquence (Racine)\\Lignes : Séquence 1..\* (Lignes)**.
    2. Sélectionnez **Paiements**.
    3. Sélectionnez **Lier**. Selon ce paramètre, chaque ligne du fichier d’analyse devra être considérée comme un règlement unique.
    4. Sélectionnez **format\\Racine : Séquence (Racine)\\Lignes : Séquence 1..\* (Lignes)\\Champs : Séquence 1..1 (Champs)\\IBAN : Chaîne (IBAN)**.
    5. Sélectionnez **Paiements\\Compte créditeur(CompteCréditeur)\\Identification\\IBAN**.
    6. Sélectionnez **Lier**. Sur la base de ce paramètre, le champ **IBAN** du modèle de données sera rempli avec la valeur du fichier d’analyse.

    ![Liaison des composants de format aux champs de modèle de données sur la page Concepteur de mappage de modèle.](../media/design-expressions-app-class-er-02.png)

13. Sur l’onglet **Validation**, suivez ces étapes pour ajouter une règle de [validation](../general-electronic-reporting-formula-designer.md#Validation) qui affiche un message d’erreur pour toute ligne du fichier d’analyse contenant un code IBAN non valide :

    1. Sélectionnez **Nouveau**, puis **Modifier la condition**.
    2. Sur la page **Concepteur de formules**, dans l’arborescence **Source de données**, développez la source de données **Vérifier\_codes** qui représente la classe d’application **ISO7064** pour afficher les méthodes disponibles de cette classe.
    3. Sélectionnez **Vérifier\_codes\\vérifierMOD1271\_36**.
    4. Sélectionnez **Ajouter une source de données**.
    5. Dans le champ **Formule**, entrez [l’expression](../general-electronic-reporting-formula-designer.md#Binding) : **Vérifier\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. Sélectionnez **Sauvegarder**, puis fermez la page.
    7. Sélectionnez **Modifier le message**.
    8. Sur la page **Concepteur de formule**, dans le champ **Formule**, entrez **CONCATENATE("Invalid IBAN code has been found:&nbsp;", format.Root.Rows.Fields.IBAN)**.
    9. Sélectionnez **Sauvegarder**, puis fermez la page.

    En fonction de ces paramètres, la condition de validation renverra *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* pour tout code IBAN non valide en appelant la méthode **verifyMOD1271\_36** existante de la classe d’application **ISO7064**. Notez que la valeur du code IBAN est définie dynamiquement au runtime en tant qu’argument de la méthode d’appel basée sur le contenu du fichier texte d’analyse.

    ![Règle de validation sur le concepteur de mappage de modèles.](../media/design-expressions-app-class-er-03.png)

14. Cliquez sur **Enregistrer**.
15. Fermez la page **Concepteur de mappage de modèles**, puis fermez la page **Mappage du modèle à la source de données**.

## <a name="run-the-format-mapping"></a>Exécuter la mise en correspondance des formats

À des fins de test, exécutez le mappage de formats à l’aide du fichier SampleIncomingMessage.txt que vous avez téléchargé plus tôt. La sortie générée contiendra les données importées depuis le fichier texte sélectionné et transférées vers le modèle de données personnalisé pendant l’importation réelle.

1. Sur la page **Mappage de modèles à la source de données**, sélectionnez **Exécuter**.
2. Sur la page **Paramètres d’états électroniques**, sélectionnez **Parcourir**, accédez au fichier **SampleIncomingMessage.txt** que vous avez téléchargé et sélectionnez-le.
3. Cliquez sur **OK**.
4. Notez que la page **Mappage du modèle à la source de données** affiche un message d’erreur concernant un code IBAN non valide.

    ![Résultat de l’exécution du mappage de format sur la page Mappage du modèle à la source de données.](../media/design-expressions-app-class-er-04.png)

5. Examinez la sortie au format XML, qui représente les données importées depuis le fichier sélectionné et transférées vers le modèle de données. Notez que seules trois lignes du fichier texte importé ont été traitées sans erreur. Le code IBAN de la ligne 4 n’est pas valide et a été ignoré.

    ![Sortie XML.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
