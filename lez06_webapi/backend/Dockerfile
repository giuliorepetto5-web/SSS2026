FROM python
RUN apt-get update && apt-get install -y git
WORKDIR /app
RUN git clone https://github.com/mmenapace/SomeBankingApp.git
# Rimuovo la cartella del frontend
RUN rm -rf /app/SomeBankingApp/frontend
WORKDIR /app/SomeBankingApp/backend
# Aggiungo il requirement "fastapi" in requirements.txt
RUN echo "\nfastapi" >> ./requirements.txt
RUN pip install -r requirements.txt
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]