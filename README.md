# Classificador Quântico Variacional para Problemas de Classificação

##  Descrição

Este projeto investiga o uso de **classificadores quânticos variacionais (VQC)** aplicados a problemas de classificação binária com diferentes níveis de complexidade.

Foram analisados dois cenários:

- Dataset **linearmente separável** (`make_blobs`)
- Dataset **não linear** (`make_moons`)

O objetivo é avaliar a capacidade de modelos quânticos em capturar padrões simples e complexos, comparando arquiteturas, funções de perda e comportamento de treinamento.

---

##  Conceitos Utilizados

- Computação Quântica
- Circuitos Variacionais
- Angle Encoding
- Entrelaçamento (Entanglement)
- Otimização com Adam
- Classificação Binária

---

##  Metodologia

### 🔹 Codificação dos Dados (Encoding)

Os dados clássicos foram reescalados para o intervalo: [0, 3.14]


e codificados nos qubits por meio de **rotações angulares (Angle Encoding)**.

---

### 🔹 Modelo Quântico

- 2 qubits (cada um representa uma feature)
- Implementado com **PennyLane**
- Saída baseada no valor esperado do operador de Pauli-Z

---

### 🔹 Configurações dos Experimentos

####  Dataset Linear (make_blobs)

- Circuito simples
- Template: `BasicEntanglerLayers`
- Função de perda: **Mean Squared Error (MSE)**
- Convergência rápida

---

####  Dataset Não Linear (make_moons)

- Circuito mais profundo
- Template: `StronglyEntanglingLayers`
- Função de perda: **Binary Cross-Entropy**
- Maior capacidade de representação

---

## 📈 Resultados

### 🔹 Dataset Linear

- Acurácia: **100%**
- Fronteira de decisão linear
- Convergência rápida

![Linear](decision_boundary.png)

---

### 🔹 Dataset Não Linear

- Acurácia: **100%**
- Fronteira de decisão não linear
- Modelo captura padrões complexos

![Moons](decision_moons.png)

---

### 🔹 Evolução da Loss

Comparação do treinamento nos dois cenários:

![Loss Linear](loss_linear.png)
![Loss Moons](loss_moons.png)

---

##  Análise

- O modelo quântico apresentou excelente desempenho em ambos os cenários
- Problemas simples são resolvidos com circuitos rasos
- Problemas complexos exigem:
  - maior profundidade
  - mais entrelaçamento
  - função de perda mais adequada

---

##  Tecnologias Utilizadas

- Python
- PennyLane
- NumPy
- Matplotlib
- Scikit-learn

---

##  Como Executar

1. Instale as dependências:

```bash
pip install pennylane numpy matplotlib scikit-learn
python main.py
