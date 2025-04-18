# 🔐 PDF Brute Force Tool

Este é um script em Python que realiza um **ataque de força bruta** em arquivos PDF protegidos por senha. Ele utiliza uma wordlist (lista de senhas) para tentar desbloquear o arquivo PDF automaticamente.

## 🚀 Como funciona

O script tenta abrir o arquivo PDF com cada senha da lista até encontrar a correta. A biblioteca `pikepdf` é usada para manipular o PDF, enquanto `tqdm` exibe uma barra de progresso durante o processo.

---

## 📦 Requisitos

- Python 3.7+
- `pikepdf`
- `tqdm`

---

## 🔧 Instalação

1. Clone o repositório ou salve o script localmente.
2. Crie um ambiente virtual (opcional, mas recomendado):

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
