# 🎓 Gerador de Certificados para o Diretório Acadêmico de Sistemas de Informação - UFF

Este script em Python foi desenvolvido para automatizar a geração de certificados de participação em palestras para o Diretório Acadêmico de Sistemas de Informação da Universidade Federal Fluminense (UFF). O código lê informações de participação de um arquivo CSV denominado `attendance.csv` e cria certificados em formato DOCX e PDF para os alunos.

## Dependências
As dependências necessárias estão listadas no arquivo `requirements.txt`. Para instalar todas as dependências, utilize o seguinte comando:

```bash
pip install -r requirements.txt
```

Certifique-se de que o arquivo `requirements.txt` está presente no mesmo diretório do script.

## Classes

### `Lecture` 🗣️
Esta classe representa as informações de uma palestra.

- **Atributos:**
  - `activity`: Tipo de atividade (sempre "Palestra" neste caso).
  - `name`: Nome da palestra.
  - `duration`: Duração da palestra.
  - `date`: Data da palestra.

### `Participant` 🙋‍♂️
Esta classe representa as informações de um participante.

- **Atributos:**
  - `name`: Nome do participante.
  - `course`: Curso do participante.
  - `registration`: Número de matrícula.
  - `email`: Endereço de e-mail.
  - `category`: Categoria do participante.
  - `hoursGranted`: Horas concedidas ao participante.

## Fluxo de Execução

1. **Inicialização do Modelo do Documento** 📄
   - Carrega um modelo de documento DOCX chamado `template.docx` utilizando a biblioteca `docxtpl`.

2. **Configuração do Diretório e Verificação de Existência** 📁
   - Define o diretório base como `./certificados`.
   - Se o diretório já existir, ele é removido e recriado.

3. **Leitura do Arquivo CSV** 📊
   - Lê o arquivo `attendance.csv` que contém informações sobre participantes e palestras.

4. **Iteração sobre as Linhas do CSV** 🔄
   - Para cada linha no arquivo CSV:
     - Cria instâncias de `Lecture` e `Participant` com informações fornecidas na linha.
     - Obtém a data e hora atual.
     - Constrói um contexto com informações do participante e da palestra.
     - Renderiza o documento DOCX com os dados do contexto.
     - Salva o documento DOCX.
     - Converte o documento DOCX para PDF utilizando a biblioteca `docx2pdf`.

## Notas Adicionais ℹ️
- Certifique-se de ter um arquivo `template.docx` adequado no mesmo diretório do script.
- O script usa a biblioteca `shutil` para limpar e recriar o diretório de certificados a cada execução.

Este guia fornece uma visão geral do script e instruções para instalação das dependências, tornando o processo mais eficiente e fácil de reproduzir. Certifique-se de revisar e ajustar conforme necessário. 🚀
