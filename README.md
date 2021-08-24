# Contador de Palavras



Exemplo de uma aplicação Python para contar as palavras de um arquivo texto. Neste exemplo há os passos para executá-la em um Cluster Dataproc no Google Cloud Platform (GCP) com Hadoop e Spark, através de um job PySpark.

1) Crie um cluster hadoop/spark no GCP usando o Dataproc. Exemplo: cluster-do-ble

2) Crie um Bucket Exemplo: gs://dataproc-do-ble/

3) Acesse o console do GCP

4) Clone este projeto

5) Copie os arquivos para o Bucket criado:

   ```
   gsutil cp contador.py livro.txt gs://dataproc-do-ble/
   ```

6) E execute um job

   ```
   gcloud dataproc jobs submit pyspark --cluster=cluster-do-ble --region="us-central1" gs://dataproc-do-ble/contador.py
   ```

7) Se olhar no Bucket, uma pasta com o nome **resultado** será criada contendo os arquivos:

   _SUCCESS

   part-00000

8) O conteúdo de part-00000 estará a contagem de palavras referente ao arquivo livro.txt

9) O retorno deve ser equivalente ao conteúdo resultado_part-00000.txt neste repositório.

10) No arquivo  **resultado.txt** consta apenas as **10 palavras mais encontradas** no arquivo.
