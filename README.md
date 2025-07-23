# **Beetle**

## 介绍
 用于先心病相关产品，包括CHD-1和CHD-2

## 环境及测试
 1. 根据运行环境，替代config.yaml和soft.yaml中的对应条目，包括CHD-1和CHD-2的不同参数、软件及数据库的存储路径等；
 2. 测试可以采用NA24385数据：/public/home/xiezhangdong/projects/FuwaiCHD_Panel/Fastq/NA24385R10.FqList.txt；
 3. 测试按CHD-1建议配置；
 3. 测试完成后，需确认相关文件满足对应的md5值：NA24385R10.Report.md5sum。

## 运行准备
 1. 需首先进入分析路径；
 2. CHD-1运行命令：nohup snakemake -s /path/to/Snakefile --cores 30 --config Sample="NA24385R10" Flag4QC="Yes" Flag4SnpIndel="Yes" Flag4SV="Yes" Flag4CNV_On="Yes" Flag4CNV_Off="Yes" Flag4Trim="No" > nohup.log 2>&1 &；
 3. CHD-2运行命令：nohup snakemake -s /path/to/Snakefile --cores 30 --config Sample="NA24385R10" Flag4QC="Yes" Flag4SnpIndel="No" Flag4SV="Yes" Flag4CNV_On="No" Flag4CNV_Off="Yes" Flag4Trim="No" > nohup.log 2>&1 &；
 4. 指定样本名比如NA24385R10，需要对应Prefix4Fq路径下有对应的文件NA24385R10.FqList.txt。该文件中每行记录一个fastq.gz，可以有多行。