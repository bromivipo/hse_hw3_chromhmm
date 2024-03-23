# hse_hw3_chromhmm

## Выполнил Потоцкий Михаил Викторович, группа 1

ссылка на колаб - https://colab.research.google.com/drive/1_beAo2axYsR07fCnPypih6pXGgyreqR1?usp=sharing

Ноутбук также загружен в репозиторий

## Файлы
Гистоновая метка | Название файла
---| ---
H2az | wgEncodeBroadHistoneGm12878H2azStdAlnRep1.bam
H3k27ac | wgEncodeBroadHistoneGm12878H3k27acStdAlnRep1.bam
H3k27me3 | wgEncodeBroadHistoneGm12878H3k27me3StdAlnRep1.bam
H3k36me3 | wgEncodeBroadHistoneGm12878H3k36me3StdAlnRep1.bam
H3k04me1 | wgEncodeBroadHistoneGm12878H3k04me1StdAlnRep1V2.bam
H3k4me2 | wgEncodeBroadHistoneGm12878H3k4me2StdAlnRep1.bam
H3k04me3 | wgEncodeBroadHistoneGm12878H3k04me3StdAlnRep2V2.bam
H3k79me2 | wgEncodeBroadHistoneGm12878H3k79me2StdAlnRep1.bam
H3k9ac | wgEncodeBroadHistoneGm12878H3k9acStdAlnRep1.bam
H3k9me3 | wgEncodeBroadHistoneGm12878H3k9me3StdAlnRep1.bam
control | wgEncodeBroadHistoneGm12878ControlStdAlnRep1.bam

## cellmarkfiletable
GM12878	| H2az	| H2az.bam	 | control.bam
--- | --- | --- | ---
GM12878	| H3k27ac	| H3k27ac.bam |	control.bam
GM12878	| H3k27me3 |	H3k27me3.bam |	control.bam
GM12878 |	H3k36me3 |	H3k36me3.bam |	control.bam
GM12878 |	H3k04me1 |	H3k04me1.bam |	control.bam
GM12878 |	H3k4me2 |	H3k4me2.bam |	control.bam
GM12878	| H3k04me3 |	H3k04me3.bam |	control.bam
GM12878 |	H3k79me2 |	H3k79me2.bam	| control.bam
GM12878 |	H3k9ac |	H3k9ac.bam |	control.bam
GM12878 |	H3k9me3 |	H3k9me3.bam |	control.bam

## chromhmm
LearnModel запустил следующим образом:

```
!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel /content/binarizedData/ /content/data 10 hg19
```

Получил в отчете следующие графики:
emissions| trasitions| overlap
--- | --- | ---
![emissions_10](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/b7c1fe58-579e-4ac9-bcb9-95e06e204244) | ![transitions_10](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/24a2cd83-d521-46df-9da7-8e813ed7cee4) |  ![GM12878_10_overlap](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/8f8990de-9490-41cc-b769-b1a642db608e)

## States

State |  Характерные гистоновые модификации | Расположение | Genome | Присвоенный эпигенетический тип 
---| --- | --- | --- | ---
 1 | H3k4me1 | RefSeqTES, RefSeqGene, ядерная ламина. Попадает в участки между генами | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/1527c393-8e21-4b5d-89ff-5063cf65f2f7) | Weak Enhancer
2 | H3k4me1 | RefSeqTES, ядерная ламина. Попадает на экзоны, интроны или участки между генами | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/6260d639-d3d0-4b5e-877b-22480e127d8f) | Weak Enhancer
3 | H3k4me3, H3k4me2, H3k4me1 | CpG, RefSeqTSS, RefSeqTSS2kb. Попадает на экзоны и интроны | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/f45d51a0-c80e-40b3-a49e-a79ee50dbb9a) | Active promoter
4 | H3k27ac, H3k4me3, H3k4me2, H3k4me1 | RefSeqTES, ядерная ламина. Попадает на интроны, экзоны и участки между генами | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/5f424990-3545-43d1-ba0f-debbda88e3bc) | Strong Enhancer
5 | H3k27ac, H3k9ac, H3k4me3, H3k4me2, H3k79me2 |  CpG, RefSeqTSS, RefSeqTSS2kb. Попадает на экзоны | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/1fcef1d7-1e65-4e96-91b0-65713817bde0) | Active promoter
6 | H3k79me2, H3k4me3, H3k4me2, H3k4me1 | RefSeqGene, RefSeqTES. Попадает на интроны | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/66f0a448-3ce2-49fe-bde0-05d28130e461) | Strong Enhancer
7 | H3k79me2, H3k4me1 | RefSeqGene. Попадает на интроны | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/66f0a448-3ce2-49fe-bde0-05d28130e461) | Weak Enhancer
8 | H3k36me3 | RefSeqTES, RefSeqGene, RefSeqExon. Попадает на экзоны, интроны и между генами | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/0f022fb4-7890-4151-adb8-83e14bc38d4e) | Transcriptional Elongation
9 | - | ядерная ламина. Занимает большую часть генома | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/a1b73cfa-466e-4bd8-896f-1ba2f9287a68) | Repressed
10 | H3k27me3 | ядерная ламина. Попадает на интроны, экзоны и участки между генами | ![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/aa76c258-4ff8-46a6-b808-06de89f6a445) | Heterochromatin

## Бонус

Код в колабе, там описано как получить новый бед файл. Файл также загружен в репозиторий. Результат следующий:

![image](https://github.com/bromivipo/hse_hw3_chromhmm/assets/113182560/cd93ab6a-0462-4124-88b4-e8daef48ab40)
