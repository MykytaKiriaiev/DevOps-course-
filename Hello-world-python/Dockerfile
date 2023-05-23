
FROM python:alpine3.10 AS builder
WORKDIR /app
COPY requirements.txt /app/requirements.txt
RUN pip install --user --no-cache-dir -r requirements.txt


FROM python:alpine3.10
WORKDIR /app
COPY --from=builder /root/.local /root/.local
COPY . /app
ENV PATH=/root/.local/bin:$PATH
EXPOSE 5000
CMD python ./launch.py