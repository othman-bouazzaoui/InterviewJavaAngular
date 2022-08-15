## - C'est quoi Spring Batch ?
> Spring Batch est un framework Java basé sur Spring qui a pour but de faciliter la création de batch.
<br>

>> ### Nous utilisons les Batchs lorsqu’il s’agit d’un traitement sur un gros volume de données, en plus on peut les planifier.<br>

## - quel sont les arguments néccessaire 
 - JobLauncher : permet de lancer un job. Il existe différentes façons de lancer un job, il est possible de le faire de façon synchrone ou bien asynchrone.

 - JobRepository : Le JobRepository est la classe qui va stocker un grand nombre de données autour du Job. À travers cette classe, il va être possible de récupérer un historique des différents jobs qui ont été lancés avec un grand nombre de données pertinentes. C’est majoritairement grâce à cette sauvegarde de données que l’on peut redémarrer des Jobs ou bien effectuer des pauses dans le traitement.

 - Job : Le Job est la représentation du batch à travers le Framework Spring Batch. Cette classe va pouvoir définir différentes Step au sein de son exécution avec un ordre précis.

 - Step : Une Step va représenter une étape au sein du batch. Si durant le traitement, on souhaite effectuer différentes tâches, cela va se représenter par l’utilisation de différentes Steps. Les Steps sont généralement stockées dans des Beans pour pouvoir y accéder facilement dans différents Job.

Il existe deux types de Step :
<b>
 >>>>> Chunk.<br>
Tasklet.</b>

## Comment je peux mettre en place un traitement batch executable à travers une requet HTTP ?

1 - La création d'une classe ImportEmployeeTasklet qui implement l'interface Tasklet, puis je rédifinie la méthode execute dont laquelle je précise ce que je veux faire :<br>
@Override
 public RepeatStatus execute(StepContribution stepContribution, ChunkContext chunkContext) throws Exception {
         <br>blablablabla .....<br>
        }

2 - La création d'une classe de configuration ImportEmployeeBatchConfiguration annoté par 
<br>@Configuration
<br>@EnableBatchProcessing
<br>@EnableAutoConfiguration

   
//Job Builder qui crée le job<br>
@Autowired
private JobBuilderFactory jobBuilderFactory;

@Autowired
private StepBuilderFactory stepBuilderFactory;

@Autowired
private ImportEmployeeTasklet tasklet; 

@Bean<br>
public Step importEmployeeStep() {<br>
    return stepBuilderFactory.get("importEmployeeStep")<br>
            .tasklet(tasklet)<br>
            .build();<br>
}

@Bean<br>
public Job importEmployeeJob(Step importEmployeeStep) {<br>
    return jobBuilderFactory.get("importEmployeeJob")<br>
            .incrementer(new RunIdIncrementer())<br>
            .start(importEmployeeStep)<br>
            .build();<br>
}

3 - Je crée un controller ImportEmployeeController
> L'execution d'une job se fais via JobLuncher
@Autowired
private JobLauncher launcher;

@Autowired
@Qualifier("importEmployeeJob")
private Job importEmployeeJob;

@PostMapping
public ResponseEntity<?> requestJobImportEmployee()hrows JobParametersInvalidException, JobRestartException, JobExecutionAlreadyRunningException, JobInstanceAlreadyCompleteException {<br><br>
        Map<String,JobParameter> params = new HashMap<>();<br>
        params.put("time", new JobParameter(System.currentTimeMillis()));<br>
        JobExecution exec = launcher.run(importEmployeeJob, new JobParameters(params));<br>
        if(exec.getExitStatus().equals(ExitStatus.COMPLETED)){<br>
            return ResponseEntity.ok("importEmployeeJob started");<br>
        }<br>
        else{<br>
            return ResponseEntity.status(HttpStatus.INTERNAL_SERVER_ERROR).build();<br>
        }<br>
    }

## En résumé (pour faciliter la compréhension):
<b>> requestJobImportEmployee du controller va demander au spring batch d'executer le job importEmployeeJob qu'on a déclaré dans la classe ImportEmployeeBatchConfiguration, ce dérnier va executer importEmployeeJob, puis cette job va lancer le importEmployeeStep, puis ce step va lancer la méthode execute de la classe ImportEmployeeTasklet dont laquelle on a mis un traitement (blabla :) )

===> à finaliser
