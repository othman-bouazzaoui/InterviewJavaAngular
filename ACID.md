La notion de transaction est récurrente dans les systèmes d’information. Par exemple, la plupart des SGBDR (Oracle, MySQL, PostGreSQL…) intègrent un moteur de transaction. Une transaction est définie par le respect de quatre propriétés désignées par l’acronyme ACID :

Les propriétés ACID (atomicité, cohérence, isolation et durabilité) sont un ensemble de propriétés qui garantissent qu'une transaction informatique est exécutée de façon fiable.

## Atomicité
La transaction garantit que l’ensemble des opérations qui la composent sont soit toutes réalisées avec succès soit aucune n’est conservée.

## Cohérence
La transaction garantit qu’elle fait passer le système d’un état valide vers un autre état valide.

## Isolation
Deux transactions sont isolées l’une de l’autre. C’est-à-dire que leur exécution simultanée produit le même résultat que si elles avaient été exécutées successivement.

## Durabilité
La transaction garantit qu’après son exécution, les modifications qu’elle a apportées au système sont conservées durablement.

Une transaction est définie par un début et une fin qui peut être soit une validation des modifications (commit), soit une annulation des modifications effectuées (rollback). On parle de démarcation transactionnelle pour désigner la portion de code qui doit s’exécuter dans le cadre d’une transaction.