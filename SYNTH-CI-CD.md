<i>Created by Lilian DevOps of Algo.solutions</i>
<hr>
<i>English version : (Click the country flag)</i>
<a href="#english"><img src="https://cdn-icons-png.flaticon.com/512/330/330425.png"  width="50" height="50"></a>

<hr>
<div id="français"></div>

# CI/CD C'est quoi ? (Infos Utiles)
## <div id="sommaire">./Sommaire :</div>

> L'approche CI/CD (Définition) : <a href="#definition">ICI</a>

> Différence entre CI et CD : <a href="#difference">ICI</a>

> Intégration Continue : <a href="#integration">ICI</a>

> Distribution Continue : <a href="#distribution">ICI</a>

> Déploiement Continue : <a href="#deploiement">ICI</a>


<hr>

### <div id="definition">./L'approche CI/CD (Définition) :</div>

L'approche CI/CD permet d'augmenter la fréquence de distribution des applications grâce à l'introduction de l'[automatisation](https://www.redhat.com/fr/topics/automation/whats-it-automation) au niveau des étapes de développement des applications. Les principaux concepts liés à l'approche CI/CD sont l'intégration continue, la [distribution continue](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) et le déploiement continu. L'approche CI/CD représente une solution aux problèmes posés par l'intégration de nouveaux segments de code pour les équipes de développement et d'exploitation (ce qu'on appelle en anglais « [integration hell](https://www.solutionsiq.com/agile-glossary/integration-hell/) », ou l'enfer de l'intégration).

Plus précisément, l'approche CI/CD garantit une automatisation et une surveillance continues tout au long du cycle de vie des applications, des phases d'intégration et de test jusqu'à la distribution et au déploiement. Ensemble, ces pratiques sont souvent désignées par l'expression « pipeline CI/CD » et elles reposent sur une [collaboration agile entre les équipes de développement et d'exploitation](https://www.redhat.com/fr/topics/devops).

<i><a href="#sommaire">(Retourner au sommaire)</a></I>
<hr>

### <div id="difference">./Quelle est la différence entre CI et CD (et l'autre CD) ?</div>

L'acronyme « CI/CD » a plusieurs significations. Le « CI » de CI/CD désigne toujours l'« intégration continue », à savoir un processus d'automatisation pour les développeurs. L'intégration continue consiste, pour les développeurs, à apporter régulièrement des modifications au code de leur application, à les tester, puis à les fusionner dans un référentiel partagé. Cette solution permet d'éviter de travailler en même temps sur un trop grand nombre d'éléments d'une application, qui pourraient entrer en conflit les uns avec les autres.

Le « CD » de CI/CD désigne la « distribution continue » et/ou le « déploiement continu », qui sont des concepts très proches, parfois utilisés de façon interchangeable. Les deux concepts concernent l'automatisation d'étapes plus avancées du pipeline, mais ils sont parfois dissociés pour illustrer le haut degré d'automatisation.

Dans le cadre de la _distribution_ continue, généralement les modifications apportées par le développeur à une application sont automatiquement testées et téléchargées dans un référentiel (tel que [GitHub](https://redhatofficial.github.io/#!/main) ou un registre de conteneurs), où elles peuvent être déployées dans un environnement de production actif par l'équipe d'exploitation. Le processus de [distribution continue](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) permet de résoudre les problèmes de visibilité et de communication entre l'équipe de développement et l'équipe métier. Ainsi, son objectif consiste à simplifier au maximum le déploiement de nouveau code.

Le _déploiement_ continu (l'autre signification possible de « CD ») peut désigner le transfert automatique des modifications du développeur depuis le référentiel vers l'environnement de production, où elles peuvent être utilisées par les clients. Ce processus permet de soulager les équipes d'exploitation surchargées par les tâches manuelles qui ralentissent la distribution des applications. Il repose sur la distribution continue et automatise l'étape suivante du pipeline.
<hr>


![CI/CD Schémas!](https://www.redhat.com/cms/managed-files/styles/wysiwyg_full_width/s3/ci-cd-flow-desktop_edited_0.png?itok=TzgJwj6p "CI/CD Schémas")
<hr>

L'expression « CI/CD » peut désigner soit uniquement les deux pratiques liées d'intégration continue et de distribution continue, soit les trois pratiques, c'est-à-dire l'intégration continue, la [distribution continue](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) et le déploiement continu. Pour compliquer encore les choses, il arrive que l'expression « distribution continue » englobe également le processus de déploiement continu.

En conclusion, mieux vaut ne pas trop s'attarder sur ces questions de sémantique. Il suffit de retenir que l'approche CI/CD se rapporte à un processus, souvent représenté sous forme de pipeline, qui consiste à introduire un haut degré d'automatisation et de surveillance continues dans le processus de développement des applications. La signification réelle de ces termes varie au cas par cas, selon le niveau d'automatisation du pipeline CI/CD. De nombreuses entreprises commencent par l'intégration continue, puis se mettent peu à peu à automatiser la distribution et le déploiement, par exemple dans le cadre du développement d'[applications cloud-native](https://www.redhat.com/fr/topics/cloud-native-apps).


<i><a href="#sommaire">(Retourner au sommaire)</a></I>

<hr>

### <div id="integration">./L'intégration continue</div>
Le concept de [développement d'applications modernes](https://www.redhat.com/fr/solutions/cloud-native-development) consiste à faire travailler plusieurs développeurs simultanément sur différentes fonctions d'une même application. Toutefois, si une entreprise prévoit de fusionner tous ces morceaux de code source le même jour (le « [merge day » ou « jour du fusionnement](https://thedailywtf.com/articles/Happy_Merge_Day!) »), alors la tâche risque de s'avérer laborieuse et de nécessiter beaucoup de procédures manuelles et de temps. En effet, lorsqu'un développeur qui travaille seul apporte des modifications à une application, celles-ci peuvent entrer en conflit avec les différentes modifications apportées simultanément par d'autres développeurs. Ce problème se complexifie encore si chaque développeur a personnalisé son propre [environnement de développement intégré](https://www.redhat.com/fr/topics/middleware/what-is-ide), au lieu d'en définir un seul dans le cloud, pour toute l'équipe.

L'intégration continue (CI) permet aux développeurs de fusionner plus fréquemment leurs modifications de code dans une « branche » partagée, ou un « tronc », parfois même tous les jours. Une fois que les modifications apportées par un développeur sont fusionnées, elles sont validées par la création automatique de l'application et l'exécution de différents niveaux de test automatisés (généralement des tests unitaires et d'intégration) qui permettent de vérifier que les modifications n'entraînent pas de dysfonctionnement au sein de l'application. En d'autres termes, il s'agit de tester absolument tout, des classes et fonctions jusqu'aux différents modules qui constituent l'application. En cas de détection d'un conflit entre le code existant et le nouveau code, le processus d'intégration continue permet de résoudre les dysfonctionnements plus facilement, plus rapidement et plus fréquemment.

[En savoir plus sur le processus d'intégration continue](https://developers.redhat.com/blog/2017/09/06/continuous-integration-a-typical-process/)

<i><a href="#sommaire">(Retourner au sommaire)</a></I>

<hr>

### <div id="distribution">./La distribution continue</div>

Après l'automatisation de la création et des tests unitaires et d'intégration dans le cadre de l'intégration continue, la [distribution continue](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) automatise la publication du code validé dans un référentiel. Aussi, pour garantir l'efficacité du processus de distribution continue, il faut d'abord introduire le processus d'intégration continue dans le pipeline de développement. La distribution continue permet de disposer d'une base de code toujours prête à être déployée dans un environnement de production.

Dans le cadre de la distribution continue, chaque étape (de la fusion des modifications de code jusqu'à la distribution des versions prêtes pour la production) implique l'automatisation des processus de test et de publication du code. À la fin de ce processus, l'équipe d'exploitation est en mesure de déployer facilement et rapidement une application dans un environnement de production.

<i><a href="#sommaire">(Retourner au sommaire)</a></I>

<hr>

### <div id="deploiement">./Le déploiement continue</div>

L'étape finale d'un pipeline CI/CD mature est le déploiement continu. En complément du processus de distribution continue, qui automatise la publication d'une version prête pour la production dans un référentiel de code, le déploiement continu automatise le lancement d'une application dans un environnement de production. En l'absence de passerelle manuelle entre la production et l'étape précédente du pipeline, le déploiement continu dépend surtout de la conception de l'automatisation des processus de test.

Dans la pratique, dans le cadre du déploiement continu, une modification apportée par un développeur à une application pourrait être publiée quelques minutes seulement après la rédaction du code en question (en supposant qu'elle passe les tests automatisés). Il est ainsi beaucoup plus facile de recevoir et d'intégrer en continu les commentaires des utilisateurs. Ensemble, ces trois pratiques CI/CD réduisent les risques liés au déploiement des applications, puisqu'il est plus simple de publier des modifications par petites touches qu'en un seul bloc. Cette approche nécessite néanmoins un investissement de départ considérable, car les tests automatisés devront être rédigés de manière à s'adapter à un large éventail d'étapes de test et de lancement dans le pipeline CI/CD.

[En savoir plus sur le déploiement continu](https://developers.redhat.com/blog/2017/05/03/achieving-deployment-excellence-with-red-hat-openshift-io/)

<i><a href="#sommaire">(Retourner au sommaire)</a></I>


# ./FIN


<div id="english"></div>

# CI/CD What's this ? (Utils Tips)
## <div id="summary">./Summary:</div>

> The CI/CD approach (Definition) : <a href="#def">GO</a>

> Difference between CI and CD : <a href="#diff">GO</a>

> Continuous Integration : <a href="#integ">GO</a>

> Continuous Distribution : <a href="#dist">GO</a>

> Continuous Deployment : <a href="#depl">GO</a>


<hr>

### <div id="def">./The CI/CD approach (Definition)</div>

The CI/CD approach makes it possible to increase the frequency of application distribution by introducing [automation](https://www.redhat.com/fr/topics/automation/whats-it-automation) at the application development stage. The main concepts related to the CI/CD approach are continuous integration, [continuous distribution](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) and continuous deployment. The CI/CD approach represents a solution to the problems posed by the integration of new code segments for development and operations teams (the so-called ["integration hell"](https://www.solutionsiq.com/agile-glossary/integration-hell/)).

Specifically, the CI/CD approach ensures continuous automation and monitoring throughout the application lifecycle, from the integration and testing phases to distribution and deployment. Together, these practices are often referred to as the CI/CD pipeline and are based on agile [collaboration between development and operations teams](https://www.redhat.com/fr/topics/devops).

<i><a href="#summary">(Go back to summary)</a></I>
<hr>

### <div id="diff">./Difference between CI and CD</div>

The acronym "CI/CD" has several meanings. The "CI" in CI/CD always stands for "continuous integration," which is an automation process for developers. Continuous integration means that developers regularly make changes to their application code, test them, and then merge them into a shared repository. This solution avoids working on too many elements of an application at the same time, which could conflict with each other.

The "CD" in CI/CD stands for "continuous distribution" and/or "continuous deployment," which are very similar concepts, sometimes used interchangeably. Both concepts relate to the automation of more advanced stages of the pipeline, but they are sometimes separated to illustrate the high degree of automation.


In _continuous_ distribution, typically developer changes to an application are automatically tested and uploaded to a repository (such as [GitHub](https://redhatofficial.github.io/#!/main) or a container registry), where they can be deployed to an active production environment by the operations team. The [continuous distribution](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) process addresses visibility and communication issues between the development team and the business team. Thus, its objective is to simplify the deployment of new code as much as possible.

Continuous _deployment_ (the other possible meaning of "CD") can refer to the automatic transfer of developer changes from the repository to the production environment, where they can be used by clients. This process relieves the burden on operations teams who are overburdened with manual tasks that slow down application distribution. It relies on continuous distribution and automates the next step in the pipeline.
<hr>


![CI/CD Schémas!](https://www.redhat.com/cms/managed-files/styles/wysiwyg_full_width/s3/ci-cd-flow-desktop_edited_0.png?itok=TzgJwj6p "CI/CD Schémas")
<hr>

The term "CI/CD" can refer to either only the two related practices of continuous integration and continuous distribution, or to all three practices, i.e., continuous integration, [continuous distribution](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) and continuous deployment. To further complicate matters, sometimes the term "continuous distribution" also includes the continuous deployment process.

In conclusion, it is best not to dwell too much on these semantic issues. Suffice it to say that the CI/CD approach refers to a process, often represented as a pipeline, which consists of introducing a high degree of continuous automation and monitoring into the application development process. The actual meaning of these terms varies on a case-by-case basis, depending on the level of automation in the CI/CD pipeline. Many organizations start with continuous integration and then gradually move to automating distribution and deployment, for example, in the development of [cloud-native applications](https://www.redhat.com/fr/topics/cloud-native-apps).


<i><a href="#summary">(Go back to summary)</a></I>

<hr>

### <div id="integ">./Continuous Integration</div>


The concept of [modern application development](https://www.redhat.com/fr/solutions/cloud-native-development) is to have multiple developers working simultaneously on different functions of the same application. However, if a company plans to merge all of these pieces of source code on the same day ([the "merge day"](https://thedailywtf.com/articles/Happy_Merge_Day!)), then the task can be laborious and require a lot of manual procedures and time. This is because when a single developer makes changes to an application, they may conflict with the various changes made simultaneously by other developers. This problem is further complicated if each developer has customized their own [integrated development environment](https://www.redhat.com/fr/topics/middleware/what-is-ide), instead of defining a single one in the cloud for the entire team.

Continuous integration (CI) allows developers to merge their code changes into a shared "branch" or "trunk" more frequently, sometimes even daily. Once a developer's changes are merged, they are validated by automatically building the application and running various levels of automated tests (usually unit and integration tests) that verify that the changes do not cause the application to malfunction. In other words, it is a matter of testing absolutely everything, from classes and functions to the various modules that make up the application. If a conflict is detected between the existing code and the new code, the continuous integration process makes it easier, faster and more frequent to resolve the malfunction.

[Learn more about the continuous integration process](https://developers.redhat.com/blog/2017/09/06/continuous-integration-a-typical-process/)

<i><a href="#summary">(Go back to summary)</a></I>

<hr>

### <div id="dist">./Continuous Distribution</div>

After automating the creation and unit and integration tests in the context of continuous integration, [continuous distribution](https://www.redhat.com/fr/topics/devops/what-is-continuous-delivery) automates the publication of validated code in a repository. Therefore, to ensure the effectiveness of the continuous distribution process, the continuous integration process must first be introduced into the development pipeline. Continuous distribution ensures that the code base is always ready to be deployed in a production environment.

In continuous distribution, each step-from merging code changes to distributing production-ready versions-involves automating the code testing and release processes. At the end of this process, the operations team is able to easily and quickly deploy an application to a production environment.

<i><a href="#summary">(Go back to summary)</a></I>

<hr>

### <div id="depl">./Continuous Deployment</div>

The final step in a mature CI/CD pipeline is continuous deployment. In addition to the continuous distribution process, which automates the release of a production-ready version to a code repository, continuous deployment automates the release of an application to a production environment. Without a manual bridge between production and the previous stage of the pipeline, continuous deployment depends primarily on the design of test process automation.

In practice, with continuous deployment, a developer's change to an application could be published within minutes of writing the code in question (assuming it passes automated testing). This makes it much easier to receive and incorporate continuous user feedback. Together, these three CI/CD practices reduce the risks associated with application deployment, since it's easier to release changes in small increments than in a single block. However, this approach requires a significant upfront investment, as automated tests will need to be written to accommodate a wide range of testing and release stages in the CI/CD pipeline.

[Learn more about continuous deployment](https://developers.redhat.com/blog/2017/05/03/achieving-deployment-excellence-with-red-hat-openshift-io/)

<i><a href="#summary">(Go back to summary)</a></I>


# ./END
