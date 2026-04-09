# Passo a passo para criar um job simples no Jenkins

Este guia mostra como criar um **job simples no Jenkins** usando o tipo **Freestyle project**, ideal para iniciantes.

---

## 1. Acesse o Jenkins

Abra o Jenkins no navegador e faça login.

Na tela inicial:

- Clique em **New Item**

---

## 2. Dê um nome ao job

No campo **Item name**, digite:

```
job-teste
```

Selecione:

- **Freestyle project**

Clique em:

- **OK**

---

## 3. Configure uma descrição (opcional)

Na seção **Description**, escreva:

```
Job simples para testar se o Jenkins está executando comandos.
```

---

## 4. Adicione um passo de execução

Role a página até **Build Steps**.

Clique em:

- **Add build step**

Escolha:

- **Execute shell** (Linux/macOS)
- **Execute Windows batch command** (Windows)

---

## 5. Digite um comando simples

### Linux / macOS

```bash
echo "Olá, Jenkins!"
date
```

### Windows

```bat
echo Olá, Jenkins!
date /t
time /t
```

---

## 6. Salve o job

Clique em:

- **Save**

---

## 7. Execute o job

Na página do job:

- Clique em **Build Now**

---

## 8. Veja o resultado

Após a execução:

1. Clique no número do build
2. Clique em **Console Output**

Você verá a saída semelhante a:

```
Olá, Jenkins!
Thu Apr 09 15:00:00 UTC 2026
```

---

# Exemplo mínimo funcional

Configuração simples:

- **Nome:** job-teste
- **Tipo:** Freestyle project
- **Build Step:** Execute shell

### Comando:

```bash
echo "Olá, Jenkins!"
uname -a
```

---

# Evoluindo o job

Depois que o primeiro job funcionar, você pode adicionar:

- Integração com **Git**
- **Build Triggers**
- Execução automática
- Arquivamento de artefatos
- Notificações

---

# Alternativa moderna: Pipeline

O Jenkins também permite criar jobs usando **Pipeline**, com configuração em código.

## Exemplo de Pipeline simples

```groovy
pipeline {
    agent any

    stages {
        stage('Teste') {
            steps {
                echo 'Olá, Jenkins!'
            }
        }
    }
}
```

---

# Dica prática

Para o primeiro teste:

1. Crie um **Freestyle project**
2. Adicione **Execute shell**
3. Execute um `echo`
4. Verifique o **Console Output**

Se isso funcionar, seu Jenkins está pronto para usos mais avançados.
