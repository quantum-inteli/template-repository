# Quantum - Liga de Computação Quântica do Inteli

<p align="center">
  <a href="https://www.inteli.edu.br/">
    <img src="assets/Quantum_logo_escuro.jpeg" alt="Quantum - Liga de Computação Quântica do Inteli" border="0" width="40%" height="40%">
  </a>
</p>

<br>

# Nome do Projeto

## 👨‍💻 Integrantes

- <a href="https://www.linkedin.com/in/example1">Nome do Integrante 1</a>
- <a href="https://www.linkedin.com/in/example2">Nome do Integrante 2</a>
- <a href="https://www.linkedin.com/in/example3">Nome do Integrante 3</a>

---

## 📜 Descrição do Projeto

Inclua aqui uma descrição detalhada do projeto. Explique o problema abordado, a abordagem metodológica adotada, as principais referências utilizadas e uma breve síntese dos resultados ou conclusões obtidas.

---

## 📁 Estrutura de Pastas

```
template-repository/
├── assets/
│   └── Quantum_logo_escuro.jpeg
├── data/
├── docs/
│   └── seu_review.md
├── experiments/
│   ├── analise_resultado.py
│   └── notebooks.md
├── output/
│   └── graficos.py
├── src/
│   └── algoritmos.md
├── LICENSE
└── README.md
```

### Descrição das Pastas

- **`assets/`** — Recursos estáticos do repositório, como imagens, logotipos e arquivos de mídia utilizados na documentação.

- **`data/`** — Dados de entrada utilizados no projeto (datasets, arquivos CSV, JSON etc.). Nem sempre estará populada, pois alguns dados podem ser confidenciais ou de grande volume; a pasta existe para padronizar a estrutura entre projetos.

- **`docs/`** — Artefatos teóricos e documentação do projeto. Em projetos de revisão bibliográfica, por exemplo, esta pasta contém o artigo principal, a lista de trabalhos revisados e outros documentos de referência.

- **`experiments/`** — Notebooks e scripts exploratórios. É onde ficam os testes, análises intermediárias, comparações de técnicas e protótipos. O conteúdo desta pasta representa o processo de investigação — não necessariamente o produto final.

- **`output/`** — Resultados gerados pelo projeto: gráficos, tabelas, relatórios exportados e demais artefatos produzidos ao longo do trabalho.

- **`src/`** — Implementações finais e prontas para uso. Após a fase experimental, os melhores métodos e abordagens são consolidados aqui em forma de código organizado, reutilizável e bem documentado.

---

## 🔧 Configuração do Ambiente

Esta seção descreve como configurar o ambiente de desenvolvimento para executar os notebooks e scripts deste repositório. Há três opções principais: **VS Code com ambiente virtual**, **Google Colab** e **Jupyter Notebook local**.

---

### Opção 1 — VS Code com Ambiente Virtual (Recomendado para uso local)

Esta é a opção mais robusta para desenvolvimento local, permitindo controle total sobre versões e dependências.

#### Pré-requisitos

- [Python 3.8 ou superior](https://www.python.org/downloads/)
- [VS Code](https://code.visualstudio.com/)
- Extensão **Python** do VS Code (da Microsoft)
- Extensão **Jupyter** do VS Code (da Microsoft)

#### Passo a passo

**1. Clone o repositório**

```bash
git clone https://github.com/sua-org/nome-do-repositorio.git
cd nome-do-repositorio
```

**2. Crie e ative um ambiente virtual**

> É altamente recomendado utilizar um ambiente virtual para isolar as dependências deste projeto e evitar conflitos com outros projetos Python na sua máquina.

No terminal, dentro da pasta do repositório:

```bash
# Criar o ambiente virtual
python3 -m venv .venv
```

Ativar o ambiente:

```bash
# Linux / macOS
source .venv/bin/activate

# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# Windows (CMD)
.venv\Scripts\activate.bat
```

Após a ativação, o terminal exibirá o prefixo `(.venv)` antes do prompt.

**3. Instale o Qiskit e as dependências**

```bash
pip install qiskit qiskit-aer qiskit-ibm-runtime
```

Para suporte a visualizações e notebooks Jupyter:

```bash
pip install matplotlib pylatexenc jupyterlab notebook
```

**4. Selecione o kernel correto no VS Code**

- Abra qualquer arquivo `.ipynb` do projeto no VS Code.
- No canto superior direito do notebook, clique em **"Select Kernel"**.
- Escolha o interpretador dentro de `.venv` (geralmente listado como `Python 3.x.x ('.venv')`).

**5. Verifique a instalação**

Em um terminal com o ambiente ativo, execute:

```python
python -c "import qiskit; print(qiskit.__version__)"
```

Se um número de versão for exibido (ex: `2.x.x`), a instalação foi bem-sucedida.

---

### Opção 2 — Google Colab (Sem instalação local)

O Google Colab é a opção mais rápida para quem deseja executar os notebooks sem configurar nada na máquina local. Basta ter uma conta Google.

> **Atenção:** O Colab não persiste pacotes instalados entre sessões. É necessário reinstalar o Qiskit toda vez que uma nova sessão for iniciada.

#### Passo a passo

**1. Acesse o Colab**

Acesse [https://colab.research.google.com](https://colab.research.google.com) e faça login com sua conta Google.

**2. Abra o notebook desejado**

- Clique em **"File" → "Open notebook"**.
- Selecione a aba **"GitHub"** e cole a URL deste repositório para navegar pelos notebooks, ou faça upload manual do arquivo `.ipynb`.

**3. Instale o Qiskit na primeira célula do notebook**

Cole e execute o seguinte bloco no início do notebook, antes de qualquer import:

```python
!pip install qiskit qiskit-aer qiskit-ibm-runtime matplotlib pylatexenc
```

Aguarde a conclusão da instalação. Caso o Colab solicite reiniciar o ambiente (runtime), clique em **"Restart runtime"** e execute novamente as células a partir do início.

**4. (Opcional) Armazene seu token IBM Quantum com segurança**

Se o notebook precisar acessar hardware quântico real via IBM Quantum, utilize o recurso de **Secrets** do Colab para não expor sua chave no código:

- Clique no ícone de chave 🔑 na barra lateral esquerda.
- Adicione um secret com o nome `QISKIT_IBM_TOKEN` e cole o valor do seu token.
- No notebook, acesse com:

```python
from google.colab import userdata
token = userdata.get('QISKIT_IBM_TOKEN')
```

---

### Opção 3 — Jupyter Notebook Local

Para quem prefere a interface clássica do Jupyter sem o VS Code.

#### Passo a passo

**1. Crie e ative um ambiente virtual** (igual à Opção 1, passos 1 e 2)

**2. Instale o Qiskit e o Jupyter**

```bash
pip install qiskit qiskit-aer qiskit-ibm-runtime matplotlib pylatexenc notebook
```

**3. Inicie o Jupyter Notebook**

```bash
jupyter notebook
```

O navegador abrirá automaticamente em `http://localhost:8888`. Navegue até a pasta `experiments/` para acessar os notebooks do projeto.

**4. Selecione o kernel correto**

Dentro do Jupyter, ao abrir um notebook, vá em **"Kernel" → "Change kernel"** e selecione o ambiente virtual criado.

---

## 📦 Dependências Principais

| Pacote                | Descrição                                                  |
|-----------------------|------------------------------------------------------------|
| `qiskit`              | SDK principal para construção de circuitos quânticos       |
| `qiskit-aer`          | Simulador local de circuitos quânticos                     |
| `qiskit-ibm-runtime`  | Acesso a hardware quântico real via IBM Quantum            |
| `matplotlib`          | Visualização de circuitos e resultados                     |
| `jupyterlab`/`notebook` | Ambiente de execução interativa                          |
| `pylatexenc`          | Renderização de circuitos em formato LaTeX                 |

---

## 📋 Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).
