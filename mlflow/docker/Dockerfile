FROM python:3.8.2-slim

RUN pip install mlflow[extras]

CMD mlflow server \
    --backend-store-uri /mnt/mlflow-disk \
    #--default-artifact-root s3://my-mlflow-bucket/ \
    --host 0.0.0.0 --port=9080
