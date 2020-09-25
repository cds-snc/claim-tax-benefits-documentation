---
layout: page
title: Conception
lang: fr
trans_url: Design
---

Nous avons élaboré notre conception de service en nous fondant sur des pratiques exemplaires et nos résultats de recherche. Ceux-ci révèlent que les déclarants ont besoin :

- d’être capable de produire leur déclaration de revenus sans avoir à se déplacer pour obtenir de l’aide.
- d’avoir l’assurance qu’ils n’auront pas d’ennuis s’ils font leur déclaration seuls.
- d’avoir l’assurance que le service n’est pas une arnaque.
- de recevoir la preuve qu’ils ont produit leur déclaration pour avoir accès à d’autres programmes et prestations.
- d’utiliser le moyen de communication qui est le plus accessible pour eux.

Sur la base de ces informations, nous avons développé un service fonctionnant sur invitation seulement avec une version en ligne et une version papier. Les invités peuvent utiliser cette méthode simplifiée pour produire leur déclaration de revenus et avoir accès à des prestations. Pour en savoir plus, le diagramme d’analyse de service est disponible sur demande [cds-snc@tbs-sct.gc.ca](mailto:cds-snc@tbs-sct.gc.ca) .

Les points de contact entre le service et les utilisateurs sont :

1. [Une lettre]({{ site.baseurl }}/assets/pdf/invitation-letter-fr.pdf) invitant les personnes à utiliser le service;
2. [Un formulaire papier]({{ site.baseurl }}/assets/pdf/paper-form-fr.pdf) pour les personnes qui ne veulent pas remplir leur déclaration de revenus en ligne;
3. [Un outil en ligne](https://claim-tax-benefits.herokuapp.com/start?lang=fr) qui permet aux personnes de remplir leur déclaration de revenus sur un site Web et qui peut prendre la forme :
4. 1. d’un parcours « allégé » qui ne demande pas aux déclarants de répondre à des questions de sécurité et qui ne divulgue aucune information financière. Les déclarants doivent attendre deux semaines pour recevoir leur avis de cotisation par la poste.
   2. d’un parcours avec authentification qui demande aux déclarants de répondre à des questions de sécurité et qui divulgue des informations financières. Les déclarants reçoivent un avis de cotisation électronique immédiatement.

La possibilité existe de développer un outil interne à l’intention du personnel de l’ARC pour traiter les formulaires papier. Cet outil pourrait ensuite être adapté pour le traitement d’autres formulaires simplifiés.

## Lettre d’invitation

L’ARC enverra la lettre d’invitation pour sélectionner des participants et les inviter à utiliser le service. La lettre explique le contexte du service et la façon d’accéder à chacune des versions.

**Principaux résultats de recherche**

- La lettre d’invitation doit expliquer le contexte du service, présenter les options offertes (version papier ou en ligne) de façon évidente et préciser les contraintes d’utilisation du service.
- La lettre doit être dans un format pouvant être envoyé par la poste ou par courriel, selon le choix des personnes. Les notifications électroniques sont particulièrement importantes pour les déclarants qui utilisent des lecteurs d’écran.

**Contraintes organisationnelles**

Impression :

- Les services d’impression de l’ARC ont plusieurs limitations, notamment l’incapacité d’inclure des encadrés ou des informations personnalisées (par exemple, l’emplacement du code d’accès personnel) dans le corps de la lettre.
- En raison des échéances, nous n’avons pas été en mesure de créer un champ dynamique pour afficher le code d’accès personnel dans la lettre. Le processus actuel requiert environ 12 à 15 mois pour intégrer ce champ ou pour créer un champ similaire qui afficherait le nom du déclarant dans le formulaire papier.
- Le nom du déclarant doit apparaître sur le formulaire pour éviter que l’individu ne donne son formulaire à une autre personne qui ne serait pas admissible au service. L’équipe a amorcé une discussion à ce sujet avec les parties concernées.

**Notifications électroniques**

- Actuellement, il est impossible d’aviser les déclarants utilisant le service en leur envoyant un courriel dans leur boîte de réception MonDossier.
- Pour des raisons de sécurité, nous ne pouvons pas fournir d’informations personnalisées telles que le code d’accès dans la lettre. Un examen plus approfondi est requis en collaboration avec les parties concernées.

**Interventions de conception**

- Fournir un contexte clair au début de la lettre qui invite les déclarants à utiliser le service et qui explique en quoi consiste le service
- Avoir des titres qui expliquent le choix entre l’option en ligne et l’option papier, et qui précisent ce dont les déclarants ont besoin pour utiliser le service

**Prochaines étapes**

- Collaborer avec l’équipe de l’ARC qui est responsable de l’impression pour afficher les options dans un tableau
- Déterminer la façon d’aviser les déclarants à l’aide de MonDossier. Une connexion directe au service pourrait aussi être possible par l’intermédiaire de MonDossier, sans avoir à utiliser de code d’accès.

## Formulaire papier

La version papier est un formulaire de déclaration de revenus simplifié à envoyer par la poste.

**Principaux résultats de recherche**

- La version papier est essentielle pour les personnes qui ne se sentent pas à l’aise d’utiliser un ordinateur ou qui n’ont pas accès à un ordinateur.
- Le formulaire papier doit être simple et écrit en langage clair, et fournir des étapes bien expliquées.
- Le formulaire ne doit pas référer à des annexes ou à des pièces d’informations externes. Tous les renseignements requis doivent être contextualisés sur la page afin que le déclarant n’ait pas à consulter d’autres documents pour remplir le formulaire.

**Contraintes organisationnelles**

- Seules des informations limitées peuvent être préremplies en raison des contraintes d’impression et des risques de sécurité. Seuls le nom et un code de référence à l’usage de l’ARC peuvent être préremplis.

**Interventions de conception**

- Les titres dans le formulaire apparaissent sous la forme d’étapes faciles à suivre.
- L’information pertinente est énoncée dans chaque étape du formulaire afin d’éviter le besoin de consulter des instructions externes et de réduire la charge cognitive.

**Prochaines étapes**

- Mener des tests de contenu pour vérifier que les instructions sont bien comprises, afin que le formulaire soit facile à remplir.
- Mettre à l’épreuve un formulaire rempli auprès de l’équipe de traitement pour vérifier que le formulaire peut être utilisé pour produire une déclaration de revenus.
- Étudier la possibilité de créer un outil interne permettant de simplifier le traitement.

## Outil en ligne

L’outil en ligne est une application Web permettant aux déclarants invités de soumettre leur déclaration de revenus.

**Principaux résultats de recherche**

- Il faut éviter les questions à double volet, qui sont un fardeau pour les déclarants, car elles peuvent être source de confusion et mener à des erreurs critiques lors de l’utilisation du service.
- Les personnes sont facilement dépassées par les questions sur le revenu, alors il faut poser des questions auxquelles elles croient pouvoir répondre facilement.
- La plupart des utilisateurs n’ont pas pu répondre à deux questions de sécurité renforcée, ce qui signifie qu’un parcours différent doit être proposé.

**Contraintes organisationnelles**

- Une authentification basée sur des questions de sécurité est requise pour pouvoir divulguer des informations financières et émettre un avis de cotisation immédiatement après l’envoi de la déclaration de revenus en ligne.
- Le service ne peut pas automatiquement préfiltrer les déclarants potentiels puisqu’il ne peut pas prédire les changements de circonstances qui les rendent inadmissibles.

**Interventions de conception**

- Afficher une question par page.
- Uniformiser la structure des questions (à réponse directe « oui » ou « non »).
- Poser des questions au sujet du déclarant plutôt que des questions au sujet de ses revenus.
- Utiliser une case à cocher uniquement sur la page où le déclarant doit confirmer ses revenus. Toutes les autres pages doivent recourir à des boutons radio binaires.
- Fournir un parcours « allégé » (aucune divulgation de renseignements financiers avec une attente de deux semaines pour recevoir l’avis de cotisation par la poste), de sorte que les personnes peuvent utiliser le service même si elles sont incapables de répondre à des questions de sécurité ou si elles sont réticentes à le faire.

**Prochaines étapes**

- Appliquer les suggestions relatives au contenu (document disponible sur demande à [cds-snc@tbs-sct.gc.ca](mailto:cds-snc@tbs-sct.gc.ca))
- Faire d’autres tests de contenu.
- Concevoir un processus d’authentification simplifié à l’aide de questions auxquelles la majorité des déclarants peuvent répondre, afin que l’ARC puisse divulguer leurs renseignements financiers.

## États du produit

### Produit minimal viable

Le produit minimal viable est la première itération du service. Nous prévoyions le mettre à la disposition de déclarants sélectionnés au moyen d’une version bêta pilote ou privée ayant des fonctionnalités et des critères d’admissibilité limités.

<table>
  <tbody>
    <tr>
      <th>Critères d’admissibilité</th>
      <th>Fonctionnalités</th>
    </tr>
    <tr>
      <td>
        <ul>
          <li>Personnes de moins de 65 ans gagnant 12 000 $/année ou moins, et personnes de 65 ans et plus gagnant 19 000 $/année ou moins</li>
          <li>Résidents de l’Ontario</li>
          <li>Pas d’époux et pas d’enfants à charge</li>
          <li>Pas d’étudiants</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>Production d’une déclaration de revenus</li>
          <li>Inscription à la prestation Trillium de l’Ontario</li>
          <li>Inscription à l’Incitatif à agir pour le climat</li>
          <li>Changement d’adresse (<strong>version papier seulement</strong>)</li>
          <li>Avis de cotisation par la poste après 2 semaines (version en ligne) et après 8 semaines (version papier)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Le produit minimal viable emploiera le parcours « allégé ».

### État mature

Le produit dont l’état est mature renvoie à une itération ultérieure avec des critères d’admissibilités plus larges et plus de fonctionnalités. Ces critères et fonctionnalités seront élargis de façon progressive et itérative.

<table>
  <tbody>
    <tr>
      <th>Critères d’admissibilité</th>
      <th>Fonctionnalités</th>
    </tr>
    <tr>
      <td>
        <ul>
          <li>Personnes gagnant 35 000 $/année ou moins</li>
          <li>N’importe quelle province de résidence</li>
          <li>Ayant un époux et ayant des enfants à charge</li>
          <li>Pas d’étudiants</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>Production d’une déclaration de revenus</li>
          <li>Inscription à la prestation Trillium de l’Ontario</li>
          <li>Inscription à l’Incitatif à agir pour le climat</li>
          <li>Changement d’adresse (<strong>version papier et parcours avec authentification uniquement</strong>)</li>
          <li>Réclamation de dons de bienfaisance, de dons politiques, de frais médicaux, etc. (pour les personnes gagnant plus que le montant minimal de base)</li>
          <li>Avis de cotisation immédiat (parcours avec authentification), par la poste après 2 semaines (parcours allégé) et par la poste après 8 semaines (version papier)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Le produit à l’état mature fournira à la fois un parcours « allégé » et « authentifié » pour la version en ligne. Les déclarants pourront choisir de répondre aux questions de sécurité pour avoir accès à plus de fonctionnalités.
