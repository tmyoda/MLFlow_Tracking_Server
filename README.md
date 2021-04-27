# MLFlow_Tracking_Server

This is a copy of the article here.
(こちらのQiita記事の丸コピです)
https://qiita.com/MasafumiTsuyuki/items/9e03e285d4b9e0c41a7c

## Usage

### How to run the server
```
docker-compose up -d
```

### MLFlow Setting
Add the following code.
(以下のコードを追記)

```
# IP address of the server where the docker-compose is running.
SERVER_IP = "192.168..."

# Set the tracking uri.
mlflow.set_tracking_uri(f"http://{SERVER_IP}:5000")

# Specify the information to the environment variable.
os.environ["MLFLOW_S3_ENDPOINT_URL"] = f"http://{SERVER_IP}:9000"
os.environ["AWS_ACCESS_KEY_ID"] = "minio-access-key"
os.environ["AWS_SECRET_ACCESS_KEY"] = "minio-secret-key"
```