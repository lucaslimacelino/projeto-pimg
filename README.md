# projeto-pimg

# Classificação de Pizzas por Tamanho usando Transformada de Hough Circular

Este repositório apresenta a solução desenvolvida para identificação e classificação
de pizzas por tamanho (pequena, média e grande) utilizando técnicas de
Processamento Digital de Imagens, com ênfase na Transformada de Hough Circular (CHT).

O projeto foi desenvolvido no contexto acadêmico, utilizando imagens adquiridas com
câmera fixa e perspectiva ortogonal (90°), de forma a garantir consistência geométrica
para a aplicação do método.

---

## Objetivo

O objetivo do trabalho é identificar pizzas em imagens digitais e classificá-las
de acordo com seu tamanho, explorando características geométricas circulares.
A Transformada de Hough Circular é utilizada para detectar o contorno externo da pizza,
permitindo estimar seu raio e realizar a classificação.

---

## Metodologia

O pipeline adotado no projeto é composto pelas seguintes etapas:

1. **Conversão de espaço de cores (RGB → HSV)**  
   Utilizada para facilitar a segmentação da pizza em relação ao fundo, explorando
   diferenças de saturação e brilho.

2. **Segmentação por limiarização em HSV**  
   Geração de uma máscara binária que separa a pizza do fundo.

3. **Processamento morfológico**  
   Aplicação de operações de fechamento, abertura, erosão e dilatação para:
   - eliminar ruídos,
   - preencher falhas internas,
   - preservar a forma circular da pizza.

4. **Extração do contorno**  
   Isolamento da borda externa da pizza, garantindo que apenas o contorno relevante
   seja utilizado pela Transformada de Hough.

5. **Transformada de Hough Circular (CHT)**  
   Aplicada sobre a imagem binária de bordas para detecção do círculo correspondente
   à pizza.

6. **Classificação por raio**  
   A classificação é realizada a partir do raio detectado pela CHT, considerando
   imagens adquiridas com mesma resolução e câmera fixa.

---

## Estrutura do Repositório

