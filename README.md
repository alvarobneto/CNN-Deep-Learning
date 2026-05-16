# CNN-Deep-Learning
APS destinada à criação e atualização de uma rede convolucional

# CNN do Zero com PyTorch: Classificação no CIFAR-10

Este repositório contém a implementação de uma Rede Neural Convolucional (CNN) construída do zero utilizando o framework **PyTorch**. O objetivo do modelo é classificar imagens coloridas de 32x32 pixels do famoso dataset **CIFAR-10** em 10 categorias diferentes (aviões, carros, pássaros, gatos, etc.).

## Funcionalidades do Projeto
- **Download Automático:** Utiliza o `torchvision` para baixar e preparar o dataset CIFAR-10 automaticamente.
- **Arquitetura:** Uma CNN leve criada subclassificando o `nn.Module`.
- **Pipeline Completo:** Inclui pré-processamento (normalização e conversão para Tensores), loop de treinamento com o otimizador Adam e avaliação de acurácia em dados de teste não vistos.

## 🛠️ Tecnologias Utilizadas
* **Python 3**
* **PyTorch** (Criação do modelo, Loss e Otimizador)
* **Torchvision** (Manipulação de imagens e datasets)
* **NumPy** (Operações auxiliares)

## Arquitetura da Rede
O modelo `CNN` possui a seguinte estrutura:
1. **Camada Convolucional 1:** 3 canais de entrada (RGB) -> 16 filtros de saída (Kernel 3x3).
2. **Pooling 1:** MaxPool2d (Kernel 2x2) para redução de dimensionalidade.
3. **Camada Convolucional 2:** 16 canais de entrada -> 32 filtros de saída (Kernel 3x3).
4. **Pooling 2:** MaxPool2d (Kernel 2x2).
5. **Flatten:** Achatamento dos mapas de características para 8x8.
6. **Camada Linear 1 (Fully Connected):** 2048 neurônios de entrada (32*8*8) -> 128 neurônios de saída.
7. **Camada Linear 2 (Saída):** 128 neurônios -> 10 neurônios (Logits para as 10 classes).
* Função de Ativação: **ReLU** entre as camadas.

## Como Executar

### Pré-requisitos
1. Instale o CIFAR-10 e adicione a pasta dos arquivos à mesma pasta do .ipynb, caso contrário, mude o endereço
2. Certifique-se de ter o PyTorch instalado. Caso não tenha, instale as dependências via pip:
```bash
pip install torch torchvision torchaudio numpy
```
## Resultados esperados
- Para 5 épocas de treinamento, como está no código, espera-se uma acurácia entre 50 e 70%
- Visando melhorar esse resultado, você pode aumentar o parâmetro 'epocas' para estender o treino e aumentar a acurácia até certo ponto
