## Comandos importantes

### Instalar as dependências do projeto
```
pip install -r requirements.txt
```

### Rodar o projeto
```
python manage.py runserver 
```

### Criar as migrações e escreve-las no banco de dados
```
python manage.py makemigrations
python manage.py migrate

```

### Criar novos app dentro do projetos
```
python manage.py startapp app
```

### Criar um super usuário para o app com o Django-allauth
```
python manage.py createsuperuser
```
https://django-allauth.readthedocs.io/en/latest/installation/quickstart.html


## Salvar credenciais de banco de dados de forma oculta usando dotenv:
1. Instalação

```
pip install python-dotenv
```

2. Criar um arquivo .env
No diretório do seu projeto, crie um arquivo chamado .env e adicione suas configurações sensíveis:

```
DB_NAME=mydatabase
DB_USER=mydatabaseuser
DB_PASSWORD=mypassword
DB_HOST=localhost
DB_PORT=5432
```


3. Configurar o arquivo settings.py
```
import os
from dotenv import load_dotenv

# Carregar variáveis de ambiente do arquivo .env
load_dotenv()

# Configurações do banco de dados
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',  # Ou o seu motor de banco de dados preferido
        'NAME': os.getenv('DB_NAME'),
        'USER': os.getenv('DB_USER'),
        'PASSWORD': os.getenv('DB_PASSWORD'),
        'HOST': os.getenv('DB_HOST'),
        'PORT': os.getenv('DB_PORT'),
    }
}
```
