# classificacao-multirotulo-rcv1
Projeto de classificação multirrótulo utilizando a base RCV1 e redes neurais profundas.


# 📚 Multilabel Classification com Redes Neurais (RCV1)

Este repositório apresenta um pipeline completo de classificação multiclasse/multirrótulo utilizando a base **RCV1 (Reuters Corpus Volume 1)**. O projeto explora diferentes arquiteturas de redes neurais, técnicas de pré-processamento e estratégias de regularização, com métricas de avaliação específicas para problemas multilabel.

## 🧠 Objetivo

Avaliar diferentes arquiteturas de redes neurais em um problema de classificação **multirrótulo**, comparando:

1. **Modelo Base**  
2. **Modelo Base + PCA (redução de dimensionalidade)**  
3. **Modelo Base com Blocos (BatchNorm + Dropout)**  
4. **Modelo Customizado (com Focal Loss)**  

Além disso, o projeto utiliza:
- **Learning Rate Finder (LR Finder)**
- **Hooks para análise de saídas intermediárias**
- **Análise detalhada de métricas** (Precision, Recall, F1, Hamming Loss)
- **Matriz de confusão multilabel**

---

## 📊 Resultados

### ✅ Modelo Base
- Precision=0.7584, Recall=0.5482, F1=0.5957, Hamming Loss=0.0201

**Thresholds:**  
- 0.10: P=0.5431, R=0.7739, F1=0.5672  
- 0.20: P=0.6358, R=0.6955, F1=0.6085  
- 0.30: P=0.7000, R=0.6463, F1=0.6255  
- 0.40: P=0.7354, R=0.5984, F1=0.6196  
- 0.50: P=0.7584, R=0.5482, F1=0.5957  
- 0.60: P=0.7603, R=0.5032, F1=0.5665  
- 0.70: P=0.7449, R=0.4776, F1=0.5454  
- 0.80: P=0.7416, R=0.4427, F1=0.5202  
- 0.90: P=0.6895, R=0.3901, F1=0.4665  

---

### ✅ Modelo Base + PCA
- Precision=0.7471, Recall=0.6177, F1=0.6335, Hamming Loss=0.0201

**Thresholds:**  
- 0.10: P=0.4084, R=0.8569, F1=0.4931  
- 0.20: P=0.5411, R=0.7804, F1=0.5856  
- 0.30: P=0.6179, R=0.7327, F1=0.6277  
- 0.40: P=0.6916, R=0.6715, F1=0.6371  
- 0.50: P=0.7471, R=0.6177, F1=0.6335  
- 0.60: P=0.7800, R=0.5772, F1=0.6239  
- 0.70: P=0.7953, R=0.5153, F1=0.5862  
- 0.80: P=0.7478, R=0.4512, F1=0.5265  
- 0.90: P=0.6431, R=0.3688, F1=0.4374  

---

### ✅ Modelo Base + Blocos
- Precision=0.8163, Recall=0.3940, F1=0.5018, Hamming Loss=0.0224

**Thresholds:**  
- 0.10: P=0.5497, R=0.7039, F1=0.5898  
- 0.20: P=0.7583, R=0.5715, F1=0.6178  
- 0.30: P=0.8083, R=0.4849, F1=0.5707  
- 0.40: P=0.8354, R=0.4346, F1=0.5378  
- 0.50: P=0.8163, R=0.3940, F1=0.5018  
- 0.60: P=0.7837, R=0.3671, F1=0.4728  
- 0.70: P=0.7488, R=0.3339, F1=0.4383  
- 0.80: P=0.6667, R=0.2888, F1=0.3847  
- 0.90: P=0.5075, R=0.1974, F1=0.2753  

---

### ✅ Modelo Customizado (Focal Loss)
- Precision=0.4500, Recall=0.1759, F1=0.2459, Hamming Loss=0.0276

**Thresholds:**  
- 0.10: P=0.0488, R=0.9778, F1=0.0840  
- 0.20: P=0.3400, R=0.6939, F1=0.4174  
- 0.30: P=0.6629, R=0.4458, F1=0.4995  
- 0.40: P=0.7008, R=0.2958, F1=0.3971  
- 0.50: P=0.4500, R=0.1759, F1=0.2459  
- 0.60: P=0.3050, R=0.1078, F1=0.1559  
- 0.70: P=0.1700, R=0.0568, F1=0.0841  
- 0.80: P=0.0550, R=0.0204, F1=0.0295  
- 0.90: P=0.0050, R=0.0025, F1=0.0033  

---

## 🧪 Extras

### 🔹 Learning Rate Finder
Cada modelo utilizou um gráfico de taxa de aprendizado para identificar a região ideal onde a perda diminui rapidamente, antes de subir. Isso permite escolher um `learning_rate` inicial apropriado.

### 🔹 Hooks
A saída da camada intermediária foi extraída com o método `demo_hook`, permitindo observar a representação aprendida na rede.

---

## 🧠 Conclusão

- O melhor desempenho em F1 foi obtido com o **Modelo Base + PCA**, sugerindo que a redução de dimensionalidade ajudou na generalização.
- O modelo com blocos teve maior precisão.
- O modelo customizado com Focal Loss teve dificuldade de convergência, possivelmente por hiperparâmetros ou necessidade de tuning mais fino.

---


## ✍️ Autor

Lemyson Oliveira Lemos
